# Raspberry Pi's 

## Raspi config

### Pre boot
In the boot folder on the flashed sd card
```bash
# ssh / ssh.txt in the boot folder will default enable ssh
touch ssh.txt

# wpa_supplicant.conf also in boot
echo country=NO > wpa_supplicant.conf

# Add the blow to wpa_supplicant.conf too 
network={
    ssid="testing"
    psk="testingPassword"
}
```

### Post boot
```bash
# To change the password
passwd

# Add ssh keys etc.
# TODO
```

## Crontab
```bash
# RPI Crontab
@reboot sleep 20 && export DISPLAY=:0 && /home/pi/Desktop/hass.sh
@weekly sleep 60 && sudo reboot
@hourly ping -q -c 4 -W 20 google.com || sudo reboot
```