                                    # Linux Red Hat Study Notes

**Greetings! I'll be publicly documenting my Linux upskill experience here. Cloud and DevOps professionals have been constantly stating that Linux is an important skill to have in the space so I'm going to spend a few months building those skills via courses and hands on labs. I highly doubt I'll be taking any Red Hat certifications but who knows. Maybe I'll attempt it.**

## 12.23.2024

**Today's Topics**
* Red Hat Certified System Administrator Course (Labs Pt. 4)

Let's get this summary created. 

Lab 24 - Red Hat Certified System Administrator (EX200) - v8 Exam Challenge Lab
This is the last and final lab. It's 3 hours. I'm just going to go through the walkthrough but this shall complete my Linux studies. For now.
Noticed I gave the repo file name the wrong extension (.rpo instead of .repo) and the OS did not like that at all. It wouldn't show the youtube-dl package in the EPEL repo. I used `mv /etc/yum.repos.d/epel.rpo /etc/yum.repos.d/epel.repo` to rename the file and that enabled it. 

I've actually caught a few errors in the solution guide which is very nice. I noticed the `fstab` input they gave me didn't have the absolute path. `mount -a` didn't like that format. I changed it though. This was dealing with persistent mounts for Stratis.

We literally did like all the RHCSA exam objectives in this one lab. I was able to follow everything although I don't fully understand every single step. I do see myself taking this test in the future. I think it would fair well in my GovTech journey but for now, I think this is all I need for a cloud role. This also took me like an hour and 45 minutes to complete. Very good practice. 

Lab 23 - Managing Basic Networking on RHEL 8
I saved this one for "last" since I knew I would most likely understand this one the easiest lol. We gave an interface an IP address, played around with DNS settings, and made sure NetworkManager starts automatically at boot. Pretty chill. 

Lab 22 - Managing Containers on RHEL 8 Using podman
Okay so this lab was actually pretty cool. We used  `podman` and `skopeo` to play around with some containers. We pulled a container down from the docker RedHat registry or something. Then we ran it and exited it. Then removed it. But I love how you can just spin up a whole new computer pretty much that quickly. Super nice. We tried to make a customer containier using `podman generate systemd` but they said this command has been deprecated. 


Lab 21 - Managing the Firewall on RHEL 8
We configured a web server and then changed access on the firewall via `firewall-cmd`. I'm not familiar with Drifting zones so that was beyond me but I know how to install, enable, and check the status of firewalld and Apache. So we're good there. 

Lab 20 - Using File Access Control Lists (ACLs) on RHEL 8
This lab was actually pretty helpful after coming back to the labs with a clear mind. The Linux ACLs have been confusing up to this point but it seems pretty straightforward now. You can have your usual permissions but you can also set permissions for certain users and groups as well. It's pretty straightforward enought to read. And that's all we pretty much did. Very helpful. 

Lab 19 - Managing Users, Groups, and Superuser Access on RHEL 8
We created and added users and groups. We then made changes to the `visudo` file. I've done all of this before. I still need to get more familiar with the `visudo` file but I'll revisit it. 


Lab 18 - Configuring Logical Management (LVM) Using RHEL 8
Apparently you have to tell the kernel of a partition changing using `partprobe`. We created some partitions and used LVM to create some logical groups. We extended and reduced them. Very flexible. Straightforward. 


Lab 17 - Managing Disk Partitions and Mounts on RHEL 8
We pretty much just set up new partitions, assigned the partitions a file system and mounted them. Then we did persistent mounting. After that, we did the same thing with swap space block devices. 



## 12.21.2024

**Today's Topics**
* Red Hat Certified System Administrator Course (Labs Pt. 3)

Lab 15 - Managing Packages and Using Application Streams in RHEL 8
Tired. May have to go back through this lab again. I don't understand all of this module stuff. The AppStream material seemed pretty straightforward though. 


Lab 16 - Managing the System Bootloader in RHEL 8
I'll fill in the notes laters. 


## 12.20.2024

**Today's Topics**
* Red Hat Certified System Administrator Course (Labs Pt. 2)

Lab 7 - Managing File Systems on RHEL 8
This lab was all about using our block devices to partition said block devices and assign them to a file system while also using `fstab` to keep that mounting point persistent. We also went through setting up a NFS but I still need to practice that. I understand the process but I would definitely have to practice this a lot. 

Lab 8 - Working with File and Directory Permissions on RHEL 8
This lab also wasn't too crazy. We just created some users and assigned them to primary and secondary groups (with passwords). The second half of the lab focused on GUID and sticky bits. I still need to get more familiar with the overlap of these commands. 

Lab 9 - Managing Layered Local Storage with Stratis on RHEL 8
We basically used Stratis to merge our block devices into a pool of storage. We can write directories and files to this pool. We then persistently mounted this pool in /etc/fstab. We used the stratis CLI commands to add block devices to this pool, create snapshots of our pool, and to destroy (erase) our pools. Seems pretty useful once you get the hang of it. 

Lab 10 - Managing Storage Using LVM on VDO on RHEL 8
We just did soome tasks with VDO. I was more interested in the script we ran and the file permissions than the actual VDO process. Im not learning this unless I need it. 

Lab 11 - Managing the Boot Process on RHEL 8
This lab was pretty straightforward. We messed around with the shutdown and reboot commands. The main thing that stood out to me was using `systemctl` to changing the target when booting up. I'm familiar with this commands and switching between the multi-user.target and the graphical.target settings. 

Lab 12 - Managing Processes and Tuned Profiles on RHEL 8
We actually did a lot in this lab. We used the `top` command to see which processes were running and using up the most resources on our OS. We also used the stress test mixed with the `renice` commands to re-prioritize the `stress` process to see how it can affect our system. We went over multiple ways to kill a process. I think `pgrep` will be very useful in the future was far as finding the PID for a service. I didn't understand the process scheduling part because I don't remember us going over this. 

We also modified the `tuned` profiles which I didn't know you can have multiple profiles running at the same time. Lastly, we used grep to search through a tuned file but we used the `-n` flag which told us exactly which line our parsed information was found on. We then used `vi +<insert #>` to jump directly to that line. I have no clue you could do this. Grep and vi are so powerful. 

Lab 13 - Working with Log Files and Journals on RHEL 8
We pretty much learned our way around using the  `journalctl` command and it's different options. The one I found the most useful was using `/NTP` (you can use whatever term or service you want) inside the actual `journalctl` output command to find the lines that contained NTP. You can also do an option to only query the logs for the last X amount of minutes. I would honestly just stick to grep for searching though. The last thing we did was make sure the logs were persistent. 

Lab 14 - Managing Key Services on RHEL 8 - systemd/Scheduling/Time Services
We pretty much went through the motions of using at, cron, and chrony for automated jobs and time servers. Nothing much to see here. 



## 12.19.2024

**Today's Topics**

Will return tomorrow. 


## 12.18.2024

**Today's Topics**
* Red Hat Certified System Administrator Course (Labs Pt. 1)

I didn't do any of the labs. Just all the video series lessons and the quizzes. We have 24 labs to complete. Lets get started. 

Lab 1 - Accessing Linux System Using RHEL 8
First off I really have to go over this key generation thing. It messes me up every time. But I just learned that you can type `ssh user@IP` followed directly by a command to log into that server and run that command. That was pretty cool. I was able to tar a file and use `scp` without having to interact directly with the remote device's CLI. 

Also, this lab was a lot more involved than all the previous labs. I'm going to have to play closer attention. 

Lab 2 - Vim Survival Kit
This is just making your more savvy with `vim`. If you just type vim, it will create a new empty file. You can do `:w <name of the file` to actually get it a name. Nice. 
I definitely need to remember the main commands for navigating a vi or vim file. It will help me alter files so much easier. But so far, I know how to work with them enough to edit them. Nothing much here. Just shows you how powerful and agile Vim can be if you really get to know it. 

Lab 3 - Using Input/Output Redirection and Analyzing Text on RHEL 8
This lab did some of these actions in a convoluted way but I did learn a little about the `find` command. You can actually use this along with the `-exec` option to search for strings within a file, not just on the file or directory. So keep that in mind. 

Lab 4 - Managing Files and Directories on RHEL 8
I really only did the hard and soft link portion of this lab. Everything else I'm familiar enough with. Felt like overkill. 

Lab 5 - Creating Simple Shell Scripts
We just created a script to add and delete users based on a user file we fed the script as input. Pretty straightforward. I can always go back over the script syntax to get more familiar with every single detail. 

Lab 6 - Managing SELinux on RHEL 8
Now, I don't plan on fully learning this until I either try to take my RHCSA exam or get a job actually using this. So We're just going to run through this lab really quickly and call it a day. 
Yeah not sure what I'm doing here but I do know I need to get more familiar with the `ausearch, semanage, restorecon, and semodule` commands. The `getenforce` and `setenforce` were pretty straightfoward. So was `sestatus`. But I still need to completely understand what SE is for. I know it's for security but I don't see why we need this additional step. 







## 12.17.2024

**Today's Topics**
* Red Hat Certified System Administrator Course (Chapter 5, 10, and 11)

Use `getfacl` and `setfacl` to see and alter ACL info. 

Use `fdisk` and `gdisk` to manage partitions. It will walk you through the process. This is also how you can allocate partitions for swap spaces. 

We're familiar with persistent mounts using /etc/fstab. Here are the best device identifiers: Files System Identifiers > file system UUID and file system Label. Device Identifiers > World Wide Idenfitifer (WWID), Partition UUID, and device serial number. We can go over the structure of the fstab file though. You have the block device, the mount location directory, the file system type on the device, the mount options (defaults), the backup option, and the check order for fsck. 

The backup option can have either a 0 or a 1 for the entry. The check order for fsck can be either 0, 1, or 2. For the backup option, 0 says skip the back up and 1 says back up the system. For fsck, 0 says skip fsck, 1 says check with the highest priority, and 2 says check the file system at the lowest priority. 


## 12.16.2024

**Today's Topics**
* Red Hat Certified System Administrator Course (Chapter 9)

