# Know your _**born2beroot**_

> He who knows <i>Windows</i> is wise. He who knows <i>Linux</i> is enlightened !
>
> \- <cite>Amine Naimi</cite> <i>(definitely not Lao Tzu)</i>

## Community enterprise Linux Operating System _or simply_ CentOS

Is an open-source Linux  _(meaning that it uses the Linux kernel)_, _Duh!_. It was developped by _Red Hat_ _(the company behind the famous Red Hat Entreprise Linux, and the main contributor to several open-source projects)_, and maintained by—also—_Red Hat_ along with the open-source community.

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

Or as _Red Hat_ explains in their [documentation](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/8/html/managing_monitoring_and_updating_the_kernel/installing-kdump_managing-monitoring-and-updating-the-kernel#what-is-kdump_installing-kdump):
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

_**P.S.** If you want to dig a little bit deeper, here is a really beautiful explanation of [How-to SELinux](https://opensource.com/business/13/11/selinux-policy-guide)_ made by [opensource.com](https://opensource.com/). And here is what [_Red Hat_](https://www.redhat.com/en/topics/linux/what-is-selinux) says about it too.

## What is AppArmor


