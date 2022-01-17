# useful_linux_commands
Полезные команды Линукс на все случаи жизни + пояснения к ним и другая полезная информация.<br>
**Информация о системах используемых в которой исполняются команды:**<br>
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
## Структура каталогов
**/** - корневой каталог<br>
**/boot** - содержит ядро Linux, образ начального RAM-диска (с драйверами, необходимыми на этапе загрузки) и сам загрузчик. Интересные файлы в **/boot**:<br>
**/boot/grub/grub.conf или menu.lst** - используются для настройки загрузчика<br>
**/boot/vmlinuz (или с похожем имененем)** - ядро Linux<br>
**/dev** - специальный каталог, содержащий узлы устройств. Здесь ядро хранит список всех известных ему устройств<br>
**/etc** - содержит все системные конфигурационные файлы. Здесь же хранится коллекция сценариев командной оболочки, запускающих системные службы во время загрузки.<br> Практически вcе файлы в этом каталоге содержат обычный читаемый текст. Особенный интерес представляют следующие файлы:<br>
**/etc/crontab** - файл, определяющий время запуска автоматизированных заданий<br>
**/etc/fstab** - таблица устройств хранения и соответсвующих им точек монтирования<br>
**/etc/passwd** - список всех учетных записей пользователей<br>
**/var** - часто меняющееся содержимое (например, различные базы данных, буферные файлы, почта пользователей и т.д.)<br>
**/var/log** - каталог содержит файлы журналов с записями о различных действиях, выполнявшихся в системе (логи)<br>
**/home** - файлы учетной записи пользователя<br>
**/lost+found** - каждый раздел или устройство, отформатированные с использованием файловой системы Linux, такой как ext3, будут иметь этот каталог. Он используется на<br> случай частичного восстановления повреждений в файловой системе. Если с системой ничего страшного не происходило - каталог будет пустым<br>
**/sbin** - каталог содержит системные бинарные (двоичные) файлы<br>
**/bin** - пользовательские бинарные файлы, необходимые для загрузки и функционирования системы<br>
**/lib** - общие библиотеки<br>
**/usr** - в каталоге хранятся все программы и файлы поддержки, используемые обычными пользователями<br>
**/usr/bin** - каталог содержит выполняемые программы, установленные дистрибутивом Linux<br>
**/usr/lib** - содержит разделяемые библиотеки для программ в /usr/bin<br>
**/usr/local** - данное дерево каталогов используется для установки тех программ, которые не входят в состав дистрибутива, но должны быть доступны всем пользователям<br>
в системе. Программы, собираемые из исходных текстов обычно устанавливаются в **/usr/local/bin**. В новейших дистрибутивах это дерево каталогов присутствует, но остается<br>
пустым, пока системный администратор не добавит туда что-нибудь<br>
**/usr/sbin** - содержит дополнительные программы для администрирования<br>
**/usr/share** - содержит все разделяемые данные, используемые программами в **/usr/sbin**, в том числе конфигурационные файлы с настройками по умолчанию, ярлыки, фоновые<br> изображения для рабочего стола, звуковые файлы и т.д.<br>
**/usr/share/doc** - большинство пакетов, установленных в системе, содержат документацию. Вся эта документация, организованная по пакетам, хранится в<br> 
каталоге **/usr/share/doc**<br>
**/media** - в современных системах Linux каталог /media будет содержать точки монтирования съемных носителей (USB, DVD-ROM и т.д.)<br>
**/mnt** - в старых системах Linux этот каталог содержал точки монтирования съемных носителей, монтируемых вручную<br>
**/proc** - специальный каталог. Не является фактической файловой системой, в том смысле, что файлы в этом каталоге не хранятся на жестком диске. Это виртуальная файловая <br>
система, поддерживаемая ядром Linux. Файлы в ней являются "глазками", через которые можно заглянуть в ядро. Эти файлы доступны для чтения и помогают "увидеть" компьютер<br>
глазами ядра<br>
**/root** - домашний каталог пользователя root<br>
**/tmp** - временное хранилище для временных файлов. В некоторых дистрибутивах каталог принудительно очищается после каждой перезагрузки системы<br>
## Групповые символы
Групповые символы позволяют выбирать имена файлов по шаблону.<br>
**\*** - любая последовательность символов<br>
**?** - любой один символ<br>
**\[символ\]** - любой один символ из указанного множества символов<br>
**\[!символ\]** - любой один символ, не принадлежащий указанному множеству символов<br>
**\[\[:класс:\]\]** - любой один символ, принадлежащий указанному классу<br>
**Наиболее часто используемые классы символов:**<br>
**\[:alnum:\]** - любой алфавитно-цифровой символ<br>
**\[:alpha:\]** - любой алфавитный символ<br>
**\[:digit:\]** - любой цифровой символ<br>
**\[:lower:\]** - любая буква в нижнем регистре<br>
**\[:upper:\]** - любая буква в верхнем регистре<br>
**Некоторые примеры шаблонов и их соответствия:**<br>
**\*** - все имена файлов<br>
**g\*** - все имена файлов, начинающиеся с символа "g"<br>
**b\*.txt** - все имена файлов, начинающиеся с символа "b", за которым следует любое число других символов, и заканчивающиеся на ".txt"<br>
**Data??** - все имена файлов, начинающиеся с символов "Data", за которым следуют ровно три любых символа<br>
**\[abc]\*** - все имена файлов, начинающиеся с символа "a", "b" или "c"<br>
**BACKUP.\[0-9\]\[0-9\]\[0-9\]** - все имена файлов, начинающиеся с символов "BACKUP.", за которыми следуют ровно три цифровых символа<br>
**\[\[:upper:\]\]\*** - все имена файлов, начинающиеся с буквы в верхнем регистре<br>
**\[!\[:digit:\]\]\*** - все имена файлов, не начинающиеся с цифры<br>
**\*\[\[:lower:\]123\]** - все имена файлов, заканчивающиеся буквой в нижнем регистре или цифрой "1", "2" или "3"<br>
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
Добавление прописной буквы **R** в качестве аргумента команды **ls** приводит к отображению подкаталогов с файлами и вложенными подкаталогами, независимо от глубины вложения<br>
**Наиболее популярные параметры команды ls:**<br>
**-a** - список всех файлов, даже с именами, начинающимися с точки, которые обычное не выводятся (скрытые файлы)<br>
**-A** - действует подобно параметру **-a**, но не выводит каталоги **.** (текущий рабочий каталог) и **..** (родительский каталог)<br>
**-d** - обычно в присутствии этого параметра команда **ls** выводит информацию о самом каталоге, а не его содержимое. Используйте этот параметр в сочетании с параметром<br>
**-l**, чтобы получить дополнительную информацию о каталоге, а не о его содержимом<br>
**-F** - добавляет в конец каждого имени символ-индикатор (например, прямой слеш, если это имя каталога)<br>
**-h**- при использовании длинного формата вывода отображает размеры файлов не в байтах, а в велечинах с единицами измерения<br>
**-l** - выводит результаты с использованием длинного формата<br>
**-r** - выводит результаты в обратном порядке. Обычно команда **ls** выводит результаты в алфавитном порядке<br>
**-S** - сортировать результаты по размеру<br>
**-t** - сортировать результаты по времени последнего изменения<br>
**Поля длинного формата вывода команды ls:**<br>
**drwxr-xr-x** - права доступа к файлу. Первый символ указывает тип файла. Например, символом дефиса обозначаются обычные файлы, а символов **d** - каталоги. Следующие три<br>
символа сообщают о правах доступа для владельца файла, следующие три - для членов группы, которой принадлежит файл, и последние три - для всех остальных<br>
**1** - число жестких ссылок на файл<br>
**root** - имя пользователя, владеющего файлом<br>
**root** - имя группы, владеющей файлом<br>
**4096** - размер файла в байтах<br>
**Dec 28 15:09** - дата и время последнего изменения<br>
**tmp\*** - имя файла<br>
## file
Выводит краткое описание содержимого папки/файла:<br>
*catware@ubuntu:~$ file newdir<br>
newdir: directory*<br>
## pwd
Отображает текущий рабочий каталог.<br>
*catware@ubuntu:~$ pwd<br>
/home/catware*<br>
## cd
Смена каталога.<br>
*catware@ubuntu:~$ pwd<br>
/home/catware*<br>
*catware@ubuntu:~$ cd /*<br>
*catware@ubuntu:/$ pwd*<br>
*/*<br>
*catware@ubuntu:/$ cd /home/catware*<br>
*catware@ubuntu:~$ pwd*<br>
*/home/catware*<br>
*catware@ubuntu:~$*<br> 
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
## less
Вывод содержимого файла по страницам.<br>
*catware@ubuntu:~$ less /etc/services<br>
\# Network services, Internet style<br>
\#<br>
\# Note that it is presently the policy of IANA to assign a single well-known<br>
\# port number for both TCP and UDP; hence, officially ports have two entries<br>
\# even if the protocol doesn't support UDP operations.<br>
\#<br>
\# Updated from https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml .<br>
\#<br>
\# New ports will be added on request if they have been officially assigned<br>
\# by IANA and used in the real-world or are needed by a debian package.<br>
\# If you need a huge list of used numbers please install the nmap package.*<br>
## touch
Создание пустого файла. Команда **touch** используется для изменения временной метки файла. С помощью этой команды вы можете изменять время доступа к файлу и время его<br> изменения. Если указанный файл не существует, touch создаст файл нулевого размера с указанным именем.<br>
*catware@ubuntu:\~$ touch myfile<br>
catware@ubuntu:\~$ ls<br>
Desktop    Downloads  myfile    Public  Templates<br>
Documents  Music      Pictures  snap    Videos*<br>
## stat
Вывод на экран информации о файле.<br>
*catware@ubuntu:~$ stat myfile<br>
  File: myfile<br>
  Size: 0         	Blocks: 0          IO Block: 4096   regular empty file<br>
