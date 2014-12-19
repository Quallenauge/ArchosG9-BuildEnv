ArchosG9-BuildEnv
=================

Build Environment for Archos G9 devices

To build do the following steps:

Use base tar image from this post:
http://forum.xda-developers.com/showpost.php?p=37634328&postcount=104  
https://mega.co.nz/#!OYNCTKAJ!y9pQ9suEHhXPUXjwUVgMFSVhmgXzxdu5tPCl1uxumIE
and place it into this folder.

```bash
mkdir archos_image
Download or create a archos.ext4.update file and place it into this folder.
```
# Init the CM repository
```bash
repo init -u git://github.com/CyanogenMod/android.git -b cm-12.0
ln -s local_manifest.xml .repo/local_manifests/local_manifest.xml

# Sync the repository and create changelog
./buildImage sync
```
# Init the android injection repository
```bash
git clone git@github.com:Quallenauge/android_injection.git -b cm-12.0
```

# Build cyanogenmod
```bash
# (Re-)build cyanogenmod
./buildImage make 2>&1 | tee build.log

# Remove cm12.0/out/target folder and build cyanogenmod
./buildImage makeFull 2>&1 | tee build.log
```

# Finish image
```bash
./buildImage buildImage
```

# Some goodies
```bash
# Perform repo command
./buildImage repo <command>

# Clean up the cyanogenmod folder by using git reset/git clean commands
./buildImage reset


```
