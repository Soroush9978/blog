
# This is my notes about Linux
# Linux
[containerd](https://containerd.io/)a

Podman is a daemonless, open source, Linux native tool designed to make it easy to find, run, build, share and deploy applications using Open Containers Initiative (OCI) Containers and Container Images.

Questions? 	
	- What is demonless and what difference does it make?
	- Learn OCI standards? 

Podman relies on an OCI compliant Container Runtime (runc, crun, runv, etc) to interface with the operating system and create the running containers.	
[Podman Network](https://github.com/containers/podman/blob/main/docs/tutorials/basic_networking.md)
[Podman Docs](https://docs.podman.io/en/latest/)

---
There is a List of TUI tools
- [list](https://github.com/rothgar/awesome-tuis)
- [aWlist](https://github.com/agarrharr/awesome-cli-apps)
- [bigAWlist](https://github.com/toolleeo/cli-apps)_
- [List of Terminal Tools](https://terminaltrove.com/list/)
- [x-cmd very interesting](https://www.x-cmd.com/pkg/)
- [unix-modern command line tool](https://github.com/johnalanwoods/maintained-modern-unix)
- [Coding Interview University](https://github.com/jwasham/coding-interview-university)
- [Awesome Shell](https://github.com/moregeek/awesome-shell)
- [DevOps-exe](https://github.com/bregman-arie/devops-exercises?tab=readme-ov-file#network)
- [test-your-sysadmin-skills](https://github.com/trimstray/test-your-sysadmin-skills)
- [DevOps-Guide](https://github.com/Tikam02/DevOps-Guide)
- [devops-resources](https://github.com/bregman-arie/devops-resources)
- [awesome-scalability](://github.com/binhnguyennus/awesome-scalability)
- [Cloud-DevOps-Learning-Resources](://github.com/ahmedtariq01/Cloud-DevOps-Learning-Resources)
- [100-GO](https://100go.co/)                                                                                                                                                        
-[The GNU Coreutils Package](https://blog.robertelder.org/gnu-coreutils-package-guide/)
-[Enterprise Integration Patterns](https://www.enterpriseintegrationpatterns.com/index.htmli)

-[https://the-algorithms.com/language/go](hittps://the-algorithms.com/language/go)

---
---
## Project :
[Interview Questions](https://github.com/chassing/linux-sysadmin-interview-questions)

Answer Theses Questions Daily with Writing down Answers :

	1.What function does DNS play on a network?
- this is the **why** ~~strike~~

>sadia

ParadeDB is a modern Elasticsearch alternative built on Postgres.

[HTTP/1.0 From Scratch](https://kmcd.dev/posts/http1.0-from-scratch/)

locate -- updatedb commnad 
find 
fzf 
batcat is bat in debian based systems

cntrl + D stopp the current standard input 
cntrl + C terminate 

GDK_BACKEND=x11 surf https://example.com

use surf browser


---
There is a software eng roadmap on youtube bytecode

Our recommended materials to crack your next tech interview.

Coding
- Leetcode
- Cracking the coding interview book
- Neetcode

System Design Interview 
- System Design Interview book 1, 2 by Alex Xu
- Grokking the system design by Design Guru
- Design Data-intensive Application book

Behavioral interview
- Tech Interview Handbook (Github repo)
- A Life Engineered (YT)
- STAR method (general method)

OOD Interview
- Interviewready
- OOD by educative
- Head First Design Patterns Book

Mock interviews
- Interviewingio
- Pramp
- Meetapro

Apply for Jobs
- Linkedin
- Monster
- Indeed
---
========


[Tmux collaboration](https://tmate.io/)
[This is serverless website](https://serverlessland.com/)



Next we might want to see how the system booted and what kernel parameters were passed when the system was started.

cat /proc/cmdline



vmstat 1 5
mpstat 2 5
ps -ef | awk '{print $1}' | sort | uniq -c
pidstat 1 5
iostat -xz 1 5
Solution
Solution
Let's look at the network usage and load of the system.

sar -n DEV 1 5

What are you seeing here? What devices are showing up? Do any devices seem to be under high load? Which one has the most traffic?

Next we check tcp packets and errors.

sar -n TCP,ETCP 1 5

Do we appear to be seeing any large numbers of errors? Why might retransmits be a big problem?


Next we will check how many packages are on the system.

dpkg -l | wc -l

Solution
Check disk information and count partitions

fdisk -l | grep -i vd

Why did we use VD?

Let's use another command to see that information another way.

lsblk

and

blkid

mount | grep vda


for type in $(ls /dev/disk); do echo "type is $type"; ls -l /dev/disk/$type; done



Let's make a giant file filled with 0's and then check available space.

dd if=/dev/zero of=/root/bigfile bs=1024k count=3000

ip addr | grep enp | grep mtu | awk '{print $2}' | sed 's/://' > /root/interface
write an ansible playbook to gather information 
What is the ip of your interface?

ip addr | grep enp | grep inet | awk '{print $2}' 
ip route | grep -i default | awk '{print $3}' 

Check network throughput to your system for 20 seconds

ifstat 2 10

Solution
Solution

Check network throughput to your system for 20 seconds

ifstat 2 10

Note: There is very little traffic (in size) into or out of your system.

Do a tcpdump to inspect the actual traffic into your system. Capture 1000 packets against your enp1s0 interface.

tcpdump -ni enp1s0 -s0 -c 1000

Let's generate a .pcap file that can be used by wireshark to inspect traffic. (We don't have wireshark on this system)

for i in $(seq 1 5); do ping -c 10 www.google.com & done; tcpdump -ni enp1s0 -s0 -c 200 -w $(hostname).pcap

Verify the size and creation of the file.

ls -lh /root/ubuntu.pcap


Check your connection to node01.

ssh node01

Type in exit to return to the original system

exit

Check system uptime and one layer of debug1.

ssh -v node01 'uptime'

What additional information was shown with the -v option? (debug1)

ssh -vv node01 'uptime'

What additional information was shown with the -vv option? (debug2)

ssh -vvv node01 'uptime' 

What additional information was shown with the -vvv option (debug3)

So we looked at a ssh connection over to node01. You should note that the keys are being used and that is why no password was asked to connect. We'll explore that more shortly.




---
What are the difference between 
printenv
env
declare -p 
set 

tell the  difference?

Can you capture whether or not processes are running? Test for httpd and sshd.

ps -ef | grep -i [h]ttpd
httpdCheck=$(echo $?)

ps -ef | grep -i [s]shd
sshdCheck=$(echo $?)

time apt upgrade -y

The chroot lab of Scott was good it was a way How to cerate JumpSever 
virt-what


dmidecode | grep -iE "virt|prod"
systemd-analyze time
systemd-analyze blame
systemd-analyze critical-chain ssh.service


---
IT-gruundshutz BSI:
[IT-Grundschutz](https://www.bsi.bund.de/DE/Themen/Unternehmen-und-Organisationen/Standards-und-Zertifizierung/IT-Grundschutz/it-grundschutz_node.html)


[BSI](https://www.bsi.bund.de/DE/Home/home_node.html)



---
[calmAV anti virus](https://docs.clamav.net/)


--- 
Grafana Installation Guide:
Refer to the Grafana Docs for latest installation instructions.

Install the required packages and Grafana GPG key.

apt install -y apt-transport-https

apt install -y software-properties-common wget

sudo wget -q -O /usr/share/keyrings/grafana.key https://apt.grafana.com/gpg.key

Add the Grafana repository.

echo "deb [signed-by=/usr/share/keyrings/grafana.key] https://apt.grafana.com stable main" | sudo tee -a /etc/apt/sources.list.d/grafana.list

Finally, we're ready to install Grafana:

apt update
# Install the latest Enterprise release:
apt install -y grafana-enterprise

Now that you've installed Grafana, let's make sure it's started.

sudo systemctl daemon-reload
sudo systemctl start grafana-server
sudo systemctl status grafana-server --no-pager

Verify that the server is serving on port 3000 (the default port)

systemctl status grafana-server --no-pager
ss -ntulp | grep grafana
ss -ntulp | grep 3000

We can also check that the external Web UI is available and change the default password.

https://5cc6e7db-6fd0-4330-8a9b-a690d3ead415-10-244-6-90-3000.spch.r.killercoda.com

Change the password. Default User: admin and Password: admin

Feel free to look around in the Web UI and then continue on to the next part of the lab.

[Hashicorp certc](https://developer.hashicorp.com/certifications)



We look at important Vim settings if you like to work with YAML during the K8s exams.
Settings

First create or open (if already exists) file .vimrc :

vim ~/.vimrc

Now enter (in insert-mode activated with i) the following lines:

set expandtab
set tabstop=2
set shiftwidth=2

Save and close the file by pressing Esc followed by :x and Enter.
Explanation

Whenever you open Vim now as the current user, these settings will be used.

If you ssh onto a different server, these settings will not be transferred.

Settings explained:

expandtab: use spaces for tab
tabstop: amount of spaces used for tab
shiftwidth: amount of spaces used during indentation
good site which has DevOps exe:
[Exp builder](https://landadevopsjob.com/experience-builder/)

[IaC](https://opentofu.org/)
[Learn kuber](https://learnk8s.io/)

---
What are the main pilars of incident response:
-Detection 
-Escalation 
-Communication
-Diagnosis
-Repair 
also there is somrhing like incident retro:
-analysis
-remidiation
-prevention

The standard regaarding these things are incident command system
national inident management system

Common terminology
Accountability 
unity of command 
explicit tranfer of responsibility

[Incident Command for IT—What We've Learned from the Fire Department](https://www.usenix.org/conference/srecon18americas/presentation/chapman)


create severity matrix and the resource allocated to it 
So the detection starts with monitoring 
also the scalation should be communicated through means of Jira ...
 

Set specefic metrics to communicate
Observe --> Orient --> decide --> act 



[QEMU](https://www.qemu.org/docs/master/about/index.html)

[What Every Programmer Should Know About Memory](https://people.freebsd.org/~lstewart/articles/cpumemory.pdfhttps://people.freebsd.org/~lstewart/articles/cpumemory.pdf)


[A terminal for the modern age█](https://tabby.sh/)

---
The difference between apt and apt-get 
[apt](https://aws.amazon.com/compare/the-difference-between-apt-and-apt-get/#:~:text=By%20default%2C%20the%20apt%20upgrade,for%20freeing%20up%20system%20memory)

----

How to concatenate and Join Pdf by pdftk 

pdftk 1.pdf 2.pd cat output 12.pdf


---
What does apt-change log does?
can you install different pkg manager on one distro?

1. The apt change log is a tool used in Debian-based Linux distributions (like Ubuntu) to view the changelog for software packages managed by the Advanced Package Tool (APT). A changelog is a detailed log or record of all notable changes made to a software package. These changes can include bug fixes, new features, security updates, or other modifications.




----
Check how to figure things out smoothly with tmux and automated script and the role of chils process and these sort of things,
the problems occurs when working with tmux and different session.
 



---

### Some Debian Hardening Material

[Official Docs](https://www.debian.org/doc/manuals/securing-debian-manual/securing-debian-manual.en.pdf)

Before you install any operating system on your computer, set up a BIOS password. After installation
(once you have enabled bootup from the hard disk) you should go back to the BIOS and change the boot
sequence to disable booting from floppy, CD-ROM and other devices that shouldn't boot. Otherwise a
cracker only needs physical access and a boot disk to access your entire system.

This is related to the recovery of root password, in this case how we can Install a new OS or boot

An intelligent partition scheme depends on how the machine is used. A good rule of thumb is to be fairly
liberal with your partitions and to pay attention to the following factors:
• Any directory tree which a user has write permissions to, such as e.g. /home, /tmp and /var/tmp/,
should be on a separate partition. This reduces the risk of a user DoS by filling up your "/" mount
point and rendering the system unusable (Note: this is not strictly true, since there is always some space
reserved for root which a normal user cannot fill), and it also prevents hardlink attacks. 1
• Any partition which can fluctuate, e.g. /var (especially /var/log) should also be on a separate
partition. On a Debian system, you should create /var a little bit bigger than on other systems, because
downloaded packages (the apt cache) are stored in /var/cache/apt/archives.
• Any partition where you want to install non-distribution software should be on a separate partition.
According to the File Hierarchy Standard, this is /opt or /usr/local. If these are separate partitions,
they will not be erased if you (have to) reinstall Debian itself.
• From a security point of view, it makes sense to try to move static data to its own partition, and then
mount that partition read-only. Better yet, put the data on read-only media. See below for more details.


he apt cache) are stored in /var/cache/apt/archives.

The concept of journaling file system
---

Make a list of services currently running on your system. Try:
$ ps aux
$ netstat -pn -l -A inet
$ /usr/sbin/lsof -i | grep LISTEN
Some other tools that can be used for forensic analysis provided in the Debian distribution are: strace and
ltrace
strace and ltrace
how they work and what they do to the system. Some other common tools include ldd (in libc6), strings
and objdump (both in binutils)


There is an ebpf tool in windows [Windows ebpf](https://github.com/microsoft/ebpf-for-windows)
[RHCA](https://github.com/Abdulhamid97Mousa/RHCSA-EX200)


Set user with exp data 
	sudo usermod -e 2030-03-01 jane
Set system account 
sudo usermod -e "" jane

sudo chage --lastday 0 jane
Mark the password for jane as expired to force her to immediately change it the next time she logs in.
sudo usermod -a -G developers jane
password warning sudo chage -W 2 jane
man limits.conf

	sudo useradd --system apachedev
Read more about tmpfs

nproc manage resource
for user

ulimit -a > /home/bob/limits
trinity    ALL=(ALL)   NOPASSWD: ALL

apropos : search for  commnad
cfdisk,
make a swap file accsess to root only 
fdisk 
mkfs
partition + file system + mount
mounting is pluging or make it perfanenet

sudo mount source destiination
why use uuid 
blkid and iit use why we use it 
find mnt
nfs-common
networrk block ddev
looking for modules.conf 	modoules-load somewhere to load the kerel module after every boot
modeprob

getfacl
getfacl - get file access control lists

chattr change the file attribute

/etc/ssh_config --> clieent config.
/etc/sshd_config --> deamon config.
the kdbinteractive	field in ssh 
The conflict between cloudinit and sshd_config 


---
timesyncd.conf
timedatectl 

What are the difference between sudo and wheel group ?


in pod yaml 
api
kind
meta : dict : lables : also dict
spec : containers
are basic field	
in kuberr ip addresses are assigned to the pod 
10.244.0.0 kuber internal 
multinode cluster networking the addresses are the same ! kuber needs us to set up netwworking 
for this cillium can be used 
kuber serviice port forwarding node port service
obvoiusly there is the concept of port forwarding 
kubectl get services
kubectl describe service 	
kubeectl get pods -o wide
kubectl create -f x.yml
---

Loadbalancing 
Networking 
PortForwarding 

---
---

---
ssh tunnel 

ssh -L -R : p ... :p 

ssh -D local port destenation host 
and the set the proxy to the local host on that port 
ssh tunneling is a good things to learn 


---
cat /etc/services

---
Read more about ssh tunneling, 
Read more about TLS, SSL 

wq

---

### how to see the details of package with apt ?
	apt show command
	apt search --names-only search_term
	dpkg -s package-name
	apt-cache stats
	apt show -a




---

[OpenPBS](https://www.openpbs.org/) :OpenPBS software optimizes job scheduling and workload management in high-performance computing (HPC) environments – clusters, clouds, and supercomputers – improving system efficiency and people’s productivity. Built by HPC people for HPC people, OpenPBS is fast, scalable, secure, and resilient, and supports all modern infrastructure, middleware, and applications. 









---

watch tower, is to update docker container
Macro text editoer 

easya ls alternatice

[dis systems reading list](https://dancres.github.io/Pages/)

some time check openvmm



----
git work flow: 
The basic workflow is always the same when I’m working with others: open a branch off of the main branch, start working, commit early & often, push early & often, open a pull request as a draft as soon as possible, finish work, make sure the commits in the branch somewhat make sense, ask for a review, merge.

When I’m working alone, I commit on the main branch 99% of the time and push after each commit.

Sometimes, when working on a branch, I notice that I need to make a new commit in a separate branch so that I can turn it into a separate pull request. There are multiple different strategies that I use here.
also i found this article useful:
[Git stategies](https://registerspill.thorstenball.com/p/how-i-use-git)



---
Website of [John Ousterhout](https://web.stanford.edu/~ouster/cgi-bin/home.php)
The courses of operating systems and philosopy of system design
also  the author of the [this](https://cacm.acm.org/research/always-measure-one-level-deeper/)



---
Learn about the backup strategy like incremental backup and ...
also look at different file systems and ZFS featurtes ...


How to create 1000 file with size of 5MB


# This is my notes about Linux

[containerd](https://containerd.io/)a

Podman is a daemonless, open source, Linux native tool designed to make it easy to find, run, build, share and deploy applications using Open Containers Initiative (OCI) Containers and Container Images.

Questions? 	
	- What is demonless and what difference does it make?
	- Learn OCI standards? 

Podman relies on an OCI compliant Container Runtime (runc, crun, runv, etc) to interface with the operating system and create the running containers.	
[Podman Network](https://github.com/containers/podman/blob/main/docs/tutorials/basic_networking.md)
[Podman Docs](https://docs.podman.io/en/latest/)

---
There is a List of TUI tools
- [list](https://github.com/rothgar/awesome-tuis)
- [aWlist](https://github.com/agarrharr/awesome-cli-apps)
- [bigAWlist](https://github.com/toolleeo/cli-apps)_
- [List of Terminal Tools](https://terminaltrove.com/list/)
- [x-cmd very interesting](https://www.x-cmd.com/pkg/)
- [unix-modern command line tool](https://github.com/johnalanwoods/maintained-modern-unix)
- [Coding Interview University](https://github.com/jwasham/coding-interview-university)
- [Awesome Shell](https://github.com/moregeek/awesome-shell)
- [DevOps-exe](https://github.com/bregman-arie/devops-exercises?tab=readme-ov-file#network)
- [test-your-sysadmin-skills](https://github.com/trimstray/test-your-sysadmin-skills)
- [DevOps-Guide](https://github.com/Tikam02/DevOps-Guide)
- [devops-resources](https://github.com/bregman-arie/devops-resources)
- [awesome-scalability](://github.com/binhnguyennus/awesome-scalability)
- [Cloud-DevOps-Learning-Resources](://github.com/ahmedtariq01/Cloud-DevOps-Learning-Resources)
- [100-GO](https://100go.co/)                                                                                                                                                        

---
---
## Project :
[Interview Questions](https://github.com/chassing/linux-sysadmin-interview-questions)

Answer Theses Questions Daily with Writing down Answers :

	1.What function does DNS play on a network?
- this is the **why** ~~strike~~


---

### backup strategy
The simple method has two backup levels: full and incremental backups. This can be generalized to any number of levels. A full backup would be level 0, and the different levels of incremental backups levels 1, 2, 3, etc. At each incremental backup level you back up everything that has changed since the previous backup at the same or a previous level.

The purpose for doing this is that it allows a longer backup history cheaply. In the example in the previous section, the backup history went back to the previous full backup. This could be extended by having more tapes, but only a week per new tape, which might be too expensive. A longer backup history is useful, since deleted or corrupted files are often not noticed for a long time. Even a version of a file that is not very up to date is better than no file at all.

With multiple levels the backup history can be extended more cheaply. For example, if we buy ten tapes, we could use tapes 1 and 2 for monthly backups (first Friday each month), tapes 3 to 6 for weekly backups (other Fridays; note that there can be five Fridays in one month, so we need four more tapes), and tapes 7 to 10 for daily backups (Monday to Thursday). With only four more tapes, we've been able to extend the backup history from two weeks (after all daily tapes have been used) to two months. It is true that we can't restore every version of each file during those two months, but what we can restore is often good enough.


---
Learn what is the systemcalls ? 
The services provided by the kernel to application programs, and the way in which they are invoked

Question: What is Journaling in FS?
The services provided by the kernel to application programs, and the way in which they are invokeThe Linux kernel consists of several important parts: process management, memory management, hardware device drivers, filesystem drivers, network management, and various other bits and pieces.   
Know that some commands are not executables, but Bash builtins, and that you can get help on them with help and help -d. You can find out whether a command is an executable, shell builtin or an alias by using type command.


    - pgrep
    - pkill
    - pstree -p 




---
good resource to check about shell: 
[good bash guide](https://github.com/jlevy/the-art-of-command-line/tree/master?tab=readme-ov-file)

which command
whatis command
whereis command

---

Make your bash scripts more robust by reliably performing cleanup.

function finish {
  # your cleanup here. e.g. kill any forked processes
  jobs -p | xargs kill
}
trap finish EXIT

---


---


## Useful git commands: 
Git Commands
51.​ git init – Initialize a git repository​
52.​ git clone repo_url – Clone a repository​
53.​ git status – Show changes​
54.​ git add . – Stage all changes​
55.​ git commit -m "msg" – Commit changes​
56.​ git push origin branch – Push changes​
57.​ git pull origin branch – Pull latest changes​
58.​ git checkout branch – Switch branch​
59.​ git branch -a – List all branches​
60.​ git merge branch – Merge branch into current
branch​
61.​ git log --oneline – Show commit history​
62.​ git diff – Show changes​
63.​ git stash – Stash changes​
64.​ git stash pop – Apply stashed changes​
​​
​
​
65.​ git reset --hard HEAD~1 – Reset last commit​
66.​ git revert commit_id – Revert commit​
67.​ git tag -a v1.0 -m "Version 1.0" – Create tag​
68.​ git push --tags – Push tags​
69.​ git rm file – Remove a file from git​
70.​ git clean -fd – Remove untracked files​
71.​ git config --global user.name "Your Name" – Set
global username​
72.​ git config --global user.email "you@example.com"
– Set global email​
73.​ git show commit_id – Show commit details​
74.​ git blame file.txt – Show changes by line​
75.​ git remote -v – Show remote repositories​
76.​ git remote add origin URL – Add remote repo​
77.​ git rebase branch – Rebase branch​
78.​ git cherry-pick commit_id – Pick specific commit​
​
​​
​
​
79.​ git fetch – Fetch remote changes​
80.​ git log --graph – Show graphical commit log​
81.​ git branch -d branch_name – Delete branch​
82.​ git pull --rebase – Rebase while pulling​
83.​ git push --force – Force push changes​
84.​ git reflog – Show reflog​
85.​ git diff HEAD~1 – Show last commit changes​
86.​ git apply patch.diff – Apply patch​
87.​ git reset --soft HEAD~1 – Soft reset​
88.​ git archive --format=tar.gz HEAD > archive.tar.gz
– Archive repo​
89.​ git grep "search_term" – Search for text​
90.​ git bisect start – Start binary search​
91.​ git ls-files – List tracked files​
92.​ git update-index --assume-unchanged file – Ignore
file temporarily​
​
​​
​
93.​ git push origin --delete branch_name – Delete
remote branch​
94.​ git pull --all – Fetch all branches​
95.​ git submodule add URL path – Add a submodule​
96.​ git submodule update --init --recursive – Update
submodules​
97.​ git commit --amend -m "Updated commit message" –
Amend commit​
98.​ git fetch --prune – Remove deleted remote
branches​
99.​ git push --mirror destination_url – Mirror
repository​
100.​git worktree add ../branch_name branch_name –
Work with multiple branches

---


User space --> system compontny --? C-libarary  standards --> kernel
Read about linux system cal every day for a year. 



---
[BC sysadmin](https://decal.ocf.berkeley.edu/archives/2024-fall/)

---
DNS is fundamentally a distributed database of hostnames to IP addresses, we manage our database so people know how to get to our site/domain, and somewhere else another person is managing their database so others can get to their domain. These domains are then able to talk to each other and build a massive contact list of the Internet.



what is the different between /etc/shadow and /etc/passwd
/etc/sudoer



---
On systems that use systemd, you can boot into rescue mode by appending
systemd.unit=rescue.target to the end of the existing Linux kernel line. At the
GRUB splash screen, highlight your desired kernel and press the “e” key to edit its
boot options. Similarly, for emergency mode, use systemd.unit=emergency.target.
Here’s an example of a typical configuration:
linux16 /vmlinuz-3.10.0-229.el7.x86_64 root=/dev/mapper/rhel_rhel-root
ro crashkernel=auto rd.lvm.lv=rhel_rhel/swap rd.lvm.lv=rhel_rhel/root
rhgb quiet LANG=en_US.UTF-8 systemd.unit=rescue.target
Type <Control-X> to start the system after you’ve made your changes.

---

---

the user in linux is just a Number UID this UID, the system use API to interact and get info about this user, getpid() function system call is for that

wite a backup script to change the name of thing in date.bck


---

Introduction
00:35 - Why These Sites Matter
01:08 - 1. VulnHub – Virtual machines with vulnerabilities for hands-on practice
01:46 - 2. Hack The Box – Competitive hacking with real-world challenges
02:35 - 3. Packet Storm Security – Security news and exploit database
03:00 - 4. OverTheWire – Gamified cybersecurity learning
05:17 - 5. Malware Traffic Analysis – Hands-on threat intelligence training
05:41 - 6. Exploit Database – Repository of real-world security vulnerabilities
06:10 - 7. SANS Cyber Aces – Beginner-friendly cybersecurity training
06:30 - 8. Hacking Articles – Ethical hacking tutorials & guides
06:57 - 9. SecurityTube – The YouTube of cybersecurity
07:22 - 10. OpenSecurityTraining – Free courses on reverse engineering & malware analysis
07:46 - 11. CTF Time – Track and join Capture The Flag competitions
08:17 - 12. Intigriti – European-focused bug bounty platform
08:44 - 13. Hack The Army – Ethical hacking challenges for U.S. military systems
09:10 - 14. Replit – Collaborative coding for penetration testing & security scripting
09:38 - 15. CyberDefenders – Hands-on SOC and digital forensics training
10:02 - 16. PortSwigger Web Security Academy – Web application security training
10:30 - 17. TryHackMe – Gamified hacking & guided tutorials
11:10 - 18. Red Team Labs – Advanced red teaming techniques
11:36 - 19. Shodan – The search engine for hackers (finding exposed devices)
12:10 - 20. Bugcrowd University – Learn professional bug bounty hunting
12:36 - 21. Hack This Site – Community-driven ethical hacking challenges
12:59 - 22. Root Me – Interactive cybersecurity challenges
13:32 - 23. Exploit.Education – Software exploitation & binary exploitation training
14:07 - 24. Pentest Tools – Online penetration testing suite
14:38 - 25. MITRE ATT&CK Framework – Understanding adversary tactics and techniques
15:06 - Conclusion

---
 

