# Clang Complete 

This *was* a fork of [RipRip/clang_complete](https://github.com/Rip-Rip/clang_complete), tailored for
iOS/Objective-C development. That project now works well with Objective-C, so
the only thing left is to figure out how to get it set up.

I'd recommend you clone from there instead, and take note of the following
instructions for getting your iOS project set up correctly:

## iOS Integration.

To get clang_complete working with iOS projects, you need a `.clang_complete`
file in the root of your project. Here's a breakdown of what needs to go in that
file:

### iOS Library Paths

    -isysroot /Applications/Xcode.app/Contents/Developer/Platforms/iPhoneOS.platform/Developer/SDKs/iPhoneOS5.1.sdk
    -include /Applications/Xcode.app/Contents/Developer/Platforms/iPhoneOS.platform/Developer/SDKs/iPhoneOS5.1.sdk/usr/include/TargetConditionals.h

Obviously, this is for iOS5.1. Update these paths as new versions of the iOS
software/XCode become available.

### PCH File

Include the path to your .pch file, if you have one:

    -include MyProject/MyProject-Prefix.pch

### Extra Paths

Include any directories you've added to *Header Search Paths* in Xcode:

    -I../core-plot/build/Debug-iphoneos/include/CorePlot-CocoaTouch
    -IBugSense-iOS.framework/Versions/A/Headers

## Vim Setup

Consider adding these settings to a `~/.vim/ftplugin/objc.vim` file:

```vim
let g:clang_use_library=1
let g:clang_periodic_quickfix=1
```
