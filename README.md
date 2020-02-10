## Setup
(Optional) Add your firebase project details to web/index.html  
flutter channel master  
flutter upgrade  
flutter config --enable-web    
flutter run -d chrome  


## Issue 
```
html_dart2js.dart:38356 Overflow on channel: plugins.flutter.io/firebase_storage.  Messages on this channel are being discarded in FIFO fashion.  The engine may not be running or you need to adjust the buffer size if of the channel.
error @ html_dart2js.dart:38356
_printDebugString @ natives.dart:22
_printDebug @ natives.dart:14
push @ channel_buffers.dart:143
handlePlatformMessage @ plugin_registry.dart:84
runBody @ async_patch.dart:86
_async @ async_patch.dart:125
handlePlatformMessage @ plugin_registry.dart:76
sendPlatformMessage @ window.dart:215
[_sendPlatformMessage] @ binding.dart:175
send @ binding.dart:224
_invokeMethod @ platform_channel.dart:146
runBody @ async_patch.dart:86
_async @ async_patch.dart:125
[_invokeMethod] @ platform_channel.dart:144
invokeMethod @ platform_channel.dart:329
getDownloadURL @ storage_reference.dart:142
runBody @ async_patch.dart:86
_async @ async_patch.dart:125
getDownloadURL @ storage_reference.dart:141
main$ @ main.dart:14
runBody @ async_patch.dart:86
_async @ async_patch.dart:125
main$ @ main.dart:4
main$ @ main_web_entrypoint.dart:13
onValue @ async_patch.dart:47
runUnary @ zone.dart:1381
handleValue @ future_impl.dart:140
handleValueCallback @ future_impl.dart:682
_propagateToListeners @ future_impl.dart:711
(anonymous) @ future_impl.dart:391
_microtaskLoop @ schedule_microtask.dart:43
_startMicrotaskLoop @ schedule_microtask.dart:52
(anonymous) @ async_patch.dart:168
Show 4 more frames
```  
  
```
errors.dart:147 Uncaught (in promise) Error: MissingPluginException(No implementation found for method StorageReference#getDownloadUrl on channel plugins.flutter.io/firebase_storage)
    at Object.throw_ [as throw] (errors.dart:196)
    at MethodChannel._invokeMethod (platform_channel.dart:154)
    at _invokeMethod.next (<anonymous>)
    at onValue (async_patch.dart:47)
    at _RootZone.runUnary (zone.dart:1381)
    at _FutureListener.thenAwait.handleValue (future_impl.dart:140)
    at handleValueCallback (future_impl.dart:682)
    at Function._propagateToListeners (future_impl.dart:711)
    at _Future.new.[_completeWithValue] (future_impl.dart:526)
    at async._AsyncCallbackEntry.new.callback (future_impl.dart:556)
    at Object._microtaskLoop (schedule_microtask.dart:43)
    at _startMicrotaskLoop (schedule_microtask.dart:52)
    at async_patch.dart:168
 ```

## Flutter doctor  
[✓] Flutter (Channel master, v1.15.3-pre.37, on Mac OS X 10.15.3 19D76, locale en-GB)
    • Flutter version 1.15.3-pre.37 at /Users/morphingcoffee/Applications/flutter
    • Framework revision 6dc3bfaa98 (2 days ago), 2020-02-07 18:28:02 -0800
    • Engine revision 6158f03ef5
    • Dart version 2.8.0 (build 2.8.0-dev.8.0 514a8d4c84)

[!] Android toolchain - develop for Android devices (Android SDK version 29.0.2)
    • Android SDK at /Users/morphingcoffee/Library/Android/sdk
    • Android NDK location not configured (optional; useful for native profiling support)
    • Platform android-29, build-tools 29.0.2
    • ANDROID_HOME = /Users/morphingcoffee/Library/Android/sdk
    • Java binary at: /Applications/Android Studio.app/Contents/jre/jdk/Contents/Home/bin/java
    • Java version OpenJDK Runtime Environment (build 1.8.0_202-release-1483-b49-5587405)
    ✗ Android license status unknown.
      Try re-installing or updating your Android SDK Manager.
      See https://developer.android.com/studio/#downloads or visit https://flutter.dev/setup/#android-setup for detailed instructions.

[✓] Xcode - develop for iOS and macOS (Xcode 11.3.1)
    • Xcode at /Applications/Xcode.app/Contents/Developer
    • Xcode 11.3.1, Build version 11C504
    • CocoaPods version 1.8.3

[✓] Chrome - develop for the web
    • Chrome at /Applications/Google Chrome.app/Contents/MacOS/Google Chrome