Busy day at work. Just filling in notes here although it's the 17th. 

`useradd`, `usermod`, and `userdel`. Same thing with groups. Use `passwd` to manage passwords for users. You can use groupmod to change the name of a group. 

On modern distros, you have to use the `-m` flag in `useradd` to tell the system to add a home directory for that user. Home directories are not automatically created. This is because certain services like nginx and stuff can have user accounts too for specific purposes but they don't need a home directory. 

A user can have only one primary group but can have multiple secondary groups. You can use `usermod` to change the secondary group for a user. Use `groups <username>` to get a user's group information. 

Use `chage <username>` for an interactive prompt to change the parameters for a user's password. 




## 12.15.2024

**Today's Topics**
* Red Hat Certified System Administrator Course  (Chapter 4)

The /var/log directory is the direction for system and application logs. `journalctl` is used for querying the systemd journal. Use persistent journals to log to disk journals persistenting across reboots. 

Go to /etc/systemd/journald.conf. This is where you can change your logging mode to persistent. You need to change #Storage=Auto to #Storage=persistent. 

`top` stands for "top-level" overview of the system's most resource-intensive tasks. It just displays the top processes currently running on the system. 

Use the `renice` command to reset the nice value of a process. The nice value affects a process's scheduling priority, determining how much CPU time it gets relative to other processes. It's called nice becuse it determines how "nice" this process will be compared to other processes by yielding some CPU time. So basically how fair it plays with other processes that are also fighting for CPU time. Remember, niceness levels range from -20 to 19 (highest to lowest (yes, seems a bit backwards, I know)). You can do `renice <nice value> -p <pid>`. Straightforward. 

The Tuned service is an intelligent application that uses system monitoring to optimize system performance for specific types of workloads. /etc/tuned/tuned-main.conf is the main configuration file for tuned. /etc/tuned is the location for custom profiles. It overrides /usr/lib/tuned configurations with the same name. /usr/lib/tuned is the distro-specific profiles, each stored in its own subdirectory. Each profile has its own tuned.conf configuration file. 

Think of `tuned` like Window's Power Plan mode. Like hey once we get to a specific battery level, go into save battery mode. Or if our battery is at 100% and we're plugged into the charger, beef up all computer performance because you have the power to do so. `tuned` for Linux is the same thing. Although you statically set these tuned profiles, you can have your system enable dynamic tuned as well. 



## 12.14.2024

**Today's Topics**
* Red Hat Certified System Administrator Course (Chapter 7 cont.)

Chapter 7 - Deploying, Configuring, and Maintaining RHEL 8 Systems. 

Use `chrony` instead of `ntp` for anything time related. You can go back over this lesson if you really need it. 

You're already familiar enough with `systemd`. Just use `systemctl` to control all the services. 

`dnf` is the same as `yum`. Just keep that in mind. 

Okay lets go over Application Streams (AppStreams). AppStreams allow for multiple versions of an application (lets say Python) can exist on the server. You can have Python 3.1, 3.2, and 3.3. As you know, sometimes services are version specific so they need to have the write version of lets say Python in order to function. This also allows for you to install new versions of an application and test it to see if it works. 

There are also profiles for each application version that only downloads the packages you need for that specific version. You have common (the usual package), devel (for developer), and minimal (for only the most basic version of the application). This allows you to only download what you need. It saves on disk space too. You can switch between both application versions and profile versions. 

Now, you'll have a system wide version that you use but another team can log into a server and temporarily switch to a version and profile that suits them. So it just allows for flexibility when using applications. 


## 12.13.2024

**Today's Topics**
* Red Hat Certified System Administrator Course (Chapter 6)

We're going to start at Chapter 6 because 6 and 7 are the biggest chapters and I would like to finish this course up. Chapter 6 is Creating and Configuring File Systems on RHEL 8. 

xfs is the default file system for RHEL 8. You can grow xfs but not shrink it. You have a max size of 1 PiB. You also have ext4 which is the latest version of the ext file system. You can grow and shrink it. Max size of 50 TiB. vfat is used for working with multiple OS like Windows and Linux. It has a maximum theoretical size of 16 TiB. 

The "f" in `fdisk` stands for format. This is how you create partitions on a block device. All you need to do is follow the prompt which is mostly just prressing enter. You can set the partition size here though. This does not put a file system on it. You still need to do `mkfs` to put the file system of your choice on the partition. 

Always follow up with a file system check (fsck) after you've created your file system. You can use this command for ext4. You can use `xfs_repair` for xfs file systems. Check everything in `lsblk` as well. 

Remember to us /etc/fstab to create persistent mounting of partitions. Use the UUID for this. You have to do `mount -a` after you've added these partitions to the `fstab` file. 

NFS (Network File Systems) are exactly that, file systems for networking. Remember, Linux is the OS of files and directories. Almost everything is a file or directory. So this is specifically for networking. There are two versions: NFS V3 and NFS V4. Linux NFS is like a shared drive system on Windows. I think it's the actual file system and not a mounted shared drive. But it's like, how the Linux systems know how to find a shared drive. Does that make sense? We'll revisit this as well. 

You need to add your shared folders to the `/etc/export` file to tell your OS what folders you want to share. I think you need to inlcude the IP address of the system hosting the shared folders. Now, you have to use `systemctl enable --now nfs-server` to make your OS an NFS server. We'll come back to this. 

Lets talk `autosfs`. We have an autofs.conf file (defines how the autofs service itself works), auto.master file (the configuration file for all the file systems within autofs), and map files (individual configuration files for on-demand mount points). 

Auto.master file - where we define all the file systems we want to mount with autofs. You only put the mount point and the location of the map file here. 
Map file - where we configure out individual mount points. 

Yeah this `autofs` stuff was confusing but I believe I got the hang of it. You have to specify on the NFS server which directories you plan to host. 

On the client side, you have to configure the auto.master file to tell the autofs service which directories are being found on the NFS server and where to look for the rules for that directory. So specify the directory first and then point your distro to the file that will give it the directory rules/info. This second part is the actual map file. You can name a map file anything you want but it would be better to start it with `auto.<whatever>` just for a good naming convention. You can do `auto.data`, `auto.dogs`, whatever. It's up to you. 

Lets head to the map file such as `auto.home`. You create this file from scratch. This is where you give your autofs the rules. Say you put `* 127.0.0.1:/home/&`. Lets break it down. The asterisk * says all users need to follow this rule. Anybody who access this file will follow this rule. The 127.0.0.1 loopback address is just stating where IP address of the NFS server. This could change if your NFS server was on a different subnet or a PIP. The /home part says that you're looking for the /home directory. The & is like a wildcard as well. If you're the user Manny, it will swap the & for Manny. 

After you do this, you'll need to enable or restart your autofs service using `systemctl`. Don't play with autofs.conf. This is if you want to change the way the autofs service behaves. You most likely won't have to do this. Only mess with the map files and auto.master files. 

I believe also in this case, you need to create these directories on your NFS server first. So the /export/home directory needs to be created. Go back over the video and see where you do this. They had to create the directories and then go into /etc/exports and define both shared drive folders here with the options. You have to do this first before doing the autofs. We'll revisit this. 


"Okay so when you use chown to set the group owner to marketing, the directory will have the root user as the owner and the marketing group as the group owner. 

If Manny has his secondary group as marketing and his primary group as Manny, he still technically has the rights to make a file in this directory because the group owner is marketing which he's a part of. 

When he creates a file, he will be the owner and the group owner will inherit his primary group which is Manny. So that's why we see Manny Manny. 

When we set a GUID or whatever for the directory (lets say engineering), no matter who creates a file or their group ownership, the file will always have a group ownership of engineering."

Okay I finally understand why GUIDs are important and the User version as well but lets talk about GUIDs. When you use set-GID, the group owner of all files in that directory will always be whatever group you set. You can set the user and owner of a directory and file using `chown`. Depending on the user's primary and secondary group, they can make changes to a directory or files in a directory. If the user's secondary group is the same as the directory's group, they can make changes although their primary group can be different. So when you do `ls`, the user and group would be that user and their PRIMARY group (which could also just be their name if the primary group wasn't set when you created this user). If you want to make sure that every file and directory is still the group that you want it to be, use the `set-GID` command.

As far as the SUID, this will make sure no matter what process is being run by whatever user, the process owner will be the one you set. It's like letting someone run something in sudo but they don't have the sudo password. They can run the process but since root is the owner, the process will execute. It's a way of elevating privileges in a safe way. 

Do I need this Stratis stuff? And this VDO stuff? Apparently it's not even on the test. I'll revisit it if I ever need it on the job. 

Chapter 7 - Deploying, Configuring, and Maintaining RHEL 8 Systems. 

`at` is good for one time jobs. `cron` is good for recurring jobs. Cron jobs are located in /etc/crontab. The directory for packages to add cron entries is /etc/cron.d. You go to /var/spool/cron for crontabs created via crontab -e. 
If you cat the /etc/crontab, it will show you format on how to build a cron job so definitely get familiar with it. 

To see a list of the crontabs or edit the crontab, use `crontab -l` and `crontab -e`, respectively. 

You need to make sure `cronie` is installed first. This is how you can use the cron service and make sure it's enabled using `systemctl`. 

`cron.d` is for service-specific tasks like httpd, nginx, and mysql. They might appear when you download these packages. You can modify them and add your own but they're usually separate from the manually configured crontab tasks that you create. Think of it as like, Windows as a Service. You might have an application that runs routine maintenance. The funny part about the maintenance is it would also be scheduled in the cron.d folder which sounds too simple to be true but that is where that application will automatically populate it's routine maintenance. The crontab is where you would just create some task from scratch and stick it here. 




## 12.12.2024

**Today's Topics**
* Red Hat Certified System Administrator Course (Chapter 1 - Chapter 3)

I actually went through an Intro to Containers and Orchestration course yesterday. It was a nice review. May look at Docker and RHCSA at the same time. 

The `tar` command by itself doesn't do anything so you always have to have options. Make sure you're familiar with the common options like c, z, f, x, v, t, etc. 


