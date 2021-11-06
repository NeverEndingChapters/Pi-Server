
## 3.0 Web Terminal
I set up [ShellInABox](https://github.com/shellinabox/shellinabox) as I quickly got tried of using PowerShell to ssh in. you can use `sudo apt install shellinabox` to install ShellInABox. 

[Installing ShellInABox](https://www.tecmint.com/shell-in-a-box-a-web-based-ssh-terminal-to-access-remote-linux-servers/)

1. check if you can install shellinabox with `sudo apt-cache search shellinabox`
2. install shellinabox with `sudo apt-get install openssl shellinabox`
> openssl is also installed as well because shellinabox uses SSL to create secure seassions.
3. Although this step isn't needed and can be skipped. I like to do it as it increase security as this is a terminal into your server. It is simply moving what port shellingabox listens to. 
By default it listens on port 4200 you can change it by using `sudo vi /etc/default/shellinabox` 
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
when your done changing the port hit Ctrl + x it will as you to save so hit y and then enter.

4. Then you can start shellinabox with `sudo service shellinaboxd start`
5. You can verify that it is running on the correct port with `sudo netstat -nap | grep shellinabox`
6. Go to `https://localhost:5120/` and you can sign in with pi and the password that you have set

> Something to note it that "__ShellInABox__" is fork of the original "__Shell In A Box__" because the original project was not maintained by the authorized author.
