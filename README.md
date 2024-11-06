# Linux Red Hat Study Notes

**Greetings! I'll be publicly documenting my Linux upskill experience here. Cloud and DevOps professionals have been constantly stating that Linux is an important skill to have in the space so I'm going to spend a few months building those skills via courses and hands on labs. I highly doubt I'll be taking any Red Hat certifications but who knows. Maybe I'll attempt it.**


## 11.06.2024


**Today's Topics**
* LPI Linux Essentials (continued)

A "computer" is RAM, storage, and CPU. That's it. 
The "$" at the end of the prompt string denotes that the current user is unprivileged. So basically, you're not the root user. If you see the "$" sign, you're unprivileged. Think of it as the ">" sign in the Cisco CLI where you're in User EXEC mode. On the other end, if you're the root user, the end of the prompt will have a "#" sign. This is the same way in Privileged EXEC mode in the Cisco CLI. 

Commands in the Terminal are entered in as Standard In (STDIN). This follows a syntax. The output is either Standard Out (STDOUT) or Standard Error (STDERR). See below. 

![Image](CommandPromptFlow.PNG)

Linux commenting starts with a pound sign (#). 

Dot files are hidden files. You can see these when you do `ls -a` or `ls --all`

"Bash takes your input and parses it—meaning it breaks it down into parts (or "tokens") to understand what you’re asking it to do." This comes into play if you have like, a command, the option, and then the object that it's acting on. Parsing just means analyzing each section of the command (because commands can have options and objects too) and then either interpret the entire command or return an error. This is "parsing a command".

Options are also called flags in Linux. You can group flags together. So instead of `ls -a -h -l' or `ls --all --human-readable --long-format` (which is called long format btw. Might be helpful to do it this way before you do the shorthand), you can just type `ls -ahl` altogether. Definitely convenient but you should check the `man <insert command>` info to know exactly what each option stands for and does. 

There are "hard-coded" BASH variables that you can't alter. Those three are $HOME (the current user's home directory), $PS1 (the primary prompt string) and $PATH (a colon-separated list of directories where the shell looks for commands). Don't trip too much on this right now. I actually don't even think we'll need $PS1 at all. 

Give a variable a value using `<variable_name>="<whatever value or string>"`. Now to reference that variable, you must use `$<variable_name>`. You must use that dollar sign. You can check this by doing `echo $<variable_name>` and getting the desired output. 

Go back over the `echo $PS1`  output. This will show you what those SecureCRT automatic commands are doing. This is all Linux scripting!!!

You can assign a variable a value of an output by doing `<variable_name>=$(<command_name>)`. For example, you van do `var1=$(ls)` to assign the variable `var1` the output of the `ls` command. Use `echo` to see the output. 

Quoting - used to disable special treatmeant of certain characters and words, as well as to prevent parameter expansion and preserve what is quoted. Basically you can put the quotes around an input for a variable so that it takes that entire value or string. Or paragraph. Whatever you put in there. If you don't put the quotation marks and you have a space, the terminal will return an error. Now, you can use the `\` character to move preserve the value of the next character. 

Also, with single quotes so '', this will take the exact value of everything in the single quotes even the escape character `\`. So it doesn't acknowledge any variables. It basically takes the string character for character. 

Double quotes will acknowledge the variable values but it will take the character value of the escape character. 

You can use `cd ~` to change to your user's home directory. 

When you do `>` to redirect the output of a command into a file, you will overwrite the entire file with the new output. If you want to add the output to the end of a file (this is called appending), you should use `>>` instead so you don't overwrite the file.

Colons `:` are used as delimiters in the file path. So basically it just breaks them up so you can include multiple file paths to a variable. So look at them like a comma pretty much. 

Yeah that backslash lab was kicking my a** lmao. It feel like choosing C 8 times in a row on a scantron sheet. Like this can't possibly be the right answer. I'll have to get more familiar with that aspect. 

## 11.05.2024


**Today's Topics**
* Linux File System Permissions (continued again)
* Lab notes
* LPI Linux Essentials

SELinux labels are pieces of information. Not sure what they're used for. We also have SELinux Booleans which, once again, not really sure what this is required for. 

Sticky bits means that a file can be deleted only by the owner of the file or the owner or the directory. SetGID is useful for executable files. It sets the group owner of the process to the group owner of the file, regardless of who is running the command. SetUID is also useful for executable files. It sounds like this does the same thing as the setGID. Not sure what the difference is. 

We also went over `chatttr` and `lsattr` although we were told we probably won't run into this. 

The `su` in `sudo su - bob` stands for switch user or substitute user. 

Distribution - comprised of a kernel, GNU core, X server (display server for the GUI), and lastly the GUI. 

Hardware is incorporated into the file hierarchy through the /dev and /sys directories, and process information is mapped in /proc. Use `uname -r` to check the kernel version. Use `lsb_release -a` to see the distribution you're running. 

The GNU Core Utilities are the basic file, shell and text manipulation utilities of the GNU operating system. These are the foundational utilities expected to exist on every OS. 

Examples of embedded Linux systems: Android and Raspberry Pi. 

Completed a simple SSH lab. I've been doing this everyday for the past week so this was really easy. You can also who `whoami` to tell you which user you're currently logged in as. 

Typical (open-source) desktop applications: OpenOffice (think Microsoft office things like Words and Excel), LibreOffice, Firefox, Thunderbird (email client), and GIMP (basically Photoshop). 

Typical (open-source) server applications: Apache HTTP Server (web server), NGINX (web server + hella other stuff), MySQL, MariaDB, Samba (file sharing (uses CIFS)), Network File System (NFS, which is a protocol, not an application), and ownCloud (similar to Dropbox but stored on your own connected hardward), 

Development languages. Lets talk about it. A shell script is designed to be run by the CLI using various scripting languages. Bash is a common shell (born again shell). C is a general-purpose imperative programming language. Java is class-based, object oriented general purpose language. Javascript is used for web pages. You also have Perl, PHP, and Python. 

Packages - a collection of files needed to install an application. Debian packages - dpkg and uses apt-get (uses .dev files). Red Hat Package manager - rpm and uses yum (uses .rpm files). These commands also look up dependencies for each package and they also store metadata about the application. 

apt stands for Advanced Package Tool. yum stands for Yellowdog Updater, Modified.

Forking occurs when developers use the main source code and "fork" from it to create their own version of an open-source software. 

"Compilation is the process of taking the human-readable source code and translating it into a lower-level form called object code." So when a computer is compiling your code, it's taking whatever you wrote in your coding language (or in the case of like, Docker, just plain ol' sentences) and turning that into a binary code. The computer's hardware can only read binary which is 0s and 1s. So compiling is taking the human-readable code and turning it into computer food. 




## 11.04.2024


**Today's Topics**
* Linux File System Permissions (continued)
* Lab notes


Use `getfacl` and `setfacl` to get and set folder ACLs on a directory. This is if you want more granular control other than just octal permissions. I'm assuming the "f" in facl stands for folder. For the 5th category, you may see a "+" on the directory indicating there is an ACL applied there. 

Use `getfacl` to determine which rules are actually in place. Sometimes, we don't know if the ACL or the octal permissions are taking over. Do `getfacl` on the file or folder to make sure. 

Use `fdisk` to create a partition on a desk. 



## 11.03.2024


**Today's Topics**
* Linux File System Permissions

Octal permissions - this is the hierarchical file descriptions for Linux. 

First field is will be either `d`, `l`, or `-`. D means directory, L means simlink, and - (dash) means a file. 
R - read and the number is 4. W - write and the number is 2. X - Execute and the number is 1. 
The final field indicates a "special" permission such as SELinux, ACLs, or other similar settings for that file. 

There are 5 categories in the octal permissions. 
- Denotes if file is a directory, symlink, or file
- Denotes the owner file permissions
- Denotes the group file permissions
- Denotes the user file permissions
- Denotes "special" permissions

You use `chmod` to change the permissions on a file. The numbers after `chmod` give the owner, group, and user the designated permissions. The numbers are 0, 4, 5, 6, and 7 which 0 means no permissions and the other numbers are generated by adding the values of the read, write, and execute permissions. Read = 4 and Execute = 1. 5 + 1 = 6. 

Use `umask` to have some customized default octal permissions for each folder and file. I believe Linux gives a default value of 666 which might not be good for security. A umask helps avoid this. 

Root users override all permission settings. 
  

## 11.02.2024


**Today's Topics**
* Linux File System

Use the command `mount` to mount a directory. Use `umount` to unmount a folder. 

![Image](LinuxFileSystem1.png)

Lets break down each part of this. You have the device name. Then it's listed "on" the directory (see the second part. It has a directory name or simply "/" for the root directory). Then it tells you the type of file system. Then it shows you the options associated with that mount. 

Use `df` to see the disk space usage for each file system. Use the `-h` option to make it more human-readable. 

`blkid` and `lsblk` gives us information on our hard drive devices I believe. When he uses `lsblk`, it shows him all the hard drives, namespaces, and partitions. So I believe this is what the command does. 

"The lsblk command in Linux is used to list information about all available or specified block devices. Block devices are storage devices that provide data in blocks, such as hard drives, solid-state drives, and USB drives"

Use `fuser` followed by the mounted directory name to find out which process is using this directory based on the PID. You can either use the `-k` option to help kill off the process so you can unmount the directory. Also, use `lsof | grep ###` to get more information on this process. 

To keep directories mounted after you reboot the system, you need to list the mount directory information in the `fstab` folder. Use the UUID for this if you can since that never changes. 

Swap space is located on the physical, hard disk memory. All your computer processes are being run in the RAM so the processes that haven't been used for a while will be put into swap space so that they're not taking up too much RAM. Hard disk storage is for long term use. Use `swapon --show` to see the information on your swap space. You can have a dedicated partition or file for your swap space. Use the `mkswap <disk name>` command to create a swap space. 

All the resources that the Linux system knows how to operate on are called Units which contain unit files. We'll use `systemd` to manage these. The instructor created one of these from scratch to show how to mount a directory. This is a bit beyond me right now. 

Ext - extended file system. There are mutliple versions: ext2, ext3, and ext4. Use `mkfs` to make a file system. Choose a disk to partition. You can use `parted <disk name>` to start an interactice wizard to help you partition your disk. Then, you can start to create file systems on each partition. 

I learned about partitioning a disk back when I was studying for the CompTIA A+ but I didn't know what it was useful for or what exactly I was doing. Partitioning a disk is basically taking the physical disk space and separating it into isolated storage spaces. I would compare this to all the ports on a switch physically being in one VLAN (by default, VLAN 1) but then you use VLANs on the switch to created additional LANs. Lets say you divide all the ports equally into 4 VLANs. This is similar to partitioning a disk. 

Use `fsck` (file system check) to check and repair a Linux file system. 

"The `tune2fs` command in Linux is used to adjust various parameters of an ext2, ext3, or ext4 file system. It’s a powerful utility for changing settings on existing file systems without reformatting them."

"The `dumpe2fs` command in Linux is used to display detailed information about ext2, ext3, or ext4 file systems. It provides a "dump" of file system metadata, which can help you understand its configuration, usage, and status without modifying it."

"The `debugfs` command in Linux is an interactive utility for examining and debugging ext2, ext3, and ext4 file systems. Unlike `dumpe2fs`, which only shows file system information, debugfs is a more advanced tool that allows both viewing and modifying file system structures."

XFS is the default file system for RHEL. `nvme1n1p5` basically says we're using NVME in namespace 1 in partition 5. I needed this for my own sanity. A namespace is a logical division of a drive. Think of it as a virtual drive. Partitions and namespaces are very similar. You divide the drive into namespaces and the namespace into partitions. 

`btrfs` (short for B-tree file system) is the default file system for Linux. You can use btrfs convert to change other file systems to btrfs. 

The "d" in `systemd` and `smartd` stands for daemon. So keep that in mind. 

You can use `autofs` to automatically mount drives. You have to install it first though. 

He also went over disk encryption. 


## 11.01.2024


**Today's Topics**
* The Linux Kernel
* Build Your Own Linux Kernel from Scratch

`uname` gives us imoprtant information on our system. You can see the version of the Linux kernel here. The instructor then used a bunch of pre-configured commands to download the kernel source tree and required documentation. I didn't fully understand this so we'll have to revisit it. 

According to Chat GPT: 
"The Linux kernel source tree is the organized directory structure containing all the source code, configuration files, and scripts necessary to build the Linux kernel. It’s called a "tree" because the files and directories branch out hierarchically, similar to a tree structure, making it easier to navigate the various components of the kernel.
[the source tree includes]
- Core kernel code
- Architecture-specific code
- Device drivers
- File systems
- Networking
- Tools and utilities"

After working out my thoughts with Chat GPT, the instructor was just downloading a version of the kernel and customizing the kernel to behave in the way that he wants. So he was in the Linux CLI and created a new directory for a new kernel. In order to access this new kernel, he can point the boot loader to the new kernel and reboot his system. Then he can work directly on the new kernel. 

`cd /boot/` is where we can find out boot settings for our system. The vmlinuz files are your actual kernel. "bz" stands for Big Z image. You also just have your "z" extension which is just a z image. These are based on low memory usage files which aren't typically a problem in  modern times. 

`make menuconfig` allowed the instructor to use a wizard to choose the features he wanted in his Linux kernel. I believe the output was saved to a .config file. Then he used the command `make bzImage` to create his kernel image. The bzImage command references the .config file in order to create the kernel. 

Afterwards, you can create the kernel modules and install them. The instructor went into switching in the new kernel code but I'll have to go over this again. 

Quick detour, I've been seeing the `.tar` extension for a while now. Never knew what it was for but Im guessing I'll start to see it a lot more now in Linux. `.tar` stands for tape archive. A tape archive refers to a method of storing data on magnetic tape which we have better methods now. `.tar` files are referred to as tarball files. Tarball - tape archive ball which in this context, ball is a way of saying bundle or package. You can think of a `.tar` file as a zip folder except better. The tarball file isn't always compressed although you can use different commands to compress it. The file can contain a full directory of folders in a hierachy (such as all the files and folders in a kernel source tree). It also keeps the file permissions and time stamps which a zip file can not do. 

RPM - Red-Hat Package Manager. "The RPM kernel package also includes kernel modules, which are pieces of code that can be loaded into the kernel at runtime. These modules extend the functionality of the kernel without requiring a full reboot, allowing for support of various hardware and filesystems."

We can use `lsmod` to see all the modules that are currently in use. 

You can add modules to a blacklist so that these modules are not loaded during the boot process. 

Use `update grub` to update the boot loader. Grub stands for GRand Unified Bootloader. The boot loader is the first piece of code that is loaded when a computer powers on. 

Kernel - the source code. The brains of the operation. It works between the hardware and software. It's responsible for the memory management, process management, device drivers, and system calls and security. 
OS - the set of applications and packages that are added for services. Inlcudes the system services, applications, and user accounts. 
Distro - a specific set of packages and applications added to the kernel. 



## 10.31.2024


**Today's Topics**
* Working with CentOS
* Linux Core Subsystems (systemd, networking, nftables, firewalld)

The user ID (uid) is what separates a normal user from a root user. The uid for root users is 0. Use `visudo` command to alternate the sudo files. You can also use this to make custom permissions for users. 

Use `sudo -i` to open an interactive sudo session. This is so you don't have to keep entering in your password over and over. 

Use the `man` command (short for manual) to look at the configuration page for that file. This can be used for `yum`, `Bash`, etc. Not all of them will have a document directory. 

Here's a quick reference sheet for editing files using `vim`.
![Image](VimShortCuts.png)

Here's a quick reference sheet for editing files using `nano`.
![Image](NanoShortCuts.png)

Runlevels - defined what a server looked like after it finished bootting. In CentOS, `systemd` manages this using targets. A target is made up of a number of services and other unit files. 

`systemctl get-default` gives us the default target that this system will boot into. You can get a list of all the targets. You can also create your own targets. I'm not going to worry about this for now since I still don't know the impact of this. 

You can manage services by using `systemctl` as well. You have start, stop, restart, reload, enable, and disable for starters. 

You can also create your own service file. They all have a unit section, service, and install section. You also have Type Options. 

I completed a lab that made use of `grep` to take information from one file and put it into another. We recorded the log messages of the day, the number of users on the CLI, and the number of CPUs on the host machine. We put all of that information into a new file. There was a lot of use of `cd`, `rm` and `ls` to navigate and correct any mistakes. Also, we can just use `grep ### > filepath/filename` in order to directly take your output and put it into another file. 

`nmcli` stands for network management CLI. This is where you can see and edit information on your network and interface settings. 

We also edited user permissions in `visudo` in order to lock down one user named Adam and elevate a user named Bob to have root access pretty much. Use `sudo - usernmae` to switch between users. You can use `logout` to logout of that user. Pretty straight forward lab although I don't fully understand how to edit the `visudo` options. 

`nftables` has replaced iptables in CentOS. "`iptables` ran the firewall (and firewalld used it as the back end)."

I completed a short lab playing with `vim` and `nano`. Nothing to really speak on. Once again, all labs will be documented later on. Simply taking notes here. 



## 10.30.2024


**Today's Topics**
* Types of Linux
* Using Linux (Beginner)
* Docker and Vagrant


**Types of Linux**

Server Linux - a Linux version that is used as a server. It doesn't always have a GUI. You usually connect to the server by SSH-ing into the terminal. Servers are usually in a data center or in the cloud. There is less software installed so you have less applications to keep track of. This is general information on servers so nothing new here. 

Desktop Linux - a Linux version that's used for daily tasks. It's like a personal computer. This definitely has a GUI. 

Mobile Linux - a Linux version used for mobile devices. Android is a modified version of the Linux kernel. 

Linux Virtual Machines - a Linux VM. Pretty straightfoward. The OS is sharing resources on a computer with another OS. 

Different Architectures - the 64-bit CPU from Intel is the most common. x86 64-bit. Get familiar with this. 

**Using Linux**

Use SSH to connect to a keyboard and monitor on the target server. Secure SHell. A shell is a command interpreter. The three layers of the SSH protocol are the transport, authentication, and connection layers. You can also use SSH to transfer files. 

The CLI is used to configure and manage Linux systems. 

Most configuration files in Linux are in plain text. 

There's a default key on your computer to connect to other devices but obviously you would want to customize this key as much as possible. 

You can use the CLI to SSH into devices. Usually it's a `username@<computer name or IP>`.

The root user is the highest access of any user. You may need to log into the root user to make changes to your OS such as download software and change file permissions. Use `sudo` for this. Sudo is logged in the system logs every time you use it. 

A Cloud Guru (ACG) then had me complete a simple lab where I logged into a CentOS and Ubuntu distribution of Linux to install a software called `Elinks` and then display some text using the software. They did this to show a difference between the install commands for both distributions. CentOS uses `yum` and Ubuntu uses `apt-get`. I'll document this in another GitHub repo.

**Docker and Vagrant**

A docker container contains everything required to run an application. They don't have to be self-contained. It's like a stripped down version of an OS image to allow you to do a specific task or run some code. 

A single Linux server can run a large number of containers. You can also use Docker to download the images you want. There's a huge database that Docker has for this. 

Vagrant is a tool from HashiCorp. It helps you build and manage virtual computer environments. It's free. I'm not really sure why we need this. Apparently, it's used to automate the creation and management of virtual machines. So Docker is for containers and Vagrant is for VMs. But can't we just use Terraform for VM creation automation?






