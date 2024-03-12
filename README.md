# Instruction to setup an example in HPE Swarm Learning:

![image](https://github.com/PNg-HA/Swarm_Learning/assets/93396414/e8875386-aff7-4a75-9760-7e13cb3c38c8)


![image](https://github.com/PNg-HA/Swarm_Learning/assets/93396414/8f843d02-1e2f-4729-ae51-a32d60effce4)

Click "Copy CURL". Download apls.zip in CentOS vm. (currently version 7).

## Install APLS in Ubuntu 20.04 LTS
Unzip with `unzip apls-file -d folder-extracted` command. If not have unzip yet, install it with `sudo apt-get install unzip`. Then `cd UNIX` and `chmod +x setup.bin`. Then run `sudo ./setup.bin`.
If you deal with this error:
![image](https://github.com/PNg-HA/Swarm_Learning/assets/93396414/47d10410-2856-4655-8fb8-c756b36fa61b)

Then `sudo apt-get install openjdk-8-jre` (remeember to sudo apt-get update & upgrade first). Then run again `sudo ./setup.bin -i silient`. Keep entering for those phrases asking "Enter":
![image](https://github.com/PNg-HA/Swarm_Learning/assets/93396414/192d3da4-cbca-4054-936f-b0ba133a041d)


If install successfully, you will receive:

![image](https://github.com/PNg-HA/Swarm_Learning/assets/93396414/980c0527-3ccd-4619-b6b7-61d183ff44c8)
![image](https://github.com/PNg-HA/Swarm_Learning/assets/93396414/fb8788c6-933d-42ec-bdfd-1e1017c8cc9a)
![image](https://github.com/PNg-HA/Swarm_Learning/assets/93396414/d0dcc7e7-ab95-47f0-b771-f9cd3b0eea8d)


Then go to the directory below and enter the command below:

![image](https://github.com/PNg-HA/Swarm_Learning/assets/93396414/3bc5e484-1699-451b-9337-1c91dea0f685)

Although status is "not running", but APLS is actually running:
![image](https://github.com/PNg-HA/Swarm_Learning/assets/93396414/bbf11f4f-e790-4daf-b6af-4e8936106029)


## Continue to the setup process
Note down the lock code. Then go to HPE Software Center. Search for ai swarm-learning.

Choose "Get license". Activate the key using the lock code (remember one lock code one account). Download all.
![image](https://github.com/PNg-HA/Swarm_Learning/assets/93396414/e7b82243-b8a8-46b0-b8e5-dea5e9f27256)

![image](https://github.com/PNg-HA/Swarm_Learning/assets/93396414/ecf44d44-0391-4246-932e-8cb58014e5bd)
![image](https://github.com/PNg-HA/Swarm_Learning/assets/93396414/2d27b542-dba4-4264-ae0c-e03d969125ba)

In the apls browser, browse and choose .DAT file. 

![image](https://github.com/PNg-HA/Swarm_Learning/assets/93396414/de8b641f-ea1e-4bab-b86e-13c38bd0d095)

Choose all licenses and clicked Install.
![image](https://github.com/PNg-HA/Swarm_Learning/assets/93396414/c38d9d35-5d69-41de-9f79-fb0eabe893b3)

The result:

![image](https://github.com/PNg-HA/Swarm_Learning/assets/93396414/8f498aff-c48b-4a1c-a276-adf918129f88)

/ Archived of old version
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

Mở port cho fw trên vm apls (centos): 
	firewall-cmd --zone=public --add-port=5814/tcp --permanent
	firewall-cmd --reload
Mở port cho fw trên vps: sudo ufw allow <port>

APLS_IP=172.30.31.2
SN_1_IP=192.168.120.235
SN_2_IP=192.168.120.118
HOST_1_IP=192.168.120.235
HOST_2_IP=192.168.120.118
SN_API_PORT=30304
SN_P2P_PORT=30303

mkdir workspace; cp -r examples/mnist workspace/; cp -r examples/utils/gen-cert workspace/mnist/

![image](https://github.com/PNg-HA/Swarm_Learning/assets/93396414/c5c6cffd-cfc1-4ef9-882c-c74b25b34294)

./workspace/mnist/gen-cert -e mnist -i 1

![image](https://github.com/PNg-HA/Swarm_Learning/assets/93396414/5338c280-8800-428f-9787-895a817ffc31)


docker network create host-1-net

sed -i "s+<PROJECT-MODEL>+$(pwd)/workspace/mnist/model+g" workspace/mnist/swci/taskdefs/swarm_mnist_task.yaml

sed -i "s+<SWARM-NETWORK>+host-1-net+g" workspace/mnist/swop/swop1_profile.yaml


sed -i "s+<HOST_ADDRESS>+${HOST_1_IP}+g" workspace/mnist/swop/swop1_profile.yaml

sed -i "s+<LICENSE-SERVER-ADDRESS>+${APLS_IP}+g" workspace/mnist/swop/swop1_profile.yaml

sed -i "s+<PROJECT>+$(pwd)/workspace/mnist+g" workspace/mnist/swop/swop1_profile.yaml 

sed -i "s+<PROJECT-CERTS>+$(pwd)/workspace/mnist/cert+g" workspace/mnist/swop/swop1_profile.yaml

sed -i "s+<PROJECT-CACERTS>+$(pwd)/workspace/mnist/cert/ca/capath+g" workspace/mnist/swop/swop1_profile.yaml

create a Docker volume and copy Swarm Learning wheel file:
docker volume rm sl-cli-lib
docker volume create sl-cli-lib
docker container create --name helper -v sl-cli-lib:/data hello-world
docker cp -L lib/swarmlearning-client-py3-none-manylinux_2_24_x86_64.whl helper:/data
docker rm helper

 On host-1, run SN node (SN1):
sudo ./scripts/bin/run-sn -d --rm --name=sn1 \
--network=host-1-net --host-ip=${HOST_1_IP} \
--sentinel --sn-p2p-port=${SN_P2P_PORT} \
--sn-api-port=${SN_API_PORT} \
--key=workspace/mnist/cert/sn-1-key.pem \
--cert=workspace/mnist/cert/sn-1-cert.pem \
--capath=workspace/mnist/cert/ca/capath \
--apls-ip=${APLS_IP}

![image](https://github.com/PNg-HA/Swarm_Learning/assets/93396414/e5b5b800-8032-44a9-bd55-d0bd8708f19f)

docker logs -f <sn-container-id>. Wait until `swarm.blCnt : INFO : Starting SWARM-API-SERVER on port: 30304` show up:

![image](https://github.com/PNg-HA/Swarm_Learning/assets/93396414/4dcc1aa6-81a8-4c73-95b6-cecaad8751e8)


Run SWOP:
sudo ./scripts/bin/run-swop -d --rm --name=swop1 --network=host-1-net \
--sn-ip=${SN_1_IP} --sn-api-port=${SN_API_PORT} \
--usr-dir=workspace/mnist/swop --profile-file-name=swop1_profile.yaml \
--key=workspace/mnist/cert/swop-1-key.pem \
--cert=workspace/mnist/cert/swop-1-cert.pem \
--capath=workspace/mnist/cert/ca/capath -e SWOP_KEEP_CONTAINERS=True -e http_proxy= -e https_proxy= \
--apls-ip=${APLS_IP}

Run SWCI
sudo ./scripts/bin/run-swci --name=swci1 --network=host-1-net \
--usr-dir=workspace/mnist/swci --init-script-name=swci-init \
--key=workspace/mnist/cert/swci-1-key.pem \
--cert=workspace/mnist/cert/swci-1-cert.pem \
--capath=workspace/mnist/cert/ca/capath \
-e http_proxy= -e https_proxy= --apls-ip=${APLS_IP}

You can monitor the containers with SLM-UI:
![image](https://github.com/PNg-HA/Swarm_Learning/assets/93396414/a8b916ff-c484-4db6-8cf4-f4edaa66661b)


### Troubleshooting diary:

#### 1. One VPS (pc1) cannot go to SLM-UI, the other (pc2) can:
![image](https://github.com/PNg-HA/Swarm_Learning/assets/93396414/a4cc92b0-d8e3-497c-9aa4-4c263766ef0d)

I check "ip route" of both and see the last line different:

![image](https://github.com/PNg-HA/Swarm_Learning/assets/93396414/992f91f4-f2ae-4b9d-9800-48c8baa0d517)

Then I delete that route and it work :))
![image](https://github.com/PNg-HA/Swarm_Learning/assets/93396414/92789f1a-f902-4dbb-b12d-77c43a482e29)

