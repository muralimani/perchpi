# rpi-custom-image

A custom Raspberry Pi Image for quickly deploying the Bird Classification model - Perch [https://github.com/google-research/perch] on edge device like Pi to classify birds through Bioaccountic monitoring. Some of the constraints in running the m/c learning model applies for this deployment model.

(1) Pre-package all the s/w, packages during the image building process and not during the deployment phase on the site, as there would not be any Wifi or internet connectivity.
(2) Download m/c learning model (400+ MB) during the image building process
(3) Ability to startup the services by default on the first boot
(4) Ability to extract the collected bird classification data from the RPi using simple mechanism like - ssh / bluetooth on a mobile or desktop.
(5) Ability to update raspi-config parameters in the RPi (password protected)

The overall process:

Build custom image:

(1) Leverage rpi-image-gen to build a custom image
(2) Define  the config & layer for customising the features relevant for the 
(3) Config - Define the image name
(4) Layer - Install all relevant software / packages

Deploying Image on sites
(1) Make the custom image available in Raspberry Pi Imager list of the images to download directly
