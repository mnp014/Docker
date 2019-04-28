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
  
