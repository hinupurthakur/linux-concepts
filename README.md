# linux-concepts

<h3>1. Inode </h3>
An Inode is a data structure containing metadata about the files.

Uniquely existing number for all the files in linux/unix filesystem.

![Screenshot from 2022-02-04 11-33-33](https://user-images.githubusercontent.com/39610703/152480487-a6b2099c-81e0-488e-a8be-41402cc3f2ad.png)

The first number on the left indicates the inode number. `-i` flag is used to get the inode number
Note: The Inode doesn't contain file content, instead it has a pointer to that data. 

Ref: 
  * https://www.redhat.com/sysadmin/inodes-linux-filesystem
  * https://www.javatpoint.com/linux-inodes


<h3>2. Zombie Process </h3> 

A process which has finished the execution but still has entry in the process table to report to its parent process is known as a zombie process.

<h4> How to kill Zombie Process </h4>

You can’t kill a zombie process because it’s already dead. It won’t respond to any signals because it’s been removed from memory—there’s nowhere to send a SIGKILL signal. You can try sending the SIGCHLD signal to the parent process, but if it didn’t work when the child process terminated, it’s unlikely to work now, either.


<b>The only reliable solution is to kill the parent process.</b> When it’s terminated, its child processes are inherited by the init process, which is the first process to run in a Linux system (its process ID is 1).

![Screenshot from 2022-02-04 12-09-06](https://user-images.githubusercontent.com/39610703/152484197-513559d5-fd6a-414d-b54d-a7e1c6e7831c.png)
![Screenshot from 2022-02-04 12-11-37](https://user-images.githubusercontent.com/39610703/152484203-83a65506-8240-4c3b-9354-277c3f5222ac.png)
![Screenshot from 2022-02-04 12-10-24](https://user-images.githubusercontent.com/39610703/152484270-1770daa1-10ab-4d93-b201-f4ef97161298.png)

NOTE: Zombies Aren’t Scary …
… unless they’re in a massive horde. A few aren’t anything to worry about and a simple reboot will wipe them out.

<h3> 3. Samba Server </h3>

Samba is an extremely useful networking tool for anyone who has both Windows and Unix systems on his network. Running on a Unix system, it allows Windows to share files and printers on the Unix host, and it also allows Unix users to access resources shared by Windows systems.

Samba is a suite of Unix applications that speak the Server Message Block (SMB) protocol. Microsoft Windows operating systems and the OS/2 operating system use SMB to perform client-server networking for file and printer sharing and associated operations. By supporting this protocol, Samba enables computers running Unix to get in on the action, communicating with the same networking protocol as Microsoft Windows and appearing as another Windows system on the network from the perspective of a Windows client.

<h3> 4. TLB </h3> 

TLB (Translation Lookaside Buffer)
![GFG Image](https://media.geeksforgeeks.org/wp-content/uploads/20190225192626/tlb1.jpg)

<h3> 5. Copy to clipboard </h3>
`pbcopy`
Use `pbcopy` with pipe for copying the output of the previous command. e.g.

```cat abc.txt | pbcopy```
<h3> 6. `w` Command </h3>
`w` command in Linux shows logged-in users and their activities.
<img width="595" alt="image" src="https://github.com/hinupurthakur/linux-concepts/assets/39610703/33ff1bdd-cbac-4ae0-b607-5a62301d6b26">


Ref:
 * https://www.geeksforgeeks.org/zombie-and-orphan-processes-in-c/
 * https://www.howtogeek.com/701971/how-to-kill-zombie-processes-on-linux/
 * https://www.samba.org/samba/docs/using_samba/ch01.html

