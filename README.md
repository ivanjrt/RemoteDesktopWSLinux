Follow these steps here To enable WSL.  https://github.com/ivanjrt/WSL2-PlatformREQ-Installer <br/>

In this case I will show you how to do the Ubuntu 18 WSL version for Windows 10 <br/>

*   Go to the Store within Windows Install Ubuntu <br/>
*   Once installed. Open the consolea copy/pase all the below line by line <br/>
*   _It Will ask you to create credentials. Very Important to remember it._


``` Javascript
	sudo apt-get install xrdp
	sudo apt-get install xfce4
	sudo apt-get install xfce4-terminal
	sudo sed -i.bak '/fi/a #xrdp multiple users configuration \n xfce-session \n' /etc/xrdp/startwm.sh
	sudo adduser xrdp ssl-cert  
	sudo ufw allow 3389/tcp
	sudo iptables -A INPUT -p tcp --dport 3389 -j ACCEPT
	sudo netfilter-persistent save
	sudo /etc/init.d/xrdp restart
```

Once done, open "Remote Desktop Connection" and type the IP address for your Linux WSL. if you dont know it run this within the console
```
ifconfig
```

type that IP in the Remote desktop, and your credentials. Boom! is done!







