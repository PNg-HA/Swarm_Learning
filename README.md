![image](https://github.com/PNg-HA/Swarm_Learning/assets/93396414/e8875386-aff7-4a75-9760-7e13cb3c38c8)


![image](https://github.com/PNg-HA/Swarm_Learning/assets/93396414/8f843d02-1e2f-4729-ae51-a32d60effce4)


Click "Copy CURL". Download apls.zip in CentOS vm. (currently version 7).

Note down the lock code. Then go to HPE Software Center. Search for ai swarm-learning.

Choose "Get license". Activate the key using the lock code (remember one lock code one account). Download all.

![image](https://github.com/PNg-HA/Swarm_Learning/assets/93396414/ecf44d44-0391-4246-932e-8cb58014e5bd)
![image](https://github.com/PNg-HA/Swarm_Learning/assets/93396414/2d27b542-dba4-4264-ae0c-e03d969125ba)

In the apls browser, browse and choose .DAT file. 

![image](https://github.com/PNg-HA/Swarm_Learning/assets/93396414/de8b641f-ea1e-4bab-b86e-13c38bd0d095)



Choose all licenses and clicked download.

![image](https://github.com/PNg-HA/Swarm_Learning/assets/93396414/c01cfa89-03f0-4ed1-af76-9f8b1368da61)

Now run the SLM_UI_installer (Linux or Windows, I choose Wins). It will open a web. The requirement:

![image](https://github.com/PNg-HA/Swarm_Learning/assets/93396414/54b96736-2666-4741-a3bd-00f39c8a3557)

The docker registry (using email activate the lock code):

![image](https://github.com/PNg-HA/Swarm_Learning/assets/93396414/540fabee-45eb-4815-9eaa-2149601f5cd2)


Now I install the SLM_UI in an Ubuntu Desktop 20.04 vm. First I have to install docker, make it run for normal user. Login docker hub from terminal.
https://docs.docker.com/engine/install/ubuntu/
https://docs.docker.com/engine/install/linux-postinstall/
Then create folder /opt/hpe/swarm-learning with mkdir -p and give it write permission with chmod +w
Then enable ssh: `sudo apt install openssh-server`, `sudo systemctl enable ssh`, `sudo ufw allow ssh`
and configure for ssh for root for the Ubun vm following the link: https://linuxconfig.org/allow-ssh-root-login-on-ubuntu-20-04-focal-fossa-linux

Now get the ip of the Ubun: 

![image](https://github.com/PNg-HA/Swarm_Learning/assets/93396414/629c60f6-72cd-480a-aaf9-7a9433db6aeb)

Then fill in the SLM_UI_installer browser and click Run: 

![image](https://github.com/PNg-HA/Swarm_Learning/assets/93396414/3412a0cd-5dae-4ff4-bff4-5995e85a1665)

Then click next. Summary:

![image](https://github.com/PNg-HA/Swarm_Learning/assets/93396414/80b92914-bc85-4b4a-98e9-7898c9144f8b)
![image](https://github.com/PNg-HA/Swarm_Learning/assets/93396414/17bf3df3-34ea-4783-8852-de77aae743f5)

Then it open a web, default admin:admin 

![image](https://github.com/PNg-HA/Swarm_Learning/assets/93396414/880d41a0-b0fb-4367-bb55-c0783b2a419d)


![image](https://github.com/PNg-HA/Swarm_Learning/assets/93396414/2e0110c0-56ad-4c2c-8fca-d824d02eadcf)


