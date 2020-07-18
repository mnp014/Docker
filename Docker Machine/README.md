#### What is docker-machine?
  Having a containerized application, it is important to be able to easily deploy them in the `cloud`, apart from running them locally using `Docker for Mac/Windows` or from a **Linux box** locally.  
  **docker-machine** is a tool which enables to create a remote virtual machine (VM) easily and manage those containers.  
  It also allows us to control the remote `docker engine` of a VM created. 
  For example: We can perform the operations like:  
   - Update the `docker engine`.
   - Restart the `virtual machine` (depending if the driver supports it)
   - View the state of `docker engine` and so on.  
  
  The main reason we would use of **docker-machine** is to create a **deployment environment** for an application and manage all the micro-services running on it.
  For instance, we can easily have a `development`, `staging` and `production` environment accessible from your own machine and update them accordingly.
  
  ##### To illustrate this with a sample docker file:
  where content of Docker-file is:  
  ```
     version: '2'
     services:
     web:
     image: dockercloud/hello-world:latest
     ports:
     - "80:80"
  ```
  
  ###### [case 1] Running docker locally:
   - Spin up the docker instance:
     ```
     docker-compose up -d
     ```
     
   - Access index.html  
     ```
     curl localhost:80
     ```
   - Stop the created container
     ```
     docker-compose down
     ```     
  ###### [case 2] Running docker remotely using docker machine:
   - Select the remote docker instance:
     ```
     eval $(docker-machine env sample-machine)
     ```
   - Validate selected environment
     ```
     docker-machine active
     ```
   - Spin up the docker instance:
     ```
     docker-compose up -d
     ```
   - Access index.html  
     ```
     curl $(docker-machine ip demo-machine):80
     ```
   - Stop the created container
     ```
     docker-compose down
     ```
  
  
  
-----
  
 - [Activate Docker-machine](https://github.com/mnp014/Docker/blob/master/Docker%20Machine/Activate%20docker-machine%20environment.md)
 - [Clean local Docker-machine env](https://github.com/mnp014/Docker/blob/master/Docker%20Machine/Clean%20local%20docker%20env.md)
 - [Config file path](https://github.com/mnp014/Docker/blob/master/Docker%20Machine/Config%20file%20path.md)
 - [Copy files between machines](https://github.com/mnp014/Docker/blob/master/Docker%20Machine/Copy%20files%20between%20machines.md)
 - [Create Docker-machine](https://github.com/mnp014/Docker/blob/master/Docker%20Machine/Create%20docker%20machine.md)
 - [Curl to docker machine in script](https://github.com/mnp014/Docker/blob/master/Docker%20Machine/Curl%20to%20docker%20machine%20in%20script.md)
 - [Delete Docker-machine](https://github.com/mnp014/Docker/blob/master/Docker%20Machine/Delete%20Create%20docker%20machine.md)
 - [Docker machine timeout - how to fix without destroying the machine?](https://github.com/mnp014/Docker/blob/master/Docker%20Machine/Docker%20machine%20timeout%20-%20how%20to%20fix%20without%20destroying%20the%20machine%3F.md)
 - [Set Active Docker-machine](https://github.com/mnp014/Docker/blob/master/Docker%20Machine/Select%20Active%20Machine.md)
 - [Start Docker-machine](https://github.com/mnp014/Docker/tree/master/Docker%20Machine)
 - [Stop Docker-machine](https://github.com/mnp014/Docker/tree/master/Docker%20Machine)
 - [Re-Start Docker-machine](https://github.com/mnp014/Docker/tree/master/Docker%20Machine)
 - [SSH into Docker-machine](https://github.com/mnp014/Docker/blob/master/Docker%20Machine/Connect%20using%20SSH.md)  
 - [Uninstall Docker-machine](https://github.com/mnp014/Docker/blob/master/Docker%20Machine/Uninstall%20Docker%20Machine.md)  
 - [View Docker-machine Env](https://github.com/mnp014/Docker/blob/master/Docker%20Machine/View%20Env%20of%20Docker-machine.md)
 - [View Active Docker machine](https://github.com/mnp014/Docker/blob/master/Docker%20Machine/View%20active%20docker%20machine.md)  
 - [View all Docker-machines](https://github.com/mnp014/Docker/blob/master/Docker%20Machine/View%20docker-machine.md)  
 
#### References:  
 - https://github.com/cnadeau/blogs/tree/master/dockermachine
 - https://www.macadamian.com/learn/docker-machine-basic-examples/#:~:text=Docker%2DMachine%20is%20a%20tool,files%20to%2Ffrom%20the%20machine.
 
