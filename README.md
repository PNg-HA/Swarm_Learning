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
and configure for ssh for root for the Ubun vm: `nano /etc/ssh/sshd_config`:

![image](https://github.com/PNg-HA/Swarm_Learning/assets/93396414/66465dc8-d7e5-4072-bf37-52573c333272)

![image](https://github.com/PNg-HA/Swarm_Learning/assets/93396414/629c60f6-72cd-480a-aaf9-7a9433db6aeb)
