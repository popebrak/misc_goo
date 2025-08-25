# ADS-B Receiver Setup Notes

Hey, old bean!

## Here's what I reckon you're gonna need to get started:

- 1 Raspberry Pi
        - doesn't really matter what kind
        - I'm using a Pi400, which is really a PiZero stuffed into a keyboard
        - Using one that has wifi and USB2 ports makes deployment a lot easier
        - I've got spares, if you want one
- 1 ADS-B radio receiver
        - I'm using an old RTL-SDRv2 USB2 dongle, worked right out of the box
        - The RTL-SDRv3 and v4 have better filtering, but I haven't noticed any difference
        - You mentioned you've got a proper commercial reciever and that might work?
        - The gnuradio stuff might not be expecting that, though
        - I've got a spare RTL-SDRv2, if you want one
- 1 Antenna of some sort or another
        - ADS-B transmits on a frequency of 1090 MHz
        - The better way to think about this is "About 1 GHz"
        - There are some speed-of-light equations to be considered, but. . .
        - Honestly, whatever little whip antenna that came with your SDR will do for now
        - I've got a spare GHz-range dipole, if you want one.


## Once you've got all that. . .

- Flash your Rpi's SD card with a current version of the OS
- Boot it up, run 'sudo apt update;sudo apt upgrade;sudo reboot' and all that
- Install tar1090 from Github
        - https://github.com/wiedehopf/tar1090
        - sudo bash -c "$(wget -nv -O - https://github.com/wiedehopf/tar1090/raw/master/install.sh)"
- Install graphs1090 from Github
        - https://github.com/wiedehopf/graphs1090
        - sudo bash -c "$(curl -L -o - https://github.com/wiedehopf/graphs1090/raw/master/install.sh)"
- Install the rbfeeder service from AirNavRadar (or wherever), if you are so-inclined
        - https://www.airnavradar.com/raspberry-pi/guide
        - sudo bash -c "$(wget -O - http://apt.rb24.com/inst_rbfeeder.sh)"

Once you've created an account and set up your station to feed data to AirNav Radar, they'll automagically give you a free business account, which is pretty sweet ($50/month, otherwise). There are plenty of other commercial ADS-B outfits like Flight24, as well as a few non-commercial outfits like adsbexchange, but I honestly haven't played with any of them just yet.
