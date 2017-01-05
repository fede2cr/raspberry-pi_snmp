# Ansible recipe for the installation of the Adafruit_Python_ADS1x15 module

This ansible recipe is designed to ease and automate the installation of the Adafruit_Python_ADS1x15 module necesary for accesing an Analog-to-Digital Converter (ADC) with chipset ADS1115 [from Adafruit](https://www.adafruit.com/products/1085) or [from CRCibernetica](http://www.crcibernetica.com/ads1115-16-bit-adc-4-channel-with-programmable-gain-amplifier/).

This recipe is designed for running on a Raspberry Pi under Raspbian, but can be easily modified for other platforms or distributions.

## Instructions

To install the module you can:
- Copy the files to the Raspberry Pi, and install the ansible package


- If you need to install multiple Raspberry Pi, you can create a hosts files with the IP and users for all of the raspberries to install, and have the python 2.7 already installed (I think it's already there in Raspbian).

## See Also

The learning guide from Adafruit for the ADS1115 at https://learn.adafruit.com/raspberry-pi-analog-to-digital-converters
