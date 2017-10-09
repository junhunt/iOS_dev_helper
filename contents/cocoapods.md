# CocoaPods

- 更新 CocoaPods 或下载  

```
sudo gem install cocoapods -n /usr/local/bin
```

- 指定源和版本  

```
source 'https://github.com/CocoaPods/Specs.git'
platform :ios, '8.0'
```

- 指定第三方版本

```
#具体版本
pod 'swiftScan', '1.0.9'

#限定版本范围
> 0.1 高于0.1版本（不包含0.1版本）的任意一个版本
>= 0.1 高于0.1版本（包含0.1版本）的任意一个版本
< 0.1 低于0.1版本（不包含0.1版本）的任意一个
<= 0.1低于0.1版本（包含0.1版本）的任意一个
~> 0.1.2  0.1.2 到 0.2（不包含）的最新版本，等效于(>= 0.1.2 && <0.2.0)，这个基于你指定的版本号的最后一个部分。
```

- 忽略引入库的所有警告  

```
inhibit_all_warnings!  
```

- 指定第三方的编译版本  

```
# 指定所有第三方的编译版本
post_install do |installer|
  installer.pods_project.targets.each do |target|
    target.build_configurations.each do |config|
      config.build_settings['SWIFT_VERSION'] = '3.2'
    end
  end
end

post_install do |installer|
    # 指定个别第三方的编译版本
    myTargets = ['Charts', 'SnapKit']

    installer.pods_project.targets.each do |target|
        if myTargets.include? target.name
            target.build_configurations.each do |config|
                config.build_settings['SWIFT_VERSION'] = '3.2'
            end
        end
    end
end
```

## 配置示例

``` pod
# 忽略引入库的所有警告
inhibit_all_warnings!

target 'FangLiLai' do
  # Comment the next line if you're not using Swift and don't want to use dynamic frameworks
  use_frameworks!

# Pods for FangLiLai
pod 'SnapKit'
pod 'Alamofire', '~> 4.0'
pod 'Kingfisher', '~> 3.0'
pod 'RealmSwift'
pod 'MJRefresh'
pod 'SVProgressHUD'
pod 'HandyJSON', '~> 1.7.1'
#pod 'SwiftyJSON'
pod 'Charts'
#pod 'ChartsRealm'
pod 'MGSwipeTableCell'
pod 'Onboard' # 只需几行代码，即可轻松创建漂亮，引人入胜的用户指导页体验。
pod 'ImageViewer'
pod 'IQKeyboardManager'
pod 'VTMagic'
pod 'swiftScan', '1.0.9'
pod 'MWPhotoBrowser'
pod 'BaiduMapKit' # 百度地图 SDK
pod 'WechatOpenSDK' # 微信 SDK
pod 'WZLBadge' # badge 红点

# pod 'SwiftyJSON'
# pod 'ObjectMapper'
# pod 'ImagePicker'
# pod 'HanekeSwift'
# pod 'Toucan'
# pod 'BeeCloud' # 包含支付宝微信银联三个渠道

end

post_install do |installer|
    # 指定个别第三方的编译版本
    myTargets = ['Charts', 'SnapKit']

    installer.pods_project.targets.each do |target|
        if myTargets.include? target.name
            target.build_configurations.each do |config|
                config.build_settings['SWIFT_VERSION'] = '3.2'
            end
        end
    end
end
```

## REFERENCE
[用CocoaPods做iOS程序的依赖管理](http://blog.devtang.com/2014/05/25/use-cocoapod-to-manage-ios-lib-dependency/)  
[CocoaPods/Specs 国内镜像，每日自动更新](https://coding.net/u/CocoaPods/p/Specs/git)  
[你真的会写Podfile吗?](http://www.jianshu.com/p/8a0fd6150159)  
[Podfile Syntax Reference](https://guides.cocoapods.org/syntax/podfile.html#podfile)
