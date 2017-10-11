# 多个 targets 的使用

- Create a New Target
1. Project -> select target -> Command-D -> Duplicate(Only) -> rename(e.g. XXDev，XX 是原来的名字)  
2. 重命名 scheme -> Manage Schemes…( Command-Shift-< )-> rename scheme to the same(XXDev).  
3. 为 target 设置不同的 图标（选做）：add "App Icons" in Assets.xcassets, named "AppIcon-Dev" and add images for it. 选择新 target，将 General 页面的 "App Icons Source" 设置为 "AppIcon-Dev"
4. alter bundle id: 选择新 target，将 General 页面的 "Bundle Identifier" 改为 "原有 bundleID-Dev"
5. 重命名 plist 文件（工程目录最下面？），改名为 XXDev-Info.plist. 将 Build Settings 中 Info.plist File 设置为 XXDev-Info.plist
6. 设置预处理标记 configure a preprocessing macro/compiler flag

```
# 注意：Build Settings 下一行要选择 All & Combined

# OC
Build Settings -> Preprocessor Macros -> Debug add DEVELOPMENT=1, Release add DEVELOPMENT=0 -> 设置宏定义(新建 TargetConfig.h 文件)：

#if DEVELOPMENT
#define SERVER_URL @"http://dev.server.com/api/"
#define API_TOKEN @"DI2023409jf90ew"
#else
#define SERVER_URL @"http://prod.server.com/api/"
#define API_TOKEN @"71a629j0f090232"
#endif



# Swift
Build Settings -> Other Swift Flags -> set value: "-DDEVELOPMENT" -> 设置宏定义(新建 TargetConfig.swift 文件)：

#if DEVELOPMENT
let SERVER_URL = "http://dev.server.com/api/"
let API_TOKEN = "DI2023409jf90ew"
#else
let SERVER_URL = "http://prod.server.com/api/"
let API_TOKEN = "71a629j0f090232"
#endif

```

- 管理多个 targets 注意事项
1. 添加新文件时，别忘了为多个 target 添加
2. 管理 Cocoapods 添加 target （link_with）

## REFERENCE
[How to Use Xcode Targets to Manage Development and Production Builds](https://www.appcoda.com/using-xcode-targets/)  