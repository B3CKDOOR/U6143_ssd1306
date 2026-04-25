# U6143_ssd1306
## Preparation
Mount the sd card

edit ``config.txt`` and add these two lines to the bottom:
```bash
dtparam=i2c_vc=on
dtparam=i2c_arm=on
```

Next up, create a folder called ``CONFIG``

make a subfolder called ``modules``

create a file with the name ``rpi-i2c.conf`` and with the following content:

```bash
i2c-dev
```


##  Clone U6143_ssd1306 library 
```bash
cd
git clone https://github.com/B3CKDOOR/U6143_ssd1306.git
```
## Run `setup_display_service.sh` script
```bash
cd ~/U6143_ssd1306
chmod +x setup_display_service.sh
sudo ./setup_display_service.sh
```
## For older 0.91 inch lcd without mcu 
- For the older version lcd without mcu controller, you can use python demo
- Install the dependent library files
```bash
sudo apt-get install python3-pip
sudo apt-get install python3-pil
sudo pip3 install --break-system-packages adafruit-circuitpython-ssd1306
```
- Test demo 
```bash 
cd ~/U6143_ssd1306/python 
sudo python3 ssd1306_stats.py
```

## Custom display temperature type 
- Open the U6143_ssd1306/C/ssd1306_i2c.h file. You can modify the value of the TEMPERATURE_TYPE variable to change the type of temperature displayed. (The default is Fahrenheit)

![EasyBehavior](https://github.com/B3CKDOOR/U6143_ssd1306/blob/master/pics/select_temperature.jpg)


## Custom display IPADDRESS_TYPE type 
- Open the U6143_ssd1306/C/ssd1306_i2c.h file. You can modify the value of the IPADDRESS_TYPE variable to change the type of IP displayed. (The default is ETH0)

![EasyBehavior](https://github.com/B3CKDOOR/U6143_ssd1306/blob/master/pics/select_ip.jpg)

## Custom display information 
- Open the U6143_ssd1306/C/ssd1306_i2c.h file. You can modify the value of the IP_SWITCH variable to determine whether to display the IP address or custom information. (The custom IP address is displayed by default)

![EasyBehavior](https://github.com/B3CKDOOR/U6143_ssd1306/blob/master/pics/custom_display.jpg)





