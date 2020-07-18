You must use the IP of the **docker-machine** itself as follow:
```
>         curl $(docker-machine ip demo-machine):80
```
**NOTE:** The docker commands are **not** run locally, they are run on the docker-machine
```
> curl localhost:80
curl: (7) Failed to connect to localhost port 80: Connection refused
```

