# Development Environment Setup (WSL 2)

## Required Programs
- WSL 2
- Docker


## Enable WSL 2 (Windows Subsystem for Linux)
Open PowerShell as Administrator (Start menu > PowerShell > right-click > Run as Administrator) and enter this command:  
  
Terminal: `PowerShell`  
  
Command:  
```powershell
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```

## Install Ubuntu
Terminal: `PowerShell`  
  
Command:  
```powershell
wsl --install
```

**once you open Ubuntu for the first time, **skip** creating a new UNIX username*  
  
If you want to remove old versions of Ubuntu, run the commands below:  
Terminal: `PowerShell`  
  
Command:  
```powershell
wsl --unregister Ubuntu
wsl --install -d Ubuntu
wsl --set-default Ubuntu
```

## Open Ubuntu in VS Code
Terminal: `Ubuntu`  
  
Command:  
```sh
code .
```

## Configure Git Credentials
Terminal: `Ubuntu`  
  
Command:  
```sh
git config --global user.name "example-username"
git config --global user.email "example@gmail.com"
```

## SSH Key Generation for Github
Terminal: `Ubuntu`  
  
Command:  
```sh
ssh-keygen -f ~/.ssh/id_rsa -P "" && clear && echo -e "Copy and paste the public key below to your GitHub account:\n\n\e[32m$(cat ~/.ssh/id_rsa.pub) \e[0m\n" # Green
```

*copy & paste the generated SSH key to your GitHub account

## Test SSH Connection
Terminal: `Ubuntu`  
  
Command:  
```sh
ssh -T git@github.com -o StrictHostKeyChecking=no
```

Expected output:
```
Hi <username>! You've successfully authenticated, but GitHub does not provide shell access.
```

## Download and Run the Script
Terminal: `Ubuntu`  
  
Command:  
```sh
curl -o script.sh https://raw.githubusercontent.com/judestp/alpha-tokyo-dev-env-setup/main/script.sh && sh script.sh
```

## "asdf: command not found"

  Once you encounter `asdf: command not found`, close the terminal and rerun the script

  *restart the terminal after ASDF installation then rerun the script.sh to continue
