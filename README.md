# device_realme_r5x_recovery
For building TWRP for Realme 5 Series

Recovery device tree for Realme 5/5i/5s/5NFC

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
- Vibration support
- External sdcard
- Support Both retrofit dynamic and static partition

## Compile

First checkout minimal twrp manifest tree:

```
repo init -u https://github.com/minimal-manifest-twrp/platform_manifest_twrp_aosp.git -b twrp-12.1
repo sync
```

Then add these projects to .repo/manifest.xml:

```xml
<project path="device/realme/r5x" name="Amritorock/device_realme_r5x_recovery" remote="github" revision="android-13" />
```

Finally execute these:

```
. build/envsetup.sh
lunch twrp_r5x-eng
mka recoveryimage
```

To test it:

```
fastboot flash recovery out/target/product/r5x/recovery.img
```

Then reboot to recovery

## Other Sources

Using precompiled kernel

## Thanks

