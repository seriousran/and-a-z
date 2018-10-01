# and-a-z (android-a-to-z)

- USB로 안드로이드를 연결했을 때 데이터를 껐다가 켜는 것을 PC프로그램으로 제어

```adb
adb shell
svc data disable
svc data enable
```
  명령어를 script 파일로 작성후에, bat으로 기기로 복사 후 실행하도록 짜놓으면 bat을 실행할때마다 data를 껐다가 켜도록 할 수 

- 안드로이드 무선 ADB 사용

```bash
@echo off
title adb connect without usb
set port=5555
echo.
echo   adb connect without usb by Mir(whdghks913)
echo.
echo   Connect your Android device and adb host computer to a common Wi-Fi network accessible to both.
echo   Waiting for device, Connect the device to the host computer with a usb
echo.
adb kill-server
adb wait-for-device
adb tcpip %port%
echo.
echo   Disconnect the USB cable from the target device.
echo   Find the IP address of the Android device, and Enter the IP address
echo.
set /P ip=  Your IP : 
adb connect %ip%:%port%
timeout /t 1
echo.
adb devices
pause
```
