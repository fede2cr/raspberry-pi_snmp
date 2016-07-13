# raspberry-pi_snmp
Small scripts for SNMP monitoring using a Raspberry Pi or similar boards

##Usage:

1. Copy the scripts to /usr/local/bin
2. Modify snmpd.conf and add this code:
> extend temp               /usr/local/bin/DHT-hum-snmp.py
> extend hum                /usr/local/bin/DHT-temp-snmp.py
3. Download MIBs
> $ sudo apt install snmp-mibs-downloader
> $ sudo download-mibs
4. Restart the snmpd service
> $ sudo systemctl restart snmpd.service
5. Verify with SNMP talk, changing "public" for you real community
> $ snmpwalk -c public -v2c localhost  NET-SNMP-EXTEND-MIB::nsExtendObjects
6. Add this Raspberry Pi to your prefered monitoring software such as Nagios, Nagios XI, Cacti or others

## Scripts
* sensor-DHT: For DHT family of sensors for temp/hum. Hardcoded for DHT11 but easy to change.

