# Diretórios



Os principais diretórios do linux são listados com ``ls /``:

````bash

root@da204385e09c:/# ls
bin   dev  home  lib32  libx32  mnt  proc  run   srv  tmp  var
boot  etc  lib   lib64  media   opt  root  sbin  sys  usr	

````



``boot`` são os arquivos que contém todos os diretórios do kernel. O diretório ``dev``  é utilizado para dispositivos, como hds externos, pendrives e discos. O diretório ``etc`` contém arquivos de configurações do linux, ``bin`` arquivos binários do linux. ``tmp`` é um diretório temporário, quando o computador é desligado esses dados se perdem. O diretório ``var`` altera seu armazenamento de maneira descontrolada.

O diretório ``home`` é referente a todos os usuários do linux, o diretório ``usr`` contém arquivos do sistema operacional, usar para guardar arquivos de sistemas importantes.  

## Comando mount

Comando mount serve para ver todas as partições montadas no linux.  Exemplo de uso:

````
[root@65ccdc0d5356 etc]#  mount


 
overlay on / type overlay (rw,relatime,lowerdir=/var/lib/docker/overlay2/l/HLONJWKH4NPLDXW7G425BOIEUO:/var/lib/docker/overlay2/l/4AZ7ROF2WBS6AIAFKAHVPQBIUM,upperdir=/var/lib/docker/overlay2/33a5fde9ed30073c729d8c32cc24645fe9845317a5030211c048a7f578f665e7/diff,workdir=/var/lib/docker/overlay2/33a5fde9ed30073c729d8c32cc24645fe9845317a5030211c048a7f578f665e7/work)
proc on /proc type proc (rw,nosuid,nodev,noexec,relatime)
tmpfs on /dev type tmpfs (rw,nosuid,size=65536k,mode=755)
devpts on /dev/pts type devpts (rw,nosuid,noexec,relatime,gid=5,mode=620,ptmxmode=666)
sysfs on /sys type sysfs (ro,nosuid,nodev,noexec,relatime)
tmpfs on /sys/fs/cgroup type tmpfs (rw,nosuid,nodev,noexec,relatime,mode=755)
cpuset on /sys/fs/cgroup/cpuset type cgroup (ro,nosuid,nodev,noexec,relatime,cpuset)
cpu on /sys/fs/cgroup/cpu type cgroup (ro,nosuid,nodev,noexec,relatime,cpu)
cpuacct on /sys/fs/cgroup/cpuacct type cgroup (ro,nosuid,nodev,noexec,relatime,cpuacct)
blkio on /sys/fs/cgroup/blkio type cgroup (ro,nosuid,nodev,noexec,relatime,blkio)
memory on /sys/fs/cgroup/memory type cgroup (ro,nosuid,nodev,noexec,relatime,memory)
devices on /sys/fs/cgroup/devices type cgroup (ro,nosuid,nodev,noexec,relatime,devices)
freezer on /sys/fs/cgroup/freezer type cgroup (ro,nosuid,nodev,noexec,relatime,freezer)
net_cls on /sys/fs/cgroup/net_cls type cgroup (ro,nosuid,nodev,noexec,relatime,net_cls)
perf_event on /sys/fs/cgroup/perf_event type cgroup (ro,nosuid,nodev,noexec,relatime,perf_event)
net_prio on /sys/fs/cgroup/net_prio type cgroup (ro,nosuid,nodev,noexec,relatime,net_prio)
hugetlb on /sys/fs/cgroup/hugetlb type cgroup (ro,nosuid,nodev,noexec,relatime,hugetlb)
pids on /sys/fs/cgroup/pids type cgroup (ro,nosuid,nodev,noexec,relatime,pids)
rdma on /sys/fs/cgroup/rdma type cgroup (ro,nosuid,nodev,noexec,relatime,rdma)
cgroup on /sys/fs/cgroup/systemd type cgroup (ro,nosuid,nodev,noexec,relatime,name=systemd)
mqueue on /dev/mqueue type mqueue (rw,nosuid,nodev,noexec,relatime)
shm on /dev/shm type tmpfs (rw,nosuid,nodev,noexec,relatime,size=65536k)
/dev/sdc on /etc/resolv.conf type ext4 (rw,relatime,discard,errors=remount-ro,data=ordered)
/dev/sdc on /etc/hostname type ext4 (rw,relatime,discard,errors=remount-ro,data=ordered)
/dev/sdc on /etc/hosts type ext4 (rw,relatime,discard,errors=remount-ro,data=ordered)
devpts on /dev/console type devpts (rw,nosuid,noexec,relatime,gid=5,mode=620,ptmxmode=666)
proc on /proc/bus type proc (ro,nosuid,nodev,noexec,relatime)
proc on /proc/fs type proc (ro,nosuid,nodev,noexec,relatime)
proc on /proc/irq type proc (ro,nosuid,nodev,noexec,relatime)
proc on /proc/sys type proc (ro,nosuid,nodev,noexec,relatime)
tmpfs on /proc/acpi type tmpfs (ro,relatime)
tmpfs on /proc/kcore type tmpfs (rw,nosuid,size=65536k,mode=755)
tmpfs on /proc/keys type tmpfs (rw,nosuid,size=65536k,mode=755)
tmpfs on /proc/timer_list type tmpfs (rw,nosuid,size=65536k,mode=755)
tmpfs on /proc/sched_debug type tmpfs (rw,nosuid,size=65536k,mode=755)
tmpfs on /sys/firmware type tmpfs (ro,relatime)
````



O comando ``df -Th`` lista todos os diretórios montados do linux:

````bash
[root@65ccdc0d5356 etc]# df -Th
Filesystem     Type     Size  Used Avail Use% Mounted on
overlay        overlay  251G  4.6G  234G   2% /
tmpfs          tmpfs     64M     0   64M   0% /dev
tmpfs          tmpfs    7.8G     0  7.8G   0% /sys/fs/cgroup
shm            tmpfs     64M     0   64M   0% /dev/shm
/dev/sdc       ext4     251G  4.6G  234G   2% /etc/hosts
tmpfs          tmpfs    7.8G     0  7.8G   0% /proc/acpi
tmpfs          tmpfs    7.8G     0  7.8G   0% /sys/firmware
````

Os arquivos ou diretórios ocultos são visíveis através de ``ls -a`` e possuem um ponto na frente, por exemplo:

````

[root@65ccdc0d5356 /]# ls
anaconda-post.log  dev  home  lib64  mnt  proc  run   srv  tmp  var
bin                etc  lib   media  opt  root  sbin  sys  usr
[root@65ccdc0d5356 /]# ls -a
.   .dockerenv         bin  etc   lib    media  opt   root  sbin  sys  usr
..  anaconda-post.log  dev  home  lib64  mnt    proc  run   srv   tmp  var
````

O arquivo ``.dockerenv``é um arquivo oculto.

O comando ``du`` lista o tamanho dos arquivos no linux:

````bash

[root@65ccdc0d5356 /]# du -sh home/
20K     home/
````

