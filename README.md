# Pi Pattern Generator

## What is does

A basic implementation of a (test) pattern generator from the HDMI output of an raspberry pi. The main reason is for our livestreaming purposes (http://koekfm.nl) so we can generate a test card for the switcher (Roland v-1HD) without hooking up a full blown computer just to generate it. (Yes, I could have bought an ATEM switch...)

Settled w/ `fbi` inspired from various sources around the net

## Setup

- Create an image w/ Debian lite
- Install FBI

      apt-get update -y
      apt-get install fbi

- Copy the png and script to the homedir (`/home/pi`)

      curl https://raw.githubusercontent.com/LeipeLeon/PiPatternGenerator/master/2160-4k-koekfm.png > 2160-4k-koekfm.png
      curl https://raw.githubusercontent.com/LeipeLeon/PiPatternGenerator/master/start-display.sh > start-display.sh

- Change the umask of file

      chmod +x start-display.sh

- Add this script to the .bashrc

      echo "/home/pi/start-display.sh" >> .bashrc

- set the bootoption w/ `sudo raspi-config`

      - 3 Boot options
        - B1 Desktop / CLI
          - B2 Console Autologin
        - B2 Wait for Network at Boot -> no
      - 5 Interfacing Options
        - P2 enable SSH (optional)
      - 7 Advanced Options
        - A2 Overscan -> no
