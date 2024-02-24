# Lenovo ThinkSmart View Android 8.1 howto

Steps taken from here https://community.home-assistant.io/t/is-this-the-perfect-standalone-tablet-for-ha/658422

1. Install EDL software (MacOs)
from here https://github.com/bkerler/edl

brew install libusb git

git clone https://github.com/bkerler/edl.git
cd edl
git submodule update --init --recursive
python3 setup.py build
sudo python3 setup.py install

2. Create folder flash

mkdir flash

3. Download kingston-ha-rom.7z from here
https://drive.google.com/file/d/1vnRMgf0pac1uKbdNDqJTANmH1t6IgflV/view?usp=sharing

and extract it to and copy content of flash directory into edl/flash folder and copy bin directory into edl/flash

4. Start the flash tool

./edl qfil bin/rawprogram.xml bin/patch0.xml flash/ --loader=flash/bin/prog_emmc_firehose_8953_ddr.mbn

5. Remove the rubber plug on bottom of unit and connect via Usb-C.

6. Boot into EDL mode by simultaneously pressing both volume buttons while powering on.

7. Power off when flashing is complete.

8. Boot into recovery mode by holding volume up while powering on. Perform a factory reset and reboot.

9. Once you can see the desktop, finish up user provisioning

adb shell settings put secure user_setup_complete 1
adb shell settings put global device_provisioned 1

10. Install a navigation bar

adb install extras/virtualsoftkeys.apk
