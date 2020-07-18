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
  
  
-----
  
 
 - [Create Docker-machine](https://github.com/mnp014/Docker/blob/master/Docker%20Machine/Create%20docker%20machine.md)
 - [Clean local Docker-machine env](https://github.com/mnp014/Docker/blob/master/Docker%20Machine/Clean%20local%20docker%20env.md)
 - [Config file path](https://github.com/mnp014/Docker/blob/master/Docker%20Machine/Config%20file%20path.md)
 - [Delete Docker-machine](https://github.com/mnp014/Docker/blob/master/Docker%20Machine/Delete%20Create%20docker%20machine.md)
 - [Docker machine timeout - how to fix without destroying the machine?]()
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
 
