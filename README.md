# Awesome Linux Containers

[![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)

## Table of Contents

* [Foundations](#foundations)
* [Specifications](#specifications)
* [Clouds](#clouds)
* [Hypervisors](#hypervisors)
* [Containers](#containers)
* [Sandboxes](#sandboxes)
* [Partial Access](#partial-access)
* [Dashboard](#dashboard)
* [Security](#security)
  - [Tools](#tools)
  - [Links](#links)
  - [Levels of security problems](#levels-of-security-problems)
  - [Technologies for security](#technologies-for-security)
* [Another Information Sources](#another-information-sources)

## Foundations

* [OPEN CONTAINER INITIATIVE](https://www.opencontainers.org/)  
The Open Container Initiative is a lightweight, open governance structure, to be formed under the auspices of the Linux Foundation, for the express purpose of creating open industry standards around container formats and runtime.
* [Cloud Native Computing Foundation](https://cncf.io/)  
The Cloud Native Computing Foundation will create and drive the adoption of a new set of common container technologies informed by technical merit and end user value, and inspired by Internet-scale computing.
* [Cloud Foundry Foundation](https://www.cloudfoundry.org/foundation/)  
The Cloud is our foundry.

## Specifications

* [Open Container Specifications](https://github.com/opencontainers/specs)  
This project is where the Open Container Initiative Specifications are written. This is a work in progress. 
* [App Container basics](https://github.com/coreos/rkt/blob/master/Documentation/app-container.md)  
App Container (appc) is an open specification that defines several aspects of how to run applications in containers: an image format, runtime environment, and discovery protocol.
* [Systemd Container Interface](https://wiki.freedesktop.org/www/Software/systemd/ContainerInterface/)  
Systemd is a suite of basic building blocks for a Linux system. It provides a system and service manager that runs as PID 1 and starts the rest of the system. If you write a container solution, please consider supporting the following interfaces.


## Clouds

* [Developer Cloud Platform](https://www.dotcloud.com/)  
PaaS from Docker creators.
* [Google Cloud Platform](https://cloud.google.com/container-engine/)  
Run Docker containers on Google Cloud Platform, powered by Kubernetes. Google Container Engine actively schedules your containers, based on declared needs, on a managed cluster of virtual machines. 
* [Mesosphere](https://mesosphere.com/)  
The Mesosphere Datacenter Operating System (DCOS) is a new kind of operating system that spans all of the machines in your datacenter or cloud. It provides a highly elastic, and highly scalable way of deploying applications, services and big data infrastructure on shared resources.
* [Kubernetes](http://kubernetes.io/)  
Manage a cluster of Linux containers as a single system to accelerate Dev and simplify Ops.
* [Jelastic](http://jelastic.com/)  
Unlimited PaaS and Container-Based IaaS in a Joint Cloud Solution for DevOps.
* [Warden](https://github.com/cloudfoundry/warden)  
Manages isolated, ephemeral, and resource controlled environments. Part of Cloud Foundry - the open platform as a service project.
* [Amazon EC2 Container Service ](https://aws.amazon.com/ecs/)   
Container management service that supports Docker containers and allows you to easily run applications on a managed cluster of Amazon EC2 instances.
* [Joyent](https://www.joyent.com/)  
High-Performance Container-Native Infrastructure for Today's Demanding Real-Time Web and Mobile Applications.


## Hypervisors

* [Docker](https://github.com/veggiemonk/awesome-docker#cloud-infrastructure)  
An open platform for distributed applications for developers and sysadmins. **Standard de facto**.
* [LXD](https://github.com/lxc/lxd)  
Daemon based on liblxc offering a REST API to manage LXC containers.
* [OpenVZ](https://openvz.org/Main_Page)  
OpenVZ is container-based virtualization for Linux. OpenVZ creates multiple secure, isolated Linux containers (otherwise known as VEs or VPSs) on a single physical server enabling better server utilization and ensuring that applications do not conflict.

## Containers

* [runc](https://github.com/opencontainers/runc)  
runc is a CLI tool for spawning and running containers according to the OCS specification.
* [Bocker](https://github.com/p8952/bocker)  
Docker implemented in around 100 lines of bash.
* [Rocket](https://github.com/coreos/rkt)  
rkt (pronounced "rock-it") is a CLI for running app containers on Linux. rkt is designed to be composable, secure, and fast. Based on AppC specification.
* [LXC](https://github.com/lxc/lxc)  
LXC is the well known set of tools, templates, library and language bindings. It's pretty low level, very flexible and covers just about every containment feature supported by the upstream kernel.
* [Vagga](https://github.com/tailhook/vagga)  
Vagga is a fully-userspace container engine inspired by Vagrant and Docker, specialized for development environments.
* [libct](https://github.com/xemul/libct)  
Libct is a containers management library which provides convenient API for frontend programs to rule a container during its whole lifetime.
* [libvirt](https://libvirt.org/drvlxc.html)  
A big toolkit to interact with the virtualization capabilities of recent versions of Linux (and other OSes).
* [systemd-nspawn](http://manpages.ubuntu.com/manpages/utopic/man1/systemd-nspawn.1.html)  
Spawn a namespace container for debugging, testing and building. Part of [systemd](https://wiki.freedesktop.org/www/Software/systemd/).
* [porto](https://github.com/yandex/porto)  
The main goal of Porto is to create a convenient, reliable interface over several Linux kernel mechanism such as cgroups, namespaces, mounts, networking etc.

## Sandboxes

* [Firejail](https://l3net.wordpress.com/projects/firejail/)  
Firejail is a SUID sandbox program that reduces the risk of security breaches by restricting the running environment of untrusted applications using Linux namespaces, seccomp-bpf and Linux capabilities.
* [NsJail](https://github.com/google/nsjail)  
NsJail is a process isolation tool for Linux. It makes use of the namespacing, resource control, and seccomp-bpf syscall filter subsystems of the Linux kernel.
* [Subuser](https://github.com/subuser-security/subuser)  
Securing the Linux desktop with Docker.
* [Snappy](https://wiki.ubuntu.com/SecurityTeam/Specifications/SnappyConfinement)  
Snappy Ubuntu Core is a new rendition of Ubuntu with transactional updates - a minimal server image with the same libraries as today’s Ubuntu, but applications are provided through a simpler mechanism.
* [xdg-app](https://wiki.gnome.org/Projects/SandboxedApps)  
xdg-app is a system for building, distributing and running sandboxed desktop applications on Linux.

## Partial Access

* [nsenter](http://man7.org/linux/man-pages/man1/nsenter.1.html)  
Run program with namespaces of other processes. Part of the util-linux.
* [ip-netns](http://man7.org/linux/man-pages/man8/ip-netns.8.html)  
Process network namespace management. Part of the iproute2.
* [unshare](http://man7.org/linux/man-pages/man1/unshare.1.html)  
Run program with some namespaces unshared from parent. Part of the util-linux.
* [python-nsenter](https://github.com/zalando/python-nsenter)  
This Python package allows entering Linux kernel namespaces (mount, IPC, net, PID, user and UTS) by doing the "setns" syscall.
* [butter](https://pypi.python.org/pypi/butter)  
Python library to interface to low level linux features (inotify, fanotify, timerfd, signalfd, eventfd, containers) with asyncio support.
* [pyspaces](https://github.com/Friz-zy/pyspaces)  
Works with Linux namespaces through glibc with pure python.
* [CRIU](https://criu.org/Main_Page)  
Checkpoint/Restore In Userspace is a software tool for Linux operating system. Using this tool, you can freeze a running application (or part of it) and checkpoint it to a hard drive as a collection of files. CRIU integrated with Docker and LXC to implement Live migration of containers.

## Dashboard

* [LXC-Web-Panel](https://lxc-webpanel.github.io/)  
Web panel for LXC on Ubuntu.

## Security

### Tools

* [Docker bench security](https://github.com/docker/docker-bench-security)  
The Docker Bench for Security is a script that checks for dozens of common best-practices around deploying Docker containers in production.
* [CoreOS Clair](https://coreos.com/blog/vulnerability-analysis-for-containers/)  
Open Source Vulnerability Analysis for your Containers.
* [bane](https://github.com/jfrazelle/bane)  
Custom AppArmor profile generator for docker containers.
* [OpenSCAP](https://github.com/OpenSCAP/container-compliance)  
The OpenSCAP ecosystem provides multiple tools to assist administrators and auditors with assessment, measurement and enforcement of security baselines.

### Links
* [CIS Security Benchmarks](https://benchmarks.cisecurity.org/about/)
* [Are Docker containers really secure?](https://opensource.com/business/14/7/docker-security-selinux)
* [Bringing new security features to Docker](https://opensource.com/business/14/9/security-for-docker)
* [Docker, Linux Containers (LXC), and security](http://www.slideshare.net/jpetazzo/docker-linux-containers-lxc-and-security)
* [For containers, security is problem #1](http://www.itworld.com/article/2920349/security/for-containers-security-is-problem-1.html)
* [Linux Container Security](https://mjg59.dreamwidth.org/33170.html)
* [Ask HN: Best Linux sandbox?](https://news.ycombinator.com/item?id=10030868)
* [CIS Docker 1.6 Benchmark v1.0.0](https://benchmarks.cisecurity.org/tools2/docker/CIS_Docker_1.6_Benchmark_v1.0.0.pdf)
* [Understanding docker security and best practices](https://blog.docker.com/2015/05/understanding-docker-security-and-best-practices/)
* [Update on Ubuntu Phone security issue](https://insights.ubuntu.com/2015/10/15/update-on-ubuntu-phone-security-issue/)
* [Don't expose the Docker socket (not even to a container)](https://www.lvh.io/posts/dont-expose-the-docker-socket-not-even-to-a-container.html)
* [RedHut Blog](http://rhelblog.redhat.com/?s=container&submit=Search)
  - [Introduction to Linux Containers](https://access.redhat.com/articles/1353593)
  - [What’s Next for Containers? User Namespaces](http://rhelblog.redhat.com/2015/07/07/whats-next-for-containers-user-namespaces/#more-1004)
  - [Architecting Containers Part 1: Why Understanding User Space vs. Kernel Space Matters](http://rhelblog.redhat.com/2015/07/29/architecting-containers-part-1-user-space-vs-kernel-space/)
  - [Architecting Containers Part 2: Why the User Space Matters](http://rhelblog.redhat.com/2015/09/17/architecting-containers-part-2-why-the-user-space-matters-2/)

### Levels of security problems

1) regular application

* always untrusted -> know it
* suid bit -> mount with nosuid
* limit available syscall -> seccomp-bpf, grsec
* leak to another container (bug in namespaces, filesystem) -> user namespaces with different uid inside for each container: 1000 in container - 14293 and 15398 outside; security modules like selinux or apparmor

2) system services like cron, ssh

* run as root -> isolate via bastion host or vm
* using /dev -> "devices" control group  
The following device nodes are created in the container by default.  
The Docker images are also mounted with nodev, which means that even if a device node was pre-created in the image, it could not be used by processes within the container to talk to the kernel.  
/dev/console,/dev/null,/dev/zero,/dev/full,/dev/tty*,/dev/urandom,/dev/random,/dev/fuse
* root calls -> capabilities (cap_sys_admin warning!)  
Here is the current list of capabilities that Docker uses: chown, dac_override, fowner, kill, setgid, setuid, setpcap, net_bind_service, net_raw, sys_chroot, mknod, setfcap, and audit_write.  
Docker removes several of these capabilities including the following:  
CAP_SETPCAP 	Modify process capabilities  
CAP_SYS_MODULE 	Insert/Remove kernel modules   
CAP_SYS_RAWIO 	Modify Kernel Memory  
CAP_SYS_PACCT 	Configure process accounting  
CAP_SYS_NICE 	Modify Priority of processes  
CAP_SYS_RESOURCE 	Override Resource Limits  
CAP_SYS_TIME 	Modify the system clock  
CAP_SYS_TTY_CONFIG 	Configure tty devices  
CAP_AUDIT_WRITE 	Write the audit log  
CAP_AUDIT_CONTROL 	Configure Audit Subsystem  
CAP_MAC_OVERRIDE 	Ignore Kernel MAC Policy  
CAP_MAC_ADMIN 	Configure MAC Configuration  
CAP_SYSLOG 	Modify Kernel printk behavior  
CAP_NET_ADMIN 	Configure the network  
CAP_SYS_ADMIN 	Catch all  
uses /proc, /sys -> remount ro, drop cap_sys_admin; security modules like selinux or apparmor; some part of this fs are "namespace-aware"  
Docker mounts these file systems into the container as "read-only" mount points.  
. /sys  
. /proc/sys  
. /proc/sysrq-trigger  
. /proc/irq  
. /proc/bus  
Copy-on-write file systems  
Docker uses copy-on-write file systems. This means containers can use the same file system image as the base for the container. When a container writes content to the image, it gets written to a container specific file system. This prevents one container from seeing the changes of another container even if they wrote to the same file system image. Just as important, one container can not change the image content to effect the processes in another container.
* uid 0 -> user namespaces, uid 0 mappet to random uid outside

3) system services like devices, network, filesystems

* root -> more of services should work on host outside; isolate sensitive functions, run as non-privileged context
* full privileges -> isolate on kernel level

4) kernel drivers, network stack, security policies

* absolute privileges -> run it in separate vm

5) general like immutable infrastructure

* container is ro
* write to small separate rw nosuid part

[src](http://www.slideshare.net/jpetazzo/docker-linux-containers-lxc-and-security)  
[src](https://opensource.com/business/14/9/security-for-docker)

### Technologies for security

Things are better. For example, most modern container technologies can make use of Linux's built-in security tools such as:  
[AppArmor](http://wiki.apparmor.net/index.php/Main_Page), [SELinux](http://selinuxproject.org/page/Main_Page) and [Seccomp](http://man7.org/linux/man-pages/man2/seccomp.2.html) policies;  
[Grsecurity](https://grsecurity.net/);  
[Control groups (cgroups)](https://access.redhat.com/documentation/en-US/Red_Hat_Enterprise_Linux/6/html/Resource_Management_Guide/ch01.html);  
[Kernel namespaces](http://man7.org/linux/man-pages/man7/namespaces.7.html)  
[src](http://www.itworld.com/article/2920349/security/for-containers-security-is-problem-1.html)

Sure, you're deploying seccomp, but you can't use selinux inside your container, because the policy isn't per-namespace (?? lxc uses apparmore for each container...)  
[sVirt](http://selinuxproject.org/page/SVirt) - selinux for kvm  
[src](https://mjg59.dreamwidth.org/33170.html)

Major kernel subsystems are not namespaced like:  
- SELinux  
- Cgroups  
- file systems under /sys  
- /proc/sys, /proc/sysrq-trigger, /proc/irq, /proc/bus

Devices are not namespaced:  
- /dev/mem  
- /dev/sd* file system devices  
- kernel modules

If you can communicate or attack one of these as a privileged process, you can own the system.  
[src](https://opensource.com/business/14/7/docker-security-selinux)

## Another Information Sources

* [sysdig-container-ecosystem](https://github.com/draios/sysdig-container-ecosystem)  
The ecosystem of awesome new technologies emerging around containers and microservices can be a little overwhelming, to say the least. We thought we might be able to help: welcome to the Container Ecosystem Project.
* [doger.io](http://doger.io/)  
This page is an attempt to document the ins and outs of containers on Linux. This is not just restricted to programmers looking to implement containers or use container like features in their own code but also Sysadmins and Users who want to get more of a handle on how containers work 'under the hood'. 
