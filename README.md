# useful_linux_commands
Полезные команды Линукс + пояснения к ним и другая полезная информация


## ls
Вывод содержимого каталога.<br>
**ls -l** - выводит не только список имен объектов, но и их права доступа к файлам, имя владельца, группу, размер файла и метку времени.<br>
При добавлении имени каталога, например **/var**, отображается содержимое этого каталога<br>
catware@ubuntu:~$ ls -l /var<br>
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
drwxrwxrwt  9 root root     4096 Dec 28 15:09 tmp<br>

