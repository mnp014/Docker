#### Step 1:
 - Remove the executable: 
```
>     rm $(which docker-machine)
```
#### Optionally:
 - Remove the machines you created.  
   - To remove each machine individually: 
      ```
      >     docker-machine rm <machine-name>
      ```  
  
   - To remove all machines:  

      ```
      >     docker-machine rm -f $(docker-machine ls -q)
      ```  
**NOTE:** Use `-force` option if required on Windows
