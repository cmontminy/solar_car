# Telemetry Demo
This program / instructions make a simple system for presenting dummy speed data. Basically a proof of concept for the InfluxDB and Grafana combo c:

---
## First Time Set Up 
*assuming you're starting with a brand new raspberry pi, if not just skip this*
* Download a copy of Raspbian Stretch from [their website](https://www.raspberrypi.org/downloads/raspbian/)
* Throw it onto your SD card with [Etcher](https://www.balena.io/etcher/)
* Connect your peripherals to the Pi and power it up
* If you want, you can clear out some bloatware with [these commands](https://github.com/raspberrycoulis/remove-bloat/blob/master/remove-bloat.sh):
```
sudo apt-get remove --purge wolfram-engine libreoffice* scratch* minecraft-pi sonic-pi dillo gpicview oracle-java8-jdk openjdk-7-jre oracle-java7-jdk openjdk-8-jre -y
sudo apt-get autoremove -y
sudo apt-get autoclean -y
sudo apt-get update
```

## Installing and Configuring Software
### InfluxDB
* Install InfluxDB with these commands:
```
sudo apt install apt-transport-https
echo "deb https://repos.influxdata.com/debian jessie stable" | sudo tee /etc/apt/sources.list.d/influxdb.list
sudo apt update
```
* Use `sudo nano -c /etc/influxdb/influxdb.conf` to edit the Influx configuration file. Scroll down to the [http] section and uncomment the line `enabled: false` and change it to `true`. Also uncomment `bind-address: :8083`
```

```
### Grafana
* Install Grafana with these commands:

*make sure that you're downloading the most recent version by checking [their website](https://grafana.com/grafana/download?platform=arm)*
```
wget https://dl.grafana.com/oss/release/grafana-rpi_6.1.4_armhf.deb 
sudo dpkg -i grafana-rpi_6.1.4_armhf.deb 
```
