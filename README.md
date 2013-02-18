iOS_command_compile
===================

iOS命令行编译相关

环境
----
Mac OSX 10.8.2
Xcode Version 4.6 (4H127)

命令行编译
=============

命令
----

xcodebuild -target Yourapp clean

xcodebuild -target PROVISIONING_PROFILE="your_mobile_provision_file_name" CODE_SIGN_IDENTITY="your_identity"

xcrun -sdk iphoneos PackageApplication -v build/Release-iphoneos/your_app.app -o /your/file/path/

以上命令就是用命令行编译的方法

细节
----

1.PROVISIONING_PROFILE 的值

    从app_store中下载回来的*.mobileprovision文件的文件名
    （需要在/Users/yourname/Library/MobileDevice/Provisioning\ Profiles/ 下,在Xcode的Organizer->Provisioning Profiles中也可以看到 ）

2.CODE_SIGN_IDENTITY 的值

    apple提供的cer文件中提供的信息，安装后，可以在system preference -> keychain access中的My Certificates tab中看到
    （Name为iPhone Distribution:your_info），这个name就是CODE_SIGN_IDENTITY的值

设定好这两个值，就可以编译和打包出可以直接上传到appstore的ipa包了


相关资料
========

Xcode Build Setting Reference
=============================

Xcode Build Setting Reference [apple doc](http://developer.apple.com/library/mac/#documentation/DeveloperTools/Reference/XcodeBuildSettingRef/1-Build_Setting_Reference/build_setting_ref.html)


Xcode file: project.pbxproj Format
==================================

Xcode Project File Format [link](http://www.monobjc.net/index.php?page=xcode-project-file-format#PBXSourcesBuildPhase)

对pboproj 的操作：
-----------------
1、plist

    plist 是mac os 有的一个命令，可以轻易将plist文件转为xml,json格式，或者将xml文件转为plist文件。
    [文档链接](http://developer.apple.com/library/mac/#documentation/Darwin/Reference/ManPages/man1/plutil.1.html)
    
2、pl

    pl 也是mac os 有的一个命令，可以将xml文件转为plist文件，但是这个文件是old-style的（即xcode中的pbxproj文件）。
    [文档链接](http://developer.apple.com/library/mac/#documentation/Darwin/Reference/ManPages/man1/pl.1.html)






