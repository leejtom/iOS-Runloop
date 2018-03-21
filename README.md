# iOS Runloop（面试题）
由一道题所引发的思考（抄书）。
> NSRunLoop的以下描述错误的是（）<br>
A. Runloop并不是由系统自动控制的<br>
B. 有3类对象可以被run loop监控：sources，timers，observers<br>
C. 线程是默认启动run loop的<br>
D. NSTimer可手动添加到新建的NSRunLoop中


## Runloop基本概念
Runloop 是什么？Runloop 还是比较顾名思义的一个东西，说白了就是一种循环，只不过它这种循环比较高级。一般的 while 循环会导致 CPU 进入忙等待状态，而 Runloop 则是一种“闲”等待，这部分可以类比 Linux 下的 epoll。当没有事件时，Runloop 会进入休眠状态，有事件发生时， Runloop 会去找对应的 Handler 处理事件。Runloop 可以让线程在需要做事的时候忙起来，不需要的话就让线程休眠。

苹果官方文档的图:
![](https://user-gold-cdn.xitu.io/2018/3/20/1624181b3d48ab34?w=484&h=253&f=jpeg&s=54266)

图中展现了 Runloop 在线程中的作用：从 input source 和 timer source 接受事件，然后在线程中处理事件。

## Runloop 与线程
- Runloop 和线程是绑定在一起的。每个线程（包括主线程）__都有一个对应的 Runloop 对象__。我们并 __不能自己创建 Runloop 对象__，但是可以获取到系统提供的 Runloop 对象。
- `主线程`的 Runloop 会在 __应用启动的时候完成启动__，`其他线程`的 Runloop 默认并不会启动，需要我们 __手动启动__。

## Input Source 和 Timer Source

这两个都是 Runloop 事件的来源，其中 Input Source 又可以分为三类：

- Port-Based Sources，系统底层的 Port 事件，例如 CFSocketRef ，在应用层基本用不到
- Custom Input Sources，用户手动创建的 Source
- Cocoa Perform Selector Sources， Cocoa 提供的 performSelector 系列方法，也是一种事件源

Timer Source 顾名思义就是`指定时器事件`了。

## Runloop Observer（CFRunLoopActivity）
Runloop 通过监控 Source 来决定有没有任务要做，除此之外，我们还可以用 Runloop Observer 来监控 Runloop 本身的状态。 Runloop Observer 可以监控下面的 runloop 事件：

CFRunLoopObserver是观察者，可以监听runLoop的状态改变
```
/* Run Loop Observer Activities */
typedef CF_OPTIONS(CFOptionFlags, CFRunLoopActivity) {
kCFRunLoopEntry = (1UL << 0), //即将进入Runloop
kCFRunLoopBeforeTimers = (1UL << 1), //即将处理NSTimer
kCFRunLoopBeforeSources = (1UL << 2), //即将处理Sources
kCFRunLoopBeforeWaiting = (1UL << 5), //即将进入休眠
kCFRunLoopAfterWaiting = (1UL << 6), //刚从休眠中唤醒
kCFRunLoopExit = (1UL << 7), //即将退出runloop
kCFRunLoopAllActivities = 0x0FFFFFFFU //所有状态改变
};
```
## Runloop Mode
在监视与被监视中，Runloop 要处理的事情还挺复杂的。为了让 Runloop 能专心处理自己关心的那部分事情，引入了 Runloop Mode 概念。
![](https://user-gold-cdn.xitu.io/2018/3/20/16241f152e363c12?w=246&h=189&f=png&s=27055)
如图所示，Runloop Mode 实际上是 Source，Timer 和 Observer 的集合，不同的 Mode 把不同组的 Source，Timer 和 Observer 隔绝开来。Runloop 在某个时刻只能跑在一个 Mode 下，处理这一个 Mode 当中的 Source，Timer 和 Observer。

苹果文档中提到的 Mode 有五个，分别是：

- NSDefaultRunLoopMode
- NSConnectionReplyMode
- NSModalPanelRunLoopMode
- NSEventTrackingRunLoopMode
- NSRunLoopCommonModes

iOS 中公开暴露出来的只有 `NSDefaultRunLoopMode` 和 `NSRunLoopCommonModes`。
__NSRunLoopCommonModes__ 实际上是一个 Mode 的 __集合__，默认包括 `NSDefaultRunLoopMode` 和 `NSEventTrackingRunLoopMode`。

## 与 Runloop 相关的坑
常开发中，与 runLoop 接触得最近可能就是通过 NSTimer 了。一个 Timer 一次只能加入到一个 RunLoop 中。我们日常使用的时候，通常就是加入到当前的 runLoop 的 default mode 中，而 ScrollView 在用户滑动时，主线程 RunLoop 会转到 UITrackingRunLoopMode 。而这个时候， Timer 就不会运行。

有如下两种解决方案：
- 第一种: 设置RunLoop Mode，例如NSTimer,我们指定它运行于 NSRunLoopCommonModes ，这是一个Mode的集合。注册到这个 Mode 下后，无论当前 runLoop 运行哪个 mode ，事件都能得到执行。
- 第二种: 另一种解决Timer的方法是，我们在另外一个线程执行和处理 Timer 事件，然后在主线程更新UI。

在 AFNetworking 3.1中，就有相关的代码，如下：
```
//AFNetworkActivityIndicatorManager.m l:227
- (void)startActivationDelayTimer {
self.activationDelayTimer = [NSTimer
timerWithTimeInterval:self.activationDelay target:self selector:@selector(activationDelayTimerFired) userInfo:nil repeats:NO];
[[NSRunLoop mainRunLoop] addTimer:self.activationDelayTimer forMode:NSRunLoopCommonModes];
}

```
这里就是添加了一个计时器，由于指定了 NSRunLoopCommonModes，所以不管 RunLoop 出于什么状态，都执行这个计时器任务。

## 关于文章提到的题目
选项C是错误的
>C. 线程是默认启动run loop的

因为：`主线程`的 Runloop 会在 __应用启动的时候完成启动__，`其他线程`的 Runloop 默认并不会启动，需要我们 __手动启动__。

参考资料

[Runloop](https://hit-alibaba.github.io/interview/iOS/ObjC-Basic/Runloop.html)
