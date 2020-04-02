# local_manifests
LineageOS 15.1 f. amami, gts210vewifi and oneplus3 - hardened microG build

## How launch a lineage-15.1 build (treble build variant):
Make sure you have checked out the 'lin-15.1-treble' branch in the local_manifests repo and synched
```Shell session
make clean
repo sync --no-tags
source build/envsetup.sh
cd z_patches
./patches_apply.sh
cd ..
export KBUILD_BUILD_USER=android
export KBUILD_BUILD_HOST=localhost
export RELEASE_TYPE=UNOFFICIAL-microG
lunch treble_arm64_avN-userdebug
make WITHOUT_CHECK_API=true systemimage
```

Note: If the build fails with an assertion in loadlocale.c, it is likely [this problem](https://groups.google.com/forum/#!topic/android-building/0kzPnw3akxg). Work around it with `export LC_ALL=C` or `unset LANG` before running `lunch`.

## How to initially set up your build tree:
```Shell session
repo init -u https://github.com/LineageOS/android.git -b lineage-15.1 --groups=all,-notdefault,-darwin,-x86,-mips
cd .repo
git clone https://github.com/lin15-microG/local_manifests 
cd local_manifests 
git checkout lin-15.1-treble
cd ../.. 
repo sync --no-tags
```
Note: If you use a MAC to build, omit the `-darwin` in above `repo init` statement.
