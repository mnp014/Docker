# Problem:
A recurring problem might occur with Docker Machine. i.e Every few days the docker-machine timeouts and will not be able to recover it once this happens.

Example
```
docker-machine ls
NAME      ACTIVE   DRIVER       STATE     URL   SWARM   DOCKER   ERRORS
default            virtualbox   Timeout
```
Environment Info
```
uname -a                 UserName MBPR 15.4.0 Darwin Kernel Version 15.4.0: Fri Feb 28 22:08:05 PST 2016; root:xnu-3248.40.184~3/RELEASE_X86_64 x86_64
docker version           1.11.0
docker-machine version   0.7.0
vboxmanage --version     5.0.20r106931
```
#### Attempted Solutions:
Tried the following things in no particular order:

 - Restarting the docker machine.
 - Running
   ```
   eval $(docker-machine env default) 
   ```
 - Regenerating the certificates
   ```
   docker-machine regenerate-certs default
   ```
 - Restarting my host box.
 - Upgrading Docker.
 - Reinstalling Docker.
 - Upgrading VirtualBox.
 - Removing all VirtualBox host-only network devices.

#### WorkAround:
destroy the docker machine and recreating it.
**Note:** This destroys all the images and containers, and it is very time consuming to set it up again.
 ```
 docker-machine rm -y default && docker-machine create -d virtualbox default && eval $(docker-machine env)
 ```

# Fix:
Run: 
 ```
 docker-machine ls -t 20
 ```
 or
 ```
 $ docker-machine restart

 $ eval $(docker-machine env)
 ```
 or
 ```
 https://www.digitalocean.com/community/tutorials/how-to-configure-the-linux-firewall-for-docker-swarm-on-ubuntu-16-04
 ```
