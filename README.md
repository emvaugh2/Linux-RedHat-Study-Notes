# Linux Red Hat Study Notes

**Greetings! I'll be publicly documenting my Linux upskill experience here. Cloud and DevOps professionals have been constantly stating that Linux is an important skill to have in the space so I'm going to spend a few months building those skills via courses and hands on labs. I highly doubt I'll be taking any Red Hat certifications but who knows. Maybe I'll attempt it.**


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






