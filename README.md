# Linux kernel - VisionBox LE MANS
This is the Linux Kernel for the IMAGO VisionBox LE MANS.

The embedded computer is based on the NXP LS2084A/LS2088A SOC.

### Key features:
* 8 core ARM Cortex-A72, 2 GHz
* 24 V power supply
* Passive cooling
* 1x PCIe x16 slot, 8 GT/s (four lanes populated)
* 2x PCIe x4 slot, 5 GT/s
* 1x mini PCIe socket
* 2x 10 Gb/s SFP+ interface
* 4x 1 Gb/s 1000BASE-T Ethernet
* 2x USB 3.0
* SD card
* mSATA socket
* RS-232 interface
* Opto-isolated I/Os (8 inputs, 8 outputs)
* Additional I/Os and LED Strobe controller available
* Compact version without PCIe slots available

## Build instructions

### Native build
```
git clone https://github.com/RalfGoebel/linux-qoriq.git
cd linux-qoriq
make visionbox-lemans_defconfig
make -j4
```

### Cross build
```
cd
wget https://releases.linaro.org/components/toolchain/binaries/6.3-2017.05/aarch64-linux-gnu/gcc-linaro-6.3.1-2017.05-x86_64_aarch64-linux-gnu.tar.xz
tar xvJf gcc-linaro-6.3.1-2017.05-x86_64_aarch64-linux-gnu.tar.xz
export PATH=$HOME/gcc-linaro-6.3.1-2017.05-x86_64_aarch64-linux-gnu/bin:$PATH
export CROSS_COMPILE=aarch64-linux-gnu-
export ARCH=arm64
git clone https://github.com/RalfGoebel/linux-qoriq.git
cd linux-qoriq
make visionbox-lemans_defconfig
make -j4
```
To build installable Debian packages:
```
make -j4 deb-pkg
```
