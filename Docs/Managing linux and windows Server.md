# Managing Linux and Windows Server


## Table of Contents


1. [Introduction](#introduction)
2. [Prerequisites](#prerequisites)
3. [Managing Linux Server](#managing-linux-server)
    - [Connecting to the Server](#connecting-to-the-server)
    - [Basic Commands](#basic-commands)
    - [User Management](#user-management)
    - [Package Management](#package-management)
    - [Service Management](#service-management)
4. [Managing Windows Server](#managing-windows-server)
    - [Connecting to the Server](#connecting-to-the-server-1)
    - [Basic Commands](#basic-commands-1)
    - [User Management](#user-management-1)
    - [Package Management](#package-management-1)
    - [Service Management](#service-management-1)
5. [Conclusion](#conclusion)

## Introduction


This documentation provides a comprehensive guide on how to manage both Linux and Windows servers. It covers essential tasks such as connecting to the server, executing basic commands, managing users, handling packages, and managing services.

## Prerequisites


- Basic understanding of command-line interface (CLI)
- Administrative access to the servers
- SSH client for Linux server management
- Remote Desktop Protocol (RDP) client for Windows server management

## Managing Linux Server



### Connecting to the Server


To connect to a Linux server, use SSH:
```sh
ssh username@server_ip_address
```

### Basic Commands


- `ls` - List directory contents
- `cd` - Change directory
- `pwd` - Print working directory
- `cp` - Copy files or directories
- `mv` - Move or rename files or directories
- `rm` - Remove files or directories

### User Management
- Add a new user:
  ```sh
  sudo adduser username
  ```
- Delete a user:
  ```sh
  sudo deluser username
  ```
- Modify a user:
  ```sh
  sudo usermod -aG groupname username
  ```

### Package Management


- Update package list:
  ```sh
  sudo apt update
  ```
- Upgrade packages:
  ```sh
  sudo apt upgrade
  ```
- Install a package:
  ```sh
  sudo apt install package_name
  ```
- Remove a package:
  ```sh
  sudo apt remove package_name
  ```

### Service Management


- Start a service:
  ```sh
  sudo systemctl start service_name
  ```
- Stop a service:
  ```sh
  sudo systemctl stop service_name
  ```
- Restart a service:
  ```sh
  sudo systemctl restart service_name
  ```
- Check service status:
  ```sh
  sudo systemctl status service_name
  ```

## Managing Windows Server



### Connecting to the Server


To connect to a Windows server, use Remote Desktop Protocol (RDP):
1. Open Remote Desktop Connection.
2. Enter the server IP address and click "Connect".
3. Enter your username and password.

### Basic Commands


- `dir` - List directory contents
- `cd` - Change directory
- `copy` - Copy files
- `move` - Move or rename files
- `del` - Delete files

### User Management


- Add a new user:
  ```powershell
  net user username password /add
  ```
- Delete a user:
  ```powershell
  net user username /delete
  ```
- Modify a user:
  ```powershell
  net localgroup groupname username /add
  ```

### Package Management


- Install a package using PowerShell:
  ```powershell
  Install-Package -Name package_name
  ```
- Uninstall a package using PowerShell:
  ```powershell
  Uninstall-Package -Name package_name
  ```

### Service Management


- Start a service:
  ```powershell
  Start-Service -Name service_name
  ```
- Stop a service:
  ```powershell
  Stop-Service -Name service_name
  ```
- Restart a service:
  ```powershell
  Restart-Service -Name service_name
  ```
- Check service status:
  ```powershell
  Get-Service -Name service_name
  ```

## Conclusion


Managing Linux and Windows servers involves understanding and executing various commands for user management, package management, and service management. This documentation provides a foundational guide to help you perform these tasks efficiently.