<p align="center">
  <a href="https://github.com/The-Intruder/Practical-Linux-Server-Administration-aka-born2beroot">
    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/f/f1/Icons8_flat_linux.svg/1200px-Icons8_flat_linux.svg.png" alt="Logo" width="80" height="80">
  </a>

  <h3 align="center">Practical Linux Server Administration <em>born2beroot</em></h3>

  <p align="center">
An immersive project designed to get familiarized with the world of system administration and server management using Linux, as well as gaining hands-on experience in setting up and configuring a secure and efficient server environment.
    <br/>
    <br/>
    <a href="https://github.com/The-Intruder/Practical-Linux-Server-Administration-aka-born2beroot/issues">Report Bug</a>
    .
    <a href="https://github.com/The-Intruder/Practical-Linux-Server-Administration-aka-born2beroot/issues">Request Feature</a>
  </p>
</p>

<div  style="display: flex; justify-content: center;">
<a  href="https://twitter.com/i_am_amine" target="_blank">
  <img  alt="Twitter Follow"  src="https://img.shields.io/twitter/follow/i_am_amine?style=social">
</a>
<img  src="https://img.shields.io/github/repo-size/The-Intruder/Practical-Linux-Server-Administration-aka-born2beroot"  alt="Repo Size">
<img  src="https://img.shields.io/github/last-commit/The-Intruder/Practical-Linux-Server-Administration-aka-born2beroot"  alt="Last Commit">
<img  src="https://img.shields.io/github/license/The-Intruder/Practical-Linux-Server-Administration-aka-born2beroot" alt="License" >
</div>

## Table Of Contents

