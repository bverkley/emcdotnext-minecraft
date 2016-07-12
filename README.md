# emcdotnext-minecraft

Project: EMCDotNext Team Minecraft + Docker + ScaleIO + REX-Ray demo.


## Process

This is documentation is based on Mac OSX:  
Open Terminal  
Create a projects folder "mkdir projects"  

## Persistent Storage
For the persistent storage part of this demo, we will be using the EMC{CODE} Vagrant Package.  You will need to install the following vagrant-triggers plugin:

vagrant plugin install vagrant-triggers

In the projects folder run  

 git clone https://github.com/emccode/vagrant  

cd into the projects folder  
cd into the scaleio folder and run:  

vagrant up

This process will automatically deploy three CentoOS 7.1 nodes, download the ScaleIO 2.0 software and install a full ScaleIO Cluster with GUI. It will also setup Docker and REX-Ray  

You can find more documentation on this setup here: https://github.com/emccode/vagrant/tree/master/scaleio    

Once ScaleIO is done, you can launch the GUI - projects/vagrant/scaleio/gui/run.sh. (Just use Finder on your Mac and drag the run.sh file into Terminal and hit enter)    

## Minecraft

Once ScaleIO is up and running, and you've verified it with the GUI - SSH into one of the CentOS servers
vagrant ssh tb (this is the tiebreaker node, you can use the mdm1 or mdm2 node if you want as well)  

docker pull vtexan/emcdotnext-minecraft  

this will download and setup minecraft 1.10.2 and we've altered the server.properties of this game with spawn-monsters=off for demo purposes.  You can edit the server.properties=true if you want to play the game with monsters.  

## How to startup Minecraft

docker run -ti -p 25565:25565 dotnext-monecraft (or whatever you called the minecraft docker container)  

## Maintainer  
* Tommy Trogden = @vtexan  
