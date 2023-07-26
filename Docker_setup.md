
# Installing Docker Desktop 
```
1. Install Docker Desktop on Windows 
```

[Docker Intallation URL](https://docs.docker.com/desktop/install/windows-install/)


``` 
2. Run intaller.exe
```

```
3. Restart computer after running intallation
```

```
4. Open GitBash terminal and check Docker Version 
```

### Command to check Docker Version

`docker --version`

![Alt text](images/Docker_version.png)

```
5. create a docker hub account using the link below
```
[Docker Hub Account URL](https://login.docker.com/u/login/identifier?state=hKFo2SB0b0Z4T1piY3dReVUwWFlDTU1kVk9yOFV5dGJMM1F4V6Fur3VuaXZlcnNhbC1sb2dpbqN0aWTZIHpMck9zZUFvY0ZocGxQbVlSeDBNVEtwQWI4LVhvNnhio2NpZNkgbHZlOUdHbDhKdFNVcm5lUTFFVnVDMGxiakhkaTluYjk)

```
6. User name: ks21
```

```
7. enable the windows subsystem for linux

dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart

```

```
8. check requirements for running WSL 2

windows logo key + R

```
```
9. enable virtual machine feature

dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart

```

```
10. download the linux kernel update package

wsl.exe --install

wsl.exe --update

```

```
11. set WSL 2 as your default version

wsl --set-default-version 2

```

```
12. ready to open docker

```
![Alt text](<images/docker home .png>)


