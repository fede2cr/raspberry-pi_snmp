# raspberry-pi_snmp DHT11 sensor
Python scripts for publishing a DHT11 humidity and temperature sensor on a Raspberry Pi, via SNMP

## Usage:

0. Install Adafruit's Python library for the DHT11 sensor
```
git clone https://github.com/adafruit/Adafruit_Python_DHT.git
cd Adafruit_Python_DHT/
sudo apt-get install build-essential python-dev
sudo python3 setup.py install
```
1. Copy the Python sensor scripts to /usr/local/bin
2. Modify snmpd.conf and add this code:
```
pass .1.3.6.1.2.1.25.1.8.1 /usr/bin/python3 /usr/local/bin/DHT-temp-snmp.py
pass .1.3.6.1.2.1.25.1.8.2 /usr/bin/python3 /usr/local/bin/DHT-hum-snmp.py

extend temp               /usr/local/bin/DHT-hum-snmp.py
extend hum                /usr/local/bin/DHT-temp-snmp.py
```
3. Download MIBs
```
$ sudo apt install snmp-mibs-downloader
$ sudo download-mibs
```
4. Add the snmp user to the GPIO group so it can access the sensor
```
$ sudo usermod -aG gpio snmp
```
5. Restart the snmpd service
```
$ sudo systemctl restart snmpd.service
```
6. Verify with SNMP talk, changing "public" for you real community
```
$ snmpwalk -c public -v2c localhost  NET-SNMP-EXTEND-MIB::nsExtendObjects
```
7. Add this Raspberry Pi to your prefered monitoring software such as Nagios, Nagios XI, Cacti or others

## Files
* sensor-DHT: For DHT family of sensors for temp/hum. Hardcoded for DHT11 but easy to change.
* snmpd-example: Minimalist snmpd.conf example and use as a base. Remember to change the rocommunity to other something different than "public".


## See also
* (SNMP on Raspberry with Cacti on Kbza's Blog)[http://www.kbza.org/2013/07/04/sensor-de-temperatura-snmp-con-raspberry-y-cacti/] that as used as a base for the SNMP part
