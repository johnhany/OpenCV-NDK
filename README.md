# OpenCV-NDK

A Color-to-grayscale Android app configured with CMake tool under Android Studio with OpenCV support.

## Requirements

* Android Studio 2.3.3

  Gradle version 3.3, Gradle Android Plugin 2.3.3

* Android NDK r15b

* JDK 8u141

* Android 7.0 (API Level 24)

* OpenCV 3.2 Android SDK

  Only native sdk is utilized. No OpenCV Java API is required.

## Configuring

### Method 1

1. Change Line #22 in `app\build.gradle` and Line #14 in `app\CMakeLists.txt` to your`<OpenCV Android SDK>/sdk/native/libs`.
2. Change Line #16 in  `app\CMakeLists.txt` to your `<OpenCV Android SDK>/sdk/native/jni/include`.
3. Re-sync and run.

### Method 2

1. Change Line #22 in `app\build.gradle` to `jniLibs.srcDirs = ['src/main/jniLibs']`. Change Line #14 in `app\CMakeLists.txt` to `set(ocvlibs "${CMAKE_SOURCE_DIR}/src/main/jniLibs")`. Copy all files in `<OpenCV Android SDK>/sdk/native/libs` to `app\src\main\jniLibs`.
2. Change Line #16 in `app\CMakeLists.txt` to `include_directories(${CMAKE_SOURCE_DIR}/src/main/cpp/include)`. Copy all files in `<OpenCV Android SDK>/sdk/native/jni/include` to `app\src\main\cpp\include`.
3. Re-sync and run.

### Method 3

1. Change Line #22 in `app\build.gradle` to `jniLibs.srcDirs = ['src/main/jniLibs']`. Change Line #14 in `app\CMakeLists.txt` to `set(ocvlibs "${CMAKE_SOURCE_DIR}/src/main/jniLibs")`. Create symlink `app\src\main\jniLibs` targeting `<OpenCV Android SDK>/sdk/native/libs`.
2. Change Line #16 in `app\CMakeLists.txt` to `include_directories(${CMAKE_SOURCE_DIR}/src/main/cpp/include)`. Create symlink `app\src\main\cpp\include` targeting `<OpenCV Android SDK>/sdk/native/jni/include`.
3. Re-sync and run.

### More details

如果您懂中文，欢迎来阅读我的文章[《Android Studio 2.3利用CMAKE进行OpenCV 3.2的NDK开发》](http://johnhany.net/2017/07/opencv-ndk-dev-with-cmake-on-android-studio)。

## License

This OpenCV-NDK project is released under the MIT license.