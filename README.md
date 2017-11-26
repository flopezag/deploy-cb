# <a name="top"></a>FIWARE IoT Hackathon content
[![License badge](https://img.shields.io/badge/license-Apache_2.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

Ansible paybooks to deploy and configure server and the installation and configuration
of docker and docker-compose over ubuntu server and install Orion and MongoDB as 
database in a FIWARE Lab [FIWARE Lab](https://cloud.lab.fiware.org) cloud.

If you want to obtain more information about FIWARE Orion Context Broker please visit 
the following web sites:
- [Orion Context Broker](https://fiware-orion.readthedocs.io)


## How to start it

- Create virtualenv and activate it:
```
virtualenv -p python2.7 $NAME_VIRTUAL_ENV
source $NAME_VIRTUAL_ENV/bin/activate
```
- Install the pre-requisites:
```
pip install -r requirements.txt
```
- Then install tempest+ralli on the node (I have noticed that sometimes it takes a while 
for the ssh-server on the nodes to start, therefore if you get an initial ssh-error, 
wait a few minutes and try again).
```
      ansible-playbook -vvvv -i inventory.yml \
      --private-key=(Key pair to access to the instance) \
      deploy-cb.yml
```
- Once this has finished successfully your IoT Platform instance server is ready to use. 
You can access your instance through the execution of the command:
```
ssh -i <YOUR SSH KEY.pem>` ubuntu@<IP of your instance>
```
And now just activate the docker-compose executing:
```
sudo docker-compose up
```
In the directory /home/ubuntu in which is located the file docker-compose.yml.

Now just enjoy FIWARE.


## How to play with it

Firstly, be sure that you have installed [curl](https://curl.haxx.se/) program 
and [jq](https://stedolan.github.io/jq/download/).



## License

These scripts are licensed under Apache License 2.0.
