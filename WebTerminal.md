
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
