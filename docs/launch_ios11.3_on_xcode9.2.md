## Launching IOS on Xcode
In this tutorial an Iphone is hooked up to a Mac mini and run via an USB cord.
#### Step 1
For this step it is give that you have xcode 9.2 and a iphone running ios11.3.1

Create an account on https://developer.apple.com and agree to the terms given.
This provides a free certificate for you to run on a Device, via USB.

#### Step 2
Start Xcode with your project that could be called "App" :stuck_out_tongue_winking_eye:
```
open App/ios/App.xcodeproj
```

[Screenshot of XCode environment](../images/img1)
In Xcode->click on root project in left panel

Choose team under Signing, and Add Account. Choose to download certificate linked to your apple-id. The credentials used for your Apple Developer Account. Remember to set the destination to your device. Furthermore, the computer and iphone should be connected to the same wifi if host in RCTWebSocketExecutor.m should be localhost. Otherwise, host should be set to the IP-address to the computer. If the computer is connected to a secure network (router) and does not display a IP-address that isn't publicly visible, try and use [ngrok](http://blog.theodo.fr/2017/11/preact-progressive-web-app-webpack-material-design-web-apis/#Check_out_the_hot_reload_on_your_phone_117) under the sub-title "Check out the hot reload on your phone!" to make localhost:8081 accessible.
 
A problem that will occur is that XCode will say something like: "XCode 9.2 does not support your device. The "[solution](https://stackoverflow.com/questions/49720178/xcode-not-supported-for-ios-11-3-by-xcode-9-2-needed-9-3?utm_medium=organic&utm_source=google_rich_qa&utm_campaign=google_rich_qa) for this will tell you how to download the needed data for giving such support. Download ZIP file [here](https://github.com/filsv/iPhoneOSDeviceSupport).

If you experience similar issues or problems related to XCode, 
[XCode release notes](https://developer.apple.com/library/content/releasenotes/DeveloperTools/RN-Xcode/Chapters/Introduction.html#//apple_ref/doc/uid/TP40001051) can help to find the answer to version-related dependencies. 
