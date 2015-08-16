# Awesome Linux Containers

## Foundations

* [OPEN CONTAINER INITIATIVE](https://www.opencontainers.org/)
* [Cloud Native Computing Foundation](https://cncf.io/)

## Specifications

* [Open Container Specifications](https://github.com/opencontainers/specs)
* [App Container basics](https://github.com/coreos/rkt/blob/master/Documentation/app-container.md)

## Clouds

* [Developer Cloud Platform](https://www.dotcloud.com/)
* [Google Cloud Platform](https://cloud.google.com/container-engine/)
* [Mesosphere](https://mesosphere.com/)
* [Kubernetes](http://kubernetes.io/)

## Hypervisors

* [Docker](https://github.com/veggiemonk/awesome-docker#cloud-infrastructure)
* [LXD](https://github.com/lxc/lxd)
* [OpenVZ](https://openvz.org/Main_Page)

## Containers

* [runc](https://github.com/opencontainers/runc)
* [Rocket](https://github.com/coreos/rkt)
* [LXC](https://github.com/lxc/lxc)
* [Vagga](https://github.com/tailhook/vagga)
* [libct](https://github.com/xemul/libct)
* [libvirt](https://libvirt.org/drvlxc.html)

## Sandboxes

* [Firejail](https://l3net.wordpress.com/projects/firejail/)
* [NsJail](https://github.com/google/nsjail)
* [Subuser](https://github.com/subuser-security/subuser)
* [Snappy](https://wiki.ubuntu.com/SecurityTeam/Specifications/SnappyConfinement)

## Partial Access

* [nsenter](http://man7.org/linux/man-pages/man1/nsenter.1.html)
* [ip-netns](http://man7.org/linux/man-pages/man8/ip-netns.8.html)
* [unshare](http://man7.org/linux/man-pages/man2/unshare.2.html)
* [python-nsenter](https://github.com/zalando/python-nsenter)
* [butter](https://pypi.python.org/pypi/butter/0.10)
* [pyspaces](https://github.com/Friz-zy/pyspaces)

## Security

### Links
* [Are Docker containers really secure?](https://opensource.com/business/14/7/docker-security-selinux)
* [Bringing new security features to Docker]https://opensource.com/business/14/9/security-for-docker)
* [Docker, Linux Containers (LXC), and security](http://www.slideshare.net/jpetazzo/docker-linux-containers-lxc-and-security)
* [For containers, security is problem #1](http://www.itworld.com/article/2920349/security/for-containers-security-is-problem-1.html)
* [Linux Container Security](https://mjg59.dreamwidth.org/33170.html)
* [Ask HN: Best Linux sandbox?](https://news.ycombinator.com/item?id=10030868)

### levels of security problems

1) regular application

* calways untrusted -> know it
* csuid bit -> mount with nosuid
* limit available syscall -> seccomp-bpf, grsec
* leak to another container (bug in namespaces, filesystem) -> user namespaces with different uid inside for each cotainer: 1000 in container - 14293 and 15398 outside; security modules like selinux or apparmor

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

* root -> more of services should work on host outside; isolate sensitive functions, run as non-privilaged context
* full privilages -> isolate on kernel level

4) kernel drivers, network stack, security policies

* absolute privilages -> run it in separate vm

5) general like immutable infrastructure

* container is ro
* write to small separate rw nosuid part

[src](http://www.slideshare.net/jpetazzo/docker-linux-containers-lxc-and-security)  
[src](https://opensource.com/business/14/9/security-for-docker)

### software for security

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
SELinux  
Cgroups  
file systems under /sys  
/proc/sys, /proc/sysrq-trigger, /proc/irq, /proc/bus

Devices are not namespaced:  
/dev/mem  
/dev/sd* file system devices  
kernel modules

If you can communicate or attack one of these as a privileged process, you can own the system.  
[src](https://opensource.com/business/14/7/docker-security-selinux)
