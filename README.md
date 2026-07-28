## LineageOS 24.0 Ext 

## Sync
```
repo init --depth=1 --no-repo-verify -u https://github.com/Los-Ext/android_manifest.git -b 17 --git-lfs -g default,-mips,-darwin,-notdefault
repo sync -c -j24 --force-sync --no-clone-bundle --no-tags --optimized-fetch --prune
```

## Trees
```
rm -rf device/samsung/r8q/
git clone https://github.com/not-samsung-sm8250/device_samsung_r8q -b lineage-24.0 device/samsung/r8q/
rm -rf device/samsung/sm8250-common/
git clone https://github.com/not-samsung-sm8250/device_samsung_sm8250-common -b seventeen device/samsung/sm8250-common/
rm -rf vendor/samsung/r8q/
git clone https://github.com/not-samsung-sm8250/vendor_samsung_r8q/ --depth=1 -b seventeen vendor/samsung/r8q/
rm -rf vendor/samsung/sm8250-common/
git clone https://github.com/not-samsung-sm8250/vendor_samsung_sm8250-common --depth=1 -b seventeen vendor/samsung/sm8250-common/
rm -rf kernel/samsung/sm8250/
git clone https://github.com/not-samsung-sm8250/kernel_samsung_sm8250 --depth=1 -b seventeen kernel/samsung/sm8250/
rm -rf hardware/samsung/
git clone https://github.com/not-samsung-sm8250/hardware_samsung -b seventeen hardware/samsung/
rm -rf hardware/samsung/nfc/
git clone https://github.com/not-samsung-sm8250/hardware_samsung_nfc/ -b seventeen hardware/samsung/nfc/
rm -rf hardware/samsung_slsi/nfc/
git clone https://github.com/not-samsung-sm8250/hardware_samsung_slsi_nfc -b seventeen hardware/samsung_slsi/nfc/
rm -rf hardware/qcom-caf/sm8250/display/
git clone https://github.com/not-samsung-sm8250/hardware_qcom-caf_display_sm8250 -b seventeen hardware/qcom-caf/sm8250/display
```


## Build
```
. build/envsetup.sh
lunch lineage_r8q-cp2a-user
m bacon
```

## Settings app workaround
```
rm -rf packages/apps/Settings
git clone https://github.com/LineageOS/android_packages_apps_Settings packages/apps/Settings --depth=2
cd packages/apps/Settings
git fetch https://github.com/LineageOS/android_packages_apps_Settings refs/changes/35/491435/1  --depth=2 && git reset --hard FETCH_HEAD
cd
git clone https://github.com/Los-Ext/android_packages_apps_Settings_ext packages/apps/Settings/ext
```
