## PixelOS 17.0

## Sync
```
repo init -u https://github.com/PixelOS-AOSP/android_manifest.git -b seventeen --git-lfs
repo sync
```

## Trees
```
rm -rf device/samsung/r8q/
git clone https://github.com/not-samsung-sm8250/device_samsung_r8q -b seventeen device/samsung/r8q/
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
source build/envsetup.sh
breakfast r8q
m pixelos
```
