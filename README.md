# raspberry-pi_snmp [![Build Status](https://travis-ci.org/fede2cr/raspberry-pi_snmp.svg?branch=master)](https://travis-ci.org/fede2cr/raspberry-pi_snmp)
Small scripts for SNMP monitoring using a Raspberry Pi or similar boards

## Description
Python scripts, SNMP config files and ansible recipes to make it simple to use the GPIO ports on a Raspberry Pi to connect sensors, and then present them via SNMP to a monitoring service.

## Sensors
![Fritzing Diagram](https://github.com/fede2cr/raspberry-pi_snmp/blob/master/fritzing/Pi%20y%20sensores.png)
- DHT11 and DHT temperature and humidity sensors
- Analog-to-digital converter (ADC) with chipset ads1115 from Adafruit
- Energy monitor shield v0.2 from CRCibernética, conected to the i2c ADC
