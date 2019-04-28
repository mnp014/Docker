### Switching using docker-machine/Box name:

 - Multiple `docker-machine` can be created and run at any point in time.
 - `docker` runs within `docker-machine`(s).</br>
 - `docker-machine ssh <docker-machine name>` is used to get inside docker-machine, where you can run docker commands like `docker image ls`</br>
 -  `exit` command is used to exit the docker machine.</br>
 
 - One docker machine can be ACTIVE at a time i.e outside shell/cmdprompt/PS can be attached to one `docker-machine` at a time.
 - `eval $(docker-machine env <docker-machine name>)` command can be used to select the active docker-machine.
 - **NOTE:**</br>
   `ACTIVE` means the current `docker-machine/Box` in use.</br>
   `RUNNING` means the State of the individual `docker-machine(s)/Box(s)`,  say (running/stopped). 
   
   ---
    ### Add alias for switching command:
    
    #### Step 1:
    Open .bashrc using any editor
    ```
           $ sudo nano .bashrc
    ```
    
    #### Step 2:
    Add following in the bottom. Save and exit.
    ```
           alias docker-machine-<SomeName>='eval $(docker-machine env <docker-machine name>)'
    ```
    where `docker-machine-<SomeName>` is the alias for the command `eval $(docker-machine env <docker-machine name>)`
    
    #### Step 3:
    commit bashrc file
    ```
           $ source .bashrc
    ```  
    
    #### Step 4:
    Use alias instead of command to switch
    ```
           $  docker-machine-<SomeName>
    ```
    
    #### Step 5:
    Confirm switch:
    ```
           $ docker-machine ls
    ```
    the `docker-machine` with the name `<SomeName>` must have `*` symbol in the `ACTIVE` column.
    
    ---
    
    
    
