# android_device_xiaomi_willow
For building TWRP for Xiaomi Redmi Note 8T

TWRP device tree for Xiaomi Redmi Note 8T

## Features

Works:

- ADB
- Decryption of /data
- Screen brightness settings
- Correct screenshot color
- MTP
- Flashing (opengapps, roms, images and so on)
- Backup/Restore (Needs more testing)
- USB OTG

TO-DO:

- Vibration support

## Compile

First checkout minimal twrp with omnirom tree:

```
repo init -u git://github.com/minimal-manifest-twrp/platform_manifest_twrp_omni.git -b twrp-9.0
repo sync
```

Then add these projects to .repo/manifest.xml:

```xml
<project path="device/xiaomi/willow" name="nLov78/android_device_xiaomi_willow" remote="github" revision="android-9.0" />
```

Finally execute these:

```
. build/envsetup.sh
lunch omni_willow-eng
mka recoveryimage ALLOW_MISSING_DEPENDENCIES=true # Only if you use minimal twrp tree.
```

To test it:

```
fastboot boot out/target/product/willow/recovery.img
```

## Other Sources

Using precompiled stock kernel.

## Thanks

- Thanks to @PeterCxy for the commits and the base: https://github.com/PeterCxy/android_device_xiaomi_violet-twrp