- [Table Of Contents](#table-of-contents)
- [Community enterprise Linux Operating System _or simply_ CentOS](#community-enterprise-linux-operating-system-or-simply-centos)
- [Debian GNU/Linux _or just_ Debian](#debian-gnulinux-or-just-debian)
- [The main differences between Debian \& CentOS](#the-main-differences-between-debian--centos)
  - [Architecture](#architecture)
  - [Packages Managing](#packages-managing)
  - [Filesystems](#filesystems)
  - [Kernel](#kernel)
- [What's X.org](#whats-xorg)
  - [Techopedia Explains X.Org Server](#techopedia-explains-xorg-server)
- [What is KDump](#what-is-kdump)
- [What is SELinux](#what-is-selinux)
- [What is AppArmor](#what-is-apparmor)
  - [What is the difference between SELinux and AppArmor](#what-is-the-difference-between-selinux-and-apparmor)
- [What is a Logical Volume Manager _(or LVM)_](#what-is-a-logical-volume-manager-or-lvm)
  - [Some related LVM bash commands](#some-related-lvm-bash-commands)
- [Reserved Blocks in Linux](#reserved-blocks-in-linux)
- [Difference between VDI, VMDK, and VHD](#difference-between-vdi-vmdk-and-vhd)
- [Difference between "Save the machine state", "Send the shutdown signal" and "Power off the machine" in VirtualBox](#difference-between-save-the-machine-state-send-the-shutdown-signal-and-power-off-the-machine-in-virtualbox)
- [The difference between `useradd` and `adduser`](#the-difference-between-useradd-and-adduser)
- [What is UFW](#what-is-ufw)
- [Most Used Commands](#most-used-commands)

## Community enterprise Linux Operating System _or simply_ CentOS

Is an open-source Linux _(meaning that it uses the Linux kernel)_, _Duh!_. It was developped by _Red Hat_ _(the company behind the famous Red Hat Entreprise Linux, and the main contributor to several open-source projects)_, and maintained by—also—_Red Hat_ along with the open-source community.

Its main use is to test features that will be integrated in future _Red Hat Entreprise Linux_ releases, and it can also be used as an OS just like any other OS for personnal uses _(probably not for typical desktop users, sorry, but it's just the truth)_ and professional uses as well _(as a server maybe)_. I mean after all it's open-source, right ?!??

## Debian GNU/Linux _or just_ Debian

Is one of the oldest Linux distros _(distributions)_, that are still used and maintained until this day

The name is somewhat a combination between:

1. The name of the _Debian_ founder: _**Ian** Murdock_
2. And his—then—girlfriend: _**Deb**ra Lynn_

Which gives us _**Deb-Ian**_

_Debian_ has several branches, the most notable one being the _Debian stable_ which is a very popular choice when it comes to _Personnal Computers_ as well as _Servers_.

It is maintained by the open-source community, specifically by a team of volunteers from all around the world, whom are guided by the _Debian Project Leader_ and three foundational documents: the _Debian Social Contract_, the _Debian Constitution_, and the _Debian Free Software Guidelines_.

## The main differences between Debian & CentOS

### Architecture

Well, the first thing to note is that _CentOS_ doesn't run on as many architectures as _Debian_ does _(they both run on **x86_64/AMD64** thought)_. But they do run on quite a lot of architectures.

### Packages Managing

Each one of these _OSs_ uses a different _Package Manager_.

- _CentOS_ uses the **RPM** package format and `YUM/DNF` as the package manager.
- _Debian_ uses the **DEB** package format and `dpkg/APT` as the package manager.

Both of them offers a fully-featured package management, they just have their differences.

### Filesystems

Both of these _OSs_ come with a different default _Filesystem_:

- _CentOS_ uses the **XFS** filesystem.
- _Debian_ uses the **EXT4** filesystem.

They both offer numerous more filesystem support _(although Debian has more compared to CentOS)_, but it generally remains a preference, unless you need to work with a specific filesystem.

### Kernel

When it comes to the Linux kernel, _Debian_ is known to be shipped with the latest kernel available _(not LATEST latest, you know)_. As oppose to _CentOS_, which prefers to stick to one kernel and keep on rolling updates on it.

_You can find more **Debian**'s kernel versioning [here](https://en.wikipedia.org/wiki/Debian_version_history#Release_table), and on **CentOS**'s kernel versioning [here](https://en.wikipedia.org/wiki/CentOS#CentOS_version_8)_

## What's X.org

Maybe you've heard about it, maybe you saw it somewhere, and now you just want to know what it is _(or not)_, well you've come to the wrong place, I don't know what it is either, but let's try to learn about it together _(JK, I already know what it is)_.

According to [Wikipedia](https://en.wikipedia.org/wiki/X.Org_Server):

> X.Org Server is the free and open-source implementation of the X Window System display server stewarded by the X.Org Foundation.

Let me guess, that didn't help much, right ?!? Well let me explain it to you in layman's terms _(or in lay-person's terms, if you're into that kind of stuff)_.

_X.org_ is actually the name of the organisation that leads the _X Window System_ or _X11_ project.

The _X11_ is a windowing system _(a Graphical User Interface Server)_, used on _Unix-like_ operating systems, i.e. it's basically just a recreation of the Microsoft Windows GUI _(kind of)_, but one that's compatible with _Unix-like_ systems.

But note that a Graphical User Interface Server needs to be hooked with a Window Manager in order to _partially_ work, and that's why we have _Desktop Environments_, they're a combination of a _Graphical User Interface Server_, a _Window Manager_, and some other tools that makes the GUI more usable.

### Techopedia Explains X.Org Server

> X.Org Server is the X Window reference implementation, which serves as the standard for all other implementations and is generally used with Unix and Linux platforms. X.Org Server is the base for KDE, GNOME and CDE desktop interfaces.
>
> The X.Org Server platform runs on a computer with graphical displays, connects with numerous programs and serves as an intermediary between client and user applications. X.Org Server receives graphical output requests from client programs, which are then displayed for users. The server also receives user input from a mouse or keyboard and then transmits data to the client application.
>
> The client-server communication protocol uses a transparent network, allowing the client and server to run on the same or different computers. Additionally, the client and server may have different architectures and OSs. Client and server communications are secured over the Internet via a data encryption mechanism known as tunneling.

## What is KDump

As the [Oracle Linux documentation](https://docs.oracle.com/cd/E37670_01/E37355/html/ol_kdump_diag.html) explains it:

> Kdump is the Linux kernel crash-dump mechanism. Oracle recommends that you enable the Kdump feature. In the event of a system crash, Kdump creates a memory image (vmcore) that can help in determining the cause of the crash. Enabling Kdump requires you to reserve a portion of system memory for exclusive use by Kdump. This memory is unavailable for other uses.
>
> Kdump uses kexec to boot into a second kernel whenever the system crashes. kexec is a fast-boot mechanism which allows a Linux kernel to boot from inside the context of a kernel that is already running without passing through the bootloader stage.

Or as _Red Hat_ explains it in their [documentation](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/8/html/managing_monitoring_and_updating_the_kernel/installing-kdump_managing-monitoring-and-updating-the-kernel#what-is-kdump_installing-kdump):

> _KDump_ is a service providing a crash dumping mechanism. The service enables you to save the contents of the system’s memory for later analysis. kdump uses the kexec system call to boot into the second kernel _(a capture kernel)_ without rebooting; and then captures the contents of the crashed kernel’s memory _(a crash dump or a vmcore)_ and saves it. The second kernel resides in a reserved part of the system memory.

So basiaclly put, **KDump**, is a _Linux Kernel_ feature which is used to dump memory content of the system when a Kernel failure or crash occurs. Whenever a Kernel failure or crash occurs, the _KDump_ feature copies the content of the main memory and exports it into an _Executable and Linkable Format(ELF)_ which can be further used to analyse the reason for Kernel crash or for system recovery.

And if that didn't make things clear, here's what _The Geek Diary_ thinks **KDump** is:

> Kdump is the Linux kernel crash dumping mechanism. In the event of a system crash, Kdump provides a memory dump _(vmcore)_ image. This image can assist in determining the cause of the crash. It is highly recommended that you enable the Kdump feature.
>
> Kexec and Kdump together ensure faster bootup and the creation of reliable kernel vmcores for diagnostic purposes. Kexec is a fast-boot mechanism that allows booting a Linux kernel from the context of an already running kernel without going through BIOS. Kdump uses Kexec to boot into a second kernel whenever the system crashes. The crash dump is captured from the context of a freshly booted kernel and not from the context of the crashed kernel. This second kernel boots with very little memory and captures the dump image.

## What is SELinux

Security-Enhanced Linux _(or SELinux)_ is a security module, initially developped by the _United States' National Security Agency_ aka _NSA_ and made public or open-source in 2000, which brings some enhancements to the Linux kernel in terms of security. To make things a little bit more clear, _SELinux_ enforces the access policy _(either the default one, or the one given by the SysAdmin)_ that will be followed by the kernel whenever a process needs to access a file or an object

The NSA Security-Enhanced Linux Team describes NSA SELinux as:

> a set of patches to the Linux kernel and utilities to provide a strong, flexible, mandatory access control (MAC) architecture into the major subsystems of the kernel. It provides an enhanced mechanism to enforce the separation of information based on confidentiality and integrity requirements, which allows threats of tampering, and bypassing of application security mechanisms, to be addressed and enables the confinement of damage that can be caused by malicious or flawed applications. It includes a set of sample security policy configuration files designed to meet common, general-purpose security goals.

_**P.S.** If you want to dig a little bit deeper, here is a really beautiful explanation of [How-to SELinux](https://opensource.com/business/13/11/selinux-policy-guide)_ made by _[opensource.com]_(<https://opensource.com/>). And here is what [_Red Hat_](https://www.redhat.com/en/topics/linux/what-is-selinux) says about it too.

## What is AppArmor

**AppArmor** _(or Application Armor)_ is—according to [Wikipedia](https://en.wikipedia.org/wiki/AppArmor)—:

> ... a _Linux kernel security module_ that allows the system administrator to restrict programs' capabilities with per-program profiles. Profiles can allow capabilities like network access, raw socket access, and the permission to read, write, or execute files on matching paths. AppArmor supplements the traditional Unix discretionary access control _(DAC)_ model by providing mandatory access control _(MAC)_. ...

[HowToGeek](https://www.howtogeek.com/118222/htg-explains-what-apparmor-is-and-how-it-secures-your-ubuntu-system/) also has a wonderful explanation of **AppArmor** that goes as follows:

> AppArmor is similar to SELinux, used by default in Fedora and Red Hat. While they work differently, both AppArmor and SELinux provide “mandatory access control” (MAC) security. In effect, AppArmor allows Ubuntu’s developers to restrict the actions processes can take. ...

_AppArmor_ _(somewhat)_ a Mandatory Access Control _(MAC)_ system which supliments the—already existing—Unix discretionary access control _(DAC)_ model by simply restricting programs to certain resources.

You can also take a look at the [Official AppArmor Documentation](https://gitlab.com/apparmor/apparmor/-/wikis/Documentation) for further understanding, and here is their [Official Website](https://apparmor.net/), and just to make sure you finish this with a full understanding of _AppArmor_, here is an explanation made by _Seth_ in [StackOverflow](https://askubuntu.com/questions/236381/what-is-apparmor).

**TL;DR** _AppArmor_ is—technically called—a **Mandatory Access Control** (MAC) system implemented upon the **Linux Security Modules** (LSM). It supplements rather than replaces the default **Discretionary Access Control** (DAC). As such it is impossible to grant a process more privileges than it had in the first place.

---

### What is the difference between SELinux and AppArmor

As [Wikipedia](https://en.wikipedia.org/wiki/AppArmor) describes it:

> _AppArmor_ is offered in part as an alternative to _SELinux_, which critics consider difficult for administrators to set up and maintain. Unlike _SELinux_, which is based on applying labels to files, AppArmor works with file paths. Proponents of AppArmor claim that it is less complex and easier for the average user to learn than SELinux. They also claim that AppArmor requires fewer modifications to work with existing systems.[citation needed] For example, SELinux requires a filesystem that supports "security labels", and thus cannot provide access control for files mounted via NFS. AppArmor is filesystem-agnostic.

And I think that it doesn't need to be explained any further.

---

## What is a Logical Volume Manager _(or LVM)_

### Some related LVM bash commands

```bash
pvs  # Physical Volumes Information
lvs  # Logical Volumes Information
vgs  # Volume Groups
df -h  # Disk Free, human-readble format
```

## Reserved Blocks in Linux

Reserved blocks are disk blocks reserved by the kernel for processes owned by privileged users to prevent operating system from a crash due to unavailability of storage space for critical processes. For example, just imagine the size of root file system is 14 GB and the root file system is 100% full, all the non privileged user processes would not be able to write data to the root file system whereas processes which are owned by privileged user (root by default) would still be able to write the data to the file system. With the help of reserved blocks, operating system keeps running for hours or sometimes days even though root file system is 100% full.

The default percentage of reserved block is `5%` of the total size of file system and can be increased or decreased based upon the requirement. However, it is not recommended to reduce the percentage of reserved block less than `5%`. Reserved blocks are supported on `ext2` and `ext3` file system(s).

## Difference between VDI, VMDK, and VHD

**VDI** is the native format of _VirtualBox_. Other virtualization software generally don't support _VDI_, but it's pretty easy to convert from _VDI_ to another format, especially with [qemu-img](https://linux.die.net/man/1/qemu-img) convert.

**VMDK** is developed by and for _VMWare_, but _VirtualBox_ and _QEMU_ _(another common virtualization software)_ also support it. This format might be the the best choice for you because you want wide compatibility with other virtualization software.

**VHD** is the native format of _Microsoft Virtual PC_. _Windows Server 2012_ introduced _VHDX_ as the successor to _VHD_, but _VirtualBox_ does not support _VHDX_.

## Difference between "Save the machine state", "Send the shutdown signal" and "Power off the machine" in VirtualBox

1. **Save the machine state:** With this option, VirtualBox "freezes" the virtual machine by completely saving its state to your local disk. When you start the VM again later, you will find that the VM continues exactly where it was left off. All your programs will still be open, and your computer resumes operation. Saving the state of a virtual machine is thus in some ways similar to suspending a laptop computer.
2. **Send the shutdown signal:** This will send an _ACPI_ shutdown signal to the virtual machine, which has the same effect as if you had pressed the power button on a real computer. So long as the VM is running a fairly modern operating system, this should trigger a proper shutdown mechanism from within the VM.
3. **Power off the machine:** With this option, _VirtualBox_ also stops running the virtual machine, but without saving its state.

## The difference between `useradd` and `adduser`

`useradd` is native binary compiled with the system. But, `adduser` is a _Perl_ script which uses `useradd` binary in back-end.

`adduser` is more user friendly and interactive than its back-end `useradd`. There's no difference in features provided.

## What is UFW

UFW stands for Uncomplicated Firewall. It is a user-friendly command-line tool used for managing firewall rules on Linux systems. UFW provides a simplified interface for configuring firewall settings, making it easier for users to set up and manage network security.

With UFW, you can define rules to allow or deny incoming and outgoing network traffic based on various criteria, such as IP addresses, ports, protocols, and interfaces. It supports both IPv4 and IPv6 configurations.

UFW is designed to be simple and intuitive, making it accessible to users who may not have extensive knowledge of firewall management. It uses a straightforward syntax and offers commands for enabling or disabling the firewall, adding or removing rules, and displaying the current status of the firewall.

Behind the scenes, UFW interacts with the underlying netfilter firewall infrastructure, also known as iptables, to implement and enforce the specified firewall rules.

By utilizing UFW, you can enhance the security of your Linux system by easily configuring firewall rules to control network traffic and protect against unauthorized access.

## Most Used Commands

| Command       | Explanation                                                                                          | Usage                                               |
| ------------- | ---------------------------------------------------------------------------------------------------- | --------------------------------------------------- |
| `apt`         | Manages software packages in Debian-based Linux distributions.                                       | `apt [options] [command]`                           |
| `apt-get`     | Manages software packages in Debian-based Linux distributions.                                       | `apt-get [options] [command]`                       |
| `aptitude`    | Manages software packages in Debian-based Linux distributions.                                       | `aptitude [options] [command]`                      |
| `apt-cache`   | Performs searches in APT's package cache.                                                            | `apt-cache [options] [command]`                     |
| `lsblk`       | Lists information about available block devices.                                                     | `lsblk [options] [device]`                          |
| `ssh`         | Securely connects to a remote server over SSH protocol.                                              | `ssh [user@]hostname [command]`                     |
| `uname`       | Displays system information, including the kernel name, version, and release.                        | `uname [options]`                                   |
| `wc`          | Counts the number of lines, words, and characters in a file or input.                                | `wc [options] [file]...`                            |
| `free`        | Displays the amount of free and used memory in the system.                                           | `free [options]`                                    |
| `df`          | Reports file system disk space usage.                                                                | `df [options] [file]...`                            |
| `top`         | Displays real-time information about system processes and resource usage.                            | `top [options]`                                     |
| `who`         | Shows information about currently logged-in users.                                                   | `who [options]`                                     |
| `users`       | Displays a list of currently logged-in users.                                                        | `users [options]`                                   |
| `hostname`    | Prints the name of the current host system.                                                          | `hostname [options]`                                |
| `last`        | Shows listing of last logged-in users.                                                               | `last [options] [username]`                         |
| `ip`          | Shows and manipulates network interfaces and routing tables.                                         | `ip [options] [object]...`                          |
| `ifconfig`    | Configures and displays network interface parameters.                                                | `ifconfig [interface] [options]`                    |
| `ping`        | Tests the reachability of a host on an IP network.                                                   | `ping [options] destination`                        |
| `traceroute`  | Tracks the route packets take across an IP network.                                                  | `traceroute [options] destination`                  |
| `journalctl`  | Views and manages logs from the systemd journal.                                                     | `journalctl [options]...`                           |
| `hostnamectl` | Controls the system hostname and related settings.                                                   | `hostnamectl [options]`                             |
| `adduser`     | Adds a new user account to the system.                                                               | `adduser [options] [username]`                      |
| `useradd`     | Adds a new user account to the system.                                                               | `useradd [options] username`                        |
| `groupadd`    | Creates a new group in the system.                                                                   | `groupadd [options] group`                          |
| `userdel`     | Deletes a user account and related files.                                                            | `userdel [options] username`                        |
| `usermod`     | Modifies user account attributes.                                                                    | `usermod [options] username`                        |
| `groupmod`    | Modifies group attributes.                                                                           | `groupmod [options] group`                          |
| `getent`      | Retrieves entries from databases configured in /etc/nsswitch.conf file (including users and groups). | `getent [options] database [key]`                   |
| `passwd`      | Changes user password.                                                                               | `passwd [options] [username]`                       |
| `ufw`         | Configures and manages Uncomplicated Firewall (UFW) settings.                                        | `ufw [options] [command]`                           |
| `systemctl`   | Controls the systemd system and service manager.                                                     | `systemctl [command] [unit]`                        |
| `service`     | Controls system services (legacy command).                                                           | `service [options] <service> <action> [options]...` |
| `systemd`     | Controls the systemd system and service manager.                                                     | `systemd [options] [command] [unit]`                |
