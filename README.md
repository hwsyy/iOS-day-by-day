# iOS-day-by-day（持续更新中）
下面是深入学习iOS过程中遇到的经典的文章，整理了方便以后查阅。

***
# 目录


- [Runtime相关](#Runtime)
- [RunLoop相关](#RunLoop)
- [Block相关](#block)
- [Swift相关](#swift)
- [常用三方](#三方)
- [其他]()
	- [微信小程序](#微信小程序)
	- [Weex相关（阿里跨平台框架）](#weex)
	- [设计相关](#设计)
	- [网站收藏](#网站收藏)

*** 
## Runtime 博文链接 <p id="Runtime"/>

* ***[Objective-C Runtime Programming Guide](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/ObjCRuntimeGuide/Introduction/Introduction.html)*** ✨

* ***[Objective-C Runtime Reference](https://developer.apple.com/library/mac/documentation/Cocoa/Reference/ObjCRuntimeRef/#//apple_ref/doc/uid/TP40001418-CH1g-126286)*** ✨

* [南峰子 Runtime系列（1 - 6）](http://southpeak.github.io/blog/2014/10/25/objective-c-runtime-yun-xing-shi-zhi-lei-yu-dui-xiang/) <br>详细介绍了runtime知识。

* [Runtime - 玉令天下的博客](http://yulingtianxia.com/blog/2014/11/05/objective-c-runtime/) <br>可以配合南峰子文章阅读。

* [Runtime - Glow 技术团队博客](http://tech.glowing.com/cn/objective-c-runtime/)
 <br> 讲解消息传递、动态方法解析和转发。

* [重识Objective-C Runtime - Smalltalk 与C 的融合· sunnyxx的技术博客(系列)](http://blog.sunnyxx.com/2016/08/13/reunderstanding-runtime-0/) <br>此文是孙源老师最近写的文章，读完收获很多。

* [Swift & the Objective-C Runtime - NShipster](http://nshipster.cn/swift-objc-runtime/) <br>从Swift 视角来观察这两个运行时中关于关联对象(associated objects)和方法交叉(method swizzling)的技术

* [结合 category 工作原理分析 OC2.0 中的 runtime - bestswifter](http://www.jianshu.com/p/d66d65314add) <br>很多人都读过`runtime.h`中`objc_class`结构体代码，你思考过`OBJC2_UNAVAILABLE`是什么意思吗？请看这篇文章，深入较少category工作原理。

* [Associated Objects](http://nshipster.cn/associated-objects/) <br>本文讲解关联对象的利与弊，值得阅读。

* [iOS runtime实战应用：成员变量和属性 - 明仔Su](http://www.jianshu.com/p/d361f169423b) <br> 作者使用简单的例子介绍了`Runtime`实现那些功能。 作者简书中有多篇关于`Runtime`文章，值得阅读。其他的文章也不错哦！

* [Runtime 10种用法（没有比这更全的了）](http://www.jianshu.com/p/3182646001d1)
<br> 作者整理`Runtime`十种用法。看完你就知道`Runtime`的重要性了。

* [OC最实用的runtime总结，面试、工作你看我就足够了！](http://www.jianshu.com/p/ab966e8a82e2)
<br>如何应用运行时？
<br>1.将某些OC代码转为运行时代码，探究底层，比如`block`的实现原理；
<br>2.拦截系统自带的方法调用（Swizzle 黑魔法），比如拦截i`mageNamed:`、`viewDidLoad`、`alloc`；
<br>3.实现分类也可以增加属性；
<br>4.实现`NSCoding`的自动归档和自动解档；
<br>5.实现字典和模型的自动转换。
<br> 文章给出了实例代码和思路，值得反复阅读练习。

#### 应用示例
* [一行代码快速集成tableView头部缩放视图 - 袁峥老师@吖了个峥](http://www.jianshu.com/p/859e3ef76b05) <br>使用`Runtime`实现`tableView`的头部视图缩放。一个简单的应用示例。

## Runloop 博文链接 <p id="RunLoop"/>
* [Threading Programming Guide](https://developer.apple.com/library/mac/documentation/Cocoa/Conceptual/Multithreading/RunLoopManagement/RunLoopManagement.html) ✨
* [NSRunLoop Class Reference](https://developer.apple.com/library/mac/documentation/Cocoa/Reference/Foundation/Classes/NSRunLoop_Class/index.html) ✨

* [深入理解RunLoop - Garan no Dou](http://blog.ibireme.com/2015/05/18/runloop/#base) <br> ibireme大神的博客。干货很多，值得收藏。

* [视频: iOS线下分享《RunLoop》by 孙源@sunnyxx](http://v.youku.com/v_show/id_XODgxODkzODI0.html)
<br> 孙源老师分享视频。

* [《招聘一个靠谱的 iOS》—参考答案（下) - 28,29](https://github.com/ChenYilong/iOSInterviewQuestions/blob/master/01%E3%80%8A%E6%8B%9B%E8%81%98%E4%B8%80%E4%B8%AA%E9%9D%A0%E8%B0%B1%E7%9A%84iOS%E3%80%8B%E9%9D%A2%E8%AF%95%E9%A2%98%E5%8F%82%E8%80%83%E7%AD%94%E6%A1%88/%E3%80%8A%E6%8B%9B%E8%81%98%E4%B8%80%E4%B8%AA%E9%9D%A0%E8%B0%B1%E7%9A%84iOS%E3%80%8B%E9%9D%A2%E8%AF%95%E9%A2%98%E5%8F%82%E8%80%83%E7%AD%94%E6%A1%88%EF%BC%88%E4%B8%8B%EF%BC%89.md#28-runloop%E5%92%8C%E7%BA%BF%E7%A8%8B%E6%9C%89%E4%BB%80%E4%B9%88%E5%85%B3%E7%B3%BB)
<br> 这个也是孙源老师整理的面试

* [Objective-C之run loop详解 - 王中周](http://blog.csdn.net/wzzvictory/article/details/9237973) <br>介绍的很详细，理解这篇文章内容，`runloop`入门了。

* [Runloop](https://hit-alibaba.github.io/interview/iOS/ObjC-Basic/Runloop.html)
<br> 这是Gitbook制作的 笔试面试知识 关于RunLoop的文章。

* [iOS多线程编程指南（三）Run Loop](https://www.dreamingwish.com/article/ios-multithread-program-runloop-the.html)<br> 本文介绍RunLoop，另外几篇文是介绍多线程的其他内容。
* [走进Run Loop的世界 (一)：什么是Run Loop？](http://chun.tips/blog/2014/10/20/zou-jin-run-loopde-shi-jie-%5B%3F%5D-:shi-yao-shi-run-loop%3F/) <br> RunLoop的基本知识点。

* [走进Run Loop的世界 (二)：如何配置Run Loop Sources](http://chun.tips/blog/2014/10/20/zou-jin-run-loopde-shi-jie-er-:ru-he-pei-zhi-run-loop-sources/) <br> 如何配置RunLoop Source。

* [关于iOS多线程，你看我就够了](http://www.jianshu.com/p/0b0d9b1f1f19)
	<br> iOS 开发中几种多线程方案，以及其使用方法和注意事项。当然也会给出几种多线程的案例，在实际使用中感受它们的区别。还有一点需要说明的是，这篇文章将会使用 `Swift` 和 `Objective-C` 两种语言讲解。
	
## Block 博文整理 <p id="block">
* [Working with Blocks -- Apple](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/ProgrammingWithObjectiveC/WorkingwithBlocks/WorkingwithBlocks.html) ✨


* [谈Objective-C block的实现](http://blog.devtang.com/2013/07/28/a-look-inside-blocks/) ✨ <br> 介绍了block的实现，block数据结构，三种分类NSConcreteGlobalBlock、NSConcreteStackBlock和NSConcreteMallocBlock。分别介绍了每种的实现，对比之间的差别。

* [Block教程系列](https://www.dreamingwish.com/article/block%E6%95%99%E7%A8%8B%E7%B3%BB%E5%88%97.html) <br> 1. 介绍block基本概念。2. 内存管理与其他特性。 3和4. block的底层实现。 

* [对Objective-C中Block的追探](http://www.cnblogs.com/biosli/archive/2013/05/29/iOS_Objective-C_Block.html) <br> 作者介绍了对block的理解，结构，生命周期，转换时机，一些设计原则等。

* [iOS中block实现的探究](http://blog.csdn.net/jasonblog/article/details/7756763)

* [Block 编程](https://hit-alibaba.github.io/interview/iOS/ObjC-Basic/Block.html)

* [招聘一个靠谱的iOS面试题整理（下）37- 39题](https://github.com/ChenYilong/iOSInterviewQuestions/blob/master/01%E3%80%8A%E6%8B%9B%E8%81%98%E4%B8%80%E4%B8%AA%E9%9D%A0%E8%B0%B1%E7%9A%84iOS%E3%80%8B%E9%9D%A2%E8%AF%95%E9%A2%98%E5%8F%82%E8%80%83%E7%AD%94%E6%A1%88/%E3%80%8A%E6%8B%9B%E8%81%98%E4%B8%80%E4%B8%AA%E9%9D%A0%E8%B0%B1%E7%9A%84iOS%E3%80%8B%E9%9D%A2%E8%AF%95%E9%A2%98%E5%8F%82%E8%80%83%E7%AD%94%E6%A1%88%EF%BC%88%E4%B8%8B%EF%BC%89.md#37-%E4%BD%BF%E7%94%A8block%E6%97%B6%E4%BB%80%E4%B9%88%E6%83%85%E5%86%B5%E4%BC%9A%E5%8F%91%E7%94%9F%E5%BC%95%E7%94%A8%E5%BE%AA%E7%8E%AF%E5%A6%82%E4%BD%95%E8%A7%A3%E5%86%B3)<br> 1. 使用block时什么情况会发生引用循环，如何解决？<br>2. 在block内如何修改block外部变量？<br>3. 使用系统的某些block api（如UIView的block版本写动画时），是否也考虑引用循环问题？
## Swift  <p id="swift">
* [The Swift Programming Language](http://wiki.jikexueyuan.com/project/swift/)<br/>极客学院出版，中文版Swift官方文档。
* [Swifter：Swift开发者必备的Tips（第三版）购买链接](https://objccn.io/products/)<br/>Swifter：Swift开发者必备的Tips第三版，这个链接是购买链接。推荐这本书籍。这本书很赞，内容价值远远超多书的价格。
* [SwiftGG 走心的 Swift 翻译组](http://swift.gg/archives/)<br/>经常更新Swift文章。
* [Swift中常用的开源库](https://github.com/SwiftOldDriver/SwiftMarch) ：从开发者角度介绍被广泛运用于实际Swift项目中的开源库。

## 常用三方库 <p id="三方">
* [常用库整理](http://www.cocoachina.com/ios/20160121/14988.html?_t_t_t=0.020374531857669353) ： 整理了常用的三方库
* [iOS项目中常用的第三方开源库](http://www.cnblogs.com/tangaofeng/p/4876219.html): 项目开发中常用三方库，避免重复造轮子

# 其他
## 微信小程序<p id="微信小程序">
* [justjavac/awesome-wechat-weapp](https://github.com/justjavac/awesome-wechat-weapp)<br>微信小程序开发资源汇总 wechat weapp

* [gavinkwoe/weapp-ide-crack](https://github.com/gavinkwoe/weapp-ide-crack)<br>【应用号】IDE + 破解 + Demo

## Weex （阿里跨平台移动开发框架）<p id="weex">
* [官方文档](https://weex-project.io/cn/)  : Weex官方文档
* [awesome-weex](https://github.com/joggerplus/awesome-weex#%E9%80%9A%E7%94%A8%E6%95%99%E7%A8%8B) : github中整理关于Weex相关资料，包括：教程，文章，网站，项目等。

## 设计 <p id="设计">
* [高清图片库](https://pixabay.com/) ： 共有约84万张免费高清图片、矢量文件和艺术插图。
* [简书上整理的设计网站](http://www.jianshu.com/p/db7eab8fe013) : 10年设计路，还是这些网站最好用
* [Web安全色](http://www.bootcss.com/p/websafecolors/)
* [RGB颜色值与十六进制颜色码转换工具](http://www.sioe.cn/yingyong/yanse-rgb-16/) : 另外，本网站还提供了一些其他应用工具，例如彩虹字生成器，发光字生成器等等。
* [Adobe Color CC](https://color.adobe.com/zh/create/color-wheel) : 一个调色板工具



## 网站收藏 <p id="网站收藏">