## 12.11.2024

**Today's Topics**
* Linux Labs (Part 6)
* Red Hat Certified System Administrator Course (Chapter 1 - Chapter 2)

RHCSA Material
You can documentation in the /usr/share/doc. I'm not really sure what the difference between the man and info commands are. I've been using man this entire time. Look at all three I guess. 

You can find the LICENSE file in the `/usr/share/doc` directory. Then navigate to the service that you're looking for (`httpd` for example) and then it should be listed in that service's directory. Along with a readme, versioning, etc. All of that. 

You can use the `tree` command to see all the directories and files listed in a directory for whatever directory you choose. This can be a lot of ouput. But it's also very useful. 

For grep, you can search for a phrase and put the destination right after that. For example, `grep httpd /var/log/* which says look for all httpd appearances in the /var/log directory and files. This is better than doing `cat /var/log/* | grep httpd`. Demoggification or whatever. 

`wc` stands for word count. 
__________________________

Bash Material

Lab 4 - Implementing Bash Flow Control in an Existing Backup Script
Okay this lab beat me over the head haha. So this one also built off of the previous scripts. We needed to create a function to cancel the script and clean up any work the script has done. I didn't know how to do this at all (besides creating the function) so I needed Chat GPT to walk me through every part. Fyi, I've never worked with traps and any form of the `sleep` command so this was new to me. Alright lets talk about it. 

In the beginning of the script, the guide created a function called `ctrlc` that will basically remove the backup files and directory the script has created. This part was pretty straight forward. You just have to be aware of the function format which is function ctrlc { ... }. The one thing I didn't really know was the the guide used an `exit code 255` command in the function. Chat GPT was saying the exit code tells you if the script was successful or not. An exit code of 0 is successful. Anything else just indicates something different. The user can give the script any number exit code they want (these exit codes are 8-bit in structure). It's nice to give it an exit code based on how you plan on interpreting your script. It can also let you know when a specific part of the script didn't work properly. 

Afterword the script was defined, the guide used the command `trap ctrlc SIGINT` which I had no clue what this meant. Lets break it down. Obviously the `ctrlc` part is referencing the function above this line. Let's start with SIGINT. When you press Ctrl + C (just in general in the Linux CLI), it will stop a process. When you press this, it sends the system a SIGINT which stands for signal interrupt. It says hey stop this process! So the line basically says, if you get a SIGINT sent to the system, trigger this trap right afterwards. Don't just stop the process. Once the trap is triggered, it will run the ctrlc function. So it's kinda like Ctrl + C -> `SIGINT trap ctrlc` in my mind but this is just the syntax they use. 

We also had to make an if loop that says if the user didn't pass an argument to the script, exit the script and tell them you need to give us something as a parameter. I understand if loops and the echo statement but obviously I just need to get more familiar with the Bash format. The one part I didn't understand was `if [ -z "$1" ]; then` (I believe this was the exact line but that's not important). I didn't know what that `-z` stood for and why we needed the quotations around the parameter variable. Now I forgot why we needed the quotation marks but lets focus on the `-z`. That basically says if the parameter has 'zero length' (I'm not sure if it said a string of zero length or a value), then this statement is true. If the statement is true, it will trigger the if loop. So that makes sense. If the parameter value is nothing, then trigger the loop saying "Give us a value". What I didn't understand is the guide also gave this if statement an exit code of 255. I'm like wouldn't you want it to have another value?? I don't know. 

Lastly, we had the actual script and everything but at the bottom of the script, we used `sleep 15` which basically says don't do anything with this script for the next 15 seconds. This is so you're able to actually press Ctrl + C because the script will run very quickly. It's not possible to press Ctrl + C that quickly. This gives you time to actually trigger the trap once you send the SIGINT to the system. So basically the script will run through all these lines so it will actually create the backup files and log file but once you trigger the trap, it will remove everything it created. You have 15 seconds to make a decision.

So the lab definitely makes sense. This was a little above me though but I know practice makes progress so we'll keep learning!

Lab 5 - Implementing Bash Regex in an Existing Backup Script
So while I was able to complete this lab on my own, the guide solution was a little different (more thorough but also more convoluted). So they basically wanted us to only backup the files that had adent and financial in the file names using Regular Expressions (RegEx). Now, I'm just getting slightly familiar with `grep` let alone the RegEx extension. So here's what I did below:

`cp -v /home/$USER/work/{aden,fina}* /home/$USER/work_backup/ >> /home/$USER/$MYLOG`

I just added aden and fina to the end of the directory so that it only matches the files that have those two terms in their file name followed by anything else (hence the asterisk). Now, I know this isn't that thorough because my backup files all began with adent, financial, or football. If they didnt START with these terms, my solution wouldnt work. But they did so it did lol. 

The guide did a RegEx expression that looked something like `grep -E (adent|financial)` which probably just said if you find these two terms anywhere in the file, match on this. I didn't ask Chat GPT so don't quote me. Then they created a for loop to keep matching these file names and copy them over. They then commented out the line I altered above. 

There are more than one way to skin a cat. I have to keep learning. But my solution worked so I'll take it as a win!

We'll revisit Bash scripting but that's the end of the Bash scripting course. My last Linux thing I'm going to pay attention to will be the RHCSA course and then I'll move over to Docker. 


## 12.10.2024

**Today's Topics**
* Linux Labs (Part 5)

Lab 2 - Incorporating Substitutions in an Existing Backup Script
So this was pretty much a play off of the last script I created. Now, they wanted us to incorporate timestamps before and after any work was completed. They said use the `date` command for this so I just googled timestamp command for Linux. I was given this from StackExchange `echo $(date +%x_%r)`. This worked perfectly. I copied and pasted in between the commands fed the ouput to the log_actions.txt file I created. It didn't work at first because I didn't realize the way they created the script, we had to feed the script name a log file name as parameter. After I figured that out, the script ran successfully. 

I believe the second part of the lab, they wanted us to assign our date command to a variable. That was the substitution part of it. I didn't know to do this but that part was very straightforward. Honestly, that is how I prefer to do this type of work anyway. Still learning that I can do that in Linux. But this was a good lab. 

Lab 3 - Using Variables in a Bash Backup Script
This builds off of the previous two scripts. This time, we want to use a variable for the home directory so that any user can use the script to back up their files. Also, they wanted us to be able to pass a parameter to the script file so the user can name their log file whatever name they chose. The funny thing about it is the first time I made the script, I used the `$HOME` environment variable so I wouldn't have to copy the long home path. So I did the same thing here. Wherever the script had the file path, I just replaced it with the $HOME variable. The script also automatically named the log file as log_backup.txt or something. I replaced all of these occurrences with $1 so whenever a use ran the script and put a file name after the script name, it would pass the $1 the log file name they chose. I switched to the other two users and tried the script. It worked. Just in case you need it in the future, just replace all most of that stuff with `/$HOME/$1`. 

Lab 4 - Implementing Bash Flow Control in an Existing Backup Script


## 12.09.2024

**Today's Topics**
* Linux Labs (Part 4)


Bash Labs 
Lab 1 - Using Bash to Write a Backup Script

Here's the script I wrote. I didn't look at the guide for this. I just experimented until I got the right one. I didn't even use Chat GPT.

#!/bin/bash

mkdir $HOME/work_backup

touch $HOME/log_actions.txt

cp -vR $HOME/work $HOME/work_backup > log_actions.txt 2>&1

Lets explain this. You have to start off with the she-bang. I created the new work_backup directory to be the new storage place for the files. I used the $HOME environment variable to make sure each time, the directory was created in that specific user's home directory. I did the same thing for the log_actions.txt file. Then I used the copy command to copy all the files. You have to use the -R option to recursively copy all the files in the original directory. I also had to use the -v option for verbose so the OS can tell us exactly what each action was doing. I wanted all the stdout and the stderr messages so I directed all of this output to a log_actions.txt file. The 2>&1 redirect just makes sure to get the stdout and stderr output. 

Simple enough. 

Good night. 


## 12.08.2024

**Today's Topics**
* Linux Labs (Part 3)

Lab 16 - Permitting and Blocking Traffic with the Firewall
This lab wasn't crazy at all. We just made sure the firewall was running and listening on port 80. We tried a curl but it wasn't permitted in the firewall. We made a rule specifically for `Client1` to connect to the server but not `Client2`. We did a curl from both clients. Then we saved the firewall rules. 

Lab 17 - Advanced Firewalld
This was above me but we created a new service and put this service in the default zone. We added two subnets to an IPset and made a rich rule for the IPset. I'm not sure why you would need to do this but that's what we did. Seems a bit convoluted. 

Lab 18 - Firewall Troubleshooting
We just wanted to figure out why the client couldn't connect to the server on port 80. We checked that the firewall was running and that it was listening on the correct port. After doing a `firewall-cmd --list-all`, we noticed the rule blocking the 10.0.1.0/24 subnet was before the rule accepting the traffic from 10.0.1.11 which is obviously a problem. We then created a new zone for the 10.0.1.11 resource but once again, I don't know why we did this. I would've just reordered the rules. 

Anyway, that completes all the Linux Networking labs. I have 5 Bash labs to do I believe. I'll do one tonight at the very least. The networking labs were way more fun than the course material. Overall, it was nice to know we can change a Linux server into any type of networking service we need. I have to continue to wrap my head around that. I'll do some of these periodically just to keep these skills fresh. 


## 12.07.2024

**Today's Topics**

I was having a rough day. Didn't even open a computer today. 


## 12.06.2024

**Today's Topics**
* Linux Labs (Part 2)

Okay I made it through 12 of the 18 networking labs. I have 6 more to go and then I have 5 scripting labs. I don't think I'm going to do all of these tomorrow but we'll see. I know the scripting is more important to me. I can handle the networking stuff if I just see it a bit more. 

Lab 13 - Create an SSH Tunnel
This lab was pretty straightforward. They just had one command that established the SSH tunnel and then we verified that it was working by using `curl`. Not too many meaningful insights but I will ask Chat GPT to breakdown the SSH command. It was only one. 

Lab 14 - Creating a Load Balancer
`haproxy` was the load balancing solution of choice for this lab. This wasn't crazy. You set up `haproxy` on the main server. You change the configuration files to include your frontend and backend information. Then you go to your two backend nodes to make sure they're listening on the correct port. Then on your client, you do a `curl` to make sure it's working. Now, my client was only getting a response from Server 2. I ran a script to do curl 10 times in a row. All came back from node 2. On the server side, it was getting a response from node 1. Still not totally sure why that is. 

Lab 15 - Setup OpenVPN
We'll revisit this. I'm having a hard time getting through this lab. We'll come back to it tomorrow. 


## 12.05.2024

**Today's Topics**
* Linux Labs

This is definitely going to be a lab day. I have about...30 labs to do. I will not be doing all of them but I will get through a good amount before I shift over to Docker for a second. I'll post all the notess I can here. 

Lab 1 - Locating Network Information:
Just quick notes so when I come back to this, I can document it quickly. I used `grep` to get the output I needed into the Network.txt file. The commmand was `nmcli d show ens5 | grep IP4.{AGD] > Network.txt` which basically just takes the network information from interface ens5 but the lab asked specifically for the IP, DG, DNS IP, and domain. That's why I used that `grep` and did the RegEx type thing with the `[AGD]` characters. Got me the exact output. Also, the "d" in this previous command stands for "device". Make a habit of installing tab completion (`yum install bash-completion`) so you can get familiar with what all these non-flag things are. I REALLY HATE when instructors don't type out everything. Its hard for newcomers to know what it all means. I always tab out everthing in the Cisco CLI just so if anybody is watching, they can follow along. 

Lab 2 - Setting a Static IP:
This one was pretty straightforward. I'll have to ask Chat GPT to break down all of the commands. For example, it seems that we have to specify the Name (System) before we reference an interface. Also, how do I know if the device's IP was set dynamically in the first place? I get how manually configuring the info and then restarting the network system will make sure that the new IP info persists but I would like to know how it was dynamic initially. Lastly, I'm going to reiterate the tab completion feature. `con` and `mod` are short for connection and modify. This could be obvious but I would like to know specifically if that's it. Also, tab definitely helps to make sure you have the right command. Extremely useful 

Lab 3 - Multiple IPs on the Same Interface
Interesting. So the output without generally specifying an interface from `nmcli connection show` will give you a bunch of output. There appears to be two separate sections of IPv4 information. One is capitalized and the other is lowercase. The uppercase section had the original IP for eth0 as 10.0.1.10. After we added the two new IPs, those IPs showed up in the lowercase section for IPv4. I wonder why this is. I'll ask Chat GPT. Other than that, this is a pretty straightforward lab. Im just following the instructions so I can get the commands under my fingers and explore. Also, just typing `nmcli` will show you the info for your interfaces as well. I had to restart it twice but the second time, the output showed the 3 IPs for the interface. Interesting

Lab 4 - Creating an Interface Team
Okay I think typing "manual" in the interface connection configuration specifies a static IP. I think. I'll ask Chat. This lab was pretty straightforward too in the sense of, while I've never done this before, I'm familiar with the process of setting up a port-channel interface in Cisco. So it's basically just memorizing this process. I'll ask Chat the smaller details as to why the process is exactly this way (more so verifying that the interfaces are up, how to tell the difference between deleting a connection and a device, what exactly does it mean to delete a connection, etc) and what's the order of operations for setting up the Master and Slave interfaces. Seems like you have to bounce them in the right order. 

Lab 5 - Working with Static Routes
Find out what `host` does. They did `host google.com`. It listed the PIPs but I want to make sure I understand it exactly. Also, go over the `ip route show` output. I want to make sure I understand every part of this output. Very interesting way to block traffic. I'll say that. 

Alright 5 labs down, 13 more to go. Taking a break. I'm only going to do 6 today and then a few Bash labs. Or who knows. I might bulldoze through all the networking labs today although I definitely should not do that. But this is fun because I'm familiar with this and this course was DIFFICULT. But the labs seem way more manageable. I doubt I'll remember how to make a DNS server and all that from scratch but at the least, I should be familiar with static IPs and routes, interface configuration, port channels and all that using the `nmcli` command. So I'll make sure I keep those skills up to date. 

Lab 6 - Establish Local Resolution
Okay the work day caught up with me. This might be my last lab for the day. We'll see what I accomplish when I get back. But yeah. I don't understand this DNS stuff so I'll have to ask Chat GPT about it. Label completed though. 

Lab 7 - Creating Name Servers
Didn't understand any of this. I think I'm going to call it one.  

Lab 8 - Troubleshooting DNS
This one actually isn't too crazy. I still need to make sure I understand all the output from `di`g and `curl`. I'm just not familiar with DNS so I don't know how to troubleshoot it. But this was simple enough where I can learn what's going on. No real notes. Just,I'm considering coming back to this. 

Lab 9 - Testing a Connection
Going to skip over the firewall labs for now because I want to be fresh to absorb as much information as possible. It's 11:09pm currently. Anyway, just like that I wish I didn't skip the firewall labs because we definitely made some firewall changes. I really gotta learn how curl works. But I see we added HTTP and HTTPS as services in the firewall. That's a bit weird. I would personally just add ports 80 and 443 but I guess....if we add it by service, we can use any port. We did this on the service side. We then went on the client side and used telnet to test connection on port 443 on the server. We were able to see all the plain text being typed. 

Lab 10 - Performing a Packet Capture
We were able to split the screen on a service into two terminals using the `screen` command. We started a new terminal using just `c` and we were able to run a packet capture on the right screen while sending data to our own server on the left screen. This was a bit trippy. I couldn't read the packet capture information too well but it did have data in it. 

Lab 11 - Port Forwarding with the Firewall
We'll need to go over what masquerading does. Looks like we just created a testing zone on the firewall for some source traffic to go to a port 80 on Server 2. I guess masquerading allows us to enable port forward. Now, they had a long port forwarding command that I just copied and pasted but I can ask Chat to break that down for me later. 

Lab 12 - Proxy Servers
Okay this will be the last lab for today. At least the last networking lab. I'm not familiar with proxy servers. I should definitely be familiar with port forwarding as a network engineer but I just haven't had to do this at all. I'm not going to say I don't care about Proxy Servers but I will say I'm not going to retain this knowledge because I haven't needed and I'm not sure when I will need it. This seemed straight forward. We had to download and enable `squid`. Then we made some changes to the conf file. We added a whitelist with .linuxacademy.com as one of the websites. We then commented out http_access localnet. Then we exported the http_proxy on the client machine (not sure what this does) and then we curled linuxacademy.com to make sure we could get it and only it. 



## 12.04.2024

**Today's Topics**
* Bash Scripting (Chapter 1 - 13)

Okay on to the fun stuff! 

All of these script files have to start with the she bang `#!/bin/bash` (or /sh). Also remember, the ~ denotes the home directory. If you type `env`, the CLI should print out all the environment variables you have in your current session. Use the \ character to escape the next character. We'll go into more detail on this later. 

![Image](BashSpecialCharacters.PNG)

Lets talk exit statuses. It's a number that is returned to the shell (you may or may not see this number) that lets you know if a command or script failed. The Zero exit status implies the script or program ran to completion and everything is fine. The Non-Zero exit status results can vary based on the script or program that generated the exit status. You can do and/or lists by using && and ||, respectively. For the or || syntax, the right side of the or will only execute if the left side failed. 

You can set custom exit codes as well. Lets talk about redirecting I/O (input and output). I'm familiar with this based on echo and appending. I'm still not super sure on why we need the opposite direction though. It was stated to "redirect file as input for a command" but my thing is, why not just us `cat` for a file and pipe that into the command? Talked to Chat GPT. Basically, "<" is less taxing on computer resources. It's cleaner and easier to read. It can be more simple but also less flexible than the pipe (pause). 

Redirecting stdout and stderr. Lets pump the brakes. Why are we doing this redirecting of stdout and stderr? Well I just had a whole conversation with Chat and from what I can see, this is a personal output control type of situation. When you run commands, you give the command an input (stdin which has a file descriptor of 0). You'll then get an output on your screen (stdout - file descriptor of 1). If there was an issue with your command (your command could've been partially successful for a fully failure), you'll receive some error messages on your screen (ex, file or directory doesn't exist) which has a stderr and file descriptor of 2. You can control where these error messages go. You can also just leave them on the screen. However, if you don't want them to go to a specific file for your own personal logging, you can use the syntax ` 2> error_log.txt]` to have all the error messages go to your (arbitrarily named) error_log.txt file instead of popping up in the CLI. Remember, you can choose whatever file name you want. 

Say you want the output of your command and any error messages associated with it to all go to one file. You can use the `2>&1` syntax at the end of your command to make sure that all error messages go to the same file or destination as your regular output information. Why do you need the "&" sign? Well this lets Linux know that the "1' is a file descriptor and not a file itself. If you didn't put the "&" sign, Linux would just write the error messages to a file named "1" which it would automatically create. So here's an example. Say you do `touch file1.txt file2.txt file3.txt`. That will create the three files. Say you do `cat file1.txt file4.txt`. Well obviously, file4.txt doesn't exist so you'll get the output (stdout) of file1.txt but you'll get an error message (stderr) for file4.txt saying "No such file or directory exists". Say you want to write the output of `cat file1.txt file4.txt` to a completely new file called `output.txt`. You would do `cat file1.txt file4.txt > output.txt`. That's all fine and dandy. Your stdout info will get sent to the output.txt file but your error message (stderr) will show up in the CLI. Say you want both the stdout and the stderr (so error messages) to all go to one file and not show up on the CLI. You would do `cat file1.txt file4.txt > output.txt 2>&1`. That is the syntax to do that. This is what it's useful for. 

Now, I'm too beginner to see why I would truly need to do this besides logging files and maybe feeding this info to other applications like Prometheus or something but I understand what's happening now. 

![Image](BashUtilityCommands.PNG)

`/dev/null` is a blackhole for information. 

LOL just got to demoggification or UUOC: useless use of cat. I do this all the time. I'll break the habit. 

Lets talk variables. Bash variables do not have data types (like strings, integers, etc.). All variables start with a "$" sign when you want to call it. Here are some Bash variables that are already built in: SHELL, LANG, MAIL, PATH, and HOSTNAME. Keep in mind, you can also make entire directories and files a variable in your Bash script.

Function - used to group code in a logical way. You can create the function in a script (lets say you define a function called cloud). Then you can simply type `cloud` in your script and it will call the function. The function will not run unless you call it. You can define it but it only just defines it. To call it, you have to type out your function name afterwards. Another way to define a function is to use `<function name> () { }`. For example, `cloud () { }` is the same as `function cloud { }`. 

When you use $1 and $2, you have to pass these parameters into the function when you call on it. In the same line. I'm used to the CLI prompting you for the additional parameters. I'll keep this in mind. 

Array = matrix. For example, `NUMBERS=(1 2 3 4 5)`. If you `echo $NUMBERS`, you only get the first (index 0) value. You have to specifically state which value you want by doing `echo ${NUMBERS[2]}`. If you use `echo ${NUMBERS[@]}`, you'll get all the values. To find the numbe of indexes in the array, you can do `echo ${#NUMBERS[@]}`. If you want to know the index list, then use `echo ${!NUMBERS[@]}`. You can add an addition to the array using NUMBERS+=(9) or whatever value you want to add. Doesnt have to be the value 9. You can call portions of your array by doing `echo ${NUMBERS[@]:2:5}` which will call on the values from from 2 to 6. Be carefuly of that last index number. It goes to the number after that. Which is weird. 

Command substitution - when you use a command in place of a variable. You can do `$(<insert command here>)` instead of predefining the variable. This allows you to use a command to get the information that you want (such as cat or grep or which or pwd) and feed it into a variable. It's like, skipping the part of creating the variable and just putting a command in it's place. I wouldn't necessarily say that. Think of it as, say you want to create a variable to be used later. You can create this variable based on the command that you want it to do so the variable will have the information you need later. I think that's how that works. 


****************** Forgot to press commit so I lost about 3 paragraphs of notes. But please believe me when I said I went over all the Flow Control info. 



## 12.03.2024

**Today's Topics**
* Linux Networking  (Chapter 13 - 15)

We went over SNORT and OpenVPN configurations. I'm going to do the labs and come back to the notes. The videos were a little difficult to follow since we didn't have an outline beforehand. Today is definitely going to be a lab day. I need to finish the LPIC labs and get started on the Networking labs which I believe I'll be documenting. 

Back to the LPIC 102 labs, we made an alias for the `systemctl status httpd.servce` command. We just named it webstat and used a "variable" so pass the command based on which service we wanted to see. We put all of these aliases in the .bashrc file. The .bashrc file will run these scripts when you log into your distro I believe. With that being said, if you make any changes to the .bashrc file, you'll have to source it (basically reload the file) using `. .bashrc` so that you can use the edited commands. Keep this in mind. The "rc' stands for run commands or resource configuration. The "." at the beginning of the file denotes that this file is hidden. Just in case you want the syntax breakdown. 

Next lab, we created a directory in the root file directory, added four users to a group, and made that group the owner of the file. This was pretty straightforward. Sometimes I have to really keep using `pwd` and `ls` to see what directory I'm in and what files are available for me. But I know I should be checking the group and passwd directories to get more information on specific users. I'm also getting a lot more familiar with the `chmod` and `chown` commands although I did end up using the man page for one of them. Just to double check. Pretty straightforward lab. 

Okay we worked with some systemd service files with timer units. I just followed the instructions but I'll post what I learned. When working with `systemd`, your files should end in .service although it can be assumed. Add the .service onto the end of your files for your own sanity. Also, you use `systemctl` to tell `systemd` what to do. `systemd` (I believe the d is for daemon) actually runs the processes but you use `systemctl` to tell it what it what to do. Think of `systemctl` as the command line tool or the dashboard to interact with systemd. If you use `vi <file_name>` on a file that doesn't exist, `vi` will create the file for you. Useful if you don't want to type `touch` beforehand. We also placed the script file in the /usr/local/sbin directory because that is a part of your $PATH variable where your system will look for executables. This is so you won't have to specify the path or append the path to the $PATH variable. Also, we plced the .service and .timer files in the /etc/systemd/system directory because this is where systemd looks for unit files. Very insightful lab. S/o Chat GPT for clearing up a bunch of things but everything is making more sense with the unit files, `systemd` and `systemctl` stuff. 

For our 4th lab, we used the `journalctl` command to find out why our httpd.service file wasn't running. So we used the systemctl commands to start the file but it wasn't working. After using `journalctl -u httpd.service` (the -u flag is for unit files I believed based on my reading of the man pages), we found that the httpd.conf file didn't exist. So we copied the backup file over to the correct directory and renamed it to httpd.conf. Then, the system was able to find it and enable it. I used `curl` and `elinks` to verify the service was up and running. I'll say this about Linux so far, I DEFINITELY need to have this entire thing color-coded (coated?). It's so much information on the screen, it's hard to decipher it all. I didn't even see that the file couldn't be found at first until I completed the lab. I was like how did they know that? After running the `journalctl` command again, I spotted it at the top. Anyway, cheers to logging. 

The next two labs are working with MTA and CUPS. I'm not going to document this but I will post some insights if I find anything interesting. UPDATE: Nothing interesting at all although it was weird sending an email like that. Felt..primitive. 

7th lab is monitoring network traffic. Right up my alley. So this lab was kind of interesting. We had two servers and we sent traffic between the two machines. We used a prehistoric looking application called `iptraf-ng` to turn on network logging and send all the output to a text file. While that was running in the background, I opened up a new terminal to start sending and receiving traffic. We used the `nc` command on a specific port to connect to the other machine. Everything we typed afterwards would appear in the second machine's terminal. Very interesting. Then, we reviewed the traffic log file to make sure we saw the port 2525 traffic. I used `grep` to filter for the port number and I saw some traffic from the source and destinations. 

5 labs left. I'm going to take a break. This is already stressing me out with the network labs because it's 18 of them. And I want to document all 18. I may have to reconsider. But we'll see.

We completed a DNS lab and a sudoers lab. I'm not extremely familiar with DNS and I didn't really understand the sudo lab so I'll have to go back and ask Chat GPT to breakdown what was happening. 



## 12.02.2024

**Today's Topics**
* Linux Networking  (Chapter 8 - 13)

In Linux, you have netfiler which is a framework provided by the Linux kernel. It permits packet filtering, NAT, and PAT. 

THe system-config-firewall interacs with the iptables.service which comes from the /sbin/iptables. These work with netfilter. "Host administratively prohibited" in Wireshark usually means the firewall blocked your traffic.

Lets talk iptables. You have a FilterTable which is used to determine if a packet is permitted to continue or be denied. You have a NAT Table. You have a Mangle Table which is used for altering the IP headers of a packet in order to modify TTL, hops, etc. You have a Raw Table which is used for opting out of connection tracking. You then have a Security Table which is used for SELinux services. 

You have 5 NetFiler hooks that correspond to the 5 iptables chains. 

NF_IP_Pre_Routing > PreRouting - triggered by incoming traffic after entering the network stack and processed before routing decisions.
NF_IP_Local_IN > Input - triggered after the incoming packet is routed if internal.
NF_IP_Forward > Forward - triggered after the incoming packet is routed if remote (forwarded). 
NF_IP_Local_Out > Output - triggered by local outbound traffic once it enters the network stack.
NF_IP_Post_Routing > PostRouting - triggered by any outbound traffic, after routing prior to traversing medium. 

This reminds me of pre-policies for prerouting. The forward rules looks like the fast-track status for FTD firewalls. The input looks like the normal policies in the FTD firewalls. All of this looks like the SNORT and LINA process that the Cisco firewalls go through and how which parts of bypassed. 

You hae IPTable States: new - a new packet not associated with any existing connection. Established - established traffic. Related - packets associated with a connection already in the system but not an existing connection. Invalid - unroutable or unidentified packets no asssociated with an exisiting connection or suitable for a new connection. Untracked - packets set in the raw table chain to bypass connection tracking. SNAT - source modified by NAT. DNAT - destination modified by NAT. 

Firewalld has zones: drop, block, public, external, dmz, work, home, internal, and trusted. 

Chat GPT chimed in. Real quick:
iptables: Older, manual, rule-based.
firewalld: Modern, dynamic, zone-based.
Both are firewalls. 

Testing at each OSI Layer: L2 - arping. L3 - ping, traceroute, tracepath. L4 - ss, telnet, tcpdump. L5-7 - dig, service tools. 

Telnet will let you test again any port. It's more useful than ping. You just have to specify the port. I didn't know you could do that. I guess this is why we use test-network connection in PowerShell. 

You can use ncat to see if a device can connect to your server on your chosen port as well. TCPdump does a similar thing. 







## 12.01.2024

**Today's Topics**
* Linux Networking  (Chapter 6 - 7)

So Linux supports port-channel/etherchannel. Just think port redundancy. They call it Teaming and Bonding. These are two ways to do it with pros and cons with each. The instructor suggests we default with Teaming instead of bonding. Teaming supports LACP support (think IEEE standard for port-channel) and it also uses NetworkManager. Bonding doesn't require teamd and it better suited for virtual environments but it looks harder to set up based on the video. When doing either or, make sure you bounce both the master and slave ports. Think of the master port/interface as the port-channel and the slave interfaces/ports as the seperate interfaces (GigabitEthernet 1/0/12 and GigabitEthernet 1/0/13 for example). Teaming has team runners. These runners are broadcast, round-robin, active-backup, loadbalance, and lacp. Most of these are self explanatory. 

Teaming also has link watchers which are ethtool (watches for link state changes), arp_ping (monitors the ARP table), and nsna_ping (for IPv6 so ignore). Lets leave this here. I'll have more comments once I run through the labs. 

You can also use `route -n` to see the route table. This looks cleaner to me. You can add static routes using `ip route add <subnet information>`. You can also block routes by using `ip route add prohibit <subnet info>`. 




## 11.30.2024

**Today's Topics**
* Linux Networking  (Chapter 1 - 6)

Linux has a `tracepath` command that uses UDP instead of ICMP. Also, with ping, Linux will by default keeping sending pings unless you do Ctrl + C. You can use the options to send only a specific amount of pings (you're familiar with 4 packets). You can also do the -T option that will send TCP packets to your destination which will use Port 80 by default. 

The `ss` command (socket statistics) is the modern version of `netstat`. Keep this in mind. 




## 11.29.2024

**Today's Topics**
* LPIC-1 - Exam 102: (Chapter 6 - 8)

We're going over X11 and X.org which provides graphical rendering for UNIX type OSs. I've never heard of this before. `libDRM` is direct rendering manager. 

You can use `cron` and `at` to set up specific "jobs" or services to run at a specified time. This can be reoccuring (cron) or one time (at and also cron). Seems pretty useful for system management and sending process metrics to softwares like Grafana and stuff. 

Keep in mind you can change the language of your distro if you want to do that. You can alter the time and date of your system too. 

Use NTP and their set of commands for anything time and date related. You're pretty familiar with NTP so don't worry about this too much. For modern distros, I believe they use `chronyd` for these NTP options. This is different from `cron` fyi. 

`rsyslog` manages all the log files for systems not using `systemd`. 

The systemd journal stores all kinds of log messages across your system. So see the information here, use the command `journalctl`. 

The entries in `journalctl` are in a databse format. Don't let the output fool you. Use the option that will allow you to see it in it's field-value format. You can also reformat all of this into JSON. Keep that in mind. 

Common Unix Printing System (CUPS) - use this for printing services. To access the WebUI, use http://localhost:631 . Remember, localhost is just your local computer. Im sure it has some type of loopback address. 

I've never had to manage printers and print servers and I don't plan on doing it now lol. I'll do the CUPS lab but I won't be storing this info in my mind unless I know I'll need it in the future. 


## 11.28.2024

**Today's Topics**
* LPIC-1 - Exam 102: (Chapter 5)

I'm pretty familiar with scripting so I'm just learning how Bash does it instead of MATLAB and Python. The OR logical operator is `||` and the AND logical operator is `&&`. 

In Bash, you can compare integer values using `eq`, `ne`, `gt`, `lt`, `ge`, and `le`. That's equal, not equal, greater than, less than, greater than or equal to, and less than or equal to. 

The `until` loop is the opposite of a `while` loop. It will repeat a loop until something is FALSE. A while loop repeat something until a condition is true. 




## 11.27.2024

**Today's Topics**
* LPIC-1 - Exam 101: (Chapter 4 continued)

Completed the rest of the labs Exam 101. I'll finish the videos in the morning. Things are starting to make sense or at the very least, I'm starting to see how things are supposed to be set up in the default way. And many of these simple commands like `chmod`, `chown`, `mkdir`, `grep` and etc are getting easier to use. I still am quite lost when it comes to the flags because I'm not familiar with which options will help me out the most but I'll start to navigate that soon. 

Look at each directory as a docking port for ships. Look at the partitions/hard drives for each block/storage device as a ship. The ship just visits the docking port and then it leaves. This is basically how mounting works. You mount (visit) the hard drive to the directory (docking port) and then once you're done and loaded all your cargo (saved files and things), you unmount the hard drive (leave the docking port) at the end of the day. Now, obviously sometimes you want persistent storage so thats you keeping your drive mounted even after rebooting but this is the overall process of mounting. 

Use `mount` and `umount` for mounting and unmounting. 

You can use `umask` to see the default permissions set for your files and directories for both the current user and the root user. You'll just have to subtract your `umask` output from 777. To see where all of these default settings are stored, go to `/etc/bashrc` where you can also modify these settings. 


## 11.26.2024

**Today's Topics**
* LPIC-1 - Exam 101: (Chapter 4)

Block devices -> "sda" means the "s" is for SCSI or SATA. "d" is for disk. "a" is for the first block devices like this. "vda" is similar but the "v' is for virtual. 

Quick review, `lsblk` is to list the block devices. `fdisk` is to create partitions of the MBR type. This is legacy. `parted` is for modern partition making for either MBR or GPT. 

Linux File Systems. We have two different types: non-journaling (ext2 - legacy) and journaling (ext3, ext4, and XFS). We also have btrfs, FAT (file allocation table), exFAT (extended FAT), etc. 

Use `blkid` to see the file systems universally unique identifier. USe `mkfs` to create a new file system on a partition. 

Another reminder, use `df` and `du` to see the disk free and disk use stats. Use the `-h` option to make it human-readable. 

Use `fsck` to check the file system for any issues. This is for maintenance. You can also use `e2fsck` for specifically ext type file systems. 


## 11.25.2024

**Today's Topics**
* LPIC-1 - Exam 101: (Chapter 3 continued)

Processes have priority levels called nice levels. The highest priority is -20. The lowest is 19. Most processes have a nice level of 0 by default. You can use the `renice` command to change the nice level of a process. Each process uses CPU time so you don't want to overly tax your resources on unnecessary processes. 

A lot of this is review. This may be the third time going through all of this. No, Im not an expert on it but I understand the overall structure of what's happening. So I'm not taking a bunch of notes. I'm noticing there are a few different ways to get the same end result though so that's cool but also overwhelming 


## 11.24.2024

**Today's Topics**
* LPIC-1 - Exam 101: (Chapter 3 continued)

Use the `./` notation to tell Linux to run an executable from the current directory you're in. 

`dd` command copies and converts files. Often used to create files of arbitrary size and to back up disk drives. You're familiar enough with `tar`, `gzip`, and `gunzip` for zipping up folders and compressing them. Remember, `tar` doesn't compress the file. It just zips it. 

You can use the `find` command to help you search for files. Use the option `-name` to find a file based on their name. You'll have to input the name of the file obviously. You can also use the `empty` option to find empty files or directories. 

Lets review file globbing: `*` matches zero or more characters. `?` matches any single character. `[abc]` matches any one of the characters in the list, case sensitive. `[^abc]` matches any one character except those in the list, case sensitive. `[0-9]` matches a range of numbers. 

Remember, use `ps` and `top` to see information on your processes. Use the following commands for process management: `uptime`, `free` (view the used and available memory and swap space), `pgrep` (find process information based on process name), `kill` (based on PID), and `pkill` (based on process name). 



## 11.23.2024

**Today's Topics**
* LPIC-1 - Exam 101: (Chapter 3)

More useful CLI commands: `sort`, `uniq`, and `tr`. 

`sed` - stream editor command. Used for a variety of tasks commonly utilitzed to alter text in a file or search and replace words. Think of this as the Replace function in the Notepad+ app. 

`split` - used to split a file ip into individual pieces. By default, each piece of the file contains up to 1,000 lines, but this can be changed to a different value or file size. I'm not sure why we would need this. 

You can use the `mv` command to rename a file. Keep this in mind. 

Use the command `file` to see a file's type. 


## 11.22.2024

**Today's Topics**
* LPIC-1 - Exam 101: (Chapter 2 continued)

Long week so no notes although I did watch all the videos for Chapter 2. I'm familiar enough with yum, rpm, apt-get, and dpkg so if things get specific, I can google what I need. The notes that I will be filling in later are related to the boot loading process and the differences between MBR and GPT. I'm not familiar with boot loading at all whether thats Windows, Linux or even Cisco so I want to rewatch those videos. 

Also, containers made more sense when the instructor talked about it. Learning the basics of Linux is making it make more sense. 


## 11.21.2024

**Today's Topics**
* LPIC-1 - Exam 101: (Chapter 2)

`/opt` directory is for optional devices. A mount point is when you take a partition or disk and mount it to a directory. 

Logical Volume Manager (LVM) - allows the creation of 'groups' of disks or partitions that can be assembled into a single (or multiple) filesystems. Think of this like an underlay-overlay situation with hard drives/block devices. You can have multiple, physical devices (like an underlay) and you can group those together into a logical file system (overlay) and use that logical system however you see fit. Use the commands `pvs`, `vgs`, and `lvs` to list out the physical volumes, volume groups, and logical volumes, respectively. 







## 11.20.2024

**Today's Topics**
* LPIC-1 - Exam 101: (Chapter 1 continued)

Lets talk about the Linux boot process. The computer starts and the BIOS on the motherboard checks out the input and output for all hardware devices. If everything works, the boot process can begin. The boot program (GRUB) will look for the section of the harddrive that contains the data needed to boot an OS. This boot loader will then load the Kernel. The kernel will then load an initial RAM disk. Then, the kernel starts off the initialization system. This loads the services and eventually discards the initial RAM disk. 

You can see boot logs using `dmesg` (the traditional utility used for viewing the kernel ring buffer) and `journalctl -k` (systemd utility to view the kernal ring buffer within the systemd journal). 

Init is short for initialization. After the Linux kernel loads up and brings in the initial RAM disk, it seeks out an initialization system to hand over control of the computer. It's going to look at /sbin/init first. The kernel will start it once it locates it. Then the init program is in control. It will first look at the /etc/inittab file for configurations. It will look for a Runlevel. What's a runlevel? A runlevel is a predefined configuration that the computer will operate within. It's 7 runlevels from 0 to 6. 

Each line in the `inittab` file has a few fields: <identifier>:<runlevel>:<action>:<process>. I will definitely be rewatching all of these videos. 

`upstart` is like `init` but it offers asynchronous starting of services which can decrease boot up times. It can work on real-time events. 

A change on a Linux system is an event. An event triggers a job. Jobs can be in two categories: Tasks and Services. 

A Task will do what is requested of it and then return to a waiting state after it's finished. A Service will continue to run unless a daemon stops it or the system admin kills the process. 

Lets talk about `systemd`. Where did this come from? So `init` and `upstart` rely on Bash shell scripts to boot up your computer. The issue with this is the script files create additional processes and have to open Bash libraries in order to run all the scripts. This uses unnecessary resources and slows down the boot time. `systemd` replaced these Bash script files with compiled C code which runs faster. Requires less resources. `systemd` uses Unit Files to boot You can find the unit files in /etc/systemd/system. To see all the unit files on a system, use the command `systemctl list-unit-files`. 

Here are the components of the Unit File. 
- [Unit]
- Description=<describes the system>
- Documentation: <this is where you put the documentation for this unit file>
- Requires=<lists out the unit files that will be activated when this unit is activated>
- Conflicts=<indicates what units can NOT be running while this one is running>
- After=<says whatever is listed here must be started before the unit that this file is for will be started>

Use the command `runlevel` command to see what runlevel you're at. Use `telinit` to change your runlevel but you must be the root user. 

Why do we need runlevels? Basically runlevels are like, minimum levels of requirement for your device to operate it. If you're working on a server, you may only need to have one user and other programs that use the device. So you may only need a multi-user run level with or without networking. If you're doing specifically maintenance and don't need any type of network services or tools, you can use a lower runlevel. This can save time and resources for when your device is starting. You may not ever need to use a GUI so why even have your device start up those services? You may not need the network so why start those processes? Your runlevel determines what you need and don't need. 

A target is a unit that syncs up with other units when the computer boots or changes states. They are used to bring the system to a new state. Other units associate themselves with a target for an operating environment. 

multi-user.target - multi-user system, similar to what runlevel 3 provides. 
graphical.target - multi-user system with a desktop environment, similar to what runlevel 5 provides.
rescue.target - pulls in a basic system and file system mounts and provides a rescue shell.
basic.target - basic system, used during the boot process before another target takes over.
sysint.target - system initilization.

Useful command: `systemctl list-unit-files -t target` - show all unit files for available targets. 

There are multiple ways to reboot and shutdown your system. Simple ways are `reboot` and `poweroff`, respectively. You also have the `wall` command that broadcasts a message to all logged in users. `acpid` is Advanced Configuration and Power Interface and it registers system events. 






## 11.19.2024

**Today's Topics**
* LPIC-1 - Exam 101: (Chapter 1)

A regular file system is a method of laying out files and folders on a physical hard disk. A pseudo file system does not exist on a physical hard disk. It's also not persistent because it only exists in RAM. `/proc` and `/sys` directories are pseudo file systems. 

`/proc/` contains information about the processes running on a system. You can see them by PID. `/sys` contains information about the system's hardware and kernel modules. 

`uname` stands for Unix name. Use this to display information about currently running kernel. `lsmod` displays a listing of all currently loaded kernel modules. `modinfo` displays information about a specified kernel module. `modprobe` command used to dynamically load and unload kernel modules at runtime. 

A few commands that could be useful for listing specific devices: `lspci` (for PCI devices), `lsusb` (for USB devices), `lscpu` (for CPU processs info), and `lsblk` (for all block devices (think external harddrives)). 

## 11.18.2024

**Today's Topics**
* Introduction to Databases on Linux (Chapters 3 - 5)

Relational databases were created in the 1970s. SQL - structured query language. Used to manipulate databases. It's an ANSI/ISO standard. Common commands are Select, Update, Insert Into, Delete, Create, Drop, and Alter. 

PostgreSQL - highly extendible RDBMS, with support for many extensions and stored procedure languages. It supports connections using TCP/IP and local UNIX sockets. 

MariaDB - hihgly flexible RDBMS with support for multiple storage engines. It was forked from MySQL when it was purchased by Oracle. Interesting. 

CouchDB - an open-source, distributed (shared-nothing architecture) multi-model NoSQL document-oriented database. Whatever that means. 

MongoDB - a document database designed for ease of development and scaling. 

Apache Cassandra - an open source, distributed NoSQL database. 

Distributed DBs are just high availability infrastructure so think of it like that. + DBs are closer to the user for lower latency. 

That wraps up databases! I still don't necessarily know what's going on but I get the foundation of it. I'm going to leave DBs alone until I really need it. On to the LPIC-1 course. 


## 11.17.2024

**Today's Topics**
* Introduction to Databases on Linux (Chapters 1 - 2)

A databse is an organized collection of data. The first database was a physical database on paper in 1890. Also, JSON format was created in 2001. 

CSV - comma separated values. Never knew what this stood for. Basic Rules
1.) Data is stored in fields/columns separated by the comma character.
2.) Records/rows are terminated by newline character
3.) A specific character encoding, byte order, or line terminator format, is not required.
4.) All records should have the same number of fields, and be in the same order
5.) Data within fields is interpreted as a sequence of characters, not as a sequence of bytes. 

XML - eXtensible Markup Language. It's a markup language much like HTML. It was designed to store and transport data in a way that is both human and machine readable. 

I'll be the first to say this course is not so great and I don't like it. Not nearly enough information has been given regarding these databases and the formatting is very weird. There are 10 labs. I'm going to complete them. 

Well, I did just learn you can open Python on the CLI by just typing `Python`. You can also exit by pressing ctrl + D. This combo is similar to Ctrl + Z in the Cisco CLI. 

So we did queries on Berkeley DB, CSV, XML, and JSON files. The easiest and most readable formats were CSV and JSON for me. I was able to do my own made up queries on JSON actually. Definitely easier to follow. 



## 11.16.2024

**Today's Topics**
* Linux User Management Deep Dive (Chapter 5)

So it seems like you edit the `visudo` file to change sudo permissions for your system. You can assign users root-level access if you want. I believe that's what's happening. Will check with Chat GPT. visudo also runs a syntax check before saving the file. Or running the file. 
"Sudoers allows particular users to run various commands as the root user, without needing the root password."

`ALL=(ALL)      ALL`. Lets break this down. The first all indicates which hosts that a user can run commands on. This is the person making the commands. The second ALL is for the target user. The last ALL indicates the commands that can be run. So you can run all commands. I still don't understand the second ALL completely.  

Before you remove a user, make sure you find the files, directories, and processes before you do so. Use `ps U <user_name>` to see which processes are being completely by a user. Check the `man` pages for all the options. Then, you can do `kill <PID>` to terminate the process. Use `find / -user <user_name>` to find the files and directories associated with a user. 

With `chmod`, you can load up the users and groups. You can do `chmd og+rw <file_name>`. Look into the instructions. It will definitely make this entire process easier. 

Set UID (SUID), Set GID (SGID), and sticky bit. The SUID executes a file as the owner of the file and not the user running the command. So like, the root user can run the command but the system will see it as the owner of the file (user1) actually running the file. Sticky bit allows for a user to only edit files or directories that they created. 

A file mask is the maximum amount of settings a file or directory can have when created. You can see this when you use the `umask` command. The number of maximum permissions overall is 777. The default function when creating folders is 777 and for files are 666. `umask` returns 4 digits. The first digit is for special permissions. The next 3 are owner, group, and other. Whatever this digit is, you subtract it from 7 to get what the default permissions will be when you create a file or folder. 

I'll have to return to the quotas. That was a bit confusing. 


## 11.15.2024

**Today's Topics**
* Linux User Management Deep Dive (Chapter 4)

Lets look into the fields for /etc/shadow. username:<hashed password with salt>:last password change (in days):minium number of days required between password changes (set to 0 for password change at any time):the maximum number of days the password is valid:the number of days before a warning message about changing your password is sent:the number of days until an account will auto-disable:the number of days that an account has been disabled

All of these fields can be changed via `passwd`. Look at the options. 

(You can actually tell which hashing algorithm is used (like SHA-256) by looking at the first number of the hashed password. They're separated by the $ signs.)

Use `chage -l <user_name>` to see all of the password attributes for a user. You can also see the options using `chage -h`. This is all good for password management. It's like AD but just not as pretty. 

If you lock a user's password, they can no longer use that password but they can still access a server in different ways where the password isn't required. If you disable a user's account, they can't use that account. Just be familiar with differences for security reasons. 


## 11.14.2024

**Today's Topics**
* Linux User Management Deep Dive (Chapter 3 continued)

We remove a user using the `userdel` command. You should remove the files and processes related to the user before you do this though. You can use the `find` command to search for anything else the user has a hand in. 

Use the `groupadd` option. You can use the additional options to get very specific about how to add groups. You can automatically assign a group a Group ID. This is good for automation and simplification with typos just in case user group naming conventions get out of hand. You can also add a user and give them a primary and secondary group all in one command. Get familiar with these commands. 

You can modify groups using `groupmod`. You can change the GID and the name of the group using this command. Always check the `man` output for these commands. Also, use `groupdel` to delete groups. 

`gpasswd` is used to administer /etcgroup and /etc/gshadow. Use it to set group passwords and the users who are able to use this password. 

`pwck` verifies the integrity of the users and authentication information. It also checks the etc/shadow file. Basically it makes sure your password isn't corrupted. 

`grpck` does the same thing just for groups. Be careful. These commands can delete users if it finds corrupted files. 

Now we have `pwconv` and `grpconv` commands. They create shadow from the passwd commands. Apparently we won't be using this much so I'll save my bandwidth until I need to come back to this. 

You can use the `id` command followed by the username to see the user's ID, primary, and secondary group. 

I'm piecing together a connection for the chmod and chown. When you do `ll` and see the file permissions for user, group and everybody else, I'm assuming you need to change this first before you give a group permission over a file. If the user or group doesn't own the file, there's no point in giving them permission over the file because I would assume it shouldn't work. So always check the permissions on the file first, transfer ownership to the correct user, and then give that user or group the correct permissions over the file. Use `chown` for transferring ownership and use `chmod` for changing permissions. Remember, the `o` flag is for user and tthe `g` flag is for group. Then you can simply put r, w, or x to change the permissions. You can also use the numbers. We'll practice both ways. 





## 11.13.2024

**Today's Topics**
* Linux User Management Deep Dive (Chapter 3)

/etc/login.dev file is where you can set the default parameters for the UID_MIN, MAX, Group MIN, MAX, and other fields for your users and groups. 

When you create a user, Linux also creates a group for that user with the same name as the user. Just be aware of this. 


## 11.12.2024

**Today's Topics**
* Linux User Management Deep Dive (Chapter 1 - 2)

UID (User Idenifier) Ranges
- UID 0 - superuser or root user.
- UID 1-200 - system users. ID range for system users for system processes. These are statically assigned by the system
- UID 201-999 - system users. ID range given to system users for system processes but dont know files on the system. These are dynamically assigned when the packages that require them are installed. These user IDs have restricted access only to the resources they need for operating
- UID 1000+ - regular users. ID range assigned for all regular users.

Use the `id` and `groups` command to see the user and group that you belong to. You can be in a primary group and a secondary group. You can find all of this user and group information in the /etc/ directory. 

A shell is a program that acts as an interface between the user and the OS kernel. A shell is created for each user once their profile has been created. It's usually /bin/bash which is for Bash. If you set a user shell to /sbin/nologin: and they try to log in, they'll receive the message "This account is currently not available." You have to create the file /etc/nologin.txt first though. If you use /bin/false:, then this will also automatically log a user out. 

Home Directory - the directory in which a user enters upon login. Also, keep in mind. If you copy files over to another user's file system or directory, you would also need to change the file permissions over to the new user. 

Just a reminder, if you see the /etc/passwd output, the format is. user:password:userid:groupid:GEKOS:HomeDirectory:LoginShell. You can see the actual password by going to the /etc/shadow but only the root user can see this. You can also see password management information here. It's about 8 fields. The password for groups is set in the /etc/gshadow file. The other fields in the group output are the group administrator and the members in the group (separated by commas). 


## 11.11.2024

**Today's Topics**
* LPI Linux Essentials (labs)

You can find which groups a user belongs to by navigating to the `/etc/group` file. Cat the file and grep out the user you're looking for. The information will be there. You can also use `groups <user_name>` to also find this information. 

To find a user's home directory, you can use the following two commands: `getent passwd <user_name>` and `cat /etc/passwd | grep <user_name>`.

Lets add some users and groups now. To add a user, just use `useradd <user_name>`. To add a group, just use `groupadd <group_name>`. To add a user to that group, use `usermod --append --groups <group_name> <user_name>`. Easy. 

Use the following command to change the OWNERSHIP (not file permissions) of a file or directory: `chown -R (new_user_owner>:<new_group_owner> <file or directory name>`

Use the following command to change the file/directory PERMISSIONS: `chmod <u (user) or g (group) + <w,r,x,> <file or directory name>`. For example, `chmod g+rx /home/susan`



## 11.10.2024

**Today's Topics**
* LPI Linux Essentials (labs)

`/usr ` stands for Unix System Resources. And remember, `/bin`/ and `/sbin/` stands for binary and system binaries. 

`df` stands for disk free. Use this to see how much storage you have available. You can also find the number of CPUs and their speed in the /proc/cpuinfo directory. You can see how much RAM is installed in the /proc/meminfo directory. You can see the swap memory being used by using the `free -m` command. Lastly, you can see the BIOS version using the `dmidecode` command. 

Use `ps aux` to see which processes are being ran. Use the `uptime` command to see the current system load. 

You can use the command `cat /etc/resolv.conf | grep nameserver` to find your DNS server. Remember, you can find your IP, MAC and DG using the `ip addr show` and `ip route show` commands. 



## 11.09.2024

**Today's Topics**
* LPI Linux Essentials (5.1 - 5.4)

`sudo` stands for super-user do. I'm getting really tired of these Linux command names. It's like they didn't even expect for people to ever truly use it in the future. 

There are 7 user attribute fields: username, password, user ID, group ID, GECOS (long name), Home Directory, and Login Shell. The password is saved as a hash so you'll just see an 'x' for that. These are for human or standard users. There are different types of users other than root and standard. 

![Image](UserAttributeFields.png)

System users are generally deployed when applications are installed, their home directories are set to application folders, and they normally do not have a login shell. The purpose of having discrete users is to separate functional privileges from other applications and services. 


## 11.08.2024

**Today's Topics**
* LPI Linux Essentials (4.2 - 4.4)

Computer hardware reviw. Central Processing Unit (CPU) - processes computer functios and performs calculations. Random Access Memory (RAM) - high-performance, volatile storage. Secondard storage (Hard drive) - persistent storage for data not currently in use. Network Interface Card (NIC) - permits connections to network. Then input and output devices like mouses, keyboards, and monitors. 

Hardware drivers reside in the running kernel (or are loaded as a module) and enable the operating system to use the hardware. 

`/boot` contains the boot loader configuration files and parameters. `/etc` contains many useful directors including `/fstab` for partition mount points, `/passwd` for local user attributes, `/group` for groups, and `/hosts` for IP addresses and hostnames. 

All processes have a process ID or a PID. You can find process data by going to `/proc/<PID>/`. You can view the running processes by using the commands `ps aux` and `ps -eF`. You can also use the command `top`. 

System messages are messages from out kernel. They're sent from the kernel ring buffer. You use `dmesg` to see this information. The kernel ring buffer holds messages related to the operation of the kernel - a ring buffer is simply a buffer of a constant size. 

Logging - common locations for system and application log data. You can get to the log directory via /var/log. The common logs are messages (general system logs and messages), syslog (for Debian-based systems), auth.log (authentication logs), secure (for Red Hat-based systems), boot.log (system boot logs), cron.log (Cron job logs), kern.log (Kernel logs), and faillog (authentication failure logs). 

Cron is kind of a like a task scheduler. Seems pretty powerful. 

Now for the good stuff. Networking. You can use `ip addr show` to see your device's IP address. You can also use the `dig` command to get DNS information for a resource. 

You can use `ip route show` to see the route table. I think it just shows you what your default gateway is (in the first line) and it shows the subnet that you're on. It also says the device that's the next hop. 

Instead of `ifconfig`, start to get familiar with `nmcli`. You can also use `netstat` and `ss` to see what devices are on the network. 


## 11.07.2024

**Today's Topics**
* LPI Linux Essentials (2.4 - 4.1)

Lets managed some folders! Use the `mkdir`, `cp`, `mv`, and `rm` commands to make, copy, move, and remove folders. 

Files are case sensitive. That's when you're manipulating them in any way, even searching for them. Also, you can use the `mv` command to rename files. Ask Chat GPT about this. 

Globbing - a useful way to search for information. Think of how a wildcard asterisk can represent "anything". This is what gobbling is. We have a few ways to go about it. Lets start with the question mark `?`. The question mark represents any ONE CHARACTER. So if you have `file?`, then Linux will search for all things that start with `file` but end with any one character. If you have `???`, then Linux will search any file that is 3 characters long. If you have `????4`, then Linux will search for a 5 length-file that starts with anything for the first 4 characters but ends in the number 4. 

The asterisk represents any character that is ANY length, not just 1 character. So if you search *4, you will get any file that ends in 4 such as file4, LinuxIsFun4, Windows10.4, etc. Anything length of characters. But wait, there's more. You can also use brackets to further constrain your search. Check the chart below and make sure your syntax is correct. 

![Image](LinuxBracketSearch.PNG)

Archiving is the process of combining multiple files and/or directories into a single file. We'll be using `tar` (tape archive) for this. I'll need to practice these options. 

Lets talk compression. Compression is the process of reducing the amount of storage that files or archives consume. We have different compression options. We have gzip (default compression for tar), bzip2 (an alternative. usually slower than gzip due to higher compression), and zip (the same compression as Windows. popular). 

I'll definitely have to practice all of these tar flags. I don't understand them fully right now. 

Piping - the process of taking the output from one command as the input to another command. Quick detour, you can use `grep <word you want to search> <file you want to search in>`. Back to piping, the left side of the pipe is the output from the original command and it will use this output as the input to the command on the right side of the pipe. 

I/O redirection may be used to feed input to  comand from a file, or to send the output of a command to a file. This is the same thing as `echo "whatever_output" > file.txt`. I don't understand when we would use "read input from a file". Seems very arbitrary. 

Regular Expressions (regex) - used to match patterns in text, similar to globbing. Seems like a powerful too but I don't see why we would need it just yet. Seems like an extension of `grep`. Update: we did a few labs using regex and I can definitely see how powerful it is. I still need to practice this. Its like solving a puzzle. 

![Image](MoreVimShortCuts.PNG)

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

You can use `cd ~` to change to your user's home directory. The tilde is for the home directory. 

When you do `>` to redirect the output of a command into a file, you will overwrite the entire file with the new output. If you want to add the output to the end of a file (this is called appending), you should use `>>` instead so you don't overwrite the file.

Colons `:` are used as delimiters in the file path. So basically it just breaks them up so you can include multiple file paths to a variable. So look at them like a comma pretty much. 

Yeah that backslash lab was kicking my a** lmao. It feel like choosing C 8 times in a row on a scantron sheet. Like this can't possibly be the right answer. I'll have to get more familiar with that aspect. 

You can just normally type in a manual page (man page) to search for whatever text you're looking for. This makes searching man pages easier. 

Info pages are more detailed man pages. Use `info <command>` to get to the info page. 

When we install a hard drive, we'll create a file system on that drive. It will follow the Filesystem Hierarchy Standard (FHS) for Linux. If you do a regular `cd`, it will take you to the home directory. `cd /` is the top/root level of the file system. 

![Image](RootDirectoryFolders.PNG)

The terminal has tab completion just like the Cisco CLI. Also, to go back to your previous directory (not up a directory but back to the one you just came from), use `cd -`. You can also use `cd ../..` to go up two levels.

If you put a period in front of a file or directory, it will be hidden. For example, file5 and .file5. To see them when you do a `ls`, use `ls -a` so they appear. 

A home directory is typically created for every ordinary user on a Linux system under /home. This is where you automatically land when you log into a user's profile. 

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






