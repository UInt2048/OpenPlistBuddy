This is a modification of Darling's implementation of PlistBuddy to run on iOS.

The Objective-C source can be compiled with:

    xcrun --sdk iphoneos clang -arch arm64 PlistBuddy.m -framework Foundation -framework CoreFoundation -o PlistBuddy

You can also just download the provided DEB directly.

You should use the arm64 DEB unless you know your device has armv7 architecture.
