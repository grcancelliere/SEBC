* Cloud provider: `Azure`
* Linux release: `CentOS 7.2`
* `Show that the disk space on each node is at least 30 GB`
``` 
[sebc@sebcgrcm ~]$ df -hT
Filesystem     Type      Size  Used Avail Use% Mounted on
/dev/sda2      xfs        50G  2.2G   48G   5% /
devtmpfs       devtmpfs  6.9G     0  6.9G   0% /dev
tmpfs          tmpfs     6.9G     0  6.9G   0% /dev/shm
tmpfs          tmpfs     6.9G  8.3M  6.9G   1% /run
tmpfs          tmpfs     6.9G     0  6.9G   0% /sys/fs/cgroup
/dev/sda1      ext4      240M  124M  100M  56% /boot
/dev/sdc1      ext4      100G   61M   95G   1% /data
/dev/sdb1      ext4      197G  2.1G  185G   2% /mnt/resource
tmpfs          tmpfs     1.4G     0  1.4G   0% /run/user/1001
[sebc@sebcgrcm ~]$ df -hT | grep /data
/dev/sdc1      ext4      100G   61M   95G   1% /data
[sebc@sebcgrcm ~]$ ssh sebcgrc1 'df -hT | grep /data'
Password:
/dev/sdc1      ext4      100G   61M   95G   1% /data
[sebc@sebcgrcm ~]$ ssh sebcgrc2 'df -hT | grep /data'
Password:
/dev/sdc1      ext4      100G   61M   95G   1% /data
[sebc@sebcgrcm ~]$ ssh sebcgrc3 'df -hT | grep /data'
Password:
/dev/sdc1      ext4      100G   61M   95G   1% /data
[sebc@sebcgrcm ~]$ ssh sebcgrc4 'df -hT | grep /data'
Password:
/dev/sdc1      ext4      100G   61M   95G   1% /data
```
* `List the command and output for` yum repolist enabled
```
[sebc@sebcgrcm ~]$ yum repolist enabled
Loaded plugins: fastestmirror
Determining fastest mirrors
repo id                                             repo name                                                                   status
!base/x86_64                                        CentOS-7 - Base                                                             9,911
!extras/7/x86_64                                    CentOS-7 - Extras                                                             432
!openlogic/x86_64                                   CentOS-7 - openlogic packages for x86_64                                      115
!updates/x86_64                                     CentOS-7 - Updates                                                          1,561
repolist: 12,019
[sebc@sebcgrcm ~]$ ssh sebcgrc1 yum repolist enabled
Password:
Loaded plugins: fastestmirror
Determining fastest mirrors
repo id                  repo name                                        status
!base/x86_64             CentOS-7 - Base                                  9,911
!extras/7/x86_64         CentOS-7 - Extras                                  432
!openlogic/x86_64        CentOS-7 - openlogic packages for x86_64           115
!updates/x86_64          CentOS-7 - Updates                               1,561
repolist: 12,019
[sebc@sebcgrcm ~]$ ssh sebcgrc2 yum repolist enabled
Password:
Loaded plugins: fastestmirror
Determining fastest mirrors
repo id                  repo name                                        status
!base/x86_64             CentOS-7 - Base                                  9,911
!extras/7/x86_64         CentOS-7 - Extras                                  432
!openlogic/x86_64        CentOS-7 - openlogic packages for x86_64           115
!updates/x86_64          CentOS-7 - Updates                               1,561
repolist: 12,019
[sebc@sebcgrcm ~]$ ssh sebcgrc3 yum repolist enabled
Password:
Loaded plugins: fastestmirror
Determining fastest mirrors
repo id                  repo name                                        status
!base/x86_64             CentOS-7 - Base                                  9,911
!extras/7/x86_64         CentOS-7 - Extras                                  432
!openlogic/x86_64        CentOS-7 - openlogic packages for x86_64           115
!updates/x86_64          CentOS-7 - Updates                               1,561
repolist: 12,019
[sebc@sebcgrcm ~]$ ssh sebcgrc4 yum repolist enabled
Password:
Loaded plugins: fastestmirror
Determining fastest mirrors
repo id                  repo name                                        status
!base/x86_64             CentOS-7 - Base                                  9,911
!extras/7/x86_64         CentOS-7 - Extras                                  432
!openlogic/x86_64        CentOS-7 - openlogic packages for x86_64           115
!updates/x86_64          CentOS-7 - Updates                               1,561
repolist: 12,019
```
* New users and groups:
```
[sebc@sebcgrcm ~]$ grep -P 'raffles|fullerton' /etc/passwd
raffles:x:2000:2000::/home/raffles:/bin/bash
fullerton:x:3000:3000::/home/fullerton:/bin/bash
[sebc@sebcgrcm ~]$ grep -P 'hotels|shops' /etc/group
hotels:x:3001:fullerton
shops:x:3002:raffles
[sebc@sebcgrcm ~]$ ssh sebcgrc1 'grep -P "raffles|fullerton" /etc/passwd'
Password:
raffles:x:2000:2000::/home/raffles:/bin/bash
fullerton:x:3000:3000::/home/fullerton:/bin/bash
[sebc@sebcgrcm ~]$ ssh sebcgrc1 'grep -P "hotels|shops" /etc/group'
Password:
hotels:x:3001:fullerton
shops:x:3002:raffles
[sebc@sebcgrcm ~]$ ssh sebcgrc2 'grep -P "raffles|fullerton" /etc/passwd'
Password:
raffles:x:2000:2000::/home/raffles:/bin/bash
fullerton:x:3000:3000::/home/fullerton:/bin/bash
[sebc@sebcgrcm ~]$ ssh sebcgrc2 'grep -P "hotels|shops" /etc/group'
Password:
hotels:x:3001:fullerton
shops:x:3002:raffles
[sebc@sebcgrcm ~]$ ssh sebcgrc3 'grep -P "raffles|fullerton" /etc/passwd'
Password:
raffles:x:2000:2000::/home/raffles:/bin/bash
fullerton:x:3000:3000::/home/fullerton:/bin/bash
[sebc@sebcgrcm ~]$ ssh sebcgrc3 'grep -P "hotels|shops" /etc/group'
Password:
hotels:x:3001:fullerton
shops:x:3002:raffles
[sebc@sebcgrcm ~]$ ssh sebcgrc4 'grep -P "raffles|fullerton" /etc/passwd'
Password:
raffles:x:2000:2000::/home/raffles:/bin/bash
fullerton:x:3000:3000::/home/fullerton:/bin/bash
[sebc@sebcgrcm ~]$ ssh sebcgrc4 'grep -P "hotels|shops" /etc/group'
Password:
hotels:x:3001:fullerton
shops:x:3002:raffles
```