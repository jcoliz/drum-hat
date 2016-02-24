# Drum HAT

* 8 Capacitive Touch Buttons
* Finger-friendly drum pad layout
* 8 under-mounted LEDs

# Installing Drum HAT

We've created a super-easy installation script that will install all pre-requisites and get your Drum HAT up and running in a jiffy. To run it fire up Terminal which you'll find in Menu -> Accessories -> Terminal on your Raspberry Pi desktop like so:

![Finding the terminal](terminal.jpg)

In the new terminal window type the following and follow the instructions:

```bash
curl -sSL get.pimoroni.com/drumhat | bash
```

If you choose to download examples you'll find them in `/home/pi/Pimoroni/drumhat`, but you can also check out the examples for Drum HAT in: [examples](examples)

## Using Drum HAT

The pads on Drum HAT are laid out like so:

```
4    3    2
5    7    1
  6    0
```

Drum HAT can call a function when a pad is hit, or when it is released. For example, to do something when the middle pad (channel 7) is hit, you should:

```python
import drumhat

@drumhat.on_hit(7)
def middle_pad():
    print("Middle Pad Hit!")
```

## Manual Install

You can install Drum HAT manually like so:

```
sudo apt-get install python-smbus
git clone https://github.com/pimoroni/drum-hat
cd drum-hat/library
sudo python setup.py install
```

Or, for Python 3:

```
sudo apt-get install python3-smbus
git clone https://github.com/pimoroni/drum-hat
cd drum-hat/library
sudo python3 setup.py install
```

In both cases you will have to enable i2c in `raspi-config`.
