# android_device_xiaomi_raphael
Modified TWRP for raphael
## Features

- Windows mount support
- Custom scripts for partitioning, formatting etc.


TO-DO:

- finish

## Compile

First checkout minimal twrp with omnirom tree:

```
repo init -u git://github.com/minimal-manifest-twrp/platform_manifest_twrp_omni.git -b twrp-9.0
repo sync
```

Then add these projects to .repo/manifest.xml:

```xml
<project path="device/xiaomi/raphael" name="mauronofrio/android_device_xiaomi_raphael" remote="github" revision="android-9.0" />
```

Finally execute these:

```
. build/envsetup.sh
lunch omni_raphael-eng
mka recoveryimage ALLOW_MISSING_DEPENDENCIES=true # Only if you use minimal twrp tree.
```

To test it:

```
fastboot boot out/target/product/raphael/recovery.img
```

## Other Sources

Kernel Sources: https://github.com/acervenky/raphaelquax

## Thanks

- Thanks to @PeterCxy for the commits and the base: https://github.com/PeterCxy/android_device_xiaomi_violet-twrp
