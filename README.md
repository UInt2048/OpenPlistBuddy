This is a modification of Darling's implementation of PlistBuddy to run on iOS.

The Objective-C source can be compiled as follows:

For arm64 devices (iPhone 5S and newer):

```
xcrun --sdk iphoneos clang PlistBuddy.m -framework CoreFoundation -framework Foundation -o _plist64/usr/libexec/PlistBuddy -arch arm64
```

For armv7 devices:

```
xcrun --sdk iphoneos clang PlistBuddy.m -framework CoreFoundation -framework Foundation -o _plistv7/usr/libexec/PlistBuddy -arch armv7
```

Then compile the DEB:

1. `find . -name ".DS_Store" -delete`
2. `ldid -S _plist64/usr/libexec/PlistBuddy`
3. `dpkg-deb -Zgzip --build _plist64`

You can also just download the provided DEB from the releases.
