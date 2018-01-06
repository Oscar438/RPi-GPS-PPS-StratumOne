# RPi-GPS-PPS-StratumOne

The following has been modified to work using ethernet gadget and a rapsberry pi0. The original project
can be found here: https://github.com/beta-tester/RPi-GPS-PPS-StratumOne

setup a Raspberry Pi 0 as an Stratum One NTP server.

USE IT AT YOUR OWN RISK

### overview schematic:
```
                     ╔═══╗       ╔══════╗         ╔══════╗  GPS-Antenna
                   ──╢ S ║       ║RPi as╟RX───────╢GPS-  ║    ═╪═
                     ║ w ║       ║NTP-  ╟TX───────╢module║     │
                     ║ i ║       ║server║         ╠═══╗  ║     │
       ╔══════╗      ║ t ╟───eth0╢      ╟GPIO#4───╢PPS║  ╟─────┘
       ║ RPi  ╟──────╢ c ║       ║      ║         ╚═══╩══╝
       ╚══════╝   ┌──╢ h ╟──┐    ║      ║
                  │  ╚═══╝  │    ╚══════╝
               ╔══╧══╗   ╔══╧══╗
               ║ PC1 ║   ║ PC2 ║
               ╚═════╝   ╚═════╝
```

## requirements

### hardware:
- Raspberry Pi 0
- SD card
- working network environment (with a connection to internet for installation only)
- GPS module with PPS output http://navspark.mybigcommerce.com/

### software:
- Raspbian Stretch Lite (2017-08-16, https://www.raspberrypi.org/downloads/raspbian/)

## installation:
assuming,
- your Raspberry Pi is running Raspbian Stretch Lite (2017-08-18),
- and has a proper connection to the internet via LAN.
- and your SD card is expanded,
- and you connected the GPS module direct to the RPi's RX/TX pins of the GPIO and the GPS PPS pin to the RPi' GPIO #4

1. run `bash install-gps-pps.sh` to install necessary packages and setup Kernel PPS, GPSD, and NTP with PPS support.
2. reboot your RPi with `sudo reboot`

done.
