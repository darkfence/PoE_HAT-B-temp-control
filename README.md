# Waveshare PoE HAT (B)
Set up the WaveShare PoE HAT (B) and configure it to react to changes in board temperature. 

The script configures a system service that will be launched at startup. 

## Installation

For the prepared program to work, set the switch controlling the fan to the off position (P0). If you are not sure which position P0 is in, set the switch so that the fan does not work when the power is on.

You can adjust the temperature at which the fan will be activated as well as at which it will stop working. To do this, edit PoE_HAT_B_code/main.py by making changes to line 20. 

```python
        POE.POE_HAT_Display(65, 45)
```
In the example above, 65 is the temperature (in Celsius degrees), above which the fan activates. When the temperature of the system drops below 45 degrees, the fan will stop working.

Installation of the service is done by running the setup.sh script

```bash
cd ~
git clone https://github.com/darkfence/PoE_HAT-B-temp-control.git && cd PoE_HAT-B-temp-control
bash setup.sh
```

To remove and disable the service, run these commands
```bash
sudo systemctl disable poe-hat.service
sudo systemctl stop poe-hat.service
rm -rf ~/.poe-hat
```

### Credits
Derived from 
- https://www.waveshare.com/wiki/PoE_HAT_(B)
- https://gist.github.com/CharlesGodwin/adda3532c070f6f6c735927a5d6e8555

Forked from [Romain-Donze/Waveshare_PoE_HAT-B](https://github.com/Romain-Donze/Waveshare_PoE_HAT-B)