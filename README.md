# <img src="https://raw.githubusercontent.com/NeverEndingChapters/pi-server/main/Homer/images/raspberrypi.png" alt="drawing" width="80"/> Pi-Server

This is me just documenting how I setup my server cause I don't what I'm doing too well and thought it could help others. Also, there will be links thoughout to the guides I followed / used.
### **_Just as a warning this is my first time ever using GitHub and my first real project_**

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

## 3.0 Web Terminal
I set up [ShellInABox](https://github.com/shellinabox/shellinabox) as I quickly got tried of using PowerShell to ssh in. you can use `sudo apt install shellinabox` to install ShellInABox. Also I like to increase security as this is a terminal into your server by 

### 1. Move what port shellingabox listens to. 
By default it listens on port 4200 you can change it by using `sudo nano /etc/default/shellinabox` 
The line you should change looks like this by default `\/`
```
# TCP port that shellinboxd's webserver listens on 
SHELLINABOX_PORT=4200
```
for example you can change it to `\/`
```
# TCP port that shellinboxd's webserver listens on 
SHELLINABOX_PORT=5120
```
when your done changing the port hit Ctrl + x it will as you to save so hit y and then enter

### 2. Enabling SSL 




> Something to note it that "__ShellInABox__" is fork of the original "__Shell In A Box__" because the original project was not maintained by the authorized author.

## 4.0 Nginx Porxy Manager & BitWarden
[Nginx Proxy Manager Raspberry Pi Install](https://www.wundertech.net/nginx-proxy-manager-raspberry-pi-install-instructions/)
[Self Host Bitwarden on a Raspberry Pi](https://www.wundertech.net/how-to-self-host-bitwarden-on-a-raspberry-pi/)
