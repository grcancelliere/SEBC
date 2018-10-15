1. Check `vm.swappiness` on all your nodes
    * Set the value to `1` if necessary

[grcancelliere@sebcm ~]$ `sudo sysctl vm.swappiness`
vm.swappiness = 1

	
2. Show the mount attributes of all volumes

[grcancelliere@sebcm ~]$ `mount -v`
sysfs on /sys type sysfs (rw,nosuid,nodev,noexec,relatime)
proc on /proc type proc (rw,nosuid,nodev,noexec,relatime)
devtmpfs on /dev type devtmpfs (rw,nosuid,size=7166396k,nr_inodes=1791599,mode=755)
securityfs on /sys/kernel/security type securityfs (rw,nosuid,nodev,noexec,relatime)
tmpfs on /dev/shm type tmpfs (rw,nosuid,nodev)
devpts on /dev/pts type devpts (rw,nosuid,noexec,relatime,gid=5,mode=620,ptmxmode=000)
tmpfs on /run type tmpfs (rw,nosuid,nodev,mode=755)
tmpfs on /sys/fs/cgroup type tmpfs (ro,nosuid,nodev,noexec,mode=755)
cgroup on /sys/fs/cgroup/systemd type cgroup (rw,nosuid,nodev,noexec,relatime,xattr,release_agent=/usr/lib/systemd/systemd-cgroups-agent,name=systemd)
pstore on /sys/fs/pstore type pstore (rw,nosuid,nodev,noexec,relatime)
cgroup on /sys/fs/cgroup/blkio type cgroup (rw,nosuid,nodev,noexec,relatime,blkio)
cgroup on /sys/fs/cgroup/devices type cgroup (rw,nosuid,nodev,noexec,relatime,devices)
cgroup on /sys/fs/cgroup/hugetlb type cgroup (rw,nosuid,nodev,noexec,relatime,hugetlb)
cgroup on /sys/fs/cgroup/memory type cgroup (rw,nosuid,nodev,noexec,relatime,memory)
cgroup on /sys/fs/cgroup/cpu,cpuacct type cgroup (rw,nosuid,nodev,noexec,relatime,cpuacct,cpu)
cgroup on /sys/fs/cgroup/cpuset type cgroup (rw,nosuid,nodev,noexec,relatime,cpuset)
cgroup on /sys/fs/cgroup/freezer type cgroup (rw,nosuid,nodev,noexec,relatime,freezer)
cgroup on /sys/fs/cgroup/perf_event type cgroup (rw,nosuid,nodev,noexec,relatime,perf_event)
cgroup on /sys/fs/cgroup/net_cls type cgroup (rw,nosuid,nodev,noexec,relatime,net_cls)
configfs on /sys/kernel/config type configfs (rw,relatime)
/dev/sda2 on / type xfs (rw,relatime,attr2,inode64,noquota)
systemd-1 on /proc/sys/fs/binfmt_misc type autofs (rw,relatime,fd=26,pgrp=1,timeout=0,minproto=5,maxproto=5,direct)
mqueue on /dev/mqueue type mqueue (rw,relatime)
hugetlbfs on /dev/hugepages type hugetlbfs (rw,relatime)
debugfs on /sys/kernel/debug type debugfs (rw,relatime)
/dev/sda1 on /boot type ext4 (rw,relatime,discard,data=ordered)
`/dev/sdc1 on /data type ext4 (rw,noatime)`
/dev/sdb1 on /mnt/resource type ext4 (rw,noatime,discard,data=ordered)
tmpfs on /run/user/1000 type tmpfs (rw,nosuid,nodev,relatime,size=1435284k,mode=700,uid=1000,gid=1000)`


3. Show the reserve space of any non-root, `ext`-based volumes
    * XFS volumes do not maintain reserve space

Azure creates a temporary volume in `/mnt/resource`, so the only non-root ext-base volume is /dev/sdc1

[grcancelliere@sebcm ~]$ `sudo tune2fs -l /dev/sdc1 | grep 'Reserved block count'`
Reserved block count:     0


4. Disable transparent hugepage support

[grcancelliere@sebcm ~]$ `cat /sys/kernel/mm/transparent_hugepage/enabled`
always madvise [never]
[grcancelliere@sebcm ~]$ `cat /sys/kernel/mm/transparent_hugepage/defrag`
always madvise [never]

4. List your network interface configuration

[grcancelliere@sebcm ~]$ `ip link`
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN mode DEFAULT
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc mq state UP mode DEFAULT qlen 1000
    link/ether 00:0d:3a:2b:a7:16 brd ff:ff:ff:ff:ff:ff

5. List forward and reverse host lookups using `getent` or `nslookup`

[grcancelliere@sebcm ~]$ `for h in sebcm sebc1 sebc2 sebc3 sebc4; do nslookup $h; done`
Server:         168.63.129.16
Address:        168.63.129.16#53

Name:   sebcm.kihzz02kljie5etfnlthlzhkid.ax.internal.cloudapp.net
Address: 10.0.0.4

Server:         168.63.129.16
Address:        168.63.129.16#53

Name:   sebc1.kihzz02kljie5etfnlthlzhkid.ax.internal.cloudapp.net
Address: 10.0.0.5

Server:         168.63.129.16
Address:        168.63.129.16#53

Name:   sebc2.kihzz02kljie5etfnlthlzhkid.ax.internal.cloudapp.net
Address: 10.0.0.6

Server:         168.63.129.16
Address:        168.63.129.16#53

Name:   sebc3.kihzz02kljie5etfnlthlzhkid.ax.internal.cloudapp.net
Address: 10.0.0.7

Server:         168.63.129.16
Address:        168.63.129.16#53

Name:   sebc4.kihzz02kljie5etfnlthlzhkid.ax.internal.cloudapp.net
Address: 10.0.0.8

6. Show the <code>nscd</code> service is running

[grcancelliere@sebcm ~]$ `sudo systemctl status nscd`
● nscd.service - Name Service Cache Daemon
   Loaded: loaded (/usr/lib/systemd/system/nscd.service; enabled; vendor preset: disabled)
   Active: active (running) since Mon 2018-10-15 12:42:47 UTC; 28min ago
  Process: 793 ExecStart=/usr/sbin/nscd $NSCD_OPTIONS (code=exited, status=0/SUCCESS)
 Main PID: 803 (nscd)
   CGroup: /system.slice/nscd.service
           └─803 /usr/sbin/nscd

Oct 15 12:42:47 sebcm nscd[803]: 803 monitoring file '/etc/resolv.conf' (5)
Oct 15 12:42:47 sebcm nscd[803]: 803 monitoring directory '/etc' (2)
Oct 15 12:42:47 sebcm nscd[803]: 803 monitoring file '/etc/services' (6)
Oct 15 12:42:47 sebcm nscd[803]: 803 monitoring directory '/etc' (2)
Oct 15 12:42:47 sebcm nscd[803]: 803 disabled inotify-based monitoring for file '/etc/netgroup': No such file or directory
Oct 15 12:42:47 sebcm nscd[803]: 803 stat failed for file '/etc/netgroup'; will try again later: No such file or directory
Oct 15 12:42:46 sebcm systemd[1]: Starting Name Service Cache Daemon...
Oct 15 12:42:47 sebcm systemd[1]: Started Name Service Cache Daemon.
Oct 15 12:42:49 sebcm nscd[803]: 803 monitored file '/etc/resolv.conf' was moved into place, adding watch
Oct 15 12:43:06 sebcm nscd[803]: 803 checking for monitored file '/etc/netgroup': No such file or directory


7. Show the <code>ntpd</code> service is running<br>

[grcancelliere@sebcm ~]$ `sudo systemctl status ntpd`
● ntpd.service - Network Time Service
   Loaded: loaded (/usr/lib/systemd/system/ntpd.service; enabled; vendor preset: disabled)
   Active: active (running) since Mon 2018-10-15 12:42:47 UTC; 28min ago
  Process: 821 ExecStart=/usr/sbin/ntpd -u ntp:ntp $OPTIONS (code=exited, status=0/SUCCESS)
 Main PID: 831 (ntpd)
   CGroup: /system.slice/ntpd.service
           └─831 /usr/sbin/ntpd -u ntp:ntp -g

Oct 15 12:42:48 sebcm ntpd[831]: Listen normally on 2 lo 127.0.0.1 UDP 123
Oct 15 12:42:48 sebcm ntpd[831]: Listening on routing socket on fd #19 for interface updates
Oct 15 12:42:48 sebcm ntpd[831]: 0.0.0.0 c016 06 restart
Oct 15 12:42:48 sebcm ntpd[831]: 0.0.0.0 c012 02 freq_set kernel 0.000 PPM
Oct 15 12:42:48 sebcm ntpd[831]: 0.0.0.0 c011 01 freq_not_set
Oct 15 12:42:51 sebcm ntpd[831]: Listen normally on 3 eth0 10.0.0.4 UDP 123
Oct 15 12:42:51 sebcm ntpd[831]: new interface(s) found: waking up resolver
Oct 15 12:42:58 sebcm ntpd[831]: 0.0.0.0 c614 04 freq_mode
Oct 15 12:59:47 sebcm ntpd[831]: 0.0.0.0 0612 02 freq_set kernel 14.311 PPM
Oct 15 12:59:47 sebcm ntpd[831]: 0.0.0.0 0615 05 clock_sync
