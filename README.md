# N64 Smooth Commands - Raspberry Pi 3 & 4

Simple ordered terminal commands to reduce lag and improve N64 performance (Star Fox, Mario 64, etc.) on Raspberry Pi 3 and Pi 4 using RetroPie / mupen64plus.

## Get to the terminal
From RetroPie menu press **F4**  
(or SSH in)

## 1. Overclock
```
sudo nano /boot/config.txt
```
Scroll to the bottom and paste these lines:

**For Pi 3:**
```
arm_freq=1300
core_freq=500
gpu_freq=500
sdram_freq=500
over_voltage=6
v3d_freq=500
force_turbo=1
```

**For Pi 4:**
```
arm_freq=2000
over_voltage=6
gpu_freq=750
```

Ctrl+X → Y → Enter  
```
sudo reboot
```

## 2. After reboot – edit main config
```
sudo nano /opt/retropie/configs/n64/mupen64plus.cfg
```
Find and change these lines:
```
RESAMPLE = "trivial"
EnableFBEmulation = False
EnableLegacyBlending = True
EnableHybridFilter = False
UseNativeResolutionFactor = 1
```
Ctrl+X → Y → Enter

## 3. Set default emulator
```
sudo nano /opt/retropie/configs/n64/emulators.cfg
```
Change the default line to:
```
default = "mupen64plus-gles2n64"
```
Ctrl+X → Y → Enter

## 4. Final reboot
```
sudo reboot
```

---
Made for quick copy-paste use. Good cooling and a solid power supply are still required.