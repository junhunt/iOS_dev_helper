# UIStoryboard

- 代码（传参）触发 segue 需要设置 identifier 标识，可以使用已经存在的 segue，或重新拉一条【控制器-控制器】的不指定触发源的 segue；调用触发函数 performSegue(withIdentifier:sender:)，之后在同一控制器 prepare(for:sender:) 方法传参。

- 代码触发 unwind 需要设置 identifier 标识，可以使用已经存在的 unwind，或重新拉一条【控制器-Exit】的不指定触发源的 unwind；调用触发函数 performSegue(withIdentifier:sender:)，之后在同一控制器 prepare(for:sender:) 方法传参。

- unwind 时首先需要在目标控制器实现 unwind 方法，这样整个 project 都能找到这个方法。

```
@IBAction func unwindToMain(segue: UIStoryboardSegue) {
}
```

## REFERENCE
[Using Segues](https://developer.apple.com/library/content/featuredarticles/ViewControllerPGforiPhoneOS/UsingSegues.html#//apple_ref/doc/uid/TP40007457-CH15-SW1)  
