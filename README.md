# DroidScript Java Compiler

Runtime Java build plugin for DroidScript.

> [!NOTE]
> Minimum required android version: 8 (SDK 26).

## How to Use

After installing the plugin, the example in the Documentation can be used to get started.

## Build

Open and compile the project with [AndroidIDE](https://github.com/AndroidIDEOfficial or Android Studio.

### Install with Shell Commands

It can be imported into DroidScript using this example:

```sh
cd app/build/outputs/apk/debug
rm -r temp
unzip app-debug.apk -d temp
cd temp
zip JavaCompiler.jar classes*.dex
rm classes.dex
cp -r assets/* .
cp -r lib/* .
rm -r lib
rm -r assets
rm -r res
rm AndroidManifest.xml
rm resources.arsc
rm -r META-INF
zip -r ../JavaCompiler.ppk *

cd ..
export PATH=$PATH:~/Library/Android/sdk/platform-tools/
adb push JavaCompiler.ppk /sdcard/Android/data/com.smartphoneremote.androidscriptfree/files/DroidScript/Plugins/JavaCompiler.ppk
```

### Install Manually

* Unzip the APK as zip.
* Add `classes.dex` files to a zip file with the name `JavaCompiler.jar`.
* Then add the `JavaCompiler.jar` file along with the contents of the `assets` folder to a zip file named `JavaCompiler.ppk`.
* Open `JavaCompiler.ppk` with DroidScript.

The `JavaCompiler.ppk` file should look like this:
```
JavaCompiler.ppk/
    - JavaCompiler.jar
    - JavaCompiler.html
    - JavaCompiler.inc
    - android.jar
```

