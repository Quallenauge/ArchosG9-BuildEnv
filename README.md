ArchosG9-BuildEnv
=================

Build Environment for Archos G9 devices

To build do the following steps:

Use base tar image from this post:
http://forum.xda-developers.com/showpost.php?p=37634328&postcount=104
and place it into this folder.

```bash
mkdir archos_image
Download or create a archos.ext4.update file and place it into this folder.
```
# Init the CM10.1 repository
```bash
repo init -u git://github.com/CyanogenMod/android.git -b cm10.1
ln -s local_manifest.xml .repo/local_manifest.xml
repo sync
```

# Build cyanogenmod
```bash
cd cm10.1
 . build/envsetup.sh
brunch archos_g9
```

# Finish image
```bash
cd ..
./buildImage
```
