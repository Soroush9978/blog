# This is the file where document learning
 
*first point ctrl+k +v is for preview markdown in vscode*

refer to [this link](https://learnxinyminutes.com/docs/markdown/) for a guide about markdown. note that there exist different flavour of markdown.

---



### 04.06.2024

## Create a dotfiles folder and move the configuration to that 
also write scripts to link those files to any systems

The book mastering Algorithm with C, recommended by Rob.
Search about fuzzy search

---

### 05.06.2024

learn about running a Tor Relays different kind of nodes gurd nodes and exit nodes 
This command show you the arch:


	dpkg --print-architecture

---

### 09.06.2024
I have done The sicherheit in cloud schulung and that was very basic
when I restarted the Services containers where down for some secends then they became up!

pandoc was a converter that I was looking for for example it takes markdowninput and gives txt, pdf or html output 
LDAP is auth server database structure 
cd /etc/openldap/slapd.d/cn=config.ldif
High Performance Software Foundation (HPSF)[this](https://hpsf.io/#hpsf-has-launched)
What the hell is personal radio station? maybe a nice hobby [this](https://www.hamexam.org/)
Also learn about OpenSCAP [this] (https://www.open-scap.org/)
---

### 10.06.2024

vim shortcut $ move to the end of line also this is the cheetsheet link that can help [sheet](https://vim.rtorr.com/)

---

### 1.06.2024

Okay so the new scope of our projct is to move the documentation from Confluence to gitlab

my first idea is to use confluence APi 
[con-doc](https://docs.atlassian.com/atlassian-confluence/REST/5.7.1/#d3e714)
[gitlab address](https://zivgitlab.uni-muenster.de/wwuit-sys/hpc/palma-documentation)
[HPC current docs](https://zivgitlab.uni-muenster.de/wwuit-sys/hpc/palma-documentation)

also there is a gem isovalent labs [paths](https://isovalent.com/learning-tracks/)

---

[Nice roadmap about sec](https://pauljerimy.com/security-certification-roadmap/)

	



ToDo:

- [x] write a Canaban boarda.
	
- [x] Gather mind and set a todo list

- [] Read sysadmin book "The practice of system administration book", "The Practice ofthe cloud System administration", "Time management for System Adminastrator"

- [x] Do ENT4 Homework and saw the video

 <del>This</del>

---

### 11.06.2024

Maybe run a MailServer on Hetzner Server 
SMTP: send message between servers, 
POP: sync from server to my computer 
IMAP: 	also sync

---


### 15.06.2024

Het-tennis youtube videos are greate 
learn about chaos engineering 
incident response
and these kind of things 
also managing the control flow of updates
SANs cheatsheet [This](https://zeltser.com/media/docs/security-incident-survey-cheat-sheet.pdf?msc=Cheat+Sheet+Blo)

grep -i what does it do ?
how to gather cpuinfo
systemd-detect-virt show if you are on a vM
vmstat
why using swap is bad strategy ? in modern linux env
add influx db and time series DB specially using for monitoring

Role of loopback interface, 
check out 
	ethtool [interface]

specify the number of time you want to ping somewhere
	
	ping -c4 ...

changing /etc/servives ?
ss -tulpen read data from there




[This is a website for eu alternative services](https://european-alternatives.eu/categories)


---



### 20.06.2024

[Nice roadmap about sec](https://pauljerimy.com/security-certification-roadmap/)


the command that i was looking for long time 

	dpkg -l
list the package that are on the server
what is nfs
pay more attention to Katacoda and kodekloud
also think about eBPF and it's function





lscpu
nproc
cat /proc/cpuinfo
dmidecode -d cpu
lsblk -f
lsof list the processes on a directory 
echo $$


lsof . |grep -v PID | awk'{2$}' |xargs kill -9

user group 

[This redhat](https://www.redhat.com/sysadmin/linux-file-permissions-explained)


test the write and read spedd with loops and dd 
	
	for i in $(seq 5); do echo "I am writing $i file"; time dd if=/dev/zero of=bigfile$i bs=4096k count=250;
	
jumbo frames and mtu and icmp packets,


lsmod 
stat /etc/...
tripwire linux what is that ?





encrypt a file using vi -x argument  
ID USERNAME
I know `sudo -l` shows you your sudoer permissions. sudo -lU maybe?





cat /proc/version	
dpkg -l | grep kernel ?
ls /boot
apt list --installed | grep linux-image
ps aux | grep ssh



lsb_release -a 
seven colum of passwd
username
password
id
group id
home 
shell

---

### 25.06.2024

cilium what is that it seems that learning kubernetees is a part of learning process
also lets do a research about HPC 


### 27.06.2024
can you touch a file with today date in it?
touch file.`date +%F` the little thing upside is strange
touch file. $(date +%F)a
for i b
for i in $(seq 5); do touch $i; done
touch {1..100}
more about seq command read about sreps

echo $$ show current bash pid
an you show all the packaages that have SSL in their name?
	  - dpkg -l | awk '{print $2}' | grep -i ssl
	  - dpkg -l | gawk '/ssl/{print $2}'
using -E for persistant env 


---

### 1.07.2024

Using the system engineering by nasa 
---

### 2.07.2024

compare between wikis strategies,

---

### 04.07.2024

I learned materials for mkdocs it is a really good platforms

---

### 07.07.2024

learn about linux systemcall interface 


---

### 08.07.2024

layer accsess technologies : Dial up, DSL, FFTH, wireless point 
adsl rj11 conector spliter
DSLAM, modem : modoulation demodulation 
BRAS
DSLAM ---> BRRAS




---
### 09.07.2024
learn how to work with multiple git 
how git works deeply and configure it and learn the owenership and overcome the difficulties

ps
ps -u
ps -efj
ps -uf


---

### 15.07.2024

learn how to change tmux statusbar color 
[tmux](https://github.com/tmux/tmux/wiki/Getting-Started)

0 in vim go to the first of the line
shift+4 will go to the end of line

Virtualization is the logical sharing of compute, storage, and networking
resources among multiple processes, allowing each to run as if it was a stand-
alone physical computer




Linux and Unix system administration handbook ( for Linux admin stuff. Highly recommended)

Pro git (for git. Very usefull)

The linux command line (from the author of automating the boring stuff with Python)

The Pragmatic Programmer (for programming)

I have only read bits and pieces of these books, but I searched reddit a lot to find vest books to learn this stuff, and these were the recommendations.


UNIX and Linux System Administration Handbook

The UNIX-HATERS Handbook

ab tool is something for testing apache webserver
sysstat needs to be set to true to run 
it uses cronjob

 ab -n 1000 -c 10 https://nextcloud.baboojoo.ir/ this command test the apache web server 
but i guess ofcourse there are certeinly modern tools like influx db, time series database or many application metrics

The pmap command reports the memory map of a process or processes.
	pmap


mpstat command for cpu testing 
ntop ng is a heavy networking monitor tool

iftop is also 
sar -n is also good 
mtr advance pathping
mtr -z show the ASN that is good for detecting autonomes network

/etc/issue
MOTD
creat motd for a banner 
tar stands for tape archive util
tar -cf stands for create file name then path and the -z is for compression
for decompressing 
tar -xzvf file name
there is a -p option to preserve a permission 
the ownership and permission of tar should be take into consideration while doing tar
a bit of history dd stands for copy and convert 
while cc was used by c compliler :))
in ideal situation you should unmount the disk 
status=progress
also change the blocksize to 1m
wow wow 
dd is really powerful and useful it is really interesting 
rsync -azurP
rsunc listen on tcp 873
rsunc -azurP -e ssh
we also can use --include and --exclude
we also should include -p option for permissions also -AGo
mess around with resolvectl command 
tracepath is the new traceroute 
compare the difference
ip -s link
nc tools



### 20.07.2024

dynnamic kernel modules 
lsmod
modinfo [kernel module]
sudo insmod
rsmode
sudo mode probe mosuldle with out ppath
lsdev
blkid
lsblk


compare SSHgaurd, fail2ban, 
i heard the concept of creating a swap file with dd and stream of zero then use it as a swap 
and then make it mkswap 

if we make a swap partition this way they are not presistant we should add them to fstab to make them persistant
systemd can do mount point and unit 

what is efi partition 
btrfs file system the is the file system that docker use?
No it is not it uses onion file system
what are layer 4 proxy?

The similar thing ti bitlocker in linux is LUKS, i mean it is crazy that some one think that maybe this feaure is better in windows, openBSD is a joke to you


for security paranoid we can use shred to wipe the disk and write new data in itteration 

apt cryptsetup-bin
IDE --> SATA type of disks 
hdparm 


sudo hdparm -I /dev/sda |less
The difference between NVMes ssd and SATA SSD

LVM has three levels
1.physical
2.groups
3.volumes
sudo pvcreate
sudo pgcreate




scp mylogin@10.0.3.142:/home/mylogin/filename .
copy a remote file to the current directory on your
local machine 


"But if this is all about automating file system actions, why not use the Bash script-
ing skills you already have? Well, you probably could, but once you start trying to
incorporate things like remote authentication and conflicting software stacks into
those scripts, your life will quickly become insanely complicated.
Orchestrators will safely and reliably manage variables and passwords for you, and
apply them within the proper context as often and in as many ways as necessary. You
don’t need to track all the fine details on your own. Because there are all kinds of
orchestration tools, the one you choose will largely depend on the specifics of your
project, organization, and background. You’ll need to ask yourself some basic ques-
tions: “Are most of the people involved going to be developers or IT professionals?”
“Will you be using a continuous integration methodology?” Table 16.1 provides some
quick and dirty profiles of four of the main players."



The concept of service level objectives




---
### 22.07.2024
rsync
rclone
dd
growisofs


nohup Run a process that continues after you log out.
flock Ensure that only one instance of a command runs at a time.

at [options] time specification
The at command schedules one or more shell commands to
run later:



tty
The tty command prints the name of the terminal device
associated with the current shell:

man -k database | less

/boot
Files for booting the system. The kernel lives here, typi‐
cally in /boot/vmlinuz or a file of similar name.
/lost+found
Damaged files that were rescued by a disk recovery tool.
/proc
Files for currently running processes; for advanced users.
/sys
Files for kernel internals; for advanced users.


how to use spell command to replace incorrect words with write ones using sed

also there is a tool called aspell


cat View files in their entirety.
less View text files one page at a time.
nl View text files with their lines numbered.
head View the first lines of a text file.
tail View the last lines of a text file.
strings Display text that’s embedded in a binary file.
od View data in octal (base 8) or other formats.


find Locate files in a directory hierarchy.
xargs Turn a list of files into a list of commands (and much more).
locate Create an index of files, and search the index for a string.
which Locate executables in your search path (command).
type Locate executables in your search path (bash built-in).
whereis Locate executables, documentation, and source files.

Perhaps Linux’s greatest strength is text manipulation: massag‐
ing a text file (or standard input) into a desired form by apply‐
ing transformations, often in a pipeline. Many commands do
this, but here I focus on some of the most important tools for
transforming text.

pandoc Convert from one markup language to another.
hxselect Extract information from an HTML file.
jq Extract information from a JSON file.
6 I ran pandoc to convert material from the third edition of this book,
written in DocBook XML, to AsciiDoc for the fourth edition.
xmllint Validate and extract information from an XML file.
csvtool Extract information from a comma-separated values (CSV) file.
split Split up a file simply into multiple files.
csplit Split up a file into multiple files using complex criteria

csplit

split

csvtool

PDF and PostScript File Handling
pdftotext Extract text from PDF files.
ps2ascii Extract text from PostScript or PDF files.
pdfseparate Extract individual pages from a PDF file.
pdftk Split, join, rotate, and otherwise manipulate PDF files.
pdf2ps, ps2pdf Convert between PDF and PostScript file formats.
ocrmypdf Perform optical character recognition (OCR) on a PDF


[itfoss community](https://itsfoss.community/c/server/4)

[LQ](https://www.linuxquestions.org/)

[Stack](https://unix.stackexchange.com/)

[NixCraft](https://www.nixcraft.com/)
kernel thing
[kernel stuff](https://kernelnewbies.org/)

[TLDP](https://tldp.org/FAQ/Linux-FAQ/online-resources.html#howtos-and-other-documentation)

FreeIPA - Identity, Policy, Audit
centeral thing probebly industery use
[THIS](https://www.freeipa.org/)

[Server fault](https://serverfault.com/?tab=active)


[very important blog](https://www.brendangregg.com/index.html)

---

### 23.07.2024

Linux kernel syscall tables 
[Linux kernel syscall tables](https://syscalls.mebeim.net/?table=x86/64/x64/latest)
[syscall things](https://syscall.sh/about)

sudo iptables -save

sudo nmap -Pn -p 1-3000 -sV 116.202.25.235    
this command also show the services 

vsftp is old standard for FTP, but the modern thing is SFTP

apachectl testconfig
also what is fuzzy search algorithm
after the LPIC2 course with it protv next i want to move to RIPE academy courses.

---

### 25.07.2024

BIND DNS server, 

---

### 27.07.2024

Kant's maxim of enlightenment 

 - enlarge thinking 
 - thinking conssistently 
 - put your self in others 

take a critical distance of what we fancy os the core aspect of the enlightenment as a process of self revelation 
there is also a decision between freedom of chice and freedom of agency 
capitalism undermine the reall freedom with freedom of choice


good blog about thechnical stuff

[homelab stuff](https://blog.davidv.dev/)

[History of command line](https://web.stanford.edu/class/cs81n/command.txt)



Linux networking 
[linux net sysctl](https://github.com/leandromoreira/linux-network-performance-parameters/)



=============================

There is a thinker Lea Ypi, a professor at LSE, Kanitian marxist, do research of connection to liberal and freedom and marxism.

Host a Gitea server, create a subdomain set a reverse proxy point it to the right servise


## useful docker command, 

docker stats
docker events
docker inspect
docker logs

----
----
Also for my next homelab project i want to run Gitea on gitea.baboojoo.ir also i want to set it as it does not have any conflict with nextcloud instance, and inssure the security of it is okay.
printenv HOME


also a nice idea about a future blog post:
explain where does the programs like htop, top get their value 
you should look at /proc/stat







sysconf is a function in Unix-like operating systems that provides a way to retrieve system configuration information at runtime. It is part of the POSIX standard and allows programs to query system-specific limits and options that are defined in header files such as unistd.h


Purpose of sysconf

The primary purpose of sysconf is to provide a way to obtain values for system limits and options that are defined at compile time but may vary between different systems or configurations. This makes programs more portable and adaptable to different environments.


----

### 28.07.2024

	echo $PATH | tr : "\n"


 recall the previous command and replace jg by jpg (first
occurrence only), just as caret notation does, run:
$ !!:s/jg/jpg/
Suppose you’ve mistakenly run the following command by typing jg instead of jpg:
$ md5sum *.jg | cut -c1-32 | sort | uniq -c | sort -nr
md5sum: '*.jg': No such file or directory
To run the command properly, you could recall it from the command history, cursor
over to the mistake and fix it, but there’s a quicker way to accomplish your goal. Just
type the old (wrong) text, the new (corrected) text, and a pair of carets (^), like this:
$ ^jg^jpg

pushd and popd maybe helpful

dirs print directory stack 

Producing text, Isolating text,Combining text, Transforming text
grep, cut, head, tail, awk
paste, diff, 
tr, rev, sed

```
	dpkg -l
	tmux pipe-pane -o "exec cat >>$HOME/'logs-tmux.log'"
	curl -s https://raw.githubusercontent.com/sivel/speedtest-cli/master/speedtest.py | python -

	
```
Redhat satelite and Pulp project for patch management

Build RPms

The nobody user in Unix-like operating systems is a special system user account used for running unprivileged processes. This user has minimal permissions and is often used for security purposes to run services that do not require elevated privileges, thereby minimizing the potential damage that can be done if the service is compromised.
Key Points About the nobody User

    Unprivileged: The nobody user has very limited permissions and cannot perform actions that require higher privileges.
    Security: Running processes as nobody helps in isolating and limiting the access of potentially vulnerable or less secure services.
    System Use: It's commonly used by system services and daemons to run safely without the need for root privileges.

Understanding the Output

    UID: The first column shows the user ID (nobody).
    PID: The second column shows the process ID.
    PPID: The third column shows the parent process ID.
    C: The fourth column shows the CPU utilization.
    STIME: The fifth column shows the start time of the process.
    TTY: The sixth column shows the terminal associated with the process.
    TIME: The seventh column shows the cumulative CPU time.
    CMD: The eighth column shows the command that started the process.
Why Use the nobody User

    Security: Running services with minimal permissions reduces the risk of system compromise.
    Isolation: It helps in isolating services from each other and from critical system components.

Common Services Running as nobody

    NFS Daemons: Network File System services often run as nobody.
    Web Servers: Some web server processes, when configured to run without special privileges, may run as nobody.
    Other Daemons: Various other system daemons and services that do not require elevated privileges might use the nobody user.

Conclusion

The nobody user is a system user with minimal privileges, commonly used to run unprivileged processes for enhanced security. Using ps -ef | grep nobody, you can identify which processes are running under this user, helping you to manage and secure your system effectively.






Warewulf: cluster managment like: xCAT, 
[warewulf](https://warewulf.org/)

Grymoire a learning blog
[Grymoire](https://www.grymoire.com/index.html#toc_My_personal_web_site_containing_a_collection_of_useful_incantations_for_wizards_of_all_sorts)

---
### 02.08.2024

What are the difference between sourcing a script and running it, 
sourcing?
sourcing tell your current bash session to exe that program
./.sh start up a new instance of bash 	



---

### 03.08.2024

MIT operating system, course which write the OS itself, 
[OS ENG](https://pdos.csail.mit.edu/6.828/2023/reference.md)

Here are some courses regardig security find out from MIT:
	1. [Net_Sec](https://www.cs.umd.edu/~jkatz/imc.html)
	2. [Network and Computer Security](https://opencw.aprende.org/courses/electrical-engineering-and-computer-science/6-857-network-and-computer-security-spring-2014/)
	3. [Also see this](https://css.csail.mit.edu/6.858/2023/general.html)


Haha This was easier than i thought: how to bind Kaps key to escape:
setxkbmap -option caps:escape

Schneier Bloog
[Schneier on Security ](https://www.schneier.com/)
[king Pi – Operating Systems Development](https://www.cl.cam.ac.uk/projects/raspberrypi/tutorials/os/)

----
### 04.08.2024

awk '{print $1} path to the file

lmit the search to package names that include your search term:
$ apt search packagename --names-only


awk 'BEGIN{FS=","; OFS="\t"} {print $!, $2, $3}' path



imagine the situation that find cant do symbolic link it does not go across file systemsshould be something about symbolic link ad these stuffs





nix shell nixpackage#
see man mtr


mtr -wo LSRABW carlaschroder.com

grep tcp /etc/services


ps -eH
ps -eFl
ps is a very powerful command 
pidof
pgrep

dd if=/dev/zero of=/dev/null






### 06.08.2024


different kind of filessystems,

BTrfs, 
ZFS

Question : when archiving a file or send it thrugh sftp or rsync when does the permission change?  The tune2fs utility with the -j argument will add an ext3 journal to the specified file system. 


[How cpus work](https://djharper.dev/post/2019/05/21/i-dont-know-how-cpus-work-so-i-simulated-one-in-code/)


/etc/shadow
/etc/passwd
/etc/login.def
/etc/default/useradd


This command is to add user to a gorup 

usermod -a -G group user
how to lock and unlock thee user by usermod 
passwd -d delete password

passwd -e expire password 
also see chage command 
when user are able to loging when with sshkeey even when the accouunt is locked 


There are  to commands to set ACL permission on linux file

setacl 
getacl 


set 
set -o posix

Look at Bash exe order, 
you knoww that one can overwrite commands with alias and bash functions, so if you want to make sure that the original command runs what you do ?

you do it with command 



incus config trust add-certificate Downloads/incus-ui.crt


[Article about reverse ssh](https://unix.stackexchange.com/questions/46235/how-does-reverse-ssh-tunneling-work)


incus is a great tool 




Try the github education pack, a




---
### Do 8. Aug 14:57:33 CEST 2024



How to read json data format
Root Object: The entire structure is a JSON: object, indicated by {}. This object contains multiple key-value pairs.


pilars of observality: what are they ? metric logs, 
[incus docs](https://linuxcontainers.org/incus/docs/main/)


----

### Fr 9. Aug 00:14:54 CEST 2024



---

How the check file metadata in linux ?

Write and script to find when an apt package is updated or modified?

stat command to show file statistics
file command also but shorter information
getfacl to show the file permission

