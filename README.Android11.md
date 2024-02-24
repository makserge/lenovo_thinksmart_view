# Lenovo ThinkSmart View Android 11 howto

Steps taken from here https://community.home-assistant.io/t/is-this-the-perfect-standalone-tablet-for-ha/658422/444

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

3. Download combined_kingston_a11_gogapps.7z from here
[https://drive.google.com/file/d/1vnRMgf0pac1uKbdNDqJTANmH1t6IgflV/view?usp=sharing](https://s3.us-east-1.wasabisys.com/filestash-buk/lenovo-thinksmart-view/combined_kingston_a11_gogapps.7z)

and extract it to and copy content of archive into edl/flash folder

4. Start the flash tool

./edl qfil rawprogram0.xml patch0.xml flash/ --loader=flash/prog_emmc_firehose_8953_ddr.mbn

5. Remove the rubber plug on bottom of unit and connect via Usb-C.

6. Boot into EDL mode by simultaneously pressing both volume buttons while powering on.

7. Power off when flashing is complete.

8. Boot into recovery mode by holding volume up while powering on. Use volume keys to navigate to the factory reset option and select it.

9. Reboot and after a few minutes you will see the duck boot animation and then the Google setup wizard.

10. Make the keyboard not take up the full screen and to make the UI elements smaller: developer options → find “smallest width” → set to 600dp to make the keyboard not take up the full screen and to make the UI elements smaller.