Device: 805h/2053d	Inode: 524386      Links: 1<br>
Access: (0664/-rw-rw-r--)  Uid: ( 1000/ catware)   Gid: ( 1000/ catware)<br>
Access: 2021-12-29 11:20:27.400129311 +0300<br>
Modify: 2021-12-29 11:20:16.008094495 +0300<br>
Change: 2021-12-29 11:20:16.008094495 +0300<br>
 Birth: -*<br>
## mkdir
Создание каталога.<br>
*catware@ubuntu:\~$ mkdir myplace*<br>
## rmdir
Удаление пустого каталога.<br>
*catware@ubuntu:\~$ mkdir myplace<br>
catware@ubuntu:\~$ cd myplace<br>
catware@ubuntu:\~/myplace$ touch newfile<br>
catware@ubuntu:\~/myplace$ ls<br>
newfile<br>
catware@ubuntu:\~/myplace$ cd ..<br>
catware@ubuntu:\~$ rmdir myplace<br>
rmdir: failed to remove 'myplace': Directory not empty*<br>
По умолчанию команда rmdir выдает ошибку, если вы попытаетесь удалить непустой каталог. Однако, если вы хотите, вы можете отменить вывод ошибки, используя<br> 
опцию --ignore-fail-on-non-empty.<br>
## rm
Удаляет файлы и целые деревья каталогов.<br>
*catware@ubuntu:\~$ rm -r myplace*<br>
## cp
Команда позволяет копировать файлы и директории.<br>
*catware@ubuntu:\~$ touch file1 file2 file3<br>
catware@ubuntu:\~$ mkdir newdir<br>
catware@ubuntu:~$ cp file1 newdir*<br>
**Некоторые часто используемые параметры для команды сp:**<br>
**-a** - скопировать файлы и каталоги со всеми атрибутами, включая идентификаторы владельцев и права доступа. Без этого параметра копии обычно получают значения<br>
атрибутов по умолчанию, определенных для пользователя, выполняющего копирование<br>
**-i** - запрашивать у пользователя подтверждение перед перезаписью существующего файла.**Если этот параметр отсутствует, команда *cp* просто перезапишет<br>
существующие файлы (без предупреждения).**<br>
**-r** - рекурсивно копировать каталоги и их содержимое. Это обязательный параметр (или параметр -а) при копировании каталогов<br>
**-u** - при копировании файлов из одного каталога в другой копировать только файлы, отсутствующие в каталоге назначения или более новые. Этот параметр удобно<br>
использовать при копировании большого числа файлов, так как он позволяет пропустить файлы, которые не требуются копировать<br>
**-v** - выводить информационные сообщения в процессе копирования<br>
**Дополнительные примеры использования команды *cp*:**<br>
**cp file1 file2** - скопирует file1 в file2. Если file2 существует, он будет затерт новым файлом file1. Если file2 отсутствует, он будет создан<br>
**cp -i file1 file2** - то же что и выше, но если file2 существует, у пользователя будет запрошено подтверждение перед перезаписью файла<br>
**cp file1 file2 dir1** - скопирует file1 и file2 в каталог dir1. Каталог dir1 должен существовать<br>
**cp dir1//* dir2** - с использованием группового символа. Скопирует все файлы из каталога dir1 в каталог dir2. Каталог dir2 должен существовать<br>
**cp -r dir1 dir2** - скопирует содержимое каталога dir1 в каталог dir2. Если каталог dir2 не существует, он будет создан и заполнен содержимым каталога dir1<br>
Если каталог dir2 существует, тогда в него будет скопирован сам каталог dir1 (вместе с содержимым)<br> 
## mv
Команда **mv** перемещает объект из одного места в другое.<br>
*catware@ubuntu:~$ mv file2 newdir*<br>
## Как узнать сколько всего места на одном из жестких дисков?
*catware@ubuntu:~$ cat /sys/block/sda/size<br>
41943040*<br>
## Как узнать как обозначены диски в системе?<br>
Linux организует подключенное хранилище как блочное устройство<br>
*catware@ubuntu:~$ cd /sys/block/<br>
catware@ubuntu:/sys/block$ ls<br>
loop0  loop10  loop12  loop14  loop16  loop18  loop3  loop5  loop7  loop9  sr0<br>
loop1  loop11  loop13  loop15  loop17  loop2   loop4  loop6  loop8  sda*<br>
## Как посмотреть разделы?
*catware@ubuntu:/sys/block$ cd sda<br>
catware@ubuntu:/sys/block/sda$ ls<br>
alignment_offset  discard_alignment  hidden     power      sda1    stat<br>
bdi               events             holders    queue      sda2    subsystem<br>
capability        events_async       inflight   range      sda5    trace<br>
dev               events_poll_msecs  integrity  removable  size    uevent<br>
device            ext_range          mq         ro         slaves*<br>
## man
Команда man позволяет получить доступ к общей базе справки по команде, функции или программе. Обычно для просмотра справки программе надо передать название команды или другого объекта в системе.<br>
*catware@ubuntu:~$ man man*<br>
## journalctl
Выведет все записи из всех журналов, включая ошибки и предупреждения, начиная с того момента, когда система начала загружаться. Старые записи событий будут наверху, более новые — внизу, вы можете использовать PageUp и PageDown чтобы перемещаться по списку, Enter — чтобы пролистывать журнал построчно и Q — чтобы выйти.<br>
*catware@ubuntu:\~$ journalctl<br>
-- Logs begin at Wed 2020-12-30 22:05:18 MSK, end at Wed 2022-01-12 16:01:20 MSK. --<br>
Dec 30 22:05:18 ubuntu kernel: Linux version 5.4.0-58-generic (buildd@lcy01-amd64-004) (gcc version 9.3.0 (Ubuntu 9.3.0-17ubuntu1~20.04)) #64-Ubuntu SMP We><br>
Dec 30 22:05:18 ubuntu kernel: Command line: BOOT_IMAGE=/boot/vmlinuz-5.4.0-58-generic root=UUID=3dbaa993-4728-4891-a08a-2d93e73df9a7 ro find_preseed=/pres><br>
Dec 30 22:05:18 ubuntu kernel: KERNEL supported cpus:<br>
Dec 30 22:05:18 ubuntu kernel:   Intel GenuineIntel<br>
Dec 30 22:05:18 ubuntu kernel:   AMD AuthenticAMD<br>
Dec 30 22:05:18 ubuntu kernel:   Hygon HygonGenuine<br>
Dec 30 22:05:18 ubuntu kernel:   Centaur CentaurHauls<br>
Dec 30 22:05:18 ubuntu kernel:   zhaoxin   Shanghai<br>
Dec 30 22:05:18 ubuntu kernel: Disabled fast string operations<br>
Dec 30 22:05:18 ubuntu kernel: x86/fpu: Supporting XSAVE feature 0x001: 'x87 floating point registers'<br>
Dec 30 22:05:18 ubuntu kernel: x86/fpu: Supporting XSAVE feature 0x002: 'SSE registers'<br>
Dec 30 22:05:18 ubuntu kernel: x86/fpu: Supporting XSAVE feature 0x004: 'AVX registers'<br>
Dec 30 22:05:18 ubuntu kernel: x86/fpu: xstate_offset[2]:  576, xstate_sizes[2]:  256<br>
Dec 30 22:05:18 ubuntu kernel: x86/fpu: Enabled xstate features 0x7, context size is 832 bytes, using 'standard' format.<br>
Dec 30 22:05:18 ubuntu kernel: BIOS-provided physical RAM map:<br>
Dec 30 22:05:18 ubuntu kernel: BIOS-e820: [mem 0x0000000000000000-0x000000000009e7ff] usable<br>
Dec 30 22:05:18 ubuntu kernel: BIOS-e820: [mem 0x000000000009e800-0x000000000009ffff] reserved<br>
Dec 30 22:05:18 ubuntu kernel: BIOS-e820: [mem 0x00000000000dc000-0x00000000000fffff] reserved<br>
Dec 30 22:05:18 ubuntu kernel: BIOS-e820: [mem 0x0000000000100000-0x00000000bfecffff] usable<br>
Dec 30 22:05:18 ubuntu kernel: BIOS-e820: [mem 0x00000000bfed0000-0x00000000bfefefff] ACPI data<br>
Dec 30 22:05:18 ubuntu kernel: BIOS-e820: [mem 0x00000000bfeff000-0x00000000bfefffff] ACPI NVS<br>
Dec 30 22:05:18 ubuntu kernel: BIOS-e820: [mem 0x00000000bff00000-0x00000000bfffffff] usable<br>
Dec 30 22:05:18 ubuntu kernel: BIOS-e820: [mem 0x00000000f0000000-0x00000000f7ffffff] reserved<br>
Dec 30 22:05:18 ubuntu kernel: BIOS-e820: [mem 0x00000000fec00000-0x00000000fec0ffff] reserved<br>
Dec 30 22:05:18 ubuntu kernel: BIOS-e820: [mem 0x00000000fee00000-0x00000000fee00fff] reserved<br>
Dec 30 22:05:18 ubuntu kernel: BIOS-e820: [mem 0x00000000fffe0000-0x00000000ffffffff] reserved<br>
Dec 30 22:05:18 ubuntu kernel: BIOS-e820: [mem 0x0000000100000000-0x000000013fffffff] usable<br>
Dec 30 22:05:18 ubuntu kernel: NX (Execute Disable) protection: active<br>
Dec 30 22:05:18 ubuntu kernel: SMBIOS 2.7 present.<br>
Dec 30 22:05:18 ubuntu kernel: DMI: VMware, Inc. VMware Virtual Platform/440BX Desktop Reference Platform, BIOS 6.00 02/27/2020<br>
Dec 30 22:05:18 ubuntu kernel: vmware: hypercall mode: 0x00<br>
Dec 30 22:05:18 ubuntu kernel: Hypervisor detected: VMware<br>
Dec 30 22:05:18 ubuntu kernel: vmware: TSC freq read from hypervisor : 3510.309 MHz<br>
Dec 30 22:05:18 ubuntu kernel: vmware: Host bus clock speed read from hypervisor : 66000000 Hz<br>
Dec 30 22:05:18 ubuntu kernel: vmware: using sched offset of 6302858877 ns<br>
Dec 30 22:05:18 ubuntu kernel: tsc: Detected 3510.309 MHz processor<br>
Dec 30 22:05:18 ubuntu kernel: e820: update [mem 0x00000000-0x00000fff] usable ==> reserved<br>
Dec 30 22:05:18 ubuntu kernel: e820: remove [mem 0x000a0000-0x000fffff] usable<br>
Dec 30 22:05:18 ubuntu kernel: last_pfn = 0x140000 max_arch_pfn = 0x400000000<br>
Dec 30 22:05:18 ubuntu kernel: MTRR default type: uncachable<br>
Dec 30 22:05:18 ubuntu kernel: MTRR fixed ranges enabled:<br>
Dec 30 22:05:18 ubuntu kernel:   00000-9FFFF write-back<br>
Dec 30 22:05:18 ubuntu kernel:   A0000-BFFFF uncachable<br>
Dec 30 22:05:18 ubuntu kernel:   C0000-CBFFF write-protect<br>
Dec 30 22:05:18 ubuntu kernel:   CC000-EFFFF uncachable<br>
Dec 30 22:05:18 ubuntu kernel:   F0000-FFFFF write-protect<br>
Dec 30 22:05:18 ubuntu kernel: MTRR variable ranges enabled:<br>
Dec 30 22:05:18 ubuntu kernel:   0 base 00000000000 mask 7E000000000 write-back<br>
Dec 30 22:05:18 ubuntu kernel:   1 base 000C0000000 mask 7FFC0000000 uncachable<br>
Dec 30 22:05:18 ubuntu kernel:   2 disabled<br>
Dec 30 22:05:18 ubuntu kernel:   3 disabled*<br>
Более подробно почитать можно тут: https://habr.com/ru/company/ruvds/blog/533918/
## date
Выводит текущие время и дату.<br>
*catware@ubuntu:~$ date<br>
Mon 17 Jan 2022 04:32:00 PM MSK*<br>
## cal
По умолчанию выводит календарь текущего месяца<br>
*catware@ubuntu:~$ cal<br>
    January 2022<br>      
