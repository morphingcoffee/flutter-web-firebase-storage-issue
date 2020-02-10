## Setup
(Optional) Add your firebase project details to web/index.html  
flutter channel master  
flutter upgrade  
flutter config --enable-web    
flutter run chrome  


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