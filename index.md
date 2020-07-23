# AIS3 environment

## Virtual Machine prepared by AIS3
### VM1
- Download: [Link](https://)
- Default user/password: ais3/ais32020
- OS: Ubuntu 20.04 Desktop
- package
	1. git
	2. python3
    3. python2
	3. docker
	4. BloodHoundAD
	5. neo4j
	6. proxychains
	7. hashcat
	8. freerdp2-x11
	9. Maltego
	10. maltego-trx

----------
## Package list
### package in Linux
- git
	- version: 2.25.1
- python3
	- version: 3.8.2
- python2
    - version: 2.7.17
- docker
    - version: 19.03.8
- BloodHoundAD
	- https://github.com/BloodHoundAD/BloodHound
- neo4j
    - version: 4.0.6
    - default user/password: neo4j/neo4j
- proxychains
	- https://github.com/haad/proxychains
- hashcat
    - version: 5.1.0
- freerdp2-x11
  - version: 2.1.1
- Maltego

  - 請自行註冊 Maltego 帳號
  - https://www.maltego.com/ce-registration/
- maltogo-trx

### package in Windows

- VMware workstation
	- version: 15 Pro
	- Need to install in your NB
	- https://www.vmware.com/go/getworkstation-win

### Install script in Ubuntu 20.04 Desktop
```bash
wget -O - https://debian.neo4j.com/neotechnology.gpg.key | apt-key add -
echo 'deb https://debian.neo4j.com stable 4.0' | tee /etc/apt/sources.list.d/neo4j.list
apt-get update

apt-get install \
docker.io=19.03.8-0ubuntu1.20.04 \
git=1:2.25.1-1ubuntu3 \
python2=2.7.17-2ubuntu4 \
neo4j=1:4.0.6 \
hashcat=5.1.0+ds1-2 \
freerdp2-x11=2.1.1+dfsg1-0ubuntu0.20.04.1 \
python3-pip

git clone https://github.com/BloodHoundAD/BloodHound
git clone https://github.com/haad/proxychains

cd proxychains/
./configure
make
sudo make install

wget https://maltego-downloads.s3.us-east-2.amazonaws.com/linux/Maltego.v4.2.11.13104.deb
dpkg -i Maltego.v4.2.11.13104.deb

pip3 install maltego-trx
```
