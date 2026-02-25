# SSH into VirtualBox VM (VSCode + Port 2222)

## VirtualBox NAT Port Forwarding

Name: SSH  
Protocol: TCP  
Host IP: 127.0.0.1  
Host Port: 2222  
Guest IP:  
Guest Port: 22  

---

## Linux VM: Install & Enable SSH

```bash
sudo apt update
sudo apt install openssh-server -y
sudo systemctl enable ssh
sudo systemctl start ssh
sudo systemctl status ssh
```

## VSCode Host Machine

File (VSCode ssh config file):
`C:\Users\ediso\.ssh\config`

```
Host localhost
  HostName localhost
  User edison
  Port 2222
```

If connection fails with a host key error, run:

`ssh-keygen -R "[localhost]:2222"`

# Alias for libraries
# Bash Aliases Setup

To use the provided bash aliases on a Linux machine:

1. Copy the file to your home directory:
  ```
  cp /path/to/.aliases ~/.aliases
  ```

2. Add the following lines to your `~/.bashrc` file:
  ```bash
  if [ -f ~/.aliases ]; then
     . ~/.aliases
  fi
  ```

On if on VSCode, you can open the file GUI with `code ~/.bashrc`

This will load your custom aliases every time you start a new bash session.

