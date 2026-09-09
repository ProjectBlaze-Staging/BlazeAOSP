# BlazeAOSP (Android 17 / ProjectBlaze 5)

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

## Hardware & Build Requirements

To build BlazeAOSP from source, your workstation should meet the following minimum specs:

| Component | Minimum Requirement | Recommended |
| :--- | :--- | :--- |
| **OS** | Linux (BlazeOS Debian/Fedora series, Debian 12, Arch) | BlazeOS Debian/Fedora series |
| **CPU** | 8 Cores / 16 Threads | 16+ Cores (AMD Ryzen / Intel Core i7/i9) |
| **RAM** | 16 GB (+ 16 GB Swap) | 32 GB – 64 GB RAM |
| **Storage** | 400 GB Free Space | 500 GB+ NVMe SSD |
| **Java** | OpenJDK 17 | OpenJDK 17 |

[**Upgrade to BlazeOS**](https://github.com/DarkMorpheus-pc/Blaze-Galaxy)

---

## Building Blaze !

### 1. Initialize the Source Repository
```bash
# Create working directory
mkdir -p ~/blaze && cd ~/blaze

# Initialize BlazeAOSP 17.0 manifest
repo init -u https://github.com/ProjectBlaze-Staging/blaze_manifest.git -b 17.0
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

## Credits & Acknowledgments

* [**Android Open Source Project (AOSP)**](https://android.googlesource.com)
* [**LineageOS**](https://github.com/LineageOS)
* [**Evolution X**](https://github.com/Evolution-X)
* [**Project Blaze Team**](https://github.com/ProjectBlaze-Staging)
