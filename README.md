# BlazeAOSP (Android 17 / 17.0)

<p align="center">
  <img src="https://raw.githubusercontent.com/ProjectBlaze-Staging/android_vendor_blaze/17.0/overlay/common/frameworks/base/core/res/res/drawable-nodpi/default_wallpaper.png" alt="BlazeAOSP Banner" width="700" />
</p>

<p align="center">
  <b>A performant, clean, and highly customizable Android Open Source Project distribution based on Android 17 (Lineage-24.0 base).</b>
</p>

---

## 🌟 Key Features (Özellikler)

BlazeAOSP combines pure AOSP stability with essential power-user customizations and performance optimizations:

* **🏠 BlazeHouse Engine**: Dedicated customization dashboard seamlessly integrated into System Settings (`Settings.BlazeHouseActivity`).
* **🔒 Native App Lock (Uygulama Kilidi)**: Built-in system-wide biometric and PIN protection for installed applications.
* **🔋 Smart Charging (Akıllı Şarj Kontrolü)**: Advanced battery health protection with customizable charge cut-off thresholds (`charging_control_charging_limit`).
* **🎮 Game Space Engine**: Performance tuning mode, notification suppression, touch responsiveness tweaks, and GPU booster.
* **🌐 Web & System Stability**: Native integration with `com.android.webview` preventing browser crashes out-of-the-box.
* **🎨 UI & Customizations**: Status bar clock positions, network traffic indicators, custom quick-settings tiles, custom wallpapers, and custom boot animation.

---

## 📱 Device Compatibility & Partition Support (Cihaz Uyumluluğu)

BlazeAOSP is designed to run on a wide variety of Android devices supporting Android 17 (Lineage-24.0 base).

### Partition Layouts (A/B vs A-Only)
* **Virtual A/B (VABC)**: Full native support for Android Virtual A/B with Compression for seamless background OTA updates without extra storage consumption.
* **Retrofit A/B**: Compatible with legacy devices retrofitted for A/B partitioning.
* **A-Only Devices**: Fully supported via traditional single-partition device tree flags.
* **Dynamic Partitions**: Native support for `system`, `system_ext`, `product`, `vendor`, and `odm` dynamic partitions.

### Hardware & Architecture
* **Architectures**: `arm64-v8a` (Primary target), `arm32` (Compatibility mode), `x86_64` (Emulator & Development).
* **Project Treble & GSI**: Fully Treble-compliant. Can be built as a Generic System Image (GSI) for Treble-supported smartphones.
* **Device Trees**: Works seamlessly with any standard AOSP / LineageOS device tree (`device/<vendor>/<codename>`).

---

## 💻 Hardware & Build Requirements (Sistem Gereksinimleri)

To build BlazeAOSP from source, your workstation should meet the following minimum specs:

| Component | Minimum Requirement | Recommended |
| :--- | :--- | :--- |
| **OS** | Linux (Ubuntu 22.04 LTS / 24.04, Debian 12, Arch) | Ubuntu 24.04 LTS 64-bit |
| **CPU** | 8 Cores / 16 Threads | 16+ Cores (AMD Ryzen / Intel Core i7/i9) |
| **RAM** | 16 GB (+ 16 GB Swap) | 32 GB – 64 GB RAM |
| **Storage** | 300 GB Free Space | 500 GB+ NVMe SSD |
| **Java** | OpenJDK 17 | OpenJDK 17 |

---

## 🚀 Building BlazeAOSP (Derleme Rehberi)

### 1. Initialize the Source Repository
```bash
# Create working directory
mkdir -p ~/blaze && cd ~/blaze

# Initialize BlazeAOSP 17.0 manifest
repo init -u https://github.com/ProjectBlaze-Staging/BlazeAOSP.git -b 17.0
```

### 2. Sync the Source Code
```bash
repo sync -c --no-clone-bundle --no-tags --optimized-fetch --prune --force-sync -j$(nproc --all)
```

### 3. Build the System
```bash
# Set up build environment
source build/envsetup.sh

# Select your device target (replace <device_codename> with your device e.g. bluejay, cheetah, etc.)
lunch lineage_<device_codename>-ap4a-userdebug

# Start compilation
m bacon -j$(nproc --all)
```

---

## 📜 Credits & Acknowledgments

* [**Android Open Source Project (AOSP)**](https://android.googlesource.com)
* [**LineageOS**](https://github.com/LineageOS)
* [**Evolution X**](https://github.com/Evolution-X)
* [**Project Blaze Team**](https://github.com/ProjectBlaze-Staging)
