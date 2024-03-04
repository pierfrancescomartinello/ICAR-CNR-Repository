# Meta Quest Pro Linking
___
## Linux
### With USB Cable
- When executing ```adb devices```, the headset was said to be unauthorized

- It was necessary to create a file named ```50-oculus.rules``` with the following content:
```bash
SUBSYSTEM="usb", ATTR{idVendor}=="2833", ATTR{idProduct}=="0186", MODE="0660" group="plugdev", symlink+="ocuquest%n"
```

- This file must be saved in the folder ```/etc/udev/rules/```, but the reading permission must be granted by executing  ```sudo chmod 777 /etc/udev/rules/``` from the home folder. Later the file created prior can be saved in the folder.

- It is necessary to kill and restart the adb server a few times using the command ```adb kill-server``` and ```adb start-server``` respectively and try to check if the authorization is complete using the command ```abd devices```

### Using a Wireless Connection
After allowing the wireless connection using a MacOS device, simply run ```adb connect <ip-address>:<port>```
___
## MacOS
### With USB Cable

- Open **Meta Quest Developer Hub**, after actving bluetooth, add a new device by pressing the ```Setup new device``` button.
- On the next screen, select the model to connect, choose the device from the list and wait for a few seconds.
- After receiving a positive confirmation of the successful connection, connect the Oculus using a USB cable.
- Then, wear the headset and grant ADB permission from it.

### Using a wireless connection

- After configuring device, enable the Wi-Fi connection from **Meta Quest Developer Hub**.