{\rtf1\ansi\ansicpg936\cocoartf1504\cocoasubrtf830
{\fonttbl\f0\fswiss\fcharset0 Helvetica;\f1\fnil\fcharset134 PingFangSC-Regular;}
{\colortbl;\red255\green255\blue255;}
{\*\expandedcolortbl;;}
\paperw11900\paperh16840\margl1440\margr1440\vieww20440\viewh12200\viewkind0
\pard\tx566\tx1133\tx1700\tx2267\tx2834\tx3401\tx3968\tx4535\tx5102\tx5669\tx6236\tx6803\pardirnatural\partightenfactor0

\f0\fs24 \cf0 # iOS Runloop
\f1 \'a3\'a8\'c3\'e6\'ca\'d4\'cc\'e2\'a3\'a9
\f0 \
\
 
\f1 \'d3\'c9\'d2\'bb\'b5\'c0\'cc\'e2\'cb\'f9\'d2\'fd\'b7\'a2\'b5\'c4\'cb\'bc\'bf\'bc\'a3\'a8\'b3\'ad\'ca\'e9\'a3\'a9\'a1\'a3
\f0 \
> NSRunLoop
\f1 \'b5\'c4\'d2\'d4\'cf\'c2\'c3\'e8\'ca\'f6\'b4\'ed\'ce\'f3\'b5\'c4\'ca\'c7\'a3\'a8\'a3\'a9
\f0 <br>\
 A. Runloop
\f1 \'b2\'a2\'b2\'bb\'ca\'c7\'d3\'c9\'cf\'b5\'cd\'b3\'d7\'d4\'b6\'af\'bf\'d8\'d6\'c6\'b5\'c4
\f0 <br>\
 B. 
\f1 \'d3\'d0
\f0 3
\f1 \'c0\'e0\'b6\'d4\'cf\'f3\'bf\'c9\'d2\'d4\'b1\'bb
\f0 run loop
\f1 \'bc\'e0\'bf\'d8\'a3\'ba
\f0 sources
\f1 \'a3\'ac
\f0 timers
\f1 \'a3\'ac
\f0 observers<br>\
 C. 
\f1 \'cf\'df\'b3\'cc\'ca\'c7\'c4\'ac\'c8\'cf\'c6\'f4\'b6\'af
\f0 run loop
\f1 \'b5\'c4
\f0 <br>\
 D. NSTimer
\f1 \'bf\'c9\'ca\'d6\'b6\'af\'cc\'ed\'bc\'d3\'b5\'bd\'d0\'c2\'bd\'a8\'b5\'c4
\f0 NSRunLoop
\f1 \'d6\'d0
\f0 \
 \
\
 ## Runloop
\f1 \'bb\'f9\'b1\'be\'b8\'c5\'c4\'ee
\f0 \
 Runloop 
\f1 \'ca\'c7\'ca\'b2\'c3\'b4\'a3\'bf
\f0 Runloop 
\f1 \'bb\'b9\'ca\'c7\'b1\'c8\'bd\'cf\'b9\'cb\'c3\'fb\'cb\'bc\'d2\'e5\'b5\'c4\'d2\'bb\'b8\'f6\'b6\'ab\'ce\'f7\'a3\'ac\'cb\'b5\'b0\'d7\'c1\'cb\'be\'cd\'ca\'c7\'d2\'bb\'d6\'d6\'d1\'ad\'bb\'b7\'a3\'ac\'d6\'bb\'b2\'bb\'b9\'fd\'cb\'fc\'d5\'e2\'d6\'d6\'d1\'ad\'bb\'b7\'b1\'c8\'bd\'cf\'b8\'df\'bc\'b6\'a1\'a3\'d2\'bb\'b0\'e3\'b5\'c4
\f0  while 
\f1 \'d1\'ad\'bb\'b7\'bb\'e1\'b5\'bc\'d6\'c2
\f0  CPU 
\f1 \'bd\'f8\'c8\'eb\'c3\'a6\'b5\'c8\'b4\'fd\'d7\'b4\'cc\'ac\'a3\'ac\'b6\'f8
\f0  Runloop 
\f1 \'d4\'f2\'ca\'c7\'d2\'bb\'d6\'d6
\f0 \'93
\f1 \'cf\'d0
\f0 \'94
\f1 \'b5\'c8\'b4\'fd\'a3\'ac\'d5\'e2\'b2\'bf\'b7\'d6\'bf\'c9\'d2\'d4\'c0\'e0\'b1\'c8
\f0  Linux 
\f1 \'cf\'c2\'b5\'c4
\f0  epoll
\f1 \'a1\'a3\'b5\'b1\'c3\'bb\'d3\'d0\'ca\'c2\'bc\'fe\'ca\'b1\'a3\'ac
\f0 Runloop 
\f1 \'bb\'e1\'bd\'f8\'c8\'eb\'d0\'dd\'c3\'df\'d7\'b4\'cc\'ac\'a3\'ac\'d3\'d0\'ca\'c2\'bc\'fe\'b7\'a2\'c9\'fa\'ca\'b1\'a3\'ac
\f0  Runloop 
\f1 \'bb\'e1\'c8\'a5\'d5\'d2\'b6\'d4\'d3\'a6\'b5\'c4
\f0  Handler 
\f1 \'b4\'a6\'c0\'ed\'ca\'c2\'bc\'fe\'a1\'a3
\f0 Runloop 
\f1 \'bf\'c9\'d2\'d4\'c8\'c3\'cf\'df\'b3\'cc\'d4\'da\'d0\'e8\'d2\'aa\'d7\'f6\'ca\'c2\'b5\'c4\'ca\'b1\'ba\'f2\'c3\'a6\'c6\'f0\'c0\'b4\'a3\'ac\'b2\'bb\'d0\'e8\'d2\'aa\'b5\'c4\'bb\'b0\'be\'cd\'c8\'c3\'cf\'df\'b3\'cc\'d0\'dd\'c3\'df\'a1\'a3
\f0 \
 \

\f1 \'c6\'bb\'b9\'fb\'b9\'d9\'b7\'bd\'ce\'c4\'b5\'b5\'b5\'c4\'cd\'bc
\f0 :\
![](https://user-gold-cdn.xitu.io/2018/3/20/1624181b3d48ab34?w=484&h=253&f=jpeg&s=54266)\
\

\f1 \'cd\'bc\'d6\'d0\'d5\'b9\'cf\'d6\'c1\'cb
\f0  Runloop 
\f1 \'d4\'da\'cf\'df\'b3\'cc\'d6\'d0\'b5\'c4\'d7\'f7\'d3\'c3\'a3\'ba\'b4\'d3
\f0  input source 
\f1 \'ba\'cd
\f0  timer source 
\f1 \'bd\'d3\'ca\'dc\'ca\'c2\'bc\'fe\'a3\'ac\'c8\'bb\'ba\'f3\'d4\'da\'cf\'df\'b3\'cc\'d6\'d0\'b4\'a6\'c0\'ed\'ca\'c2\'bc\'fe\'a1\'a3
\f0 \
\
## Runloop 
\f1 \'d3\'eb\'cf\'df\'b3\'cc
\f0 \
- Runloop 
\f1 \'ba\'cd\'cf\'df\'b3\'cc\'ca\'c7\'b0\'f3\'b6\'a8\'d4\'da\'d2\'bb\'c6\'f0\'b5\'c4\'a1\'a3\'c3\'bf\'b8\'f6\'cf\'df\'b3\'cc\'a3\'a8\'b0\'fc\'c0\'a8\'d6\'f7\'cf\'df\'b3\'cc\'a3\'a9
\f0 __
\f1 \'b6\'bc\'d3\'d0\'d2\'bb\'b8\'f6\'b6\'d4\'d3\'a6\'b5\'c4
\f0  Runloop 
\f1 \'b6\'d4\'cf\'f3
\f0 __
\f1 \'a1\'a3\'ce\'d2\'c3\'c7\'b2\'a2
\f0  __
\f1 \'b2\'bb\'c4\'dc\'d7\'d4\'bc\'ba\'b4\'b4\'bd\'a8
\f0  Runloop 
\f1 \'b6\'d4\'cf\'f3
\f0 __
\f1 \'a3\'ac\'b5\'ab\'ca\'c7\'bf\'c9\'d2\'d4\'bb\'f1\'c8\'a1\'b5\'bd\'cf\'b5\'cd\'b3\'cc\'e1\'b9\'a9\'b5\'c4
\f0  Runloop 
\f1 \'b6\'d4\'cf\'f3\'a1\'a3
\f0 \
- `
\f1 \'d6\'f7\'cf\'df\'b3\'cc
\f0 `
\f1 \'b5\'c4
\f0  Runloop 
\f1 \'bb\'e1\'d4\'da
\f0  __
\f1 \'d3\'a6\'d3\'c3\'c6\'f4\'b6\'af\'b5\'c4\'ca\'b1\'ba\'f2\'cd\'ea\'b3\'c9\'c6\'f4\'b6\'af
\f0 __
\f1 \'a3\'ac
\f0 `
\f1 \'c6\'e4\'cb\'fb\'cf\'df\'b3\'cc
\f0 `
\f1 \'b5\'c4
\f0  Runloop 
\f1 \'c4\'ac\'c8\'cf\'b2\'a2\'b2\'bb\'bb\'e1\'c6\'f4\'b6\'af\'a3\'ac\'d0\'e8\'d2\'aa\'ce\'d2\'c3\'c7
\f0  __
\f1 \'ca\'d6\'b6\'af\'c6\'f4\'b6\'af
\f0 __
\f1 \'a1\'a3
\f0 \
\
## Input Source 
\f1 \'ba\'cd
\f0  Timer Source\
\

\f1 \'d5\'e2\'c1\'bd\'b8\'f6\'b6\'bc\'ca\'c7
\f0  Runloop 
\f1 \'ca\'c2\'bc\'fe\'b5\'c4\'c0\'b4\'d4\'b4\'a3\'ac\'c6\'e4\'d6\'d0
\f0  Input Source 
\f1 \'d3\'d6\'bf\'c9\'d2\'d4\'b7\'d6\'ce\'aa\'c8\'fd\'c0\'e0\'a3\'ba
\f0 \
\
- Port-Based Sources
\f1 \'a3\'ac\'cf\'b5\'cd\'b3\'b5\'d7\'b2\'e3\'b5\'c4
\f0  Port 
\f1 \'ca\'c2\'bc\'fe\'a3\'ac\'c0\'fd\'c8\'e7
\f0  CFSocketRef 
\f1 \'a3\'ac\'d4\'da\'d3\'a6\'d3\'c3\'b2\'e3\'bb\'f9\'b1\'be\'d3\'c3\'b2\'bb\'b5\'bd
\f0 \
- Custom Input Sources
\f1 \'a3\'ac\'d3\'c3\'bb\'a7\'ca\'d6\'b6\'af\'b4\'b4\'bd\'a8\'b5\'c4
\f0  Source\
- Cocoa Perform Selector Sources
\f1 \'a3\'ac
\f0  Cocoa 
\f1 \'cc\'e1\'b9\'a9\'b5\'c4
\f0  performSelector 
\f1 \'cf\'b5\'c1\'d0\'b7\'bd\'b7\'a8\'a3\'ac\'d2\'b2\'ca\'c7\'d2\'bb\'d6\'d6\'ca\'c2\'bc\'fe\'d4\'b4
\f0 \
\
Timer Source 
\f1 \'b9\'cb\'c3\'fb\'cb\'bc\'d2\'e5\'be\'cd\'ca\'c7
\f0 `
\f1 \'d6\'b8\'b6\'a8\'ca\'b1\'c6\'f7\'ca\'c2\'bc\'fe
\f0 `
\f1 \'c1\'cb\'a1\'a3
\f0 \
\
## Runloop Observer
\f1 \'a3\'a8
\f0 CFRunLoopActivity
\f1 \'a3\'a9
\f0 \
Runloop 
\f1 \'cd\'a8\'b9\'fd\'bc\'e0\'bf\'d8
\f0  Source 
\f1 \'c0\'b4\'be\'f6\'b6\'a8\'d3\'d0\'c3\'bb\'d3\'d0\'c8\'ce\'ce\'f1\'d2\'aa\'d7\'f6\'a3\'ac\'b3\'fd\'b4\'cb\'d6\'ae\'cd\'e2\'a3\'ac\'ce\'d2\'c3\'c7\'bb\'b9\'bf\'c9\'d2\'d4\'d3\'c3
\f0  Runloop Observer 
\f1 \'c0\'b4\'bc\'e0\'bf\'d8
\f0  Runloop 
\f1 \'b1\'be\'c9\'ed\'b5\'c4\'d7\'b4\'cc\'ac\'a1\'a3
\f0  Runloop Observer 
\f1 \'bf\'c9\'d2\'d4\'bc\'e0\'bf\'d8\'cf\'c2\'c3\'e6\'b5\'c4
\f0  runloop 
\f1 \'ca\'c2\'bc\'fe\'a3\'ba
\f0 \
\
CFRunLoopObserver
\f1 \'ca\'c7\'b9\'db\'b2\'ec\'d5\'df\'a3\'ac\'bf\'c9\'d2\'d4\'bc\'e0\'cc\'fd
\f0 runLoop
\f1 \'b5\'c4\'d7\'b4\'cc\'ac\'b8\'c4\'b1\'e4
\f0 \
```\
/* Run Loop Observer Activities */\
typedef CF_OPTIONS(CFOptionFlags, CFRunLoopActivity) \{ \
kCFRunLoopEntry = (1UL << 0), //
\f1 \'bc\'b4\'bd\'ab\'bd\'f8\'c8\'eb
\f0 Runloop\
kCFRunLoopBeforeTimers = (1UL << 1), //
\f1 \'bc\'b4\'bd\'ab\'b4\'a6\'c0\'ed
\f0 NSTimer \
kCFRunLoopBeforeSources = (1UL << 2), //
\f1 \'bc\'b4\'bd\'ab\'b4\'a6\'c0\'ed
\f0 Sources \
kCFRunLoopBeforeWaiting = (1UL << 5), //
\f1 \'bc\'b4\'bd\'ab\'bd\'f8\'c8\'eb\'d0\'dd\'c3\'df
\f0  \
kCFRunLoopAfterWaiting = (1UL << 6), //
\f1 \'b8\'d5\'b4\'d3\'d0\'dd\'c3\'df\'d6\'d0\'bb\'bd\'d0\'d1
\f0  \
kCFRunLoopExit = (1UL << 7), //
\f1 \'bc\'b4\'bd\'ab\'cd\'cb\'b3\'f6
\f0 runloop \
kCFRunLoopAllActivities = 0x0FFFFFFFU //
\f1 \'cb\'f9\'d3\'d0\'d7\'b4\'cc\'ac\'b8\'c4\'b1\'e4
\f0 \
\};\
``` \
## Runloop Mode\

\f1 \'d4\'da\'bc\'e0\'ca\'d3\'d3\'eb\'b1\'bb\'bc\'e0\'ca\'d3\'d6\'d0\'a3\'ac
\f0 Runloop 
\f1 \'d2\'aa\'b4\'a6\'c0\'ed\'b5\'c4\'ca\'c2\'c7\'e9\'bb\'b9\'cd\'a6\'b8\'b4\'d4\'d3\'b5\'c4\'a1\'a3\'ce\'aa\'c1\'cb\'c8\'c3
\f0  Runloop 
\f1 \'c4\'dc\'d7\'a8\'d0\'c4\'b4\'a6\'c0\'ed\'d7\'d4\'bc\'ba\'b9\'d8\'d0\'c4\'b5\'c4\'c4\'c7\'b2\'bf\'b7\'d6\'ca\'c2\'c7\'e9\'a3\'ac\'d2\'fd\'c8\'eb\'c1\'cb
\f0  Runloop Mode 
\f1 \'b8\'c5\'c4\'ee\'a1\'a3
\f0 \
![](https://user-gold-cdn.xitu.io/2018/3/20/16241f152e363c12?w=246&h=189&f=png&s=27055)\

\f1 \'c8\'e7\'cd\'bc\'cb\'f9\'ca\'be\'a3\'ac
\f0 Runloop Mode 
\f1 \'ca\'b5\'bc\'ca\'c9\'cf\'ca\'c7
\f0  Source
\f1 \'a3\'ac
\f0 Timer 
\f1 \'ba\'cd
\f0  Observer 
\f1 \'b5\'c4\'bc\'af\'ba\'cf\'a3\'ac\'b2\'bb\'cd\'ac\'b5\'c4
\f0  Mode 
\f1 \'b0\'d1\'b2\'bb\'cd\'ac\'d7\'e9\'b5\'c4
\f0  Source
\f1 \'a3\'ac
\f0 Timer 
\f1 \'ba\'cd
\f0  Observer 
\f1 \'b8\'f4\'be\'f8\'bf\'aa\'c0\'b4\'a1\'a3
\f0 Runloop 
\f1 \'d4\'da\'c4\'b3\'b8\'f6\'ca\'b1\'bf\'cc\'d6\'bb\'c4\'dc\'c5\'dc\'d4\'da\'d2\'bb\'b8\'f6
\f0  Mode 
\f1 \'cf\'c2\'a3\'ac\'b4\'a6\'c0\'ed\'d5\'e2\'d2\'bb\'b8\'f6
\f0  Mode 
\f1 \'b5\'b1\'d6\'d0\'b5\'c4
\f0  Source
\f1 \'a3\'ac
\f0 Timer 
\f1 \'ba\'cd
\f0  Observer
\f1 \'a1\'a3
\f0 \
\

\f1 \'c6\'bb\'b9\'fb\'ce\'c4\'b5\'b5\'d6\'d0\'cc\'e1\'b5\'bd\'b5\'c4
\f0  Mode 
\f1 \'d3\'d0\'ce\'e5\'b8\'f6\'a3\'ac\'b7\'d6\'b1\'f0\'ca\'c7\'a3\'ba
\f0 \
\
- NSDefaultRunLoopMode\
- NSConnectionReplyMode\
- NSModalPanelRunLoopMode\
- NSEventTrackingRunLoopMode\
- NSRunLoopCommonModes\
\
iOS 
\f1 \'d6\'d0\'b9\'ab\'bf\'aa\'b1\'a9\'c2\'b6\'b3\'f6\'c0\'b4\'b5\'c4\'d6\'bb\'d3\'d0
\f0  `NSDefaultRunLoopMode` 
\f1 \'ba\'cd
\f0  `NSRunLoopCommonModes`
\f1 \'a1\'a3
\f0    \
__NSRunLoopCommonModes__ 
\f1 \'ca\'b5\'bc\'ca\'c9\'cf\'ca\'c7\'d2\'bb\'b8\'f6
\f0  Mode 
\f1 \'b5\'c4
\f0  __
\f1 \'bc\'af\'ba\'cf
\f0 __
\f1 \'a3\'ac\'c4\'ac\'c8\'cf\'b0\'fc\'c0\'a8
\f0  `NSDefaultRunLoopMode` 
\f1 \'ba\'cd
\f0  `NSEventTrackingRunLoopMode`
\f1 \'a1\'a3
\f0 \
\
## 
\f1 \'d3\'eb
\f0  Runloop 
\f1 \'cf\'e0\'b9\'d8\'b5\'c4\'bf\'d3
\f0 \

\f1 \'b3\'a3\'bf\'aa\'b7\'a2\'d6\'d0\'a3\'ac\'d3\'eb
\f0  runLoop 
\f1 \'bd\'d3\'b4\'a5\'b5\'c3\'d7\'ee\'bd\'fc\'bf\'c9\'c4\'dc\'be\'cd\'ca\'c7\'cd\'a8\'b9\'fd
\f0  NSTimer 
\f1 \'c1\'cb\'a1\'a3\'d2\'bb\'b8\'f6
\f0  Timer 
\f1 \'d2\'bb\'b4\'ce\'d6\'bb\'c4\'dc\'bc\'d3\'c8\'eb\'b5\'bd\'d2\'bb\'b8\'f6
\f0  RunLoop 
\f1 \'d6\'d0\'a1\'a3\'ce\'d2\'c3\'c7\'c8\'d5\'b3\'a3\'ca\'b9\'d3\'c3\'b5\'c4\'ca\'b1\'ba\'f2\'a3\'ac\'cd\'a8\'b3\'a3\'be\'cd\'ca\'c7\'bc\'d3\'c8\'eb\'b5\'bd\'b5\'b1\'c7\'b0\'b5\'c4
\f0  runLoop 
\f1 \'b5\'c4
\f0  default mode 
\f1 \'d6\'d0\'a3\'ac\'b6\'f8
\f0  ScrollView 
\f1 \'d4\'da\'d3\'c3\'bb\'a7\'bb\'ac\'b6\'af\'ca\'b1\'a3\'ac\'d6\'f7\'cf\'df\'b3\'cc
\f0  RunLoop 
\f1 \'bb\'e1\'d7\'aa\'b5\'bd
\f0  UITrackingRunLoopMode 
\f1 \'a1\'a3\'b6\'f8\'d5\'e2\'b8\'f6\'ca\'b1\'ba\'f2\'a3\'ac
\f0  Timer 
\f1 \'be\'cd\'b2\'bb\'bb\'e1\'d4\'cb\'d0\'d0\'a1\'a3
\f0 \
\

\f1 \'d3\'d0\'c8\'e7\'cf\'c2\'c1\'bd\'d6\'d6\'bd\'e2\'be\'f6\'b7\'bd\'b0\'b8\'a3\'ba
\f0 \
- 
\f1 \'b5\'da\'d2\'bb\'d6\'d6
\f0 : 
\f1 \'c9\'e8\'d6\'c3
\f0 RunLoop Mode
\f1 \'a3\'ac\'c0\'fd\'c8\'e7
\f0 NSTimer,
\f1 \'ce\'d2\'c3\'c7\'d6\'b8\'b6\'a8\'cb\'fc\'d4\'cb\'d0\'d0\'d3\'da
\f0  NSRunLoopCommonModes 
\f1 \'a3\'ac\'d5\'e2\'ca\'c7\'d2\'bb\'b8\'f6
\f0 Mode
\f1 \'b5\'c4\'bc\'af\'ba\'cf\'a1\'a3\'d7\'a2\'b2\'e1\'b5\'bd\'d5\'e2\'b8\'f6
\f0  Mode 
\f1 \'cf\'c2\'ba\'f3\'a3\'ac\'ce\'de\'c2\'db\'b5\'b1\'c7\'b0
\f0  runLoop 
\f1 \'d4\'cb\'d0\'d0\'c4\'c4\'b8\'f6
\f0  mode 
\f1 \'a3\'ac\'ca\'c2\'bc\'fe\'b6\'bc\'c4\'dc\'b5\'c3\'b5\'bd\'d6\'b4\'d0\'d0\'a1\'a3
\f0 \
- 
\f1 \'b5\'da\'b6\'fe\'d6\'d6
\f0 : 
\f1 \'c1\'ed\'d2\'bb\'d6\'d6\'bd\'e2\'be\'f6
\f0 Timer
\f1 \'b5\'c4\'b7\'bd\'b7\'a8\'ca\'c7\'a3\'ac\'ce\'d2\'c3\'c7\'d4\'da\'c1\'ed\'cd\'e2\'d2\'bb\'b8\'f6\'cf\'df\'b3\'cc\'d6\'b4\'d0\'d0\'ba\'cd\'b4\'a6\'c0\'ed
\f0  Timer 
\f1 \'ca\'c2\'bc\'fe\'a3\'ac\'c8\'bb\'ba\'f3\'d4\'da\'d6\'f7\'cf\'df\'b3\'cc\'b8\'fc\'d0\'c2
\f0 UI
\f1 \'a1\'a3
\f0 \
\

\f1 \'d4\'da
\f0  AFNetworking 3.1
\f1 \'d6\'d0\'a3\'ac\'be\'cd\'d3\'d0\'cf\'e0\'b9\'d8\'b5\'c4\'b4\'fa\'c2\'eb\'a3\'ac\'c8\'e7\'cf\'c2\'a3\'ba
\f0 \
```\
//AFNetworkActivityIndicatorManager.m l:227\
- (void)startActivationDelayTimer \{\
    self.activationDelayTimer = [NSTimer\
                                 timerWithTimeInterval:self.activationDelay target:self selector:@selector(activationDelayTimerFired) userInfo:nil repeats:NO];\
    [[NSRunLoop mainRunLoop] addTimer:self.activationDelayTimer forMode:NSRunLoopCommonModes];\
\}\
\
```\

\f1 \'d5\'e2\'c0\'ef\'be\'cd\'ca\'c7\'cc\'ed\'bc\'d3\'c1\'cb\'d2\'bb\'b8\'f6\'bc\'c6\'ca\'b1\'c6\'f7\'a3\'ac\'d3\'c9\'d3\'da\'d6\'b8\'b6\'a8\'c1\'cb
\f0  NSRunLoopCommonModes
\f1 \'a3\'ac\'cb\'f9\'d2\'d4\'b2\'bb\'b9\'dc
\f0  RunLoop 
\f1 \'b3\'f6\'d3\'da\'ca\'b2\'c3\'b4\'d7\'b4\'cc\'ac\'a3\'ac\'b6\'bc\'d6\'b4\'d0\'d0\'d5\'e2\'b8\'f6\'bc\'c6\'ca\'b1\'c6\'f7\'c8\'ce\'ce\'f1\'a1\'a3
\f0 \
\
## 
\f1 \'b9\'d8\'d3\'da\'ce\'c4\'d5\'c2\'cc\'e1\'b5\'bd\'b5\'c4\'cc\'e2\'c4\'bf
\f0 \

\f1 \'d1\'a1\'cf\'ee
\f0 C
\f1 \'ca\'c7\'b4\'ed\'ce\'f3\'b5\'c4
\f0 \
>C. 
\f1 \'cf\'df\'b3\'cc\'ca\'c7\'c4\'ac\'c8\'cf\'c6\'f4\'b6\'af
\f0 run loop
\f1 \'b5\'c4
\f0 \
\

\f1 \'d2\'f2\'ce\'aa\'a3\'ba
\f0 `
\f1 \'d6\'f7\'cf\'df\'b3\'cc
\f0 `
\f1 \'b5\'c4
\f0  Runloop 
\f1 \'bb\'e1\'d4\'da
\f0  __
\f1 \'d3\'a6\'d3\'c3\'c6\'f4\'b6\'af\'b5\'c4\'ca\'b1\'ba\'f2\'cd\'ea\'b3\'c9\'c6\'f4\'b6\'af
\f0 __
\f1 \'a3\'ac
\f0 `
\f1 \'c6\'e4\'cb\'fb\'cf\'df\'b3\'cc
\f0 `
\f1 \'b5\'c4
\f0  Runloop 
\f1 \'c4\'ac\'c8\'cf\'b2\'a2\'b2\'bb\'bb\'e1\'c6\'f4\'b6\'af\'a3\'ac\'d0\'e8\'d2\'aa\'ce\'d2\'c3\'c7
\f0  __
\f1 \'ca\'d6\'b6\'af\'c6\'f4\'b6\'af
\f0 __
\f1 \'a1\'a3
\f0 \
\

\f1 \'b2\'ce\'bf\'bc\'d7\'ca\'c1\'cf
\f0 \
\
[Runloop](https://hit-alibaba.github.io/interview/iOS/ObjC-Basic/Runloop.html)}