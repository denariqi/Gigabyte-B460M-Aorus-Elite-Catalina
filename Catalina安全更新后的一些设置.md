## Catalina 10.15.7 (19H2026)安全更新 2022-004 之后:
### 打开[文件共享]:
sudo launchctl load -w /System/Library/LaunchDaemons/com.apple.smbd.plist
###  打开[远程登录]:
sudo launchctl load -w /System/Library/LaunchDaemons/ssh.plist
### [文件共享认证]失败的解决方法:
sudo /usr/libexec/configureLocalKDC
## USBInjectAll
- 用Hackintool (3.5.3) 配合 USBInjectAll.kext (0.76)，生成 SSDT-EC-USBX.aml 和 SSDT-UIAC.aml，放入ACPI目录；
- 在 Kext 目录保留 USBInjectAll.kext (0.76) 和 XHCI-Injector.kext (0.92 )；
- 不需要去除 Kernel 内核设置里的 XhciPortLimit 选项，保持解锁15个USB口限制。
- USB2.0和3.0都正常，最高到5Gb/秒，不会被降速到480Mb，雷雳3正常挂载Lacie 3T的盘。
