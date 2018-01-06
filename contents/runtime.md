# runtime

## 是什么

- [初识 Objective-C Runtime][ref1]
> 首先Objective-C是C语言的扩展，并加入了面向对象特性和Smalltalk式的消息传递机制。而这个扩展的核心就是一个用C和汇编语言写的RunTime库，这个库所做的事情就是加载类信息，进行方法的分发和转发，正是这个库赋予了Objective-C的动态特性。  
>
>对于C语言，函数的调用在编译的时候就会去决定调用哪个函数。而OC是一种动态语言，它会尽可能的把代码执行的决策从编译和链接的时候，推迟到运行时。  
>
>给一个对象发送的一个消息并不会立即执行，而是在运行的时候再去寻找他对应的实现。那么你就可以把消息转发给你想要的对象，或者随意交换一个方法的实现之类的。

## 什么用
## 怎么用
## REFERENCE
[ref1]:http://www.saitjr.com/ios/objc-runtime.html

[初识 Objective-C Runtime][ref1]
[Objective-C Runtime](https://developer.apple.com/documentation/objectivec/objective_c_runtime)  
[Objective-C Runtime Programming Guide](https://developer.apple.com/library/content/documentation/Cocoa/Conceptual/ObjCRuntimeGuide/Introduction/Introduction.html#//apple_ref/doc/uid/TP40008048)  
[Objective-C Runtime 1小时入门教程(形象/生动/详细的文章，细读)](https://www.ianisme.com/ios/2019.html)  
[Object Model](https://nishitmehta.com/page/2/)  
[runtime obj4 源码](https://github.com/opensource-apple/objc4)  
