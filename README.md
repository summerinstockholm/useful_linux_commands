# useful_linux_commands
Полезные команды Линукс + пояснения к ним и другая полезная информация


## ls
Вывод содержимого каталога.
**ls -l** - выводит не только список имен объектов, но и их права доступа к файлам, имя владельца, группу, размер файла и метку времени.
При добавлении имени каталога, например **/var**, отображается содержимое этого каталога
catware@ubuntu:~$ ls -l /var
total 48
drwxr-xr-x  2 root root     4096 Dec 28 15:12 backups
drwxr-xr-x 17 root root     4096 Jan  7  2021 cache
drwxrwsrwt  2 root whoopsie 4096 Jul 31  2020 crash
drwxr-xr-x 71 root root     4096 Dec  2 09:07 lib
drwxrwsr-x  2 root staff    4096 Apr 15  2020 local
lrwxrwxrwx  1 root root        9 Dec 30  2020 lock -> /run/lock
drwxrwxr-x 14 root syslog   4096 Dec 28 15:07 log
drwxrwsr-x  2 root mail     4096 Jul 31  2020 mail
drwxrwsrwt  2 root whoopsie 4096 Jul 31  2020 metrics
drwxr-xr-x  2 root root     4096 Jul 31  2020 opt
lrwxrwxrwx  1 root root        4 Dec 30  2020 run -> /run
drwxr-xr-x 12 root root     4096 Dec  2 08:49 snap
drwxr-xr-x  7 root root     4096 Jul 31  2020 spool
drwxrwxrwt  9 root root     4096 Dec 28 15:09 tmp

