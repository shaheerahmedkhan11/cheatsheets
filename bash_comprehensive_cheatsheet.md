# Bash Comprehensive Cheatsheet

## Basic Commands
- `pwd`: Print current working directory
- `ls`: List directory contents
- `cd [dir]`: Change directory to `dir`
- `cp [source] [destination]`: Copy files or directories
- `mv [source] [destination]`: Move or rename files or directories
- `rm [file]`: Remove file
- `mkdir [dir]`: Create new directory `dir`
- `rmdir [dir]`: Remove empty directory `dir`
- `touch [file]`: Create an empty file or update the timestamp of the file

## File Viewing
- `cat [file]`: Concatenate and display file content
- `less [file]`: View file content one page at a time
- `more [file]`: Similar to `less`, but with limited navigation
- `head [file]`: Display the first 10 lines of `file`
- `tail [file]`: Display the last 10 lines of `file`
- `tail -f [file]`: Continuously display the last lines of `file` as it grows

## File Permissions
- `chmod [permissions] [file]`: Change the file permissions
  - Example: `chmod 755 [file]`
- `chown [owner]:[group] [file]`: Change the file owner and group
  - Example: `chown user:group [file]`
- `chgrp [group] [file]`: Change the group ownership of the file

## Searching
- `grep [pattern] [file]`: Search for `pattern` in `file`
  - Example: `grep "hello" file.txt`
- `find [path] -name [pattern]`: Find files by `name` in `path`
  - Example: `find /home -name "*.txt"`
- `locate [name]`: Find files by name using the locate database

## Process Management
- `ps`: Display current processes
- `top`: Display and manage running processes
- `kill [pid]`: Terminate process with process ID `pid`
- `killall [name]`: Terminate all processes with name `name`
- `bg`: Resume a suspended job in the background
- `fg`: Bring a background job to the foreground
- `&`: Run a command in the background
  - Example: `command &`

## Networking
- `ping [host]`: Send ICMP ECHO_REQUEST to network hosts
- `ifconfig`: Display or configure network interfaces
- `netstat`: Print network connections, routing tables, interface statistics
- `ssh [user]@[host]`: Open SSH connection to `host` as `user`
- `scp [source] [destination]`: Securely copy files between hosts
  - Example: `scp file.txt user@remote:/path/to/destination`
- `ssh-keygen`: Generate a new SSH key pair
- `ssh-copy-id [user]@[host]`: Copy your SSH public key to a remote host

## Compression
- `tar -cvf [archive.tar] [file]`: Create a tarball
- `tar -xvf [archive.tar]`: Extract a tarball
- `gzip [file]`: Compress file using gzip
- `gunzip [file.gz]`: Decompress gzip file

## Text Processing
- `awk '{print $1}' [file]`: Pattern scanning and processing language
  - Example: `awk '{print $1}' file.txt`
- `sed 's/[pattern]/[replacement]/' [file]`: Stream editor for filtering and transforming text
  - Example: `sed 's/old/new/' file.txt`
- `cut -d[delimiter] -f[field] [file]`: Remove sections from each line of files
  - Example: `cut -d':' -f1 /etc/passwd`

## Disk Usage
- `df -h`: Display disk space usage in human-readable format
- `du -h [path]`: Estimate file space usage

## Shell Scripting
- `#!/bin/bash`: Define the shell to interpret the script
- `echo [text]`: Print text to the terminal
- `read [variable]`: Read input from the terminal into a variable
- `variables`: Define variables without spaces around the `=`
  - Example: `myvar="Hello"`
- `if [ condition ]; then ... fi`: Conditional statements
- `for [variable] in [list]; do ... done`: For loops
- `while [ condition ]; do ... done`: While loops
- `function name { ... }`: Define a function

## Miscellaneous
- `alias [name]='[command]'`: Create an alias for a command
  - Example: `alias ll='ls -lah'`
- `history`: Display command history
- `!!`: Repeat the last command
- `!n`: Repeat the `n`th command from history
- `man [command]`: Display the manual page for a command

## Redirection
- `>`: Redirect output to a file, overwriting the file
  - Example: `echo "Hello" > file.txt`
- `>>`: Redirect output to a file, appending to the file
  - Example: `echo "Hello" >> file.txt`
- `<`: Redirect input from a file
  - Example: `cat < file.txt`
- `|`: Pipe the output of one command into another
  - Example: `ls | grep "pattern"`

## Environment Variables
- `export [variable]=[value]`: Set environment variable
- `echo $[variable]`: Print the value of an environment variable
  - Example: `echo $PATH`

## Package Management (Debian-based systems)
- `apt-get update`: Update package index
- `apt-get upgrade`: Upgrade installed packages
- `apt-get install [package]`: Install new package
- `apt-get remove [package]`: Remove installed package
- `apt-get search [keyword]`: Search for packages

## Package Management (Red Hat-based systems)
- `yum update`: Update package index and upgrade installed packages
- `yum install [package]`: Install new package
- `yum remove [package]`: Remove installed package
- `yum search [keyword]`: Search for packages

## Job Control
- `jobs`: List current jobs
- `ctrl + z`: Suspend the current foreground job
- `ctrl + c`: Kill the current foreground job

## System Information
- `uname -a`: Display system information
- `hostname`: Display or set the system's hostname
- `uptime`: Show how long the system has been running
- `dmesg`: Print kernel ring buffer messages
- `whoami`: Display the current user

## Date and Time
- `date`: Display or set the system date and time
- `cal`: Display a calendar

## Systemd Commands
- `systemctl [command] [unit]`: Control the systemd system and service manager
  - Example: `systemctl start nginx`
- `systemctl start [service]`: Start a service
- `systemctl stop [service]`: Stop a service
- `systemctl restart [service]`: Restart a service
- `systemctl reload [service]`: Reload the configuration of a service without restarting
- `systemctl enable [service]`: Enable a service to start at boot
- `systemctl disable [service]`: Disable a service from starting at boot
- `systemctl status [service]`: Show the status of a service
- `systemctl is-active [service]`: Check if a service is active
- `journalctl -u [service]`: View logs for a specific service

## SSH Commands
- `ssh [user]@[host]`: Open SSH connection to `host` as `user`
- `ssh-keygen`: Generate a new SSH key pair
- `ssh-copy-id [user]@[host]`: Copy your SSH public key to a remote host
- `scp [source] [destination]`: Securely copy files between hosts
  - Example: `scp file.txt user@remote:/path/to/destination`
- `sftp [user]@[host]`: Open SFTP connection to `host` as `user`
- `ssh-agent`: Start the SSH agent
- `ssh-add [key]`: Add a private key to the SSH agent

Keep this cheatsheet handy for quick reference to common Bash commands and operations.