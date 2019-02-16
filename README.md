# local_manifests
LineageOS 15.1 f. amami, gts210vewifi and oneplus3

## How launch a lineage-15.1 build:
```Shell session
make clean
repo sync --no-tags
source build/envsetup.sh
brunch $device
```
where ***$device*** is either **amami**, **gts210vewifi** or **oneplus3**.

## How to initially set up your build tree:
```Shell session
repo init -u https://github.com/LineageOS/android.git -b lineage-15.1 --groups=all,-notdefault,-darwin,-x86,-mips
cd .repo
git clone https://github.com/lin15-microG/local_manifests 
cd local_manifests 
git checkout lineage-15.1
cd ../.. 
repo sync --no-tags
```
Note: If you use a MAC to build, omit the `-darwin` in above `repo init` statement.

## Trouble shooting
We have an own [thread on XDA](https://forum.xda-developers.com/sony-xperia-z1-compact/development/rom-lineageos-15-1-xperia-z1-compact-t3884247) for the amami device - you should find solutions to your issues there or you are welcome to post new ones...