Su Mo Tu We Th Fr Sa<br>  
                   1<br>  
 2  3  4  5  6  7  8<br>  
 9 10 11 12 13 14 15<br>  
16 17 18 19 20 21 22<br>  
23 24 25 26 27 28 29<br>  
30 31*<br>
## df
Выводит объем свободного пространства на дисках.<br>
*catware@ubuntu:~$ df<br>
Filesystem     1K-blocks     Used Available Use% Mounted on<br>
udev             4023664        0   4023664   0% /dev<br>
tmpfs             811284     1864    809420   1% /run<br>
/dev/sda5       19992176 10656532   8297052  57% /<br>
tmpfs            4056400        0   4056400   0% /dev/shm<br>
tmpfs               5120        4      5116   1% /run/lock<br>
tmpfs            4056400        0   4056400   0% /sys/fs/cgroup<br>
/dev/loop0           128      128         0 100% /snap/bare/5<br>
/dev/loop1        151424   151424         0 100% /snap/chromium/1854<br>
/dev/loop2        151168   151168         0 100% /snap/chromium/1864<br>
/dev/loop3         56832    56832         0 100% /snap/core18/2253<br>
/dev/loop4         56960    56960         0 100% /snap/core18/2284<br>
/dev/loop5         63360    63360         0 100% /snap/core20/1242<br>
/dev/loop6         63488    63488         0 100% /snap/core20/1270<br>
/dev/loop8        166784   166784         0 100% /snap/gnome-3-28-1804/145<br>
/dev/loop7        168832   168832         0 100% /snap/gnome-3-28-1804/161<br>
/dev/loop9        224256   224256         0 100% /snap/gnome-3-34-1804/72<br>
/dev/loop10       224256   224256         0 100% /snap/gnome-3-34-1804/77<br>
/dev/loop11       253952   253952         0 100% /snap/gnome-3-38-2004/87<br>
/dev/loop12        66688    66688         0 100% /snap/gtk-common-themes/1515<br>
/dev/loop13        66816    66816         0 100% /snap/gtk-common-themes/1519<br>
/dev/loop14        52224    52224         0 100% /snap/snap-store/547<br>
/dev/loop15        55552    55552         0 100% /snap/snap-store/558<br>
/dev/loop16        43264    43264         0 100% /snap/snapd/14066<br>
/dev/loop17        44416    44416         0 100% /snap/snapd/14295<br>
/dev/sda1         523248        4    523244   1% /boot/efi<br>
tmpfs             811280       20    811260   1% /run/user/1000*<br>
## free
Выводит объем свободного пространства в оперативной памяти.<br>
*catware@ubuntu:~$ free<br>
              total        used        free      shared  buff/cache   available<br>
Mem:        8112804      887464     6491688        2016      733652     6971692<br>
Swap:        945416           0      945416*<br>
