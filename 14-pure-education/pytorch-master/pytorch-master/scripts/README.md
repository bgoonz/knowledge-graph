# README

This directory contains the useful tools.

## build\_android.sh

This script is to build PyTorch/Caffe2 library for Android. Take the following steps to start the build:

* set ANDROID\_NDK to the location of ndk

```bash
export ANDROID_NDK=YOUR_NDK_PATH
```

* run build\_android.sh

  ```bash
  #in your PyTorch root directory
  bash scripts/build_android.sh
  ```

  If succeeded, the libraries and headers would be generated to build\_android/install directory. You can then copy these files from build\_android/install to your Android project for further usage.

You can also override the cmake flags via command line, e.g., following command will also compile the executable binary files:

```bash
bash scripts/build_android.sh -DBUILD_BINARY=ON
```

## build\_ios.sh

This script is to build PyTorch/Caffe2 library for iOS, and can only be performed on macOS. Take the following steps to start the build:

* Install Xcode from App Store, and configure "Command Line Tools" properly on Xcode.
* Install the dependencies:

```bash
brew install cmake automake libtool
```

* run build\_ios.sh

  ```bash
  #in your PyTorch root directory
  bash scripts/build_ios.sh
  ```

  If succeeded, the libraries and headers would be generated to build\_ios/install directory. You can then copy these files  to your Xcode project for further usage.

