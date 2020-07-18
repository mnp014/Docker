*NOTE: `docker-machine` is also reffered as `Box`*

  #### Command to create `docker-machine`
  ##### Step 1:
 ```
 docker-machine create -d <virtualbox> <docker-machine_Name>
 ```
 where `-d` is driver flag </br>
 `<virtualbox>` is the driver name.</br>
 
 debug: if virtualbox is not found
 ```
 $ whereis virtualbox
 virtualbox:
 $ sudo apt-get install virtualbox
 ```

  ##### Step 2:
  ```
   $ docker-machine ls
   NAME                   ACTIVE   DRIVER       STATE     URL   SWARM   DOCKER   ERRORS
   <docker-machine_Name>  *        virtualbox   running
  ```

-----
## Shell scripts to create docker machine on different platforms:  
Step 1: 
Copy the following into `<script>.sh` file and run them as scripts 

### 1. Create on VirtualBox: 

```
#!/usr/bin/env bash
set -e
MACHINE_NAME="MACHINE NAME"
docker-machine create --driver virtualbox ${MACHINE_NAME}
```

### 2. Create on Azure:  
```
#!/usr/bin/env bash
set -e
MACHINE_NAME="VIRTUAL MACHINE NAME"
RESOURCE_GROUP="RESOURCE GROUP NAME"
SUBSCRIPTION="YOUR AZURE SUBSCRIPTION ID"
AZURE_LOCATION="eastus"
AZURE_VNET_NAME="VNET NAME"
docker-machine create --driver azure 
                      --azure-availability-set="MACHINE_NAME-as" 
                      --azure-subscription-id="${SUBSCRIPTION}" 
                      --azure-location "${AZURE_LOCATION}" 
                      --azure-open-port 80 
                      --azure-open-port 443 
                      --azure-size "${AZURE_MACHINE_SIZE}" 
                      --azure-subnet "${AZURE_VNET_NAME}-subnet" 
                      --azure-vnet "${AZURE_VNET_NAME}" 
                      --azure-resource-group "${RESOURCE_GROUP}" 
                        ${MACHINE_NAME}
```  
**NOTE:** Care has to be taken while using `docker-machine rm <machine-name>` to **delete** the **Azure virtual machine** and **all related resources** from the subscription.
just to avoid accidental resoure deletion.  

### 3. Generic command for creation:  
**NOTE:** This driver does not yet allow you to restart/shutdown the system.  
```
#!/usr/bin/env bash
set -e
MACHINE_IP="MACHINE IP"
MACHINE_NAME="MACHINE NAME"
SSH_USER="MACHINE USERNAME"
SSH_PUBLIC_KEY="MACHINE USERNAME PUBLIC KEY PATH"
# If you did an ssh-copy-id to the machine: ~/.ssh/id_rsa
docker-machine create --driver generic 
--generic-ip-address=${MACHINE_IP} 
--generic-ssh-key ${SSH_PUBLIC_KEY}
--generic-ssh-user ${SSH_USER}
${MACHINE_NAME}
```  
  
