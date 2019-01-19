# local_manifests
LineageOS 15.1 f. amami and oneplus3 - hardened micgoG build

## How launch a lineage-15.1 build:
Make sure you have checked out the 'lin-15.1-microG' branch in the local_manifests repo and synched
```Shell session
make clean
repo sync --no-tags
source build/envsetup.sh
brunch $device
```
where ***$device*** is either **amami** or **oneplus3**.

## How to initially set up your build tree:
```Shell session
repo init -u https://github.com/LineageOS/android.git -b lineage-15.1 --groups=all,-notdefault,-darwin,-x86,-mips
cd .repo
git clone https://github.com/lin15-microG/local_manifests 
cd local_manifests 
git checkout lin-15.1-microG
cd ../.. 
repo sync --no-tags
```
Note: If you use a MAC to build, omit the `-darwin` in above `repo init` statement.
