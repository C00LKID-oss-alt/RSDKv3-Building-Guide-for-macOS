# RSDKv3-Building-Guide-for-macOS
This is a guide on how to build RSDKv3 on **macOS** since I can't find any videos or tutorial except for the RSDKv3-Decompilation repo but this tutorial will be much more easier for people to understand. I compiled it myself on macOS 27.3 Apple Silicon and can work for other Macs.

## Prerequisites
**Xcode**: [Download](https://apps.apple.com/fr/app/xcode/id497799835?mt=12) it, and don't open it yet, we will need it for later.

**Command Line Tools**: Open Terminal, copy and paste this: `xcode-select --install`.

## Cloning the repository
Open Terminal, copy and paste this in Terminal: `git clone --recursive https://github.com/RSDKModding/RSDKv3-Decompilation`.

But if you already cloned the repo before and it's not deleted then copy and paste this in the repo: `git submodule update --init --recursive`.

## Getting the dependencies
**SDL2**: [Download](https://github.com/libsdl-org/SDL/releases/tag/release-2.32.10) it as a **.dmg** file. Then open the .dmg file and move the SDL2.framework to `[root of repo]/dependencies/mac/`.

**libogg**: [Download](https://xiph.org/downloads/) and extract it as `[root of repo]/dependencies/mac/libogg`. Then go inside the folder and run the "configure" file by simply double-clicking on it.

**libvorbis**: [Download](https://xiph.org/downloads/) and extract it as `[root of repo]/dependencies/mac/libvorbis`.

**libtheora**: [Download](https://github.com/xiph/theora/releases/tag/v1.1.0) the .zip file and extract it as `[root of repo]/dependencies/mac/libtheora`.

## Compiling the game
### Xcode:
Once you've followed the instructions above, open Xcode, and select the RSDKv3 target. Then, **change the deployment target to the recommended OS version** and build the project by pressing the "Run" button or (⌘+B). The app will then be created in `~/Library/Developer/Xcode/DerivedData/RSDKv3-[and a whole bunch of letters]/Build/Products/Release/RSDKv3.app`. **Press (⌘+⇧+.) to see the `~/Library` folder.**

### Command Line Tools:
If you want to use the **Command Line Tools** instead, run the following command: `xcodebuild -project RSDKv3.xcodeproj -scheme RSDKv3 DSTROOT="./build" -configuration Release DEPLOYMENT_LOCATION=YES`. The app will then be created in `~/RSDKv3-Decompilation/build/Applications/RSDKv3.app`.

### Build flags for the Command Line Tools
To add flags into your build command, use: `OTHER_CFLAGS=` at the end of your build command, for example: `xcodebuild -project RSDKv3.xcodeproj -scheme RSDKv3 DSTROOT="./build" -configuration Release DEPLOYMENT_LOCATION=YES OTHER_CFLAGS="-DRETRO_DEV_EXTRA=\\\"Darwin\\ -\\ AppleClang\\\""`.

**A list of build flags can be found [here](https://github.com/RSDKModding/RSDKv3-Decompilation/blob/master/dependencies/mac/README.md#customization).**

 







