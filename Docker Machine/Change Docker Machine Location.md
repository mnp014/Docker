Docker machine location can be changed by moving `.docker` directory to another drive and creating a junction point to it.
---
#### Step 1:
```
Move `.docker` directory from `source dir` to `destination dir`
```
Example:
```
Move `.docker` directory from `C:\Users\username` to `D:\`
```
---
#### Step 2:
Run:
```
>       C:\Users\username>mklink /j .docker < D:\Destination Path >\.docker
```

Example:
```
C:\Users\username>mklink /j .docker D:\.docker
Junction created for .docker <<===>> D:\.docker
```
