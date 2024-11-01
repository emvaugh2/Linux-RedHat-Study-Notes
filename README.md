# Linux Red Hat Study Notes

**Greetings! I'll be publicly documenting my Linux upskill experience here. Cloud and DevOps professionals have been constantly stating that Linux is an important skill to have in the space so I'm going to spend a few months building those skills via courses and hands on labs. I highly doubt I'll be taking any Red Hat certifications but who knows. Maybe I'll attempt it.**


## 11.01.2024


**Today's Topics**
* The Linux Kernel

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






