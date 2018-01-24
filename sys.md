
- [text processing](#text-processing)
- [network](#network)
- [shell](#shell)
- [file system](#file-system)
- [services](#services)
- [packages](#packages)
- [sed](#sed)
- [awk](#awk)
- [filesystem](#filesystem)
- [server checklist](#server-checklist)

## text processing

|Commands|
:--|
|cut -c 1-10
|cut -d : -f 1,5
|grep -c/-R
|sort -rn
|/usr/libexec/locate.updatedb
|sort -u; sort -k 5 (sort column)
|uniq -c
|tr '\*' ':'
|find . -mtime -5/+5
|find . -newer '\*.c'
|find -name B -exec vim {} + (+ results one invocation of cmd)
|find -name '\*.c' -delete
|find . \! -name "\*.gz"  maxdepth 1 -print
|find $1 -type f -exec stat --format '%Y :%y %n' "{}" \;
|find /var -type f -size +10M -exec ls -lh {} \;  
|find . -name '\*.pyc' -exec git rm -f '{}' \;

## network

|Commands|
:--|
|dig / drill / host
|host
|netcat
|tcpdump -neor pf.log
|rsync -rt --size-only
|netstat -tulpn -> Linux
|netstat -naf inet -> BSD

## shell

|Commands|Description
:--|:--|
!!:2-3|
!-2 |second to last command
!?string | most recent cmd
!?string?:\* | params of last cmd
^hre^her |
!!:s/a/A/:s/b/B/
!\* | last cmd's parameters
!^ | last cmd's first param
!$ | last cmd's last param
ls /urs/urs; !!:gs/urs/usr/ |
touch file.{1..5} |
cp file{,.bak} |
\*(m0) | modified today
\*(m-4) | last modified <4 days ago
echo /usr/ports/\*/\*http\* | tab expands

## file system

|Commands|
:--|
df -h
du -hd 1
dd if=/dev/sda of=/dev/sdb
dd if=/dev/sda of=~/disk1.img
chmod 1:x, 2:w, 4:r; 7:rwx
chmod u+x, g+x, u-x, g-x
fdisk -l
gparted

## services

|Linux|
:--|
|systemctl {start \| stop \| restart}
|systemctl list-unit-files --type=service
|systemctl {enable \| disable}

|OpenBSD|
:--|
|rcclt ls on, started, failed
|/etc/rc.d/service start/stop reload/restart/check

|FreeBSD|
:--|
service sshd status/restart
service -e (list started services)

## packages

|Commands|Description
:--|:--|
|apt install/remove <pkg> | Install/remove <pkg>
|apt list --installed / dpkg -l | List installed packages
|apt -s install <pkg> | Simulate what would be done 
|apt update | Refreshes repository index
|apt list --upgradable | Show upgradable packages
|apt upgrade | Upgrades all upgradable packages
|apt full-upgrade | Upgrades packages with auto-handling of dependencies
|apt search <pkg> / apt-cache search <pkg> | Searches for the program
|apt show <pkg> | Displays control file
|apt-cache policy [<pkg>] | Shows all policies or of <pkg>
|/etc/apt/sources.list | List of available repositories
|dpkg -L <pkg> | List files installed by <pkg>
|dpkg -s <pkg> | Displays headers of an installed package
|dpkg -S <file> | Displays which package(s) contins <file>
|/var/log/dpkg.log | Log of all dpkg actions

|OpenBSD|
:--|
|pkg_add -u
|pkg_info -Q openvpn
|https://stable.mtier.org/openup

|FreeBSD|
:--|
|portsnap fetch/extract/update
|freebsd-update fetch / extract
|freebsd-update IDS
|pkg info -l
|pkg autoremove
|pkg clean (-a removes up-to-date downloaded pkgs)
|pkg upgrade
|pkg -vv

## sed

|Commands|Description
:--|:--|
sed 's/jessie/stretch/g' file |
sed 's/[ \t]\*$//' | del trailing space
sed '/x/s/a/b/g' | sub "a" with "b" for lines contain "x"

## awk

|Commands|Description
:--|:--|
awk -F ":" '{print $1 }' /etc/passwd | print login names of all users
awk '{print $2, $1}' file |  print first 2 fields, in opposite order
awk '{ $2 = ""; print }' | delete second field
awk '$5 == "foo"' | print lines field #5 equals "foo"
awk '$7 ~ /^[a-f]/' | match field against a regex

## server checklist

|Commands|
:--|
|rc.conf
|sshd_config (authmethod)
|ssh-keygen
|vim, git, zsh
|mail, alias root, ssmtp
|tzsetup
|df -h
|swapinfo -g
|syslog
|hostnames
|updates
|download src
|verify permissions
|ufw/pf/ipfw


