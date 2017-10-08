# Breakpoint debug 断点调试

### Condational Breakpoint
添加断点 -> Edit Breakpoint -> 设置 Condition，当满足该条件时会触发断点。

### Exception Breakpoint
Breakpoint navigator -> + -> Exception Breakpoint...，遇到错误程序会自动定位到栈底的信息。

### Symbolic Breakpoint
Breakpoint navigator -> + -> Symbolic Breakpoint... ->. 
设置 Symbol，可设置函数或指定类的函数，如 viewDidLoad，ViewController.viewDidLoad，
当函数被调用时会触发断点。  

### Watch Breakpoint
找到变量第一次出现的地方，添加断点，进入 debug 模式后在 Variables View 中右键变量，选择 Watch 变量名。当变量被改变时会触发断点。

### 日志信息断点
添加断点 -> Edit Breakpoint -> Add Action -> Log Message，在输入框中输入 The number is: @number@（注，@number@ 中的 number 是监控的变量）。勾选 Automatically continue after evaluating actions 后断点不会停留但继续输出日志。

### 发声断点
同日志信息断点，Action 选择 Sound。当触发断点时会发出设置的声音。

### MORE
[Xcode 的正确打开方式——Debugging](http://www.cocoachina.com/ios/20150225/11190.html)
[iOS各种调试技巧](https://daiweilai.github.io/2015/04/13/iOS%E5%90%84%E7%A7%8D%E8%B0%83%E8%AF%95%E6%8A%80%E5%B7%A7/)