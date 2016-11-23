# Selfiebooth Baas van Horst aan de Maas

![Illustration Selfiebooth](illustration.png)
Python code and assets Selfiebooth Baas van Horst aan de Maas.

## Hardware setup

### 1. Camera module

Connect raspberry PI camera module to board

### 2. GPIO setup for button

TODO: Add readme for GPIO setup (hardware)

## Software setup

### 1. Prerequisites

- Raspbian
- Enabled pi camera module (https://www.raspberrypi.org/documentation/usage/camera/)
- Python image library
- Python yaml library
- Python picamera library

When you are on raspbian, please run the `install_deps` script:

    ./install_deps

### 2. Clone this repository

    git clone https://github.com/reinzor/selfieboot.git /home/pi/selfiebooth

### 3. Add to startup (rc.local)

    sudo vim /etc/rc.local
    sudo /home/pi/selfiebooth/src/app.py 

## Configuration file 
The app searches for an USB stick that is inserted to the pi. If a config folder exists with a config.yaml, it will try to load this configuration. If none is found the default_config will be copied to the USB. If another config
directory existed; a backup will be created. 

### Config file parameters
- bottom_image: image path
- top_image: image path
- flash_image: image path
- countdown_images: list of image paths, every image takes 1 second
- screensaver_images: list of image paths
- flash_time: time in secs
- freeze_time: time in secs
- screensaver_time: time in secs
- screensaver_slide_time: time in secs
- screen_width: pixel size
- screen_height: pixel size

All specified paths are relative to the config file
