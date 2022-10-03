---
id: 72h5htbgffig8fk3uhz5ygh
title: Linux
desc: ''
updated: 1664779077381
created: 1663825778825
---

## Why Linux?

- As per stackoverflow, Linux is the most common and the most loved platform used for development.
- Most of the devops tools primarily need Linux and most of them are released on Linux first before moving on to other operating systems.

## Linux Distributions

There are many Linux distributions available. Some of the popular ones are:

- CentOS (Open Source RHEL)
- Ubuntu
- Red Hat Enterprise Linux (RHEL)
- Fedora
- Debian

## Shell

The text-based CLI that helps you run commands to interact with the operating system is called the shell. The shell is the interface between the user and the operating system. For Linux, it's called the Linux shell.

![Shell Types](/assets/images/2022-09-22-11-41-31.png)

## Basic Commands

Cheatsheet: <https://www.guru99.com/linux-commands-cheat-sheet.html>

- `echo`: Prints the given string to the terminal.
- `ls`: Lists the files and directories in the current directory.
- `cd`: Changes the current directory.
- `pwd`: Prints the current working directory.
- `mkdir`: Creates a new directory.

To run multiple commands, separate it by a semi-colon:

```bash
    echo "Hello"; echo "World"
    cd new_dir; mkdir www; pwd
```

![Make a directory hierarchy](/assets/images/2022-09-22-11-45-22.png)

Remember, the shell is case-sensitive. So, `mkdir` and `MKDIR` are different commands.

## File System

Remove a file:

```bash
    rm file.txt
```

Remove a directory using `rmdir`:

```bash
    rmdir new_dir
```

or:

```bash
    rm -r /tmp/new_dir
```

`-r` is used to remove a directory recursively.

To copy a file:

```bash
    cp file.txt file2.txt
```

The first part is source file name and the second part is the destination file name.

To copy one directory and all of it's contents to another path:

```bash
    cp -r /tmp/new_dir /tmp/new_dir_copy
```

To create a file:

```bash
    touch /tmp/new_dir/file.txt
```

To add content to a file:

```bash
    cat > /tmp/new_dir/file.txt
```

You can use `Enter` to add a new line and `Ctrl + D` to save the file.

To view the contents of a file:

```bash
    cat /tmp/new_dir/file.txt
```

To move a file:

```bash
    mv /tmp/new_dir/file.txt /tmp/new_dir/file2.txt
```

This is equivalent to renaming a file or cutting and pasting a file.

## User Accounts

`whoami` prints the current user.

`id` prints the user id and the group id.

`su` switches to another user.

`ssh user@host` allows you to connect to a remote `host` with `user`.

Every Linux system has a root user who has no restrictions on the system and can perform any task. This is why in most production environments or enterprise environments, access to the root user is restricted, and you'll almost never login to the system as the root user.

A root user can grant root access to a regular user by granting them `sudo` privileges by making an entry to the `/etc/sudoers` file. So the user is a regular user with root privileges.

When a regular user is granted a `sudo` privilege, they can now elevate their permission level and perform tasks that they otherwise couldn't by using a prefix any command with the keyword `sudo`.

![Granting sudo privileges](/assets/images/2022-09-23-14-17-27.png)

## Download files

`curl -O https://example.com/file.txt` downloads the file to the current directory. `-O` option is used to save the result to a file.

`wget https://example.com/file.txt -O some-file.txt` downloads the file to the current directory.`-O` option is used to specify the name of the file that you want it to store locally as.

## Check OS Version

`ls /etc/*release*` prints the OS version.

`cat /etc/*release*` prints more details about the OS version.

## Package Managers

Package managers are used to install, update, and remove software packages on the system.

CentOS and Red Hat Enterprise Linux use RPM (Red Hat Package Manager) package manager.

A software is packaged into a bundle with the extension `.rpm`. This bundle contains all the files that are required to run the software.

To install a package:

```bash
    rpm -i package.rpm
```

To uninstall a package:

```bash
    rpm -e package.rpm
```

To query a package:

```bash
    rpm -q package.rpm
```

To update a package:

```bash
    rpm -U package.rpm
```

RPM don't install dependencies automatically. So, you'll have to install the dependencies manually.

So you need a solution that can install dependencies automatically. This is where `yum` comes in.

`yum` is a high level package manager that is used to install, update, and remove software packages on the system. `yum` uses `rpm` under the hood.

To install a package:

```bash
    yum install ansible
```

Yum searches software repositories that act as warehouses containing hundreds and thousands of software rpm packages. These repositories can be local or remote or available publicly in the internet.

When you install a package using `yum`, it automatically finds the dependencies and installs them in order of requirement.

The list of repositories that are configured on the system can be found in the `/etc/yum.repos.d/` directory.

Every OS comes bundled with its own set of repositories. You can add more repositories to the system by adding them to the `/etc/yum.repos.d/` directory.

To see the list of repositories that are configured on the system:

```bash
    yum repolist
```

Listing the files under the `/etc/yum.repos.d/` directory, shows the files where these repositories are configured:

```bash
    ls /etc/yum.repos.d/
```

If you check the contents of these configuration files, you will see the URL of the location where all packages are stored.

![YUM Repos](/assets/images/2022-10-03-12-03-54.png)

If you visit the URL, you will see the list of packages(`.rpm` files) that are available in the repository.

To see the list of packages that are installed on the system, followed by the package name, if you want to search for it's particular package:

```bash
    yum list ansible
```

To remove a package:

```bash
    yum remove ansible
```

To show all the list of available versions of a package:

```bash
    yum --showduplicates list ansible
```

To install a specific version of a package:

```bash
    yum install ansible-2.9.6
```
