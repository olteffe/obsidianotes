**del**
```bash
rm -R waste (удалить каталог “waste” со всем вложенным содержимым)
```
---
**secretcopy**

```bash
sudo scp -i /home/olteffe/key/id_dsa ubuntu@1.1.1.1:/home/ubuntu/wg0-client-ime.conf /home/oleg/key/
```
***
**очистить историю ввода баш**
```bash
history -c
```
***

**convert ssh to ppk**
```bash
puttygen pet -o pet.ppk
```
***
**create pair key**
```bash
puttygen -t rsa -b 2048 -C "user@host" -o keyfile.ppk
puttygen keyfile.ppk -O public-openssh -o keyfile.pub
```
---
**oracle linux update**
```bash
sudo yum check-update; sudo yum update -y
```
***

**install epel in oracle linux aarch64**
```bash
sudo dnf search epel		<-search
sudo dnf install oracle-epel-release-el8.aarch64  <-install repo
```
if it disabled -> go to /etc/yum.repos-d/ and replace “enabled=1” in need file-repo
***

**sshguard**
https://wiki.archlinux.org/title/sshguard
```bash
sudo systemctl enable sshguard
sudo systemctl start sshguard
```
***
