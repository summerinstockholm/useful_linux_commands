# useful_linux_commands
Полезные команды Линукс на все случаи жизни + пояснения к ним и другая полезная информация.<br>
**Информация о системах используемых в качестве выполнения комманд:**<br>
**Ubuntu:**<br>
*catware@ubuntu:~$ hostnamectl<br>
   Static hostname: ubuntu<br>
         Icon name: computer-vm<br>
           Chassis: vm<br>
        Machine ID: 3d4a108fde8e4d9c80561ddfd585aaa7<br>
           Boot ID: 07716a6f4d4947e1af9b3f9db16f1d57<br>
    Virtualization: vmware<br>
  Operating System: Ubuntu 20.04.3 LTS<br>
            Kernel: Linux 5.11.0-41-generic<br>
      Architecture: x86-64*<br>
## ls
Вывод содержимого каталога.<br>
**ls -l** - выводит не только список имен объектов, но и их права доступа к файлам, имя владельца, группу, размер файла и метку времени.<br>
При добавлении имени каталога, например **/var**, отображается содержимое этого каталога<br>
*catware@ubuntu:~$ ls -l /var<br>
total 48<br>
drwxr-xr-x  2 root root     4096 Dec 28 15:12 backups<br>
drwxr-xr-x 17 root root     4096 Jan  7  2021 cache<br>
drwxrwsrwt  2 root whoopsie 4096 Jul 31  2020 crash<br>
drwxr-xr-x 71 root root     4096 Dec  2 09:07 lib<br>
drwxrwsr-x  2 root staff    4096 Apr 15  2020 local<br>
lrwxrwxrwx  1 root root        9 Dec 30  2020 lock -> /run/lock<br>
drwxrwxr-x 14 root syslog   4096 Dec 28 15:07 log<br>
drwxrwsr-x  2 root mail     4096 Jul 31  2020 mail<br>
drwxrwsrwt  2 root whoopsie 4096 Jul 31  2020 metrics<br>
drwxr-xr-x  2 root root     4096 Jul 31  2020 opt<br>
lrwxrwxrwx  1 root root        4 Dec 30  2020 run -> /run<br>
drwxr-xr-x 12 root root     4096 Dec  2 08:49 snap<br>
drwxr-xr-x  7 root root     4096 Jul 31  2020 spool<br>
drwxrwxrwt  9 root root     4096 Dec 28 15:09 tmp*<br>
Если добавить к команде **ls** аргумент **h**, будут отображены ещё и размеры файлов в удобочитаемом виде.<br>
*catware@ubuntu:~$ ls -lh /var/log<br>
total 3.2M<br>
-rw-r--r--  1 root              root               0 Dec 28 15:07 alternatives.log<br>
-rw-r--r--  1 root              root            7.9K Dec  2 09:08 alternatives.log.1<br>
-rw-r--r--  1 root              root             247 Sep 18 22:56 alternatives.log.2.gz<br>
-rw-r--r--  1 root              root             270 Jun 28  2021 alternatives.log.3.gz<br>
-rw-r--r--  1 root              root             330 Apr  8  2021 alternatives.log.4.gz<br>
-rw-r--r--  1 root              root             127 Jan  7  2021 alternatives.log.5.gz<br>
-rw-r--r--  1 root              root            3.7K Dec 31  2020 alternatives.log.6.gz<br>
drwxr-xr-x  2 root              root            4.0K Dec 28 15:07 apt<br>
-rw-r-----  1 syslog            adm             2.7K Dec 28 15:30 auth.log<br>
-rw-r-----  1 syslog            adm             9.2K Dec 28 15:07 auth.log.1<br>
-rw-r-----  1 syslog            adm             1.2K Dec  2 08:47 auth.log.2.gz<br>
-rw-r-----  1 syslog            adm             1.5K Nov  4 22:52 auth.log.3.gz<br>
-rw-r-----  1 syslog            adm             1.6K Sep 18 22:31 auth.log.4.gz<br>
-rw-r--r--  1 root              root            102K Jul 31  2020 bootstrap.log<br>
-rw-rw----  1 root              utmp               0 Dec  2 08:47 btmp<br>
-rw-rw----  1 root              utmp               0 Nov  4 22:52 btmp.1<br>
drwxr-xr-x  2 root              root            4.0K Dec 28 15:07 cups<br>
drwxr-xr-x  2 root              root            4.0K Jul 21  2020 dist-upgrade<br>
-rw-r--r--  1 root              adm             140K Dec 28 15:07 dmesg<br>
-rw-r--r--  1 root              adm             141K Dec  2 09:10 dmesg.0<br>
-rw-r--r--  1 root              adm              25K Dec  2 08:47 dmesg.1.gz<br>
-rw-r--r--  1 root              adm              25K Nov  4 22:52 dmesg.2.gz<br>
-rw-r--r--  1 root              adm              26K Sep 18 22:58 dmesg.3.gz<br>
-rw-r--r--  1 root              adm              24K Sep 18 22:31 dmesg.4.gz<br>
-rw-r--r--  1 root              root               0 Dec 28 15:07 dpkg.log<br>
-rw-r--r--  1 root              root            119K Dec  2 09:08 dpkg.log.1<br>
-rw-r--r--  1 root              root             11K Sep 18 23:00 dpkg.log.2.gz<br>
-rw-r--r--  1 root              root             15K Jun 28  2021 dpkg.log.3.gz<br>
-rw-r--r--  1 root              root             14K Apr  8  2021 dpkg.log.4.gz<br>
-rw-r--r--  1 root              root            3.0K Jan  7  2021 dpkg.log.5.gz<br>
-rw-r--r--  1 root              root            118K Dec 31  2020 dpkg.log.6.gz<br>
-rw-r--r--  1 root              root             32K Dec 30  2020 faillog<br>
-rw-r--r--  1 root              root             12K Dec  2 09:08 fontconfig.log<br>
drwx--x--x  2 root              gdm             4.0K Oct  7  2019 gdm3<br>
-rw-r--r--  1 root              root            1.3K Dec 28 15:07 gpu-manager.log<br>
drwxr-xr-x  3 root              root            4.0K Jul 31  2020 hp<br>
drwxrwxr-x  2 root              root            4.0K Dec 30  2020 installer<br>
drwxr-sr-x+ 3 root              systemd-journal 4.0K Dec 30  2020 journal<br>
-rw-r-----  1 syslog            adm             5.3K Dec 28 15:08 kern.log<br>
-rw-r-----  1 syslog            adm             366K Dec 28 15:07 kern.log.1<br>
-rw-r-----  1 syslog            adm              27K Dec  2 08:47 kern.log.2.gz<br>
-rw-r-----  1 syslog            adm              53K Nov  4 22:52 kern.log.3.gz<br>
-rw-r-----  1 syslog            adm              50K Sep 18 22:31 kern.log.4.gz<br>
-rw-rw-r--  1 root              utmp            286K Dec 30  2020 lastlog<br>
drwxr-xr-x  2 root              root            4.0K Sep  5  2019 openvpn<br>
drwx------  2 root              root            4.0K Jul 31  2020 private<br>
drwx------  2 speech-dispatcher root            4.0K Jan 19  2020 speech-dispatcher<br>
-rw-r-----  1 syslog            adm             152K Dec 28 15:30 syslog<br>
-rw-r-----  1 syslog            adm             844K Dec 28 15:07 syslog.1<br>
-rw-r-----  1 syslog            adm              55K Dec  2 08:47 syslog.2.gz<br>
-rw-r-----  1 syslog            adm             113K Nov  4 22:52 syslog.3.gz*<br>
Добавление прописной буквы **R** в качестве аргумента команды **ls** приводит к отображению подкаталогов с файлами и вложенными подкаталогами, независимо от глубины вложения.
## pwd
Отображает текущий рабочий каталог.<br>
*catware@ubuntu:~$ pwd<br>
/home/catware*<br>
## cd
Смена каталога.<br>
*catware@ubuntu:~$ pwd<br>
/home/catware<br>
catware@ubuntu:~$ cd /<br>
catware@ubuntu:/$ pwd<br>
/<br>
catware@ubuntu:/$ cd /home/catware<br>
catware@ubuntu:~$ pwd<br>
/home/catware<br>
catware@ubuntu:~$*<br> 
**cd** без каких-либо аргументов вернет вас в домашний каталог вошедшего в систему пользователя.
## cat
Вывод содержимого файла целиком. Его можно прочитать, но не редактировать. Это приемлимо для небольших файлов, таких как файл fstab в папке /etc.<br>
*catware@ubuntu:~$ cat /etc/fstab<br>
\# /etc/fstab: static file system information.<br>
\#<br>
\# Use 'blkid' to print the universally unique identifier for a<br>
\# device; this may be used with UUID= as a more robust way to name devices<br>
\# that works even if disks are added and removed. See fstab(5).<br>
\#<br>
\# <file system> <mount point>   <type>  <options>       <dump>  <pass><br>
\# / was on /dev/sda5 during installation<br>
UUID=3dbaa993-4728-4891-a08a-2d93e73df9a7 /               ext4    errors=remount-ro 0       1<br>
\# /boot/efi was on /dev/sda1 during installation<br>
UUID=C195-F970  /boot/efi       vfat    umask=0077      0       1
/swapfile                                 none            swap    sw              0       0<br>
/dev/fd0        /media/floppy0  auto    rw,user,noauto,exec,utf8 0       0*<br>
