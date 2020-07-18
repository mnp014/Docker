#### Using SCP:
 - Copy from **local** to **home folder of docker-machine**:
    ```
    >     docker-machine scp ~/<sample.txt> <machine-name>:~/
    ```
 - Copy from **docker-machine** to **home folder of local**:
    ```
    >     docker-machine scp <machine-name>:~/<sample.txt> ~/
    ```
---
    
#### Example:
    
  - `local` --> `docker-machine`
    ```
    >     docker-machine scp ~/sample.txt machine-name:~/root/
    ```
  - `docker-machine` --> `local`
    ```
    >     docker-machine scp machine-name:~/sample.txt ~/root/ 
    ```