[✓] Android Studio (version 3.5)
    • Android Studio at /Applications/Android Studio.app/Contents
    • Flutter plugin version 43.0.1
    • Dart plugin version 191.8593
    • Java version OpenJDK Runtime Environment (build 1.8.0_202-release-1483-b49-5587405)

[✓] Connected device (2 available)
    • Chrome     • chrome     • web-javascript • Google Chrome 80.0.3987.87
    • Web Server • web-server • web-javascript • Flutter Tools
    
    
## flutter run -d chrome -v

```
[  +19 ms] executing: [/Users/morphingcoffee/Applications/flutter/] git -c log.showSignature=false log -n 1 --pretty=format:%H
[  +27 ms] Exit code 0 from: git -c log.showSignature=false log -n 1 --pretty=format:%H
[        ] 6dc3bfaa98e13c0f174e0cc229e7b43678d4d0c0
[        ] executing: [/Users/morphingcoffee/Applications/flutter/] git describe --match v*.*.* --first-parent --long --tags
[  +16 ms] Exit code 0 from: git describe --match v*.*.* --first-parent --long --tags
[        ] v1.15.2-37-g6dc3bfaa9
[   +5 ms] executing: [/Users/morphingcoffee/Applications/flutter/] git rev-parse --abbrev-ref --symbolic @{u}
[   +7 ms] Exit code 0 from: git rev-parse --abbrev-ref --symbolic @{u}
[        ] origin/master
[        ] executing: [/Users/morphingcoffee/Applications/flutter/] git ls-remote --get-url origin
[   +6 ms] Exit code 0 from: git ls-remote --get-url origin
[        ] https://github.com/flutter/flutter.git
[  +34 ms] executing: [/Users/morphingcoffee/Applications/flutter/] git rev-parse --abbrev-ref HEAD
[   +8 ms] Exit code 0 from: git rev-parse --abbrev-ref HEAD
[        ] master
[   +3 ms] executing: sw_vers -productName
[  +11 ms] Exit code 0 from: sw_vers -productName
[        ] Mac OS X
[        ] executing: sw_vers -productVersion
[  +10 ms] Exit code 0 from: sw_vers -productVersion
[        ] 10.15.3
[        ] executing: sw_vers -buildVersion
[  +11 ms] Exit code 0 from: sw_vers -buildVersion
[        ] 19D76
[  +17 ms] Artifact Instance of 'AndroidMavenArtifacts' is not required, skipping update.
[        ] Artifact Instance of 'AndroidGenSnapshotArtifacts' is not required, skipping update.
[        ] Artifact Instance of 'AndroidInternalBuildArtifacts' is not required, skipping update.
[        ] Artifact Instance of 'IOSEngineArtifacts' is not required, skipping update.
[        ] Artifact Instance of 'FlutterWebSdk' is not required, skipping update.
[   +1 ms] Artifact Instance of 'WindowsEngineArtifacts' is not required, skipping update.
[        ] Artifact Instance of 'MacOSEngineArtifacts' is not required, skipping update.
[        ] Artifact Instance of 'LinuxEngineArtifacts' is not required, skipping update.
[        ] Artifact Instance of 'LinuxFuchsiaSDKArtifacts' is not required, skipping update.
[        ] Artifact Instance of 'MacOSFuchsiaSDKArtifacts' is not required, skipping update.
[        ] Artifact Instance of 'FlutterRunnerSDKArtifacts' is not required, skipping update.
[        ] Artifact Instance of 'FlutterRunnerDebugSymbols' is not required, skipping update.
[  +23 ms] executing: /Users/morphingcoffee/Library/Android/sdk/platform-tools/adb devices -l
[   +5 ms] Exit code 0 from: /Users/morphingcoffee/Library/Android/sdk/platform-tools/adb devices -l
[        ] List of devices attached
[   +8 ms] executing: /usr/bin/xcode-select --print-path
[   +5 ms] Exit code 0 from: /usr/bin/xcode-select --print-path
[        ] /Applications/Xcode.app/Contents/Developer
[        ] executing: /usr/bin/xcodebuild -version
[  +87 ms] Exit code 0 from: /usr/bin/xcodebuild -version
[        ] Xcode 11.3.1
           Build version 11C504
[   +2 ms] executing: xcrun --find xcdevice
[   +6 ms] Exit code 0 from: xcrun --find xcdevice
[        ] /Applications/Xcode.app/Contents/Developer/usr/bin/xcdevice
[   +1 ms] executing: xcrun xcdevice list --timeout 1
[+1460 ms] [
             {
               "simulator" : true,
               "operatingSystemVersion" : "11.4 (15F79)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPhone9,2",
               "identifier" : "48E3FC92-28F0-4AD0-8809-3F51BEA31EB3",
               "architecture" : "x86_64",
               "modelName" : "iPhone 7 Plus",
               "name" : "iPhone 7 Plus"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "11.4 (15F79)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPhone10,5",
               "identifier" : "3DAB7988-BBD2-42A8-9304-2969EB88BA21",
               "architecture" : "x86_64",
               "modelName" : "iPhone 8 Plus",
               "name" : "iPhone 8 Plus"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "12.2 (16E226)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPhone10,6",
               "identifier" : "805653CD-638D-4060-9C45-7F1A3DB4B143",
               "architecture" : "x86_64",
               "modelName" : "iPhone X",
               "name" : "iPhone X"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "12.2 (16E226)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPad11,3",
               "identifier" : "03F78D3B-18EB-4C78-8438-4BF2C3A9483F",
               "architecture" : "x86_64",
               "modelName" : "iPad Air (3rd generation)",
               "name" : "iPad Air (3rd generation)"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "12.2 (16E226)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPad7,3",
               "identifier" : "DF69602E-479D-4A9E-A3A6-415ABDC448D6",
               "architecture" : "x86_64",
               "modelName" : "iPad Pro (10.5-inch)",
               "name" : "iPad Pro (10.5-inch)"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "11.4 (15F79)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPhone7,1",
               "identifier" : "5E4E6F6F-AFB8-407E-8D7C-C3CA9DC6883A",
               "architecture" : "x86_64",
               "modelName" : "iPhone 6 Plus",
               "name" : "iPhone 6 Plus"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "12.2 (16E226)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPhone10,5",
               "identifier" : "64F5BD82-C2A9-4C9B-BE3A-549FD26E15D4",
               "architecture" : "x86_64",
               "modelName" : "iPhone 8 Plus",
               "name" : "iPhone 8 Plus"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "13.3 (17K446)",
               "available" : true,
               "platform" : "com.apple.platform.appletvsimulator",
               "modelCode" : "AppleTV6,2",
               "identifier" : "A13F9807-6C9D-4AD9-8DB2-E4CD80196D14",
               "architecture" : "x86_64",
               "modelName" : "Apple TV 4K",
               "name" : "Apple TV 4K"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "10.3.1 (14E8301)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPhone6,1",
               "identifier" : "48E8D5BC-2614-4DAD-9DD0-94C37F06AA0B",
               "architecture" : "x86_64",
               "modelName" : "iPhone 5s",
               "name" : "iPhone 5s"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "13.3 (17C45)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPhone12,1",
               "identifier" : "8271A80B-84B7-4E8A-B539-915BB3F8BE08",
               "architecture" : "x86_64",
               "modelName" : "iPhone 11",
               "name" : "iPhone 11"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "12.2 (16E226)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPhone7,2",
               "identifier" : "4BFAC6B2-9DE4-4028-BD6C-7BFBD524C4B1",
               "architecture" : "x86_64",
               "modelName" : "iPhone 6",
               "name" : "iPhone 6"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "13.3 (17C45)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPhone12,5",
               "identifier" : "A8A88C93-367A-4A84-A967-09E1EE64AEFA",
               "architecture" : "x86_64",
               "modelName" : "iPhone 11 Pro Max",
               "name" : "iPhone 11 Pro Max"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "13.3 (17C45)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPad7,12",
               "identifier" : "23EC3E72-3705-4ECE-922E-B8E7748520F9",
               "architecture" : "x86_64",
               "modelName" : "iPad (7th generation)",
               "name" : "iPad (7th generation)"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "11.4 (15F79)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPhone6,1",
               "identifier" : "5048B87E-0504-47CA-A9E4-B1F0A87FF309",
               "architecture" : "x86_64",
               "modelName" : "iPhone 5s",
               "name" : "iPhone 5s"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "12.2 (16E226)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPad8,1",
               "identifier" : "C838998A-79E8-4931-A82D-7145C66F6DCB",
               "architecture" : "x86_64",
               "modelName" : "iPad Pro (11-inch)",
               "name" : "iPad Pro (11-inch)"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "12.2 (16E226)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPad7,1",
               "identifier" : "9D694F05-A0A3-4E6C-88BE-24FE45B7FD93",
               "architecture" : "x86_64",
               "modelName" : "iPad Pro (12.9-inch) (2nd generation)",
               "name" : "iPad Pro (12.9-inch) (2nd generation)"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "10.3.1 (14E8301)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPhone9,1",
               "identifier" : "3A340796-4842-46A8-A5ED-F9558CFC63E5",
               "architecture" : "x86_64",
               "modelName" : "iPhone 7",
               "name" : "iPhone 7"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "12.2 (16E226)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPad7,6",
               "identifier" : "78DC76DD-AB50-47E7-ADC2-7C7E53098A5B",
               "architecture" : "x86_64",
               "modelName" : "iPad (6th generation)",
               "name" : "iPad (6th generation)"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "11.4 (15F79)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPhone8,1",
               "identifier" : "243D5F51-0F8A-4F05-A0E4-1FA3A25E95AB",
               "architecture" : "x86_64",
               "modelName" : "iPhone 6s",
               "name" : "iPhone 6s"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "12.2 (16E226)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPhone10,4",
               "identifier" : "0052F937-1875-4125-9FB0-2CD2F6B35427",
               "architecture" : "x86_64",
               "modelName" : "iPhone 8",
               "name" : "iPhone 8"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "10.3.1 (14E8301)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPad5,4",
               "identifier" : "78DAF65C-294D-4E01-84E2-B0C22F1F5939",
               "architecture" : "x86_64",
               "modelName" : "iPad Air 2",
               "name" : "iPad Air 2"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "10.3.1 (14E8301)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPad6,12",
               "identifier" : "0976CF43-7D68-4CBC-A8FE-E2E26BB4CBD3",
               "architecture" : "x86_64",
               "modelName" : "iPad (5th generation)",
               "name" : "iPad (5th generation)"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "10.3.1 (14E8301)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPhone7,1",
               "identifier" : "A9176371-99ED-49FD-B8E8-A70C22E5E646",
               "architecture" : "x86_64",
               "modelName" : "iPhone 6 Plus",
               "name" : "iPhone 6 Plus"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "12.2 (16E226)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPhone8,2",
               "identifier" : "D81C82B0-250B-4DEF-806D-44CFB2C2B44C",
               "architecture" : "x86_64",
               "modelName" : "iPhone 6s Plus",
               "name" : "iPhone 6s Plus"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "11.4 (15F79)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPhone10,6",
               "identifier" : "FFF9E696-59DE-4129-AC89-1E40F557947C",
               "architecture" : "x86_64",
               "modelName" : "iPhone X",
               "name" : "iPhone X"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "10.3.1 (14E8301)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPhone8,1",
               "identifier" : "419BA9A3-63A1-4220-9CE9-0446EF11840E",
               "architecture" : "x86_64",
               "modelName" : "iPhone 6s",
               "name" : "iPhone 6s"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "12.2 (16E226)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPad4,2",
               "identifier" : "64920AE3-23FF-4FD1-8DBF-913BE2DD5542",
               "architecture" : "x86_64",
               "modelName" : "iPad Air",
               "name" : "iPad Air"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "13.3 (17C45)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPhone12,3",
               "identifier" : "53C31E6F-63E9-448F-B980-D65DC71441B9",
               "architecture" : "x86_64",
               "modelName" : "iPhone 11 Pro",
               "name" : "iPhone 11 Pro"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "11.4 (15F79)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPad6,4",
               "identifier" : "4EC4E7CF-1EE6-4BED-BDB0-22CD9E80A7AC",
               "architecture" : "x86_64",
               "modelName" : "iPad Pro (9.7-inch)",
               "name" : "iPad Pro (9.7-inch)"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "10.3.1 (14E8301)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPad6,4",
               "identifier" : "0C290B4B-FEAB-44BE-8546-FA3C626D8A7A",
               "architecture" : "x86_64",
               "modelName" : "iPad Pro (9.7-inch)",
               "name" : "iPad Pro (9.7 inch)"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "12.2 (16E226)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPhone8,1",
               "identifier" : "83027B96-82F6-4496-A9A8-BB6A60EF536C",
               "architecture" : "x86_64",
               "modelName" : "iPhone 6s",
               "name" : "iPhone 6s"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "12.2 (16E226)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPad6,12",
               "identifier" : "CD75A5D4-81BD-4BAE-8B35-7FF7C63C0FD2",
               "architecture" : "x86_64",
               "modelName" : "iPad (5th generation)",
               "name" : "iPad (5th generation)"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "13.3 (17C45)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPad8,5",
               "identifier" : "12715779-E244-4011-9847-2C124AA0BCB9",
               "architecture" : "x86_64",
               "modelName" : "iPad Pro (12.9-inch) (3rd generation)",
               "name" : "iPad Pro (12.9-inch) (3rd generation)"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "12.2 (16E226)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPhone8,4",
               "identifier" : "CB007CA3-D65E-45F1-83C6-951A60D206D0",
               "architecture" : "x86_64",
               "modelName" : "iPhone SE",
               "name" : "iPhone SE"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "10.3.1 (14E8301)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPhone8,2",
               "identifier" : "9649829B-A4E4-48C5-A9AF-45BBD6339B09",
               "architecture" : "x86_64",
               "modelName" : "iPhone 6s Plus",
               "name" : "iPhone 6s Plus"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "10.3.1 (14E8301)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPad7,3",
               "identifier" : "55479B5D-6AC2-4536-8D7B-E1F10D6E3020",
               "architecture" : "x86_64",
               "modelName" : "iPad Pro (10.5-inch)",
               "name" : "iPad Pro (10.5-inch)"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "12.2 (16E226)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPhone11,2",
               "identifier" : "39121409-3C4D-49D7-B984-4897889A1427",
               "architecture" : "x86_64",
               "modelName" : "iPhone Xs",
               "name" : "iPhone Xs"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "11.4 (15F79)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPad6,12",
               "identifier" : "713833D2-7E21-40B9-A45D-A45101018103",
               "architecture" : "x86_64",
               "modelName" : "iPad (5th generation)",
               "name" : "iPad (5th generation)"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "12.2 (16E226)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPhone9,2",
               "identifier" : "0053E33C-0166-4184-B01F-F9AB6AEE6FF8",
               "architecture" : "x86_64",
               "modelName" : "iPhone 7 Plus",
               "name" : "iPhone 7 Plus"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "13.3 (17C45)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPhone10,4",
               "identifier" : "987B3046-06C9-4B8D-950E-52D171BBEC89",
               "architecture" : "x86_64",
               "modelName" : "iPhone 8",
               "name" : "iPhone 8"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "12.2 (16E226)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPad8,5",
               "identifier" : "3BDBF584-B789-425C-AD8F-D91361402556",
               "architecture" : "x86_64",
               "modelName" : "iPad Pro (12.9-inch) (3rd generation)",
               "name" : "iPad Pro (12.9-inch) (3rd generation)"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "12.2 (16E226)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPhone11,2",
               "identifier" : "1531652E-F759-4D96-875B-066953FA16A8",
               "architecture" : "x86_64",
               "modelName" : "iPhone Xs",
               "name" : "iOS 12.2"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "6.1.1 (17S445)",
               "available" : true,
               "platform" : "com.apple.platform.watchsimulator",
               "modelCode" : "Watch4,4",
               "identifier" : "48D416B1-E5C1-4787-BD8D-86B0B30D2FAA",
               "architecture" : "i386",
               "modelName" : "Apple Watch Series 4 - 44mm",
               "name" : "Apple Watch Series 4 - 44mm"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "6.1.1 (17S445)",
               "available" : true,
               "platform" : "com.apple.platform.watchsimulator",
               "modelCode" : "Watch4,3",
               "identifier" : "D51C96B3-A45B-4CAF-ACAD-09ECEB38A8FF",
               "architecture" : "i386",
               "modelName" : "Apple Watch Series 4 - 40mm",
               "name" : "Apple Watch Series 4 - 40mm"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "11.4 (15F79)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPhone9,1",
               "identifier" : "F365C9AB-E43A-4A96-9C74-29A9ED60D9C3",
               "architecture" : "x86_64",
               "modelName" : "iPhone 7",
               "name" : "iPhone 7"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "12.2 (16E226)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPhone11,4",
               "identifier" : "40D4A05E-7260-4060-9C99-C880268A3521",
               "architecture" : "x86_64",
               "modelName" : "iPhone Xs Max",
               "name" : "iPhone Xs Max"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "10.3.1 (14E8301)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPad6,8",
               "identifier" : "E613BACC-90BD-4ECE-A865-5D3D89877FEE",
               "architecture" : "x86_64",
               "modelName" : "iPad Pro (12.9-inch)",
               "name" : "iPad Pro (12.9 inch)"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "10.3.1 (14E8301)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPhone5,1",
               "identifier" : "89DAC39F-0937-43E8-9A5D-9A4E937944AC",
               "architecture" : "i386",
               "modelName" : "iPhone 5",
               "name" : "iPhone 5"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "12.2 (16E226)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPad5,4",
               "identifier" : "EE86BEB1-9AF8-419C-89AB-DADA20DA6D87",
               "architecture" : "x86_64",
               "modelName" : "iPad Air 2",
               "name" : "iPad Air 2"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "11.4 (15F79)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPhone8,4",
               "identifier" : "2B178C88-6CFE-4BF3-BF1A-8810A04A3BFA",
               "architecture" : "x86_64",
               "modelName" : "iPhone SE",
               "name" : "iPhone SE"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "10.3.1 (14E8301)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPad7,1",
               "identifier" : "3FED93DC-1041-4583-BC9A-70587629B34B",
               "architecture" : "x86_64",
               "modelName" : "iPad Pro (12.9-inch) (2nd generation)",
               "name" : "iPad Pro (12.9-inch) (2nd generation)"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "12.2 (16E226)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPhone9,1",
               "identifier" : "77A8CFA1-7756-46E2-89E9-1B07E7307995",
               "architecture" : "x86_64",
               "modelName" : "iPhone 7",
               "name" : "iPhone 7"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "11.4 (15F79)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPhone7,2",
               "identifier" : "6E746F46-862C-4305-9EB9-1B1398367C6F",
               "architecture" : "x86_64",
               "modelName" : "iPhone 6",
               "name" : "iPhone 6"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "11.4 (15F79)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPad6,8",
               "identifier" : "25F1DCE2-BCC1-4A76-827E-60EB5FC41884",
               "architecture" : "x86_64",
               "modelName" : "iPad Pro (12.9-inch)",
               "name" : "iPad Pro (12.9-inch)"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "13.3 (17C45)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPhone10,5",
               "identifier" : "01BAA4D6-7DF5-45E0-A82E-A09BE8C6D68F",
               "architecture" : "x86_64",
               "modelName" : "iPhone 8 Plus",
               "name" : "iPhone 8 Plus"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "12.2 (16E226)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPad6,8",
               "identifier" : "B4428027-87B9-4EFE-B20A-B982723DCF0E",
               "architecture" : "x86_64",
               "modelName" : "iPad Pro (12.9-inch)",
               "name" : "iPad Pro (12.9-inch)"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "12.2 (16E226)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPhone11,8",
               "identifier" : "3002CB5F-B8BA-458D-9C9B-307B379A1661",
               "architecture" : "x86_64",
               "modelName" : "iPhone Xʀ",
               "name" : "iPhone Xʀ"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "11.4 (15F79)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPad5,4",
               "identifier" : "3E554154-42F1-4485-8C24-784C2C02D4E7",
               "architecture" : "x86_64",
               "modelName" : "iPad Air 2",
               "name" : "iPad Air 2"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "12.2 (16E226)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPhone7,1",
               "identifier" : "87A529EC-95ED-4257-BEE4-A15B8AAB5B93",
               "architecture" : "x86_64",
               "modelName" : "iPhone 6 Plus",
               "name" : "iPhone 6 Plus"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "10.3.1 (14E8301)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPad4,2",
               "identifier" : "8CD29A53-A3D0-444F-AE06-0104E8C51158",
               "architecture" : "x86_64",
               "modelName" : "iPad Air",
               "name" : "iPad Air"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "11.4 (15F79)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPad7,3",
               "identifier" : "19046682-9059-48FD-B64C-F9A1DE0A2167",
               "architecture" : "x86_64",
               "modelName" : "iPad Pro (10.5-inch)",
               "name" : "iPad Pro (10.5-inch)"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "12.2 (16E226)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPhone6,1",
               "identifier" : "21D43298-0BA7-4B9E-8B31-44F5E7ED29FD",
               "architecture" : "x86_64",
               "modelName" : "iPhone 5s",
               "name" : "iPhone 5s"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "11.4 (15F79)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPad7,1",
               "identifier" : "CE8EC6F9-A59C-4499-B801-6F6D060EC00F",
               "architecture" : "x86_64",
               "modelName" : "iPad Pro (12.9-inch) (2nd generation)",
               "name" : "iPad Pro (12.9-inch) (2nd generation)"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "10.3.1 (14E8301)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPhone7,2",
               "identifier" : "F0EB9EE4-A2A5-4B20-BA47-37749E8DBF18",
               "architecture" : "x86_64",
               "modelName" : "iPhone 6",
               "name" : "iPhone 6"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "10.3.1 (14E8301)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPhone9,2",
               "identifier" : "3C1E06C5-48FA-46D5-A579-9EE08D34DDC7",
               "architecture" : "x86_64",
               "modelName" : "iPhone 7 Plus",
               "name" : "iPhone 7 Plus"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "6.1.1 (17S445)",
               "available" : true,
               "platform" : "com.apple.platform.watchsimulator",
               "modelCode" : "Watch5,4",
               "identifier" : "46953ACF-9EB6-43DE-9BEA-03B5A830E760",
               "architecture" : "i386",
               "modelName" : "Apple Watch Series 5 - 44mm",
               "name" : "Apple Watch Series 5 - 44mm"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "11.4 (15F79)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPad4,2",
               "identifier" : "E0C21DD0-03C4-4AC9-8381-0F6E4E25A8EA",
               "architecture" : "x86_64",
               "modelName" : "iPad Air",
               "name" : "iPad Air"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "11.4 (15F79)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPhone10,4",
               "identifier" : "5C78B59E-4FF9-4FB8-847F-26602929241B",
               "architecture" : "x86_64",
               "modelName" : "iPhone 8",
               "name" : "iPhone 8"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "12.2 (16E226)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPad6,4",
               "identifier" : "C01E19CC-CDFE-48C7-BD85-6ABFCF335A7B",
               "architecture" : "x86_64",
               "modelName" : "iPad Pro (9.7-inch)",
               "name" : "iPad Pro (9.7-inch)"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "13.3 (17C45)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPad8,1",
               "identifier" : "435730F8-4FFF-4EAA-AE88-CE4A5EC62C6D",
               "architecture" : "x86_64",
               "modelName" : "iPad Pro (11-inch)",
               "name" : "iPad Pro (11-inch)"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "13.3 (17C45)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPad11,3",
               "identifier" : "69F9DD68-6E97-4674-A0D9-1F3898522D74",
               "architecture" : "x86_64",
               "modelName" : "iPad Air (3rd generation)",
               "name" : "iPad Air (3rd generation)"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "13.3 (17K446)",
               "available" : true,
               "platform" : "com.apple.platform.appletvsimulator",
               "modelCode" : "AppleTV6,2",
               "identifier" : "D6D5A698-5B46-42D0-848A-D5E6C3CFD6F4",
               "architecture" : "x86_64",
               "modelName" : "Apple TV 4K (at 1080p)",
               "name" : "Apple TV 4K (at 1080p)"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "11.4 (15F79)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPhone8,2",
               "identifier" : "CF7AF07F-60AA-42A3-ABB7-7D3F588906AA",
               "architecture" : "x86_64",
               "modelName" : "iPhone 6s Plus",
               "name" : "iPhone 6s Plus"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "13.3 (17C45)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPad6,4",
               "identifier" : "6458EB7D-CD15-4ED9-81AA-24E743C85C44",
               "architecture" : "x86_64",
               "modelName" : "iPad Pro (9.7-inch)",
               "name" : "iPad Pro (9.7-inch)"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "10.3.1 (14E8301)",
               "available" : true,
               "platform" : "com.apple.platform.iphonesimulator",
               "modelCode" : "iPhone8,4",
               "identifier" : "BA119C4A-78CE-495A-8257-F3DC708FF3D1",
               "architecture" : "x86_64",
               "modelName" : "iPhone SE",
               "name" : "iPhone SE"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "6.1.1 (17S445)",
               "available" : true,
               "platform" : "com.apple.platform.watchsimulator",
               "modelCode" : "Watch5,3",
               "identifier" : "687788ED-63D5-45A9-87E3-CFEF80612BE8",
               "architecture" : "i386",
               "modelName" : "Apple Watch Series 5 - 40mm",
               "name" : "Apple Watch Series 5 - 40mm"
             },
             {
               "simulator" : true,
               "operatingSystemVersion" : "13.3 (17K446)",
               "available" : true,
               "platform" : "com.apple.platform.appletvsimulator",
               "modelCode" : "AppleTV5,3",
               "identifier" : "73AC9C25-5EDB-4F70-A8EC-CD35DCDEDA66",
               "architecture" : "x86_64",
               "modelName" : "Apple TV",
               "name" : "Apple TV"
             }
           ]
[  +17 ms] /usr/bin/xcrun simctl list --json devices
[ +105 ms] Artifact Instance of 'AndroidMavenArtifacts' is not required, skipping update.
[        ] Artifact Instance of 'AndroidGenSnapshotArtifacts' is not required, skipping update.
[        ] Artifact Instance of 'AndroidInternalBuildArtifacts' is not required, skipping update.
[        ] Artifact Instance of 'IOSEngineArtifacts' is not required, skipping update.
[   +1 ms] Artifact Instance of 'WindowsEngineArtifacts' is not required, skipping update.
[        ] Artifact Instance of 'MacOSEngineArtifacts' is not required, skipping update.
[        ] Artifact Instance of 'LinuxEngineArtifacts' is not required, skipping update.
[        ] Artifact Instance of 'LinuxFuchsiaSDKArtifacts' is not required, skipping update.
[        ] Artifact Instance of 'MacOSFuchsiaSDKArtifacts' is not required, skipping update.
[        ] Artifact Instance of 'FlutterRunnerSDKArtifacts' is not required, skipping update.
[        ] Artifact Instance of 'FlutterRunnerDebugSymbols' is not required, skipping update.
[  +55 ms] Found plugin firebase_core at /Users/morphingcoffee/Applications/flutter/.pub-cache/hosted/pub.dartlang.org/firebase_core-0.4.3+3/
[   +5 ms] Found plugin firebase_core_web at /Users/morphingcoffee/Applications/flutter/.pub-cache/hosted/pub.dartlang.org/firebase_core_web-0.1.1+2/
[   +1 ms] Found plugin firebase_storage at /Users/morphingcoffee/Applications/flutter/.pub-cache/hosted/pub.dartlang.org/firebase_storage-3.1.1/
[  +41 ms] Found plugin firebase_core at /Users/morphingcoffee/Applications/flutter/.pub-cache/hosted/pub.dartlang.org/firebase_core-0.4.3+3/
[   +1 ms] Found plugin firebase_core_web at /Users/morphingcoffee/Applications/flutter/.pub-cache/hosted/pub.dartlang.org/firebase_core_web-0.1.1+2/
[        ] Found plugin firebase_storage at /Users/morphingcoffee/Applications/flutter/.pub-cache/hosted/pub.dartlang.org/firebase_storage-3.1.1/
[  +83 ms] Launching lib/main.dart on Chrome in debug mode...
[        ] Building application for the web...
[  +78 ms] Found plugin firebase_core at /Users/morphingcoffee/Applications/flutter/.pub-cache/hosted/pub.dartlang.org/firebase_core-0.4.3+3/
[   +1 ms] Found plugin firebase_core_web at /Users/morphingcoffee/Applications/flutter/.pub-cache/hosted/pub.dartlang.org/firebase_core_web-0.1.1+2/
[        ] Found plugin firebase_storage at /Users/morphingcoffee/Applications/flutter/.pub-cache/hosted/pub.dartlang.org/firebase_storage-3.1.1/
[+5104 ms] Starting daemon...
[ +118 ms] Initializing inputs
[   +9 ms] Reading cached asset graph...
[ +138 ms] Reading cached asset graph completed, took 135ms

[ +231 ms] Checking for updates since last build...
[ +451 ms] Checking for updates since last build completed, took 451ms

[  +10 ms] Initializing inputs
[   +2 ms] Reading cached asset graph...
[        ] Reading cached asset graph completed, took 135ms
[        ] Checking for updates since last build...
[        ] Checking for updates since last build completed, took 451ms
[ +694 ms] About to build [web]...
[   +3 ms] Running build...
[ +148 ms] Running build completed, took 83ms

[        ] Caching finalized dependency graph...
[   +5 ms] Caching finalized dependency graph completed, took 87ms

[   +3 ms] Succeeded after 177ms with 0 outputs (0 actions)

[   +8 ms] Building application for the web... (completed in 7.0s)
[        ] Attempting to connect to browser instance..
[+2794 ms] Debug service listening on ws://127.0.0.1:53267/hD9xlFL0yLk=

[ +269 ms]       Failed to load asset at path: packages/build_web_compilers/src/dev_compiler/dart_sdk.js.

                 Status code: 404

                 Headers:
                 {
             "date": "Mon, 10 Feb 2020 21:01:11 GMT",
             "content-length": "9",
             "x-frame-options": "SAMEORIGIN",
             "content-type": "text/plain; charset=utf-8",
             "x-xss-protection": "1; mode=block",
             "x-content-type-options": "nosniff",
             "server": "dart:io with Shelf",
             "via": "1.1 shelf_proxy"
           }

                 Content:
                 Not Found}

[  +21 ms] Attempting to connect to browser instance.. (completed in 3.1s)
[   +1 ms] Warning: Flutter's support for web development is not stable yet and hasn't
[        ] been thoroughly tested in production environments.
[        ] For more information see https://flutter.dev/web
[        ] 🔥  To hot restart changes while running, press "r". To hot restart (and refresh the browser), press "R".
[        ] For a more detailed help message, press "h". To quit, press "q".
[   +8 ms] Debug service listening on ws://127.0.0.1:53267/hD9xlFL0yLk=
[+14666 ms] Stopped debug service on ws://127.0.0.1:53267

[  +20 ms] Application finished.

```