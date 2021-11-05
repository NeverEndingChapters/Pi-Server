# <img src="https://raw.githubusercontent.com/NeverEndingChapters/pi-server/main/Homer/images/raspberrypi.png" alt="drawing" width="80"/> Pi-Server

This is me just documenting how I setup my server cause I don't what I'm doing too well and thought it could help others. Also, there will be links thoughout to the guides I followed / used.
 - **_Just as a warning this is my first time ever using GitHub and my first real project_**

## 1.0 Setup of Pi-server
As I plan on doing this fully from SSH and terminal I doing a headless setup doing the following. 
1. I picked to install Raspberry Pi OS Lite (32-bit) on my SD card. 
2. When using the raspbeery pi imager you can hit ctrl+shift+x to open an extra menu.
With the menu I set my time zone, configured wifi, and setup SSH. 
3. I wrote the image to my sd card and booted it on my pi.
4. Once it booted i need to get my pi's ip address on my local network and I find it on my network with angry ip scanner.
5. After I SSH into my pi with PowerShell `ssh pi@localhost` and sign in with my password.
6. After got in I ran both `sudo apt update` and `sudo apt upgrade` to make sure the OS is fully updated.

## 2.0 Installing Portainer / Docker
 - [Raspberry pi how to install docker & portainer](https://www.wundertech.net/portainer-raspberry-pi-install-how-to-install-docker-and-portainer/)

We updated the raspberry pi bit ago at the start of the doc so skiping that step. 

1. So we go staight to running the script to install Docker. 
`curl -sSL https://get.docker.com | sh`
2.  After the script completes, we need to give our Pi user account access to Docker. 
`sudo usermod -aG docker pi`
3.  After the user has been added, we are going to run a command to download the latest Portainer image for the ARM processor (which is what the Raspberry Pi uses).
`sudo docker pull portainer/portainer-ce:linux-arm`
4.  Last step is to create a new container that will run Portainer. If you are already using port 9000 on your Raspberry Pi you will need to change the ports below.
```
sudo docker run --restart always -d -p 9000:9000 -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce:linux-arm
```
5. Go to `http://localhost :9000/` to get to the portainer web gui and create as log in password
6. select Local and Connect and with that you should be connected to your portainer

## 3.0 ShellInABox
[ShellInABox](/ShellInABox.md) implements a web server that creats web based terminal emulator. This emulator is accessible to any JavaScript and CSS enabled web browser and does not require any additional browser plugins.

## 4.0 Nginx Proxy Manager 
[Nginx](Nginx.md) is a reverse proxy is a great way to increase security and performance when exposing services on your network.
A reverse proxy is a server that sits in front of your web servers and forwards client requests to the web servers. 
In simpler terms you only have to expose one server (using ports 80/443) and will be able to expose as many web services as you want.

## 5.0 BitWarden
[Bitwarden](/BitWarden.md) is an integrated open source password management solution for individuals, teams, and business organizations
