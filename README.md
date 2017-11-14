# home-assistant

Hass.io configuration for local hub running Ubuntu 16.04.  Includes a MQTT bridge to communicate with Samsung SmartThings Hub, as well as CI/CD through Travis-ci.  Current IoT ecosystem includes bluetooth, wireless, IR/RF, and ZigBee devices.  Current hubs include Alexa and Samsung Smartthings.

## Getting Started

These instructions include an installation of home-assistant, mosquitto, and smartthings-mqtt-bridge.  You should be able to set up a home-assistant.io hub & mqtt bridge to communicate with SmartThings after reading this.  Be advised that this configuration is currently unsecure.

### Requirements
* nodejs
* npm
* pm2
* python3
* pip3


# Installation Instructions
## 1. Install home-assistant.io
```
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install python3-pip python3-dev
sudo pip3 install --upgrade virtualenv
```
```
python3 -m venv $HOME/homeassistant
source $HOME/homeassistant/bin/activate
pip3 install --upgrade homeassistant
$HOME/homeassistant/bin/hass
```
Source: https://home-assistant.io/docs/installation/virtualenv/

## 2. Install mosquitto
```
sudo apt-get install mosquitto mosquitto-clients
cd /etc/mosquitto
sudo mosquitto_passwd -c /etc/mosquitto/pwfile YOUR_NAME
```
Source: https://home-assistant.io/docs/mqtt/broker#run-your-own

## 3. Install & configure smartthings-mqtt-bridge
```
npm install -g smartthings-mqtt-bridge
pm2 start smartthings-mqtt-bridge
```
Github: https://github.com/stjohnjohnson/smartthings-mqtt-bridge
Video: https://www.youtube.com/watch?v=6YX1LRL5axE

# todos
Travis-ci - WIP
Dynamic DNS - WIP
Launch script
Security/Backups
