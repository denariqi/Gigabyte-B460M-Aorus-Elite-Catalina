# Gigabyte-B460M-Aorus-Elite Hackintosh
- Gigabyte B460M Aorus Elite
- 10th Gen Intel(R) Core(TM) i5-10400 (F)  Intel Comet Lake
- DDR4 2666 32GB (16GB+16GB)
- AMD RX570 4G (Sapphire)
- BCM94360CD
- iMac20,1 (MacPro7.1)
- macOS: Catalina Later
- BASE EFI: OpencCore 7.6
# ACPI
- SSDT-PLUG-DRTNIA.aml
- SSDT-EC-USBX-DESKTOP.aml
- SSDT-AWAC.aml
- SSDT-PM.aml
# Drivers
- HfsPlus.efi
- OpenRuntime.efi
# Tools
- CFGLock.efi
- OpenShell.efi
- VerifyMsrE2.efi
# KextS
- Lilu
- VirtualSMC
  + SMCProcessor
  + SMCSuperIO
- WhateverGreen
- AppleALC
- NVMeFix
- RestrictEvents
- USBPorts (USBInjectAll)
- IntelMausi
- AGPMInjector
- RadeonBoost
- XHCI-unsupported
# BIOS Settings
### Disable
- Fast Boot
- Secure Boot
- Serial/COM Port
- Parallel Port
- VT-d (can be enabled if you set `DisableIoMapper` to YES)
- Compatibility Support Module (CSM).
- Thunderbolt (For initial install, as Thunderbolt can cause issues if not setup correctly)
- Intel SGX
- Intel Platform Trust
- CFG Lock (MSR 0xE2 write protection)
	- This must be off, if you can't find the option then **`ENABLE`** `AppleXcpmCfgLock`. 
	- Your hack will not boot with `CFG-Lock` enabled.
### Enable
- VT-x
- Above 4G decoding. 
	- This must be on, if you can't find the option then add `npci=0x2000` to `boot-args`. 
	- Do not have both this option and `npci` on `boot-args` enabled at the same time.
	- 2020+ BIOS Notes: When enabling Above4G, Resizable BAR Support may become an available on some Z490 and newer motherboards. Please ensure this is **`DISABLED`** instead of set to Auto.
- Hyper-Threading
- Execute Disable Bit
- EHCI/XHCI Hand-off
- OS type: Windows 8.1/10 UEFI Mode
- DVMT Pre-Allocated (iGPU Memory): 64MB
- SATA Mode: AHCI
# CPU Power Management
CPU power management is handled with 'CPUFriend and CPUFriendDataProvider for SMBIOS MacPro7, 1'.
