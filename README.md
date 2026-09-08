# BlazeAOSP

<p align="center">
<img src="https://raw.githubusercontent.com/ProjectBlaze-Staging/android_vendor_blaze/17.0/overlay/common/frameworks/base/core/res/res/drawable-nodpi/default_wallpaper.png" alt="BlazeAOSP" width="600" />
</p>

### Getting Started

To get started with the BlazeAOSP sources, you'll need to get familiar with [Git and Repo](https://source.android.com/setup/build/downloading).

#### Initialize the repository:

```bash
repo init -u https://github.com/ProjectBlaze-Staging/BlazeAOSP.git -b 17.0 --git-lfs
```

#### Sync the source code:

```bash
repo sync -c --no-clone-bundle --no-tags --optimized-fetch --prune --force-sync -j$(nproc --all)
```

---

### Building the System

From the root of your source tree, run the following commands to initialize the environment:

```bash
source build/envsetup.sh
```

Choose your target device:

```bash
lunch lineage_<device_codename>-ap4a-userdebug
```

Start compilation:

```bash
m bacon -j$(nproc --all)
```

---

### Credits & Acknowledgments

* [**Google / AOSP**](https://android.googlesource.com)
* [**LineageOS**](https://github.com/LineageOS)
* [**Evolution X**](https://github.com/Evolution-X)
* [**Project Blaze Team**](https://github.com/ProjectBlaze-Staging)
