**ssh with config ovpn**
```bash
sudo openvpn --config ./Downloads/academy.ovpn
```
---
Each manual page has a short description available within it. This tool searches the descriptions for instances of a given keyword.

```bash
apropos <keyword>
```
---
**System Information**

| Command  | Description                                                                                                                        |
|--------- | ---------------------------------------------------------------------------------------------------------------------------------- |
| whoami   | Displays current username.                                                                                                         |
| id       | Returns users identity                                                                                                             |
| hostname | Sets or prints the name of current host system.                                                                                    |
| uname    | Prints basic information about the operating system name and system hardware.                                                      |
| pwd      | Returns working directory name.                                                                                                    |
| ifconfig | The ifconfig utility is used to assign or to view an address to a network interface and/or configure network interface parameters. |
| ip       | Ip is a utility to show or manipulate routing, network devices, interfaces and tunnels.                                            |
| netstat  | Shows network status.                                                                                                              |
| ss       | Another utility to investigate sockets.                                                                                            |
| ps       | Shows process status.                                                                                                              |
| who      | Displays who is logged in.                                                                                                         |
| env      | Prints environment or sets and executes command.                                                                                   |
| lsblk    | Lists block devices.                                                                                                               |
| lsusb    | Lists USB devices                                                                                                                  |
| lsof     | Lists opened files.                                                                                                                |
| lspci    | Lists PCI devices.                                                                                                                 |

**User managemente**

| Command  | Description                                                                                                                      |
| -------- | -------------------------------------------------------------------------------------------------------------------------------- |
| su       | The `su` utility requests appropriate user credentials via PAM and switches to that user ID (the default user is the superuser). |
| useradd  | Creates a new user or update default new user information.                                                                       |
| userdel  | Deletes a user account and related files.                                                                                        |
| usermod  | Modifies a user account.                                                                                                         |
| addgroup | Adds a group to the system.                                                                                                      |
| delgroup | Removes a group from the system.                                                                                                 |
| passwd   | Changes user password.                                                                                                           |

---
**The repository list**
```/etc/apt/sources.list```

---
**to provide information about packages installed on our system offline**
```bash
apt-cache search impacket
```
and then show info about package
```bash
apt-cache show impacket-scripts
```
---
**list installed packages**
```bash
apt list --installed
```
---
**install packages with dpkg**
```bash
sudo dpkg -i strace_4.21-1ubuntu1_amd64.deb
```
---
**list systemctl**
```bash
systemctl list-units --type=service
```
---
**logs in systemctl**
```bash
journalctl -u ssh.service --no-pager
```
---
**process signals**

| Signal | Description                                                                                          |
| ------ | ---------------------------------------------------------------------------------------------------- |
| 1      | `SIGHUP` - This is sent to a process when the terminal that controls it is closed.                   |
| 2      | `SIGINT` - Sent when a user presses `[Ctrl] + C` in the controlling terminal to interrupt a process. |
| 3      | `SIGQUIT` - Sent when a user presses `[Ctrl] + D` to quit.                                           |
| 9      | `SIGKILL` - Immediately kill a process with no clean-up operations.                                  |
| 15     | `SIGTERM` - Program termination.                                                                     |
| 19     | `SIGSTOP` - Stop the program. It cannot be handled anymore.                                          |
| 20     | `SIGTSTP` - Sent when a user presses `[Ctrl] + Z` to request for a service to suspend. The user can handle it afterward.                                                                                                     |

---
**create file**
```bash
touch <name>
```
---
**create parent dir**
```bash
mkdir -p Storage/local/user/documents
```
---
**view dirs in tree**
```bash
tree .
```
---
**Move Files to Specific Directory**
```bash
mv information.txt readme.txt Storage/
```
---
**copy**
```bash
cp Storage/readme.txt Storage/local/
```
---
**show path to tools**
```bash
which python
```
---
**find file recursive**
```bash
find <directory> -type f | wc -l
```
---
**find with hidden errors and  send result in file  result.txt**
```bash
find / -executable -type f -name xxd 2>/dev/null > results.txt
```
**send err and out in separate files**
```bash
find /etc/ -name shadow 2> stderr.txt 1> stdout.txt
```
---
**append to exist file**
```bash
find /etc/ -name passwd >> stdout.txt 2>/dev/null
```
---
**view first,  last,  first 10, last 10 lines of file**
```bash
more /etc/passwd
less /etc/passwd
head /etc/passwd
tail /etc/passwd
```
---
**sort lines**
```bash
cat /etc/passwd | sort
```
---
**grep exclude "/bin/false" or "/usr/bin/nologin"**
```bash
cat /etc/passwd | grep -v "false\|nologin"
```
---
**cut result**
```bash
cat /etc/passwd | grep -v "false\|nologin" | cut -d":" -f1
```

Therefore we use the option "-d" and set the delimiter to the colon character (:) and define with the option "-f" the position in the line we want to output

---
**replace characters**
```bash
cat /etc/passwd | grep -v "false\|nologin" | tr ":" " "
```
---
**add result in column**
```bash
cat /etc/passwd | grep -v "false\|nologin" | tr ":" " " | column -t
```
---
**awk: show first and last column **
```bash
cat /etc/passwd | grep -v "false\|nologin" | tr ":" " " | awk '{print $1, $NF}' | column -t
```
---
**sed: replace the word "`bin`" with "`HTB`." in stdout**
```bash
cat /etc/passwd | grep -v "false\|nologin" | tr ":" " " | awk '{print $1, $NF}' | sed 's/bin/HTB/g'
```
---
# Permission Management
```bash
ls -l /etc/passwd

- rwx rw- r--   1 root root 1641 May  4 23:42 /etc/passwd
- --- --- ---   |  |    |    |   |__________|
|  |   |   |    |  |    |    |        |_ Date
|  |   |   |    |  |    |    |__________ File Size
|  |   |   |    |  |    |_______________ Group
|  |   |   |    |  |____________________ User
|  |   |   |    |_______________________ Number of hard links
|  |   |   |_ Permission of others (read)
|  |   |_____ Permissions of the group (read, write)
|  |_________ Permissions of the owner (read, write, execute)
|____________ File type (- = File, d = Directory, l = Link, ... )
```
---
**Change Permissions**
0 = no permissions whatsoever; this person cannot read, write, or execute the file
1 = execute only
2 = write only
3 = write and execute (1+2)
4 = read only
5 = read and execute (4+1)
6 = read and write (4+2)
7 = read and write and execute (4+2+1)
```shell-session
Binary Notation:                4 2 1  |  4 2 1  |  4 2 1
----------------------------------------------------------
Binary Representation:          1 1 1  |  1 0 1  |  1 0 0
----------------------------------------------------------
Octal Value:                      7    |    5    |    4
----------------------------------------------------------
Permission Representation:      r w x  |  r - x  |  r - -
```
u - owner, g - Group, o - others, a - All users
[+] or a [-] to add remove the designated permissions
```bash
chmod a+r shell && ls -l shell
```
**Change Owner**
```bash
chown <user>:<group> <file/directory>
chown root:root shell && ls -l shell
```
---
**samba connect**
```bash
smbclient \\\\zimmerman\\public mypasswd
```
---
**gobuster scan**
```bash
sudo gobuster dir -u 10.129.174.247 -w /usr/share/wordlists/dirb/common.txt
```
---
