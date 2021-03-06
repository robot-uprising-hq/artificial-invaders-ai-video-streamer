## Flashing SD-card and starting Raspberry Pi
1. Install Raspberry Pi OS to your Raspberry Pi's SD-card.
1. Open `boot`-section of the SD-card and type `touch ssh` in terminal to create empty file called `ssh`. The presence of this file starts the ssh server on Raspberry Pi and you can ssh into the Pi after boot.
1. If you are using ethernet cable connect it to the Raspberry Pi.
1. If you are using WIFI connection do the following. **NOTICE: The multicasting of the video stream will most likely not work via WIFI. We recommend to use ethernet cable!** Rename `wpa_supplicant.conf_TEMPLATE` to `wpa_supplicant.conf` and fill in the `ssid` and `psk` of your WIFI. Move the `wpa_supplicant.conf`-file to the `boot`-section of the SD-card.
1. Put in the Raspberry Pi Camera module to the Raspberry Pi.
1. Start Raspberry Pi with the SD-card.
1. Find Raspberry Pi's IP-address and log in. Default user is `pi` and password `raspberry`.

---
## Setting up Raspberry Pi
1. 
    ```
    sudo apt update && sudo apt upgrade -y
    ```
2. 
    ```
    sudo raspi-config
    ```
    In Raspi-Config change the following:
    - 7 Advanced Options -> A1 Expand Filesystem
    - 7 Advanced Options -> A3 Memory Split -> 256MB (This might help Rpi camera can handle 3280 x 2464 resolution)
    - 5 Interfacing Options -> P1 Camera -> Enable Camera
3. Restart Raspberry Pi and log back in.

---

## AI Video Streamer installation
1.  Install Gstreamer
    ```
    sudo apt install -y gstreamer1.0-tools \
                        gstreamer1.0-plugins-base \
                        gstreamer1.0-plugins-good \
                        gstreamer1.0-plugins-bad \
                        gstreamer1.0-plugins-ugly
    ```

---
## Rapsberry Pi camera info
https://www.raspberrypi.org/documentation/raspbian/applications/camera.md

https://www.raspberrypi.org/documentation/hardware/camera/