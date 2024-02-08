# webcam-tweaks

Some tips from [this video](https://youtu.be/E-uGN8nfeGc?si=Lt_6djewXvILOu19), which 
should allow me to control the Elgato Facecam Pro (and other devices) on Linux. 

## Setup

```
sudo apt install usbview v4l-utils
```

## usbview

Allows you to inspect which devices are connnected to what. You want your webcam to be 
connected to a USB 3 port that's able to deliver sufficient power.

```console
$ sudo usbview
```

## v41-utils

```console
$ v4l2-ctl --list-devices
Integrated_Webcam_HD: Integrate (usb-0000:00:14.0-11):
	/dev/video0
	/dev/video1
	/dev/video2
	/dev/video3

Elgato Facecam Pro: Elgato Face (usb-0000:38:00.0-1):
	/dev/video4
	/dev/video5
```

Setting focus to manual, then zoom in

```console
$ v4l2-ctl --set-ctrl=focus_auto=0
$ v4l2-ctl --set-ctrl=focus_absolute=150
$ v4l2-ctl --set-ctrl=focus_zoom=150
$ v4l2-ctl --set-ctrl=white_balance_temperature_auto=1
```
