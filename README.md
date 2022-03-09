## Custom Mi Note 3 kernel


**steps:**

```sh
git clone -b ndk-r19 https://android.googlesource.com/platform/prebuilts/gcc/linux-x86/aarch64/aarch64-linux-android-4.9 toolchain
mkdir -p out
export ARCH=arm64
export SUBARCH=arm64
export CROSS_COMPILE=${PWD}/toolchain/bin/aarch64-linux-android-
make O=out jason_user_defconfig
make -j$(nproc) O=out 2>&1 | tee kernel.log
```


Ref:

- https://github.com/0fengzi0/Blog/issues/18
- https://github.com/MiCode/Xiaomi_Kernel_OpenSource/issues/957
