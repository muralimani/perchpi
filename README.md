# rpi-custom-image

A custom Raspberry Pi Image for quickly deploying the Bird Classification model - Perch [https://github.com/google-research/perch] on edge device like Pi to classify birds through Bioaccountic monitoring. Some of the constraints in running the m/c learning model applies for this deployment model.

* Pre-package all the s/w, packages during the image building process and not during the deployment phase on the site, as there would not be any Wifi or internet connectivity.
* Download m/c learning model (400+ MB) during the image building process
* Ability to startup the services by default on the first boot
* Ability to extract the collected bird classification data from the RPi using simple mechanism like - ssh / bluetooth on a mobile or desktop.
* Ability to update raspi-config parameters in the RPi (password protected)

The overall process:

**Build custom image:**

Step 1: Git clone the RaspberryPi Custom image (rpi-image-gen)

```
git clone https://github.com/raspberrypi/rpi-image-gen.git
cd rpi-image-gen
sudo ./install_deps.sh
```

Step 2: Git clone the custom image for PerchPi
```
git clone https://github.com/raspberrypi/rpi-image-gen.git
cd rpi-image-gen
sudo ./install_deps.sh
```
Leverage rpi-image-gen to build a custom image
Define the config & layer for customising the features relevant for the
Config - Define the image name
Layer - Install all relevant software / packages

```
./rpi-image-gen build -S examples/perchpi -c examples/perchpi/config/perchpi.yaml

```
**Deploying Image on sites**

Make the custom image available in Raspberry Pi Imager list of the images to download directly

