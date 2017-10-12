# Unit Test
> 单元测试是对程序代码单元进行函数级别的测试，是面向最小软件设计单元的验证工作。它是软件最小组成单位的测试，是软件开发过程中的最基本的测试。它处在软件开发过程中实施的最低级别的测试活动，即检查单元程序模块有无错误。它是在编码完成后必须进行的测试工作，也可以称之为模块测试。

不管是开发还是测试，如果不断地做着重复性的工作，问自己一个问题：是不是有更高效的办法？

已有工程添加单元测试：PROJECT -> target -> 底部 “+” 号。

### demo  
[PercentageCalculator](https://github.com/junhunt/iOS_demo/tree/master/PercentageCalculator)  

### iOS单元测试基本规范
- 新建项目勾选Include Unit Tests,可以自动生成"项目名+Tests"的Target，对于已有项目，新建单元测试Target命名也应遵循"项目名+Tests";

- 官方生成的默认测试类，包含了一个setUp()方法和tearDown()方法，分别用来在每个测试方法运行之前做初始化准备，和在测试方法运行之后做清理工作；

- 类中所有的测试方法的名字都要以 test 关键字开头，否则 Xcode 无法识别，测试方法命名时，统一为即"test"+方法名；

- 工程Target中的包名，统一与测试Target中的包名一一对应，即测试Target中的包名命名为：原包名+"Test"

- 同理，工程Target中的类名，也统一与测试Target中的类名一一对应，即测试Target中的类名命名为：类名+"Test";

### 为什么做单元测试
- 帮助理解需求  
单元测试应该反映Use Case，把被测单元当成黑盒测试其外部行为。

- 提高实现质量  
单元测试不保证程序做正确的事，但能帮助保证程序正确地做事，从而提高实现质量。

- 测试成本低  
相比集成测试、验收测试，单元测试所依赖的外部环境少，自动化程度高，时间短，节约了测试成本。

- 反馈速度快  
单元测试提供快速反馈，把bug消灭在开发阶段，减少问题流到集成测试、验收测试和用户，降低了软件质量控制的成本。

- 利于重构  
由于有单元测试作为回归测试用例，有助于预防在重构过程中引入bug。

- 文档作用  
单元测试提供了被测单元的使用场景，起到了使用文档的作用。

- 对设计的反馈  
一个模块很难进行单元测试通常是不良设计的信号，单元测试可以反过来指导设计出高内聚、低耦合的模块。

### MORE
[Xcode7 中用 Swift 做单元测试](http://swift.gg/2016/03/23/unit-testing-swift/)  
[用Swift语言做App开发之单元测试](http://www.cnblogs.com/cdutedu/p/4297868.html)  
[iOS 单元测试和UI测试教程](http://www.cocoachina.com/ios/20170718/19930.html)  
[没有单元测试，何谈重构](http://www.cocoachina.com/ios/20161123/18163.html)  
[XCTest​Case /XCTest​Expectation /measure​Block()](http://nshipster.com/xctestcase/)  
[如何在 Swift 中测试 UIAlertController](http://www.swift.gg/2015/10/12/how-to-test-uialertcontroller-in-swift/)  
[iOS 单元测试之XCTest详解](http://blog.csdn.net/hello_hwc/article/details/46671053)  
[UI Texting inXcode](https://developer.apple.com/videos/play/wwdc2015/406/)  
[About Testing with Xcode](https://developer.apple.com/library/content/documentation/DeveloperTools/Conceptual/testing_with_xcode/chapters/01-introduction.html)  
