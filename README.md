# <img src="https://raw.githubusercontent.com/NeverEndingChapters/pi-server/main/Homer/images/raspberrypi.png" alt="drawing" width="80"/> Pi-Server
**_Just as a warning this is my first time ever using GitHub and my first real project_**
Cause I don't what I'm doing to well there will be links thoughout to the guides I followed / used.

## 1.0 Setup of Pi-server
Installed Raspberry Pi OS Lite (32-bit) on a SD card
when using the raspbeery pi imager you can hit ctrl+shift+x to open an extra menu.
With the menu I set my time zone, configured wifi, and setup SSH. 
Then, I wrote the image to my sd care and booted it on my pi. which is my raspberry pi 4 model B / 8GB
After I SSH into my pi I ran both `sudo apt update` and `sudo apt upgrade` to make sure the OS is fully updated.

## 2.0 Web Terminal
I set up [ShellInABox](https://github.com/shellinabox/shellinabox) as I quickly got tried of using PowerShell to ssh in. For me ShellInABox is just a really nice quality of life tool.
> Something to note it that "__ShellInABox__" is fork of the original "__Shell In A Box__" because the original project was not maintained by the authorized author.

## 3.0 Portainer / Docker
[Raspberry pi how to install docker & portainer](https://www.wundertech.net/portainer-raspberry-pi-install-how-to-install-docker-and-portainer/)

## 4.0 Nginx Porxy Manager & BitWarden
[Nginx Proxy Manager Raspberry Pi Install](https://www.wundertech.net/nginx-proxy-manager-raspberry-pi-install-instructions/)
[Self Host Bitwarden on a Raspberry Pi](https://www.wundertech.net/how-to-self-host-bitwarden-on-a-raspberry-pi/)
