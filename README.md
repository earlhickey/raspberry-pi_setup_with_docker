
# raspberry-pi_setup_with_docker

In order to use a Raspberry Pi you need an OS and setup network. Working with Git repo's and docker is recommended because it is fast to setup and code is stored in the cloud. When a SD card fails you can easaly restore (don't forget to backup data!).

## Setup

### Download Raspbian Lite
https://www.raspberrypi.org/downloads/raspbian/
https://downloads.raspberrypi.org/raspbian_lite_latest

### Burn the Raspbian image to the SD card

OsX app: balenaEther

### Enable ssh
```
touch /Volumes/boot/ssh
```

### Create wifi network info
```
cp wpa_supplicant_example.conf wpa_supplicant.conf (update ssid + password)
cp wpa_supplicant.conf /Volumes/boot/wpa_supplicant.conf
```

### Eject SD card

### Login
```
ssh-keygen -R raspberrypi.local
ssh pi@raspberrypi.local (default pw is raspberry)
```

### Change hostname (mypi) & password
```
sudo raspi-config
```

### Update
```
sudo apt-get update -y
sudo apt-get upgrade -y
```

### Source
https://desertbot.io/blog/headless-raspberry-pi-3-bplus-ssh-wifi-setup



## Docker

### Install docker
```
curl -fsSL get.docker.com -o get-docker.sh && sh get-docker.sh
sudo groupadd docker
sudo gpasswd -a pi docker
docker run hello-world
```

### Install docker-compose
```
sudo apt update
sudo apt install -y python python-pip libffi-dev python-backports.ssl-match-hostname
sudo pip install docker-compose
```

### Source
https://manre-universe.net/how-to-run-docker-and-docker-compose-on-raspbian/

## Git

### Install Git
```
sudo apt-get install git
```