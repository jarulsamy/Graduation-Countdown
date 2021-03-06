# Graduation-Countdown

A simple date countdown script for use with a Adafruit 16x2 LCD and a raspberry pi.

## Usage

Wire the LCD and buttons to the RPI according to these pin details.

<table>
<tr><th>Buttons</th><th>LCD</th></tr>
<tr><td>

| Button | RPI BCM Pin |
| :----: | :---------: |
|   RED  |      22     |
|  GREEN |      27     |
|  BLUE  |      17     |

</td><td>

| LCD Pin | RPI BCM Pin |
| :-----: | :---------: |
|    RS   |      18     |
|    EN   |      23     |
|    D4   |      24     |
|    D5   |      25     |
|    D6   |      8      |
|    D7   |      7      |

</td></tr> </table>

Of course these can be changed if you edit the pin numbers in `lcd.py`. This just worked best for me.

### Setup

This software is only compatible with **Python 3.6** or greater.

Install the Adafruit Python CharLCD python library. Unfortunately it has been deprecated and is no longer updated in favor of the newer AdaFruit circuit python library. It is still hosted [here.](https://github.com/adafruit/Adafruit_Python_CharLCD). This software will eventually be ported to a newer library.

> Ensure all the dependencies are installed to the **SYSTEM** python3 (`/usr/bin/python3` in most cases), otherwise you will not be able to access the GPIO pins.

## Systemd

Edit the systemd service file; `LCD-countdown.service` to fit your needs. Essentially just point the service to where you clone this repository.

Copy the systemd service file to `/etc/systemd/system/` and reload the systemctl daemon:

```bash
sudo cp LCD-countdown.service /etc/systemd/system/.
sudo systemctl daemon-reload
```

Now you can start and stop the service just like any other systemd service:

```bash
sudo systemctl start LCD-countdown # Start the service.
sudo systemctl stop LCD-countdown # Stop the service.
sudo systemctl restart LCD-countdown # Restart the service.
sudo systemctl status LCD-countdown # Check the status of the service.
sudo systemctl enable LCD-countdown # Start the service on boot.
sudo systemctl disable LCD-countdown # Don't start the service on boot.
```

## Support

Reach out to me at one of the following places!

-   Email (Best) at joshua.gf.arul@gmail.com
-   Twitter at <a href="http://twitter.com/jarulsamy_" target="_blank">`@jarulsamy_`</a>

* * *
