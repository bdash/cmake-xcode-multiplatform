# Demonstration of CMake bug

Steps to reproduce:

1. `cmake -G Xcode .`
2. `xcodebuild -sdk iphonesimulator`

The build will fail with an error like so:

```
clang: error: no such file or directory: 'cmake-xcode-multiplatform/Debug/liblibrary.a'
```

Note that the path in the error message references a `Debug/` directory, when `liblibrary.a` is
built into `Debug-iphonesimulator/`.
