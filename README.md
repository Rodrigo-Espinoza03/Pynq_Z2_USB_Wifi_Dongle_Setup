# Pynq_Z2_USB_Wifi_Dongle_Setup
Using the Ralink 5370 Chipset, 2.4GHz, usb wifi dongle. Pynq Z-2 image version is 3.1.1.

Use Tera Term or Putty and set baud rate to 115200. Select COM port. Let pynq board boot.
Turn on and change mobile hotspot properties.

Step 1: Connect USB wifi dongle to usb port of board.

Step 2: Enter "lsusb" and make sure wifi dongle is detected. If so, proceed to next step.

Step 3: Enter "sudo nano /etc/network/interfaces"

Step 4: Enter the following: 

auto lo
iface lo inet loopback

// for ethernet connection:

auto eth0
iface eth0 inet static
    address 192.168.2.99
    netmask 255.255.255.0

// for hotspot:

auto wlan0
iface wlan0 inet dhcp
    wpa-ssid ""
    wpa-psk ""

Note: Use the name and password from your hotsport. Enter hotspot name for wpa-ssid. Enter hotspot password for wpa-psk.
Step 5:  Select ctrl+O, then click enter, then select ctrl+X to leave nano text editor.

Step 6: Enter "sudo reboot"
