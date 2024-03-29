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
Вывод содержимого файла целиком. Его можно прочитать, но не редактировать. Это приемлимо для небольших файлов, таких как файл fstab в папке /etc. Эта команда читает<br>
содержимое одного или нескольких файлов и копирует его в стандартный вывод.<br>
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
**Некоторые параметры команды *mv*:**<br>
**-i** - запрашивать у пользователя подтверждение перед записью существующего файла. Если этот параметр отсутствует, команда *mv* просто перезапишет существующие файлы<br>
**-u** - при перемещении файлов из одного каталога в другой перемещать только файлы, отсутствующие в каталоге назначения или более новые<br>
**-v** - выводить информационные сообщения в процессе перемещения<br>
**Некоторые примеры использования команды *mv*:**<br>
**mv file1 file2** - переместит file1 в file2. Если file2 существует, он будет заменен на новый файл file1. Если file2 отсутствует, он будет создан. В любом случае файл<br> file1 исчезнет<br>
**mv -v file1 file2** - то же, что и выше, но если файл file2 существует, у пользователя будет запрошено подтверждение перед перезаписью файла<br>
**mv file1 file2 dir1** - переместит file1 и file2 в каталог dir1. Каталог dir1 должен существовать<br>
**mv dir1 dir2** - если каталог dir2 отсутствует, команда *mv* создаст его и переместит содержимое каталога dir1 в каталог dir2, после чего удалит dir1. Если каталог dir2<br>
существует, команда *mv* переместит каталог dir1 (вместе с его содержимым) в каталог dir2<br>
## ln
Создание ссылок. *ln* применяется для создания жесткой или символической ссылки.<br>
Можно использовать одним из двух способов:
**ln файл ссылка** - создает жесткую ссылку<br>
**Жесткая ссылка не может указывать на файл за пределами собственной файловой системы. Это означает, что ссылка не может указывать на файл, находящийся в другом разделе<br> диска.**<br>
**Жесткая ссылка не может указывать на каталог.**<br>
Жесткая ссылка не отличима от самого файла. В отличие от символических ссылок, при выводе списка с содержимым каталогов жесткие ссылки никак не выделяются.<br>
При удалении жесткой ссылки удаляется только сама ссылка, а файл остается на месте, пок не будут удалены все жесткие ссылки на файл.<br>
**Когда создается символическая ссылка, в действительности создается файл особого типа, содержащий текстовый указатель на файл или каталог.**<br>
**Файл, на который указывает символическая ссылка, и сама символическая ссылка почти неотличимы друг от друга. Например, если попытаться что-то записать в символическую<br>
ссылку, запись будет выполнена в файл, на который она указывает. Однако при удалении символической ссылки удаляется только *символическая ссылка, но не файл*. Если удалить<br>
файл, до того как будет удалена ссылка, ссылка останется на месте, но будет указывать в никуда. Такие ссылки называют *битыми*.**<br>
**Создание жестких ссылок**:<br>
*catware@ubuntu:\~$ mkdir playground<br>
catware@ubuntu:\~$ cd playground<br>
catware@ubuntu:\~/playground$ mkdir dir1 dir2<br>
catware@ubuntu:\~/playground$ cp /etc/passwd .<br>
catware@ubuntu:\~/playground$ mv passwd fun<br>
catware@ubuntu:\~/playground$ ln fun fun-hard<br>
catware@ubuntu:\~/playground$ ln fun dir1/fun-hard<br>
catware@ubuntu:\~/playground$ ln fun dir2/fun-hard<br>
**Как убедится что fun и fun-hard один и тот же файл?**<br>
Рассуждая о жестких ссылках - полезно представлять файлы состоящими из двух частей - раздела с данными, где хранится содержимое и раздела с именем, где хранится имя файла<br>
Создавая жесткую ссылку, мы фактически создаем дополнительный раздел с именем, ссылающийся на тот же раздел с данными. Цепочку дисковых блоков система присваивает тому,<br>
что называется индексным узлом (inode), который затем присваивается разделу с именем. То есть каждая жесткая ссылка ссылается на опреденный индексный узел с содержимым<br> 
файла. Команда *ls* может извлекать эту информацию. Для этого ее нужно вызвать с параметром *-i*<br>
*catware@ubuntu:\~/playground$ ls -li<br>
total 16<br>
924319 drwxrwxr-x 2 catware catware 4096 Jan 20 15:58 dir1<br>
924320 drwxrwxr-x 2 catware catware 4096 Jan 20 15:59 dir2<br>
924322 -rw-r--r-- 4 catware catware 2741 Jan 20 14:39 fun<br>
924322 -rw-r--r-- 4 catware catware 2741 Jan 20 14:39 fun-hard*<br>
**Жесткие ссылки не могут указывать на файлы, находящиеся на других физических устройства.**<br>
**Жесткие ссылки не могут указывать на каталоги - только на файлы.**<br>
**Символическая ссылка - это файл особого типа, хранящий текстовый указатель на файл или каталог.**<br>
*catware@ubuntu:\~/playground$ ln -s fun fun-sym<br>
catware@ubuntu:\~/playground$ ln -s ../fun dir1/fun-sym<br>
catware@ubuntu:\~/playground$ ln -s ../fun dir2/fun-sym<br>
catware@ubuntu:\~/playground$ ls -l dir1<br>
total 4<br>
-rw-r--r-- 4 catware catware 2741 Jan 20 14:39 fun-hard<br>
lrwxrwxrwx 1 catware catware    6 Jan 20 16:20 fun-sym -> ../fun*<br>
Запись с информацией о fun-sym в dir1 сообщает, что это символическая ссылка (первый символ **l** в первом поле), указывающая на ../fun, что правильно. Относительно<br>
символической ссылки fun-sym файл fun находится в каталоге уровнем выше. Стоит обратить также внимание на размер файла симлинка равный 6, - это число символов в строке<br>
../fun, а не размер файла, на который он указывает.<br>
Помимо обычных файлов, симлинки могут указывать также на каталоги:<br>
*catware@ubuntu:\~/playground$ ln -s dir1 dir1-sym<br>
catware@ubuntu:\~/playground$ ls -li<br>
total 16<br>
924319 drwxrwxr-x 2 catware catware 4096 Jan 20 16:20 dir1<br>
923707 lrwxrwxrwx 1 catware catware    4 Jan 20 16:28 dir1-sym -> dir1<br>
924320 drwxrwxr-x 2 catware catware 4096 Jan 20 16:20 dir2<br>
924322 -rw-r--r-- 4 catware catware 2741 Jan 20 14:39 fun<br>
924322 -rw-r--r-- 4 catware catware 2741 Jan 20 14:39 fun-hard<br>
921996 lrwxrwxrwx 1 catware catware    3 Jan 20 16:20 fun-sym -> fun*<br>
## rm
Удаляет файлы и целые деревья каталогов.<br>
*catware@ubuntu:\~$ rm -r myplace*<br>
**Параметры команды *rm*:**
**-i** - запрашивать у пользователя подтверждение перед удалением существуюего файла<br>
**-r** - рекурсивно удалить каталоги. То есть вместе с каталогом будут удалены все его подкаталоги. Это обязательный параметр при удалении каталогов<br>
**-f** - игнорировать отсутствующие файлы и не запрашивать подтверждения. Этот параметр отменяет действие параметра *-i*<br>
**-v** - выводить информационные сообщения в процессе удаления<br>
**Некоторые примеры использования команды *rm*:**<br>
**rm file1** - просто удалит файл file1<br>
**rm -i file1** - перед удалением file1 запросит подтверждение у пользователя<br>
**rm -r file1 dir1** - удалит файл file1 и каталог dir1 со всем его содержимым<br>
**rm -rf file1 dir1** - то же что и выше, но в отсутствие file1 и/или dir1 просто продолжит работу, не выводя никаких сообщений<br>
*catware@ubuntu:~/playground$ rm fun-hard<br>
catware@ubuntu:~/playground$ ls -li<br>
total 12<br>
924319 drwxrwxr-x 2 catware catware 4096 Jan 20 16:20 dir1<br>
923707 lrwxrwxrwx 1 catware catware    4 Jan 20 16:28 dir1-sym -> dir1<br>
924320 drwxrwxr-x 2 catware catware 4096 Jan 20 16:20 dir2<br>
924322 -rw-r--r-- 3 catware catware 2741 Jan 20 14:39 fun<br>
921996 lrwxrwxrwx 1 catware catware    3 Jan 20 16:20 fun-sym -> fun<br>
catware@ubuntu:~/playground$ rm -i fun<br>
rm: remove regular file 'fun'? y<br>
catware@ubuntu:~/playground$ ls -li<br>
total 8<br>
924319 drwxrwxr-x 2 catware catware 4096 Jan 20 16:20 dir1<br>
923707 lrwxrwxrwx 1 catware catware    4 Jan 20 16:28 dir1-sym -> dir1<br>
924320 drwxrwxr-x 2 catware catware 4096 Jan 20 16:20 dir2<br>
921996 lrwxrwxrwx 1 catware catware    3 Jan 20 16:20 fun-sym -> fun<br>
catware@ubuntu:~/playground$ less fun-sym<br>
fun-sym: No such file or directory<br>
catware@ubuntu:~/playground$ rm fun-sym dir1-sym<br>
catware@ubuntu:~/playground$ ls -li<br>
total 8<br>
924319 drwxrwxr-x 2 catware catware 4096 Jan 20 16:20 dir1<br>
924320 drwxrwxr-x 2 catware catware 4096 Jan 20 16:20 dir2<br>
catware@ubuntu:~/playground$ cd<br>
catware@ubuntu:~$ rm -r playground*<br><br>
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
## Что такое команды?
Команда может быть:<br>
**Выполняемой программой. К этой категории относятся скомпилированные двоичные программы, например написанные на C/C++, программы, написанные на языках<br>
сценариев, таких как shell, Perl и т.д.**<br>
**Встроенной командной, реализованной внутри самой командной оболочки. Например, команда *cd*.**<br>
**Функцией командой оболочки. Функции командной оболочки - это миниатюрные сценарии на языке командной оболочки, встроенные в окружение.**<br>
**Псевдонимом. Псевдоним (alias) - это команда, которую мы можем определить сами, сконструировав из других команд.<br>
## type
Получение типа команды<br>
*catware@ubuntu:\~$ type type<br>
type is a shell builtin<br>
catware@ubuntu:\~$ type ls<br>
ls is aliased to `ls --color=auto'<br>
catware@ubuntu:\~$ type cp<br>
cp is /usr/bin/cp*<br>
## which
Определение местоположения исполняемого файла.<br>
catware@ubuntu:~$ which ls<br>
/usr/bin/ls*<br>
## help
Получение справки для встроенных команд.<br>
*catware@ubuntu:~$ help cd<br>
cd: cd [-L|[-P [-e]] [-@]] [dir]<br>
    Change the shell working directory.<br>
    
    Change the current directory to DIR.  The default DIR is the value of the<br>
    HOME shell variable.<br>
    
    The variable CDPATH defines the search path for the directory containing<br>
    DIR.  Alternative directory names in CDPATH are separated by a colon (:).<br>
    A null directory name is the same as the current directory.  If DIR begins<br>
    with a slash (/), then CDPATH is not used.<br>
    
    If the directory is not found, and the shell option `cdable_vars' is set,<br>
    the word is assumed to be  a variable name.  If that variable has a value,<br>
    its value is used for DIR.<br>
    
    Options:<br>
      -L	force symbolic links to be followed: resolve symbolic<br>
    		links in DIR after processing instances of `..'<br>
      -P	use the physical directory structure without following<br>
    		symbolic links: resolve symbolic links in DIR before<br>
    		processing instances of `..'<br>
      -e	if the -P option is supplied, and the current working<br>
    		directory cannot be determined successfully, exit with<br>
    		a non-zero status<br>
      -@	on systems that support it, present a file with extended<br>
    		attributes as a directory containing the file attributes<br>
    
    The default is to follow symbolic links, as if `-L' were specified.<br>
    `..' is processed by removing the immediately previous pathname component<br>
    back to a slash or the beginning of DIR.<br>
    
    Exit Status:<br>
    Returns 0 if the directory is changed, and if $PWD is set successfully when<br>
    -P is used; non-zero otherwise.<br>
## man
Вывод страниц справочного руководства. В большинстве систем man использует less для вывода страницы, поэтому при просмотре страницы можно использовать все известные команды<br>
less.<br>
*catware@ubuntu:~$ man ls*<br>
Организация справочного руководства:<br>
**1** - пользовательские команды<br>
**2** - программные интерфейсы системных вызовов в ядре<br>
**3** - программные интерфейсы в библиотеке C<br>
**4** - специальные файл, такие как узлы устройств и драйверы<br>
**5** - форматы файлов<br>
**6** - игры и развлечения, такие как хранители экрана<br>
**7** - прочее<br>
**8** - команды системного администрирования<br>
## apropos
Вывод списка подходящих программ.<br>
*catware@ubuntu:~$ apropos cd<br>
apt-cdrom (8)        - APT CD-ROM management utility<br>
cd-create-profile (1) - Color Manager Profile Creation Tool<br>
cd-fix-profile (1)   - Color Manager Testing Tool<br>
cd-it8 (1)           - Color Manager Testing Tool<br>
gcov-dump (1)        - offline gcda and gcno profile dump tool<br>
gcov-dump-9 (1)      - offline gcda and gcno profile dump tool<br>
gcov-tool (1)        - offline gcda profile processing tool<br>
gcov-tool-9 (1)      - offline gcda profile processing tool<br>
hex2hcd (1)          - Broadcom Bluetooth firmware converter<br>
hipercdecode (1)     - Decode a HIPERC stream into human readable form.<br>
libOpenCL (7)        - OCL-ICD implementation of OpenCL ICD loader<br>
libOpenCL.so (7)     - OCL-ICD implementation of OpenCL ICD loader<br>
mcd (1)              - change MSDOS directory<br>
mcdiff (1)           - Visual shell for Unix-like systems.<br>
Net::DNS::RR::CDNSKEY (3pm) - DNS CDNSKEY resource record<br>
Net::DNS::RR::CDS (3pm) - DNS CDS resource record<br>
Net::DNS::SEC::ECDSA (3pm) - DNSSEC ECDSA digital signature algorithm<br>
rsyncd.conf (5)      - configuration file for rsync in daemon mode<br>
systemd-timesyncd (8) - Network Time Synchronization<br>
systemd-timesyncd.service (8) - Network Time Synchronization<br>
tcdrain (3)          - get and set terminal attributes, line control, get and...<br>
timesyncd.conf (5)   - Network Time Synchronization configuration files<br>
timesyncd.conf.d (5) - Network Time Synchronization configuration files<br>
x86_64-linux-gnu-gcov-dump (1) - offline gcda and gcno profile dump tool<br>
x86_64-linux-gnu-gcov-dump-9 (1) - offline gcda and gcno profile dump tool<br>
x86_64-linux-gnu-gcov-tool (1) - offline gcda profile processing tool<br>
x86_64-linux-gnu-gcov-tool-9 (1) - offline gcda profile processing tool<br>
XML::LibXML::CDATASection (3pm) - XML::LibXML Class for CDATA Sections*<br>
## whatis
Вывод очень краткого описания команды.<br>
*catware@ubuntu:~$ whatis ls<br>
ls (1)               - list directory contents*<br>
## alias
Команду *alias* можно использовать для создания псевдонимов с определенным набором команд которые выполнятся последовательно или для просмотра всех доступных псевдонимах<br>
в системе на текущий момент<br>
*catware@ubuntu:\~$ type foo<br>
bash: type: foo: not found<br>
catware@ubuntu:\~$ alias foo='cd /usr; ls; cd -'<br>
catware@ubuntu:\~$ foo<br>
bin    include  lib32  libexec  local  share<br>
games  lib      lib64  libx32   sbin   src<br>
/home/catware<br>
catware@ubuntu:\~$ alias<br>
alias alert='notify-send --urgency=low -i "$([ $? = 0 ] && echo terminal || echo error)" "$(history|tail -n1|sed -e '\''s/^\s*[0-9]\+\s*//;s/[;&|]\s*alert$//'\'')"'<br>
alias egrep='egrep --color=auto'<br>
alias fgrep='fgrep --color=auto'<br>
alias foo='cd /usr; ls; cd -'<br>
alias grep='grep --color=auto'<br>
alias l='ls -CF'<br>
alias la='ls -A'<br>
alias ll='ls -alF'<br>
alias ls='ls --color=auto'*<br>
## Стандартный ввод, вывод и вывод ошибок
**Перенаправление стандартного вывода:**<br>
Механизм перенаправления ввода/вывода позволяет явно указать, куда должен осуществляться стандартный вывод. Чтобы перенаправить стандартный вывод в другой файл вместо экрана<br>
нужно добавить в команду оператор перенаправления *>* и имя файла.<br>
*catware@ubuntu:\~$ ls -l /usr/bin > ls-output.txt*<br>
Если понадобится очистить какой-нибудь файл:<br>
*catware@ubuntu:\~$ > ls-output.txt*<br>
**Перенаправление стандартного вывода ошиибок:**<br>
*catware@ubuntu:\~$ ls -l /bin/usr/text 2> ls-error.txt<br>
catware@ubuntu:\~$ cat ls-error.txt<br>
ls: cannot access '/bin/usr/text': No such file or directory*<br>
**Перенаправление стандартного вывода и стандартного вывода ошибок в один файл:**<br>
Старый традиционный метод:<br>
*catware@ubuntu:\~$ ls -l /bin/usr/ > ls-output.txt 2>&1*<br>
Здесь выполняются два перенапаправления. Сначала - перенаправление стандартного вывода в файл *ls-output.txt*, а затем, с использованием нотации 2>&1, -<br>
перенаправление файлового дескриптора 2 (стандартный вывод ошибок) в файловый дескриптор 1 (стандартный вывод).<br>
Перенаправление стандартного вывода ошибок всегда должно производиться после перенаправления стандартного вывода, иначе этот трюк не сработает.<br>
Современный вариант:<br>
*catware@ubuntu:~$ ls -l /bin/usr &> ls-output.txt*<br>
В данном примере используется единственный оператор &>, перенаправляющий стандартный вывод и стандартный вывод ошибок в файл ls-output.txt. Аналогично можно<br>
перенаправить стандартный вывод и стандартный вывод ошибок с добавлением в конец одного и того же файла:<br>
*catware@ubuntu:~$ ls -l /bin/usr &>> ls-output.txt*<br>
## Конвейеры
С помощью оператора конвейера | (вертикальная черта) стандартный вывод одной команды можно связать со стандартным вводом другой.<br>
*catware@ubuntu:~$ ls -l /usr/bin | less*<br>
## Фильтры<br>
Фильтры принимают ввод, изменяют его определенным образом и выводят результат:<br>
*catware@ubuntu:~$ ls -l /bin /usr/bin | sort | less*<br>
Поскольку в команде указаны два каталога (/bin и /usr/bin), вывод команды ls будет состоять из двух сортированных списков, по одному для каждого каталога.<br>
Добавив команду *sort* в конвейер, мы изменили данные, чтобы получить единый сортированный список.<br>
## uniq - поиск или удаление повторяющихся строк:**<br>
Команда *uniq* часто используется в комбинации с командой *sort*. *uniq* принимает сортированный список данных либо со стандартного ввода, либо из файла, имя которого можно<br>
передать в единственном аргументе и по умолчанию удаляет повторяющиеся строки из списка. Поэтому, чтобы гарантировать отсутствие дубликатов в нашем списке (то есть любых<br>
программ с одинаковыми именами в каталогах /bin и /usr/bin), lj, добавим *uniq* в конвейер:<br>
*catware@ubuntu:~$ ls /bin /usr/bin | sort | uniq | less*<br>
В примере выше использовал *uniq* для удаления любых повторяющихся строк в выводе команды *sort*. Если потребуется наоборот - получить список дубликатов, то добавляем<br> параметр -d:<br>
*catware@ubuntu:~$ ls /bin /usr/bin | sort | uniq -d | less*<br>
## wc
Вывод числа строк, слов и байтов. Команда *wc* используется для подсчета числа строк, слов и байтов в файлах. Команду удобно использовать в конвейерах для подсчета:<br>
например, подсчитать числов элементов в нашем сортированном списке можно так:<br>
*catware@ubuntu:~$ ls /bin /usr/bin | sort | uniq | wc -l<br>
1581*<br>
## grep
Поиск строк, соответствующих шаблону. Выводит строку с найденным совпадением.<br>
Допустимм, что нам надо найти все файлы в списке программ, которые имеют в своем имени последовательность символов *zip*. Результаты такого поиска могут подсказать,<br>
какие программы в системе имеют отношение к сжатию файлов.<br>
*catware@ubuntu:~$ ls /bin /usr/bin | sort | uniq | grep zip<br>
bunzip2<br>
bzip2<br>
bzip2recover<br>
funzip<br>
gpg-zip<br>
gunzip<br>
gzip<br>
mzip<br>
p7zip<br>
preunzip<br>
prezip<br>
prezip-bin<br>
unzip<br>
unzipsfx<br>
zip<br>
zipcloak<br>
zipdetails<br>
zipgrep<br>
zipinfo<br>
zipnote<br>
zipsplit*<br>
**Пара удобных параметров**:
**-i** - требует от *grep* игнорировать регистр символов в процессе поиска (обычно поиск выполняется с учетом регистра)<br>
**-v** - требует от *grep* выводить только строки, где совпадение с шаблоном<br>
## head
Вывод первых N строк (по умолчанию если указывать без аргумента - 10 строк) из файла.<br>
*catware@ubuntu:~$ head -n 5 /var/log/syslog*<br>
Jan 26 11:50:05 ubuntu rsyslogd: [origin software="rsyslogd" swVersion="8.2001.0" x-pid="965" x-info="https://www.rsyslog.com"] rsyslogd was HUPed*<br>
Jan 26 11:50:05 ubuntu dbus-daemon[953]: dbus[953]: Unknown group "power" in message bus configuration file*<br>
Jan 26 11:50:06 ubuntu systemd[1]: logrotate.service: Succeeded.*<br>
Jan 26 11:50:06 ubuntu systemd[1]: Finished Rotate log files.*<br>
Jan 26 11:50:08 ubuntu NetworkManager[954]: <info>  [1643187008.5188] NetworkManager (version 1.22.10) is starting... (for the first time)*<br>
Или в конвейерах:<br>
*catware@ubuntu:~$ ls /usr/bin | head -n 5*<br>
## tail
Вывод последних N строк (по умолчанию если указывать без аргумента - 10 строк) из файла. C помощью этой команды можно наблюдать за изменением файла в режим реального<br> времени:<br>
*catware@ubuntu:~$ tail -n 5 /var/log/syslog<br>
Jan 26 18:58:54 ubuntu gnome-shell[1909]: Window manager warning: Overwriting existing binding of keysym 34 with keysym 34 (keycode d).<br>
Jan 26 18:58:54 ubuntu gnome-shell[1909]: Window manager warning: Overwriting existing binding of keysym 35 with keysym 35 (keycode e).<br>
Jan 26 18:58:54 ubuntu gnome-shell[1909]: Window manager warning: Overwriting existing binding of keysym 36 with keysym 36 (keycode f).<br>
Jan 26 18:58:54 ubuntu gnome-shell[1909]: Window manager warning: Overwriting existing binding of keysym 38 with keysym 38 (keycode 11).<br>
Jan 26 18:58:54 ubuntu gnome-shell[1909]: Window manager warning: Overwriting existing binding of keysym 39 with keysym 39 (keycode 12).*<br>
## tee
Чтение со стандартного ввода и запись в стандартный вывод и в файлы. Linux предоставляет команду *tee*, которая создает T-образное разветвление в конвейере.<br>
Команда *tee* читает данные со стандартного ввода и копирует их в стандартный вывод (чтобы дать возможсть передать их дальше по конвейеру) и в один или <br>
несколько файлов. Это может пригодиться для сохранения промежуточных результатов обработки в конвейереж. Сохраню полный список файлов в каталогах в файле<br>
*ls.txt*, перед тем как он будет отфильтрован командой *grep*:<br>
*catware@ubuntu:\~$ ls /usr/bin | tee ls.txt | grep zip<br>
bunzip2<br>
bzip2<br>
bzip2recover<br>
funzip<br>
gpg-zip<br>
gunzip<br>
gzip<br>
mzip<br>
p7zip<br>
preunzip<br>
prezip<br>
prezip-bin<br>
unzip<br>
unzipsfx<br>
zip<br>
zipcloak<br>
zipdetails<br>
zipgrep<br>
zipinfo<br>
zipnote<br>
zipsplit*<br>
## Где хранится информация о пользователях/группах/паролях в линукс?
**О пользователях:**<br>
*catware@ubuntu:~$ cat /etc/passwd*<br>
**О группах:**<br>
*catware@ubuntu:~$ cat /etc/group*<br>
**О паролях:**<br>
*catware@ubuntu:~$ ls -la /etc/shadow<br>
-rw-r----- 1 root shadow 1359 Dec 30  2020 /etc/shadow*<br>
## echo
Выводит строку текста<br>
*catware@ubuntu:\~$ echo this is a some kind of test<br>
this is a some kind of test*<br>
*echo* выведет любой свой аргумент.<br>
*catware@ubuntu:\~$ echo \*<br>
Desktop Documents Downloads Music newdir Pictures Public snap Templates Videos*<br>
\* - означает последовательность любых символов в имени файла, перед тем как выполнить команду *echo*, оболочка bash замещает символ \* чем-то другим<br>
в данном случае именами файлов в текущем рабочем каталоге. После нажатия клавиши *Enter* командная оболочка автоматически производит подстановку любых <br>
групповых симоволов в командной строке, прежде чем выполнить ее, поэтому команда *echo* не увидела \* - она получила уже готовый результат после подстановки.<br>
Механизм работых групповых символов назвается - подстановкой пути.
*catware@ubuntu:\~$ echo D\*<br>
Desktop Documents Downloads*<br>
*catware@ubuntu:\~$ echo \*s<br>
Documents Downloads Pictures Templates Videos<br>
*catware@ubuntu:\~$ echo [[:upper:]]\*<br>
Desktop Documents Downloads Music Pictures Public Templates Videos*<br>
*catware@ubuntu:\~$ echo /usr/\*/share*<br>
Вывести домашний каталог текущего пользователя:<br>
*catware@ubuntu:\~$ echo \~<br>
/home/catware*<br>
Вывести домашний каталог root пользователя:<br>
*catware@ubuntu:\~$ echo \~root<br>
/root*<br>
Командная оболочка поддерживает также подстановку результатов арифметических выражений. Это позволяет использовать командную строку как калькулятор:<br>
*catware@ubuntu:\~$ echo $((2+2))<br>
4*<br>
Для подстановки арифметических выражений используется следующий формат:<br>
**$((выражение))**, где **выражение** - это арифметическое выражение, состоящее из значений и арифметических операторов.<br>
*catware@ubuntu:\~$ echo $(((5\*\*2) \* 3))<br>
75*<br>
*catware@ubuntu:\~$ echo Пять разделить на два будет $((5/2))<br>
Пять разделить на два будет 2*<br>
*catware@ubuntu:\~$ echo и $((5%2)) в остатке.Б<br>
и 1 в остатке.<br>
C помощью подстановки фигурных скобок создается множество текстовых строк:<br>
*catware@ubuntu:\~$ echo Впереди-{A,B,C}-позади<br>
Впереди-A-позади Впереди-B-позади Впереди-C-позади*<br>
Внутри фигурных скобок находится список строк, разделенных запятыми, или диапазон целых чисел или одиночных символов. Использование пробелов внутри фигурных скобок<br>
не допускается.<br>
*catware@ubuntu:\~$ echo Число_{1..5}<br>
Число_1 Число_2 Число_3 Число_4 Число_5*<br>
*catware@ubuntu:\~$ echo $BASH_VERSION<br>
5.0.17(1)-release*<br>
*catware@ubuntu:\~$ echo {01..15}<br>
01 02 03 04 05 06 07 08 09 10 11 12 13 14 15*<br>
*catware@ubuntu:~$ echo {001..15}<br>
001 002 003 004 005 006 007 008 009 010 011 012 013 014 015*<br>
Диапазон символов в обратном порядке:<br>
*catware@ubuntu:\~$ echo {Z..A}<br>
Z Y X W V U T S R Q P O N M L K J I H G F E D C B A*<br>
Организовать список каталогов по годам и месяцам:<br>
*catware@ubuntu:\~$ mkdir Photos*<br>
*catware@ubuntu:\~$ cd Photos*<br>
*catware@ubuntu:\~/Photos$ mkdir {2020..2022}-{1..12}*<br>
*catware@ubuntu:\~/Photos$ ls -la<br>
total 152<br>
drwxrwxr-x 38 catware catware 4096 Jan 30 16:07 .<br>
drwxr-xr-x 19 catware catware 4096 Jan 30 16:06 ..<br>
drwxrwxr-x  2 catware catware 4096 Jan 30 16:07 2020-1<br>
drwxrwxr-x  2 catware catware 4096 Jan 30 16:07 2020-10<br>
drwxrwxr-x  2 catware catware 4096 Jan 30 16:07 2020-11<br>
drwxrwxr-x  2 catware catware 4096 Jan 30 16:07 2020-12<br>
drwxrwxr-x  2 catware catware 4096 Jan 30 16:07 2020-2<br>
drwxrwxr-x  2 catware catware 4096 Jan 30 16:07 2020-3<br>
drwxrwxr-x  2 catware catware 4096 Jan 30 16:07 2020-4<br>
drwxrwxr-x  2 catware catware 4096 Jan 30 16:07 2020-5<br>
drwxrwxr-x  2 catware catware 4096 Jan 30 16:07 2020-6<br>
drwxrwxr-x  2 catware catware 4096 Jan 30 16:07 2020-7<br>
drwxrwxr-x  2 catware catware 4096 Jan 30 16:07 2020-8<br>
drwxrwxr-x  2 catware catware 4096 Jan 30 16:07 2020-9<br>
drwxrwxr-x  2 catware catware 4096 Jan 30 16:07 2021-1<br>
drwxrwxr-x  2 catware catware 4096 Jan 30 16:07 2021-10<br>
drwxrwxr-x  2 catware catware 4096 Jan 30 16:07 2021-11<br>
drwxrwxr-x  2 catware catware 4096 Jan 30 16:07 2021-12<br>
drwxrwxr-x  2 catware catware 4096 Jan 30 16:07 2021-2<br>
drwxrwxr-x  2 catware catware 4096 Jan 30 16:07 2021-3<br>
drwxrwxr-x  2 catware catware 4096 Jan 30 16:07 2021-4<br>
drwxrwxr-x  2 catware catware 4096 Jan 30 16:07 2021-5<br>
drwxrwxr-x  2 catware catware 4096 Jan 30 16:07 2021-6<br>
drwxrwxr-x  2 catware catware 4096 Jan 30 16:07 2021-7<br>
drwxrwxr-x  2 catware catware 4096 Jan 30 16:07 2021-8<br>
drwxrwxr-x  2 catware catware 4096 Jan 30 16:07 2021-9<br>
drwxrwxr-x  2 catware catware 4096 Jan 30 16:07 2022-1<br>
drwxrwxr-x  2 catware catware 4096 Jan 30 16:07 2022-10<br>
drwxrwxr-x  2 catware catware 4096 Jan 30 16:07 2022-11<br>
drwxrwxr-x  2 catware catware 4096 Jan 30 16:07 2022-12<br>
drwxrwxr-x  2 catware catware 4096 Jan 30 16:07 2022-2<br>
drwxrwxr-x  2 catware catware 4096 Jan 30 16:07 2022-3<br>
drwxrwxr-x  2 catware catware 4096 Jan 30 16:07 2022-4<br>
drwxrwxr-x  2 catware catware 4096 Jan 30 16:07 2022-5<br>
drwxrwxr-x  2 catware catware 4096 Jan 30 16:07 2022-6<br>
drwxrwxr-x  2 catware catware 4096 Jan 30 16:07 2022-7<br>
drwxrwxr-x  2 catware catware 4096 Jan 30 16:07 2022-8<br>
drwxrwxr-x  2 catware catware 4096 Jan 30 16:07 2022-9*<br>
Посмотреть переменную USER, которая хранит ваше имя пользователя:
*catware@ubuntu:\~$ echo $USER<br>
catware*<br>
Увидеть список доступных переменных:<br>
*catware@ubuntu:\~$ printenv | less*<br>
Подстановка команд позволяет использовать поток вывода команд в качестве аргументов других команд:<br>
*catware@ubuntu:\~$ echo $(ls)<br>
Desktop Documents Downloads ls-result.txt Music newdir Pictures Public snap Templates Videos*<br>
Или:<br>
*catware@ubuntu:\~$ ls -l $(which cp)<br>
-rwxr-xr-x 1 root root 153976 Sep  5  2019 /usr/bin/cp*<br>
Здесь результат команды *which cp* передается как аргумент команде *ls*, благодар чему мы получаем информацию о программе *cp*, не зная полного пути к ней.<br>
Можно использовать целые конвейеры:<br>
*catware@ubuntu:\~$ file $(ls -d /usr/bin/* | grep zip)<br>
/usr/bin/bunzip2:      ELF 64-bit LSB shared object, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2,<br> BuildID[sha1]=00c09d800d549d58e3b7c4f6170446cc69bf14a5, for GNU/Linux 3.2.0, stripped<br>
/usr/bin/bzip2:        ELF 64-bit LSB shared object, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2,<br> BuildID[sha1]=00c09d800d549d58e3b7c4f6170446cc69bf14a5, for GNU/Linux 3.2.0, stripped<br>
/usr/bin/bzip2recover: ELF 64-bit LSB shared object, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2,<br> BuildID[sha1]=aa9666f913c3a67eab9d62585a9b37e46d0c7cb9, for GNU/Linux 3.2.0, stripped<br>
/usr/bin/funzip:       ELF 64-bit LSB shared object, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2,<br> BuildID[sha1]=16c10d3e99879c6257b23fba3c49032d8ac2e5b4, for GNU/Linux 3.2.0, stripped<br>
/usr/bin/gpg-zip:      POSIX shell script, ASCII text executable<br>
/usr/bin/gunzip:       POSIX shell script, ASCII text executable<br>
/usr/bin/gzip:         ELF 64-bit LSB shared object, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2,<br> BuildID[sha1]=445b2aa3186ca2fc7b96fa7c42c348a1662769c1, for GNU/Linux 3.2.0, stripped<br>
/usr/bin/mzip:         symbolic link to mtools<br>
/usr/bin/p7zip:        POSIX shell script, ASCII text executable<br>
/usr/bin/preunzip:     POSIX shell script, ASCII text executable<br>
/usr/bin/prezip:       POSIX shell script, ASCII text executable<br>
/usr/bin/prezip-bin:   ELF 64-bit LSB shared object, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2,<br> BuildID[sha1]=ce7944c0866242d3af5e47a0ca2bf83df0adb18f, for GNU/Linux 3.2.0, stripped<br>
/usr/bin/unzip:        ELF 64-bit LSB shared object, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2,<br> BuildID[sha1]=24cc026c903214b86a62f49ad96b94dc0e4de18e, for GNU/Linux 3.2.0, stripped<br>
/usr/bin/unzipsfx:     ELF 64-bit LSB shared object, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2,<br> BuildID[sha1]=cda85960c0f2092ac909d08f29f8f51a02451e6b, for GNU/Linux 3.2.0, stripped<br>
/usr/bin/zip:          ELF 64-bit LSB shared object, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 2.6.32,<br> BuildID[sha1]=c828586e6e7cf929500a5b9c04faece9eceed5cc, stripped<br>
/usr/bin/zipcloak:     ELF 64-bit LSB shared object, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 2.6.32,<br> BuildID[sha1]=6675095584351a4d9e63370ceb1dcce0232c6140, stripped<br>
/usr/bin/zipdetails:   Perl script text executable<br>
/usr/bin/zipgrep:      POSIX shell script, ASCII text executable<br>
/usr/bin/zipinfo:      ELF 64-bit LSB shared object, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2,<br> BuildID[sha1]=24cc026c903214b86a62f49ad96b94dc0e4de18e, for GNU/Linux 3.2.0, stripped<br>
/usr/bin/zipnote:      ELF 64-bit LSB shared object, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 2.6.32,<br> BuildID[sha1]=9d9a7264805021adae207c5d13fb0ab43a6fb04e, stripped<br>
/usr/bin/zipsplit:     ELF 64-bit LSB shared object, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 2.6.32,<br> BuildID[sha1]=80f65d65f35b6bb9d37e8074bfa1e01c4b7ce18e, stripped<br>
В этом примере результаты конвейера превратились в список аргументов команды *file*. Механизм подстановки команд имеет альтернативный синтаксис, унаследованный<br>
от более старых командных оболочек, который также поддерживается в bash. В нем вместо знака доллара и круглых скобок используются обратные апострофы:<br>
*catware@ubuntu:\~$ ls -l `which cp`<br>
-rwxr-xr-x 1 root root 153976 Sep  5  2019 /usr/bin/cp*<br>
Экранирование:<br>
*catware@ubuntu:\~$ echo text ~/\*.txt {a,b} $(echo foo) $((2+2)) $USER<br>
text /home/catware/ls-result.txt a b foo 4 catware*<br>
*catware@ubuntu:\~$ echo "text ~/\*.txt {a,b} $(echo foo) $((2+2)) $USER"<br>
text ~/\*.txt {a,b} foo 4 catware*<br>
*catware@ubuntu:\~$ echo 'text ~/\*.txt {a,b} $(echo foo) $((2+2)) $USER'<br>
text ~/\*.txt {a,b} $(echo foo) $((2+2)) $USER*<br>
Экранирование одного символа:<br>
*catware@ubuntu:~$ echo "Баланс счета пользователя $USER: \$5.00"<br>
Баланс счета пользователя catware: $5.00*<br>
Управляющие последовательности:<br>
**\a** - звонок. Заставляет компьютер подать звуковой сигнал<br>
**\b** - backspace<br>
**\n** - новая строка<br>
**\r** - возврат каретки<br>
**\t** - табуляция<br>
*catware@ubuntu:\~$ sleep 10; echo -e "Time's up\a"<br>
Time's up*<br>
## history
Выводит содержимое истории команд<br>
*catware@ubuntu:~$ history | less*<br>
А что если нам понадобилось найти команды, использовавшиеся для получения списка содержимого /usr/bin:<br>
*catware@ubuntu:\~$ history | grep /usr/bin | less<br>
   73  ls -l /usr/bin > ls-output.txt<br>
   77  ls -l /usr/bin > ls-output.txt<br>
   98  ls -l /usr/bin | less<br>
   99  ls -l /bin /usr/bin | sort | less<br>
  102  ls /bin /usr/bin | sort | uniq | less<br>
  104  ls /bin /usr/bin | sort | uniq -d | less<br>
  105  ls /bin /usr/bin | sort | uniq | wc -l<br>
  106  ls /bin /usr/bin | sort | uniq | grep zip<br>
  113  ls /usr/bin | tail -n 5<br>
  114  ls /usr/bin | head -n 5<br>
  117  ls /usr/bin | tee ls.txt | grep zip<br>
  176  file $(ls -d /usr/bin/\* | grep zip)<br>
  203  history | grep /usr/bin | less*<br>
## id
Выводит информацию об идентичности пользователя<br>
*catware@ubuntu:\~$ id<br>
uid=1000(catware) gid=1000(catware) groups=1000(catware),4(adm),24(cdrom),27(sudo),30(dip),46(plugdev),120(lpadmin),131(lxd),132(sambashare)*<br>
## Чтение, запись и выполнение
Права доступа к файлам и каталогам определяются в терминах права на чтение, права на запись и права на выполнение.<br>
*catware@ubuntu:\~$ > foo.txt<br>
catware@ubuntu:\~$ ls -l foo.txt<br>
-rw-rw-r-- 1 catware catware 0 Mar  1 15:24 foo.txt*<br>
Первые 10 символов в выводе - это **атрибуты файла**. Первый из этих символов определяет **тип файла**:<br>
**-** - обычный файл<br>
**d** - каталог<br>
**l** - символическая ссылка. **Для символических ссылок все остыльные атрибуты имеют значение rwxrwxrwx и не отражают действительные права доступа. Фактические<br>
права доступа к файлу определяются атрибутами самого файла, на который указывает символическая ссылка.<br>
**c** - специальный файл символьного устройства. Файлы этого типа соответствуют устройствам, таким как терминал или модем, которые обрабатывают данные как потоки байтов.<br>
**b** - специальный файл блочного устройства. Файлы этого типа соответствуют устройствам, таким как привод жесткого диска или CD-ROM, которые обрабатывают данные блоками.<br>
Остальные девять символов в атрибутах файла называются **режимом доступа к файлу** и представляют права на чтение, запись и выполнение для владельца файла, группы - <br>
владельца файла и всех остальных<br>
Владелец/Группа/Мир/<br>
rwx/rwx/rwx/<br>
**Атрибуты прав доступа:**<br>
**r** - **Файлы:** разрешается открывать и читать содержимое файла. **Каталоги:** разрешается читать содержимое каталога, если вместе с этим атрибутом установлен атрибут<br> права на выполнение<br>
**w** - **Файлы:** разрешается записывать в файл или усекать его; однако этот атрибут не дает права переименовывать и удалять файлы. Возможность переименования и удаления<br> файлов определяется атрибутом вмещаещего каталога. **Каталоги:** Разрешается создавать, удалять и переименовывать файлы внутри каталога, если вместе с этим атрибутом<br> установлен атрибут права на выполнение.<br>
**x** - **Файлы:** Разрешается интерпретировать файл как программу и выполнять ее. Файлы, содержащие программы на языках сценариев, дополнительно должны быть доступны для<br>
чтения, иначе они не будут выполнятся. **Каталоги:** Разрешается входить в каталог, то есть выполнять команду *cd* для перехода в него.<br>
Примеры установки атрибутов прав доступа к файлам:<br>
**-rwx------** - обычный файл, доступный владельцу для чтения, записи и выполнения. Никто другой не имеет прав доступа к файлу<br>
**-rw-------** - обычный файл, доступный владельцу для чтения и записи. Никто другой не имеет прав доступа к файлу<br>
**-rw-r--r--** - обычный файл, доступный владельцу для чтения и записи. Члены группы имеют право читать файл. Все остальные имею право читать файл<br>
**-rwxr-xr-x** - обычный файл, доступный владельцу для чтения, записи и выполнения. Все остальные имеют право читать и выполнять файл<br>
**-rw-rw----** - обычный файл, доступный для чтения и записи только владельцу и членам группы<br>
**Lrwxrwxrwx** - символическая ссылка. Все символические ссылки имеют недействительные атрибуты. Фактические права доступа к файлу определяются атрибутами самого<br>
файла, на который указывает символическая ссылка<br>
**drwxrwx---** - каталог. Владелец и члены группы могут входить в каталог, создавать, переименовывать и удалять файлы внутри каталога<br>
**drwxr-x---** - каталог. Владелец может входить в каталог, создавать, переименовывать и удалять файлы внутри каталога. Члены группы могут входить в каталог, но не могут<br>
создавать, переименовывать и удалять файлы внутри каталога<br>
## chmod
Изменение режима доступа к файлу. Права доступа к файлу или каталогу может изменить только владелец или суперпользователь. Команда **chmod** поддерживает два разных способа<br>
изменения режима:<br>
**с использованием восьмеричных чисел;**<br>
**с использование символического представления;**<br>
При использовании восьмеричной формы записи шаблон желаемых привелегий определяется воьсмеричными цифрами:<br>
**0**-**---**<br>
**1**-**--x**<br>
**2**-**-w-**<br>
**3**-**-wx**<br>
**4**-**-r-**<br>
**5**-**r-x**<br>
**6**-**rw-**<br>
**7**-**rwx**<br>
С помощью трех воьсмеричных цифр мы можем определить режим доступа к файлу для владельца, для группы и для остального мира.<br>
*catware@ubuntu:\~$ > foo.txt<br>
catware@ubuntu:\~$ ls -la | grep foo.txt<br>
-rw-rw-r--  1 catware catware     0 Mar 12 21:51 foo.txt<br>
catware@ubuntu:\~$ chmod 600 foo.txt<br>
catware@ubuntu:\~$ ls -la foo.txt<br>
-rw------- 1 catware catware 0 Mar 12 21:51 foo.txt*<br>
Передав аргумент 600, мы установили права для владельца, позволяющие ему читать данные из файла и записывать их в файл, и при этом отобрали все права у группы<br>
и остального мира.<br>
Самые популярные шаблоны:<br>
**7(rwx)**<br>
**6(rw-)**<br>
**5(r-x)**<br>
**4(r--)**<br>
**0(---)**<br>
Команда **chmod** поддерживает символическую форму определения режима доступа к файлу. Символическая форма записи делится на три части:<br>
**для кого устанавливаются разрешения;**<br>
**какие операции с разрешениями будут выполняться;**<br>
**на какие разрешения эти операции будут влиять;**<br>
Чтобы указать для кого устанавливаются разрешения, используется комбинация символов **u, g, a, o**.<br>
**u** - сокращенно от user, означает владельца файла или каталога;
**g** - группа;<br>
**o** - сокращено от other, означает весь остальной мир;<br>
**a** - сокращенно от all, т.е. это комбинация из всех трех символов **u, g, o**;<br>
Если не указан ни один символ, предполагается **a** (all - все). Операцией может быть знак **+**, соответствующий добавлению заданных разрешений, знак **-**, соответствующий<br>
отъему заданных разрешений, или знак **=**, указывающий, что только заданные разрешения должны быть установлены, а все остальные отобраны.<br>
Разрешения определяются символами **r, w, x**.<br>
Примеры символической формы записи прав доступа к файлам:<br>
**u+x** - добавляет право на выполнение, но только для владельца<br>
**u-x** - отнимает право на выполнение у владельца<br>
**+x** - добавляет право на выполнение для владельца, группы и остального мира. Эквивалент записи **a+x**<br>
**o-rw** - отнимает право на чтение и запись  у всех, кроме владельца и группы<br>
**go=rw** - устанавливает право на чтение и запись для всех, кроме владельца. Если прежде файл имел разрешение на выполнение для группы и всего мира, это право отнимается<br>
## umask
Определение разрешений доступа к файлам по умолчанию, которые устанавливаются для файла при его создании.<br>
*catware@ubuntu:\~$ rm -f foo.txt<br>
catware@ubuntu:\~$ umask<br>
0002<br>
catware@ubuntu:\~$ > foo.txt<br>
catware@ubuntu:\~$ ls -l foo.txt<br>
-rw-rw-r-- 1 catware catware 0 Mar 13 12:54 foo.txt*<br>
Сначала удалили созданный ранее файл foo.txt. Выполнили команду **umask** без аргумента, чтобы увидеть текущее значение маски. Она вернула значение **0002** - восьмеричное<br>
представление действующей маски. Затем создали новый файл **foo.txt** и вывели для него разрешения. Владелец и группа получили права на чтение и запись, тогда как все<br>
остальные - только право на чтение. Весь мир не получил права на запись из-за значения маски.<br>
## ps
Просмотр списка процессов.<br>
*catware@ubuntu:\~$ ps<br>
    PID TTY          TIME CMD<br>
   2133 pts/0    00:00:00 bash<br>
   2140 pts/0    00:00:00 ps*<br>
По умолчанию **ps** выводит не очень много информации, только процессы, связанные с текущим сеансом. Поле **PID** - уникальный идентификатор процесс. Поле **TTY** - <br>
это сокращение от teletype, оно содержит информацию об управляющем терминале процесса. Поле **TIME** содержит объем процессорного времени, потреблененного процессом.<br>
Если добавить параметр **x** можно получить более богатую информацию о происходящем в системе:<br>
*catware@ubuntu:|~$ ps x<br>
    PID TTY      STAT   TIME COMMAND<br>
   1596 ?        Ss     0:00 /lib/systemd/systemd --user<br>
   1597 ?        S      0:00 (sd-pam)<br>
   1602 ?        S<sl   0:00 /usr/bin/pulseaudio --daemonize=no --log-target=jou<br>
   1604 ?        SNsl   0:00 /usr/libexec/tracker-miner-fs<br>
   1623 ?        Ssl    0:00 /usr/libexec/gvfsd<br>
   1628 ?        Sl     0:00 /usr/libexec/gvfsd-fuse /run/user/1000/gvfs -f -o b<br>
   1630 ?        Ssl    0:00 /usr/libexec/gvfs-udisks2-volume-monitor<br>
   1641 ?        Sl     0:00 /usr/bin/gnome-keyring-daemon --daemonize --login<br>
   1645 ?        Ssl    0:00 /usr/libexec/gvfs-mtp-volume-monitor<br>
   1656 ?        Sl     0:00 /usr/libexec/goa-daemon<br>
   1670 ?        Ssl    0:00 /usr/libexec/gvfs-afc-volume-monitor<br>
   1682 tty2     Ssl+   0:00 /usr/lib/gdm3/gdm-x-session --run-script env GNOME_<br>
   1685 tty2     Sl+    0:02 /usr/lib/xorg/Xorg vt2 -displayfd 3 -auth /run/user<br>
   1702 tty2     Sl+    0:00 /usr/libexec/gnome-session-binary --systemd --syste<br>
   1769 ?        Ss     0:00 /usr/bin/ssh-agent /usr/bin/im-launch env GNOME_SHE<br>
   1786 ?        Ssl    0:00 /usr/libexec/at-spi-bus-launcher<br>
   1791 ?        S      0:00 /usr/bin/dbus-daemon --config-file=/usr/share/defau<br>
   1797 ?        Ssl    0:00 /usr/libexec/gnome-session-ctl --monitor<br>
   1841 ?        Sl     0:00 ibus-daemon --panel disable --xim<br>
   1865 ?        Ssl    0:00 /usr/libexec/xdg-permission-store<br>
   1868 ?        Sl     0:00 /usr/libexec/gnome-shell-calendar-server<br>
   1880 ?        Ssl    0:00 /usr/libexec/evolution-source-registry<br>
   1882 ?        Sl     0:00 /usr/libexec/dconf-service<br>
   1894 ?        Ssl    0:00 /usr/libexec/evolution-calendar-factory<br>
   1900 ?        Sl     0:00 /usr/bin/gjs /usr/share/gnome-shell/org.gnome.Shell<br>
   1915 ?        Ssl    0:00 /usr/libexec/gsd-a11y-settings<br>
   1956 ?        Sl     0:00 /usr/libexec/gsd-disk-utility-notify<br>
   2071 ?        Ssl    0:00 /usr/libexec/evolution-addressbook-factory<br>
   2133 pts/0    Ss     0:00 bash<br>
   2201 ?        Ssl    0:00 /usr/libexec/gvfsd-metadata<br>
   2204 ?        Sl     0:00 update-notifier<br>
   2261 pts/0    R+     0:00 ps x<br>
Дополнительный параметр **x** (без дефиса) сообщает команде **ps**, что та должна вывести все процессы, независимо от того, какие терминалы (если таковые имеются) управляют<br>
ими. Символ **?** в поле **TTY** указывает на отсутствие управляющего терминала. Таким образом параметр **x** позволяет увидеть все процессы в системе, которыми мы владеем.<br>
Так как в системе одновременно выполняется множество процессов, **ps** производит довольно длинные списки. Часто бывает полезно передать вывод **ps** команде **less**<br>
через конвейер, чтобы его проще было просматривать. Некоторые комбинации параметров приводят к выводу очень длинные строк.<br>
Столбец **STAT** - сокращение от state, столбец содержит информацию о текущем состоянии процесса.<br>
Состояния процессов:<br>
**R** -  выполняется. Процесс выполняется или готов к выполнению.<br>
**S** - приостановлен. Процесс временно не выполняется. Скорее всего, находится в ожидании опредленного события, такого как нажатие клавиши или прибытие сетевого пакета.<br>
**D** - приостановлен без возможности прерывания. Процесс ожидает завершения операции ввода/вывода, например, дисковым устройством.<br>
**T** - остановлен. Процесс принудительно остановлен.<br>
**Z** - недействующий процесс-зомби. Это дочерний процесс, который завершился, но не был удален родителем.<br>
**<** - высокоприоритетный процесс. Существует возможность наиболее важным процессам выделить больше процессорного времени. Данное свойство процесса называется **niceness**<br>
(уступчивость). Про процессы с более высоким приоритетом говорят, что они менее уступчивы, потому что потребляют больше процессорного времени, оставляя меньше другим<br>
процессам.<br>
**N** - низкоприоритетный процесс. Процесс с низким приоритетом (или уступчивый процесс) получает процессорное время только после того, как будут обслужены процессы с более<br>
высоким приоритетом.<br>
*catware@ubuntu:\~$ ps aux<br>
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND<br>
root           1  0.3  0.1 167656 11456 ?        Ss   16:38   0:05 /sbin/init au<br>
root           2  0.0  0.0      0     0 ?        S    16:38   0:00 [kthreadd]<br>
root           3  0.0  0.0      0     0 ?        I<   16:38   0:00 [rcu_gp]<br>
root           4  0.0  0.0      0     0 ?        I<   16:38   0:00 [rcu_par_gp]<br>
systemd+     872  0.0  0.1  23868 11960 ?        Ss   16:38   0:00 /lib/systemd/<br>
avahi        920  0.0  0.0   8528  3436 ?        Ss   16:38   0:00 avahi-daemon:<br>
root         921  0.0  0.0   9420  2940 ?        Ss   16:38   0:00 /usr/sbin/cro<br>
message+     923  0.0  0.0   9888  6328 ?        Ss   16:38   0:01 /usr/bin/dbus<br>
root         924  0.0  0.2 336024 19660 ?        Ssl  16:38   0:01 /usr/sbin/Net<br>
syslog       936  0.0  0.0 224352  5328 ?        Ssl  16:38   0:00 /usr/sbin/rsy<br>
root         937  0.2  0.4 1390836 38180 ?       Ssl  16:38   0:04 /usr/lib/snap<br>
avahi        964  0.0  0.0   8348   332 ?        S    16:38   0:00 avahi-daemon:<br>
whoopsie    1148  0.0  0.1 253120 15532 ?        Ssl  16:38   0:00 /usr/bin/whoo<br>
kernoops    1152  0.0  0.0  11260   440 ?        Ss   16:38   0:00 /usr/sbin/ker<br>
kernoops    1154  0.0  0.0  11260   444 ?        Ss   16:38   0:00 /usr/sbin/ker<br>
rtkit       1225  0.0  0.0 152936  2904 ?        SNsl 16:38   0:00 /usr/libexec/<br>
root        1328  0.0  0.1 252148  9632 ?        Ssl  16:38   0:00 /usr/lib/upow<br>
colord      1553  0.0  0.1 246196 14360 ?        Ssl  16:39   0:00 /usr/libexec/<br>
root        1583  0.0  0.1 314664  9852 ?        Sl   16:42   0:00 gdm-session-w<br>
catware     1596  0.0  0.1  19116 10312 ?        Ss   16:42   0:00 /lib/systemd/<br>
catware     2071  0.0  0.3 746916 29428 ?        Ssl  16:42   0:00 /usr/libexec/<br>
catware     2125  0.0  0.6 813220 49556 ?        Dsl  16:42   0:01 /usr/libexec/<br>
catware     2133  0.0  0.0  10616  4888 pts/0    Ss   16:42   0:00 bash<br>
root        2149  0.0  0.0      0     0 ?        I    16:43   0:00 [kworker/1:3-<br>
root        2197  0.0  0.0      0     0 ?        I    16:43   0:00 [kworker/5:0-<br>
catware     2201  0.0  0.0 162180  6180 ?        Ssl  16:43   0:00 /usr/libexec/<br>
catware     2204  0.0  0.4 460648 39668 ?        Sl   16:43   0:00 update-notifi<br>
root        2246  0.0  0.0      0     0 ?        I    16:43   0:00 [kworker/3:0-<br>
catware     2312  3.0  0.5 552568 44404 ?        Sl   17:05   0:00 /usr/bin/naut<br>
catware     2337  0.0  0.0  11496  3256 pts/0    R+   17:05   0:00 ps aux*<br>
Данная комбинация параметров выводит процессы, принадлежащие всем пользователям. При использовании параметров без начального дефиса команда действует "в стиле BSD".<br>
**USER** - идентификатор пользователя. Владелец процесса.<br>
**%CPU** - использование процессора в процентах.<br>
**%MEM** - использование памяти в процентах.<br>
**VSZ** - объем виртуальной памяти.<br>
**RSS** - размер страниц памяти. Объем физической памяти (ОЗУ), используемой процессом, кб.<br>
**START** - время запуска процесса. Для значений свыше 24 часов выводится дата.<br>
## top
Просмотр состояния процессов в динамике с помощью top. Она постоянно обновляет информацию о процессах (по умолчанию с периодом, равным 3 секундам), чтобы показать их<br>
активность с течением времени. Имя программы *top* отражает тот факт, что она используется для просмотра наиболее активных процессов в системе. Вывод команды **top**<br>
делится на две части: сводная информация о системе и таблица процессов, отсортированных по потреблению ими процессора:<br>
*catware@ubuntu:\~$ top<br>
top - 17:20:28 up 42 min,  1 user,  load average: 0.00, 0.00, 0.03<br>
Tasks: 335 total,   1 running, 334 sleeping,   0 stopped,   0 zombie<br>
%Cpu(s):  0.1 us,  0.1 sy,  0.0 ni, 99.7 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st<br>
MiB Mem :   7915.3 total,   6322.5 free,    907.0 used,    685.9 buff/cache<br>
MiB Swap:    923.3 total,    923.3 free,      0.0 used.   6758.1 avail Mem<br> 
    PID USER      PR  NI    VIRT    RES    SHR S  %CPU  %MEM     TIME+ COMMAND<br>                                            
   1685 catware   20   0  294460  65048  40332 S   6.3   0.8   0:11.14 Xorg<br>                                               
   1818 catware   20   0 4395092 262080 104248 S   5.3   3.2   0:20.23 gnome-shell<br>                                        
   2125 catware   20   0  814692  50292  38544 S   3.0   0.6   0:03.54 gnome-terminal-<br>                                    
   1966 catware   20   0  287872  37352  29584 S   0.7   0.5   0:06.73 vmtoolsd<br>                                           
    457 root     -51   0       0      0      0 S   0.3   0.0   0:00.44 irq/16-vmwgfx<br>                                      
   2247 root      20   0       0      0      0 I   0.3   0.0   0:00.14 kworker/4:0-events<br>                                 
   2418 catware   20   0   12092   4024   3112 R   0.3   0.0   0:00.08 top<br>                                                
      1 root      20   0  167656  11456   8304 S   0.0   0.1   0:05.37 systemd<br>                                            
      2 root      20   0       0      0      0 S   0.0   0.0   0:00.07 kthreadd<br>                                           
      3 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 rcu_gp<br>                                             
      4 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 rcu_par_gp<br>                                         
      6 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/0:0H-events_highpri<br>                        
      9 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 mm_percpu_wq<br>                                       
     10 root      20   0       0      0      0 S   0.0   0.0   0:00.00 rcu_tasks_rude_<br>                                    
     11 root      20   0       0      0      0 S   0.0   0.0   0:00.00 rcu_tasks_trace<br>                                    
     12 root      20   0       0      0      0 S   0.0   0.0   0:00.03 ksoftirqd/0<br>                                        
     13 root      20   0       0      0      0 I   0.0   0.0   0:01.56 rcu_sched<br>                                          
     14 root      rt   0       0      0      0 S   0.0   0.0   0:00.07 migration/0*<br>
**top** - имя программы<br>
**17:20:28** - текущее время<br>
**up 42 min** - это поле называется uptime (продолжительность работы). Показывает время, прошедшее с момента последней загрузки системы. В данном примере система<br> проработала 42 минуты<br>
**1 user** - в системе работают два пользователя<br>
**load average** - средняя нагрузка - это число процессов, ожидающих возобновления работы, т.е. число процессов в состоянии "выполняется" и совместно использующих<br>
процессор. Здесь показаны три значения для разных интервалов времени. Первое значение отражает среднюю нагрузку за последние 60 секунд, второе - за последние<br>
5 минут и третье - за последние 15 минут. Значения ниже 1,0 сообщают, что система не нагружена.<br>
**Tasks** - суммарное число процессов в разных состояниях<br>
**0.1 us** - 0.1% процессорного времени затрачено на выполнение пользовательских процессов.<br>
**0.1 sy** - 0.1% процессорного времени затрачено на выполнение системных процессов.<br>
**0.0 ni** - 0.0% процессорного времени затрачено на выполнение уступчивых (nice), то есть низкоприоритетных процессов.<br>
**99.7 id** - 99.7% процессорного времени составили простои.<br>
**Mem** - объем использованной физической памяти (ОЗУ).<br>
**Swap** - объем использованного пространства в файле подкачки (виртуальная память).<br>
## kill
Используется для завершения процессов. Позволяет принудительно завершить выполнение вышедшей из-под контроля программы, отвергающей любые другие попытки закрыть ее.<br>
*catware@ubuntu:\~$ xlogo &<br>
[1] 12508<br>
catware@ubuntu:~$ kill 12508*<br>
Наиболее часто используемые сигналы
**1** - HUP - Обрыв связи. Пережиток старых добрых времен, когда терминалы подключались к удаленным компьютерам посредством телефонных линий и модемов<br>
Этот сигнал используется, чтобы подсказать программе, что потеряна связь с управляющим терминалом. Действие этого сигнала можно продемонстрировать, закрыв окно<br>
терминала. Программа переднего плана, запущенная в терминале, получит сигнал и завершится. Также этот сигнал используется многими программами-демонами для<br> повторной инициализации. То есть когда программа-демон получает этот сигнал, она перезапускается и повторно читает свои конфигурационные файлы. Веб-сервер Apache,<br>
например, как раз такая программа-демон, она именно так реагирует на сигнал HUP.<br>
**2** - INT - Прервать. Выполняет ту же функцию, что и нажатие комбинации CTRL+C в терминале. Обычно приводит к завершению программы.<br>
**9** - KILL - Уничтожить. Это специальный сигнал. В большинстве случаев программы сами могут решать, как реагировать на сигналы, вплоть до полного их<br> игнорирования, но сигнал KILL в действительности никогда не передается целевой программе. Вместо этого ядро немедленно завершает указанный процесс. Когда процесс<br>
завершается таким способом, он не имеет возможности "прибрать за собой" или сохранить результаты своей работы. По этой причине сигнал KILL следует использовать<br>
только как крайнее средство, когда другие сигналы на завершение программы не приводят к желаемому результату.<br>
**15** - TERM - Завершить. Это сигнал по умолчанию, посылаемый командой kill. Если программа достаточно "живая", чтобы принять этот сигнал, она завершится.<br>
**18** - CONT - Продолжить. Этот сигнал восстанавливает нормальную работу процесса после сигнала STOP.
**19** - STOP - Приостановить. Этот сигнал заставляет процесс приостановиться, не завершаясь. Подобно сигналу KILL, он не передается целевому процессу и потому не<br>
может быть проигнорирован им.<br>
**20** - TSTP - Сигнал "стоп" с клавиатуры. Этот сигнал посылается терминалом после нажатия комбинации CTRL+Z. В отличие от сигнала STOP, TSTP передается<br> программе, и программа может решить игнорировать его.<br>
**3** - QUIT - Выйти.<br>
**11** - SEGV - Ошибка сегментации. Этот сигнал посылается программе, предпринявшей попытку недопустимого обращения к памяти, т.е. попытку выполнить<br>
запись в память, доступ к которой запрещен.<br>
**28** - WINCH - Изменение окна. Этот сигнал посылается системой при изменении размеров окна терминала. Некоторые программы, такие как top и less, реагируют<br>
на этот сигнал, обновляя свой вывод в соответствии с новыми размерами окна терминала.<br>
## killall
Посылка сигналов нескольким процессам. 
*catware@ubuntu:\~$ xlogo &<br>
[1] 3485<br>
catware@ubuntu:\~$ xlogo &<br>
[2] 3486<br>
catware@ubuntu:\~$ killall xlogo<br>
catware@ubuntu:\~$<br>
[1]-  Terminated              xlogo<br>
[2]+  Terminated              xlogo*<br>
## ping
Команда ping посылает специальные сетевые пакеты ICMP ECHO_REQUEST указанному сетевому узлу. Большинство сетевых устройств принимает эти пакеты и отвечат на них, <br>
\- это позволяет проверить сетевые соединения.<br>
*catware@srvubuntu:~$ ping linuxcommand.org<br>
PING linuxcommand.org (216.105.38.11) 56(84) bytes of data.<br>
64 bytes from secureprojects.sourceforge.net (216.105.38.11): icmp_seq=1 ttl=128 time=183 ms<br>
64 bytes from secureprojects.sourceforge.net (216.105.38.11): icmp_seq=3 ttl=128 time=190 ms<br>
64 bytes from secureprojects.sourceforge.net (216.105.38.11): icmp_seq=4 ttl=128 time=180 ms<br>
64 bytes from secureprojects.sourceforge.net (216.105.38.11): icmp_seq=5 ttl=128 time=181 ms<br>
64 bytes from secureprojects.sourceforge.net (216.105.38.11): icmp_seq=6 ttl=128 time=180 ms<br>
--- linuxcommand.org ping statistics ---<br>
6 packets transmitted, 5 received, 16,6667% packet loss, time 5047ms<br>
rtt min/avg/max/mdev = 179.977/182.712/189.586/3.632 ms*<br>
## traceroute
Программа traceroute выводит список всех "переходов" (hops) на пути сетевого трафика между локальной системой и указанным узлом сети. Например, увидеть, как<br>
выглядит маршрут к сайту https://ya.ru:<br>
*catware@srvubuntu:~$ traceroute ya.ru<br>
traceroute to ya.ru (87.250.250.242), 30 hops max, 60 byte packets<br>
 1  _gateway (192.168.121.2)  0.228 ms  0.285 ms  0.210 ms<br>
 2  \* \* \*<br>
 3  \* \* \*<br>
 4  \* \* \*<br>
 5  \* \* \*<br>
 6  \* \* \*<br>
 7  \* \* \*<br>
 8  \* \* \*<br>
 9  \* \* \*<br>
10  \* \* \**<br>
\* - означает что маршрутизатор не предоставляет идентификационной информации. Иногда это можно преодолеть через параметр **-T** или **-I**.<br>
## ip
Многофункциональный инструмент для настройки параметров подключения к сети, пришла на замену устаревшей команды **ifconfig**. С помощью **ip** можно исследовать<br>
сетевые интерфейсы и таблицу маршрутизации системы.<br>
*catware@srvubuntu:~$ ip a<br>
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000<br>
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00<br>
    inet 127.0.0.1/8 scope host lo<br>
       valid_lft forever preferred_lft forever<br>
    inet6 ::1/128 scope host<br>
       valid_lft forever preferred_lft forever<br>
2: ens32: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000<br>
    link/ether 00:0c:29:7f:49:3c brd ff:ff:ff:ff:ff:ff<br>
    inet 192.168.121.33/24 brd 192.168.121.255 scope global ens32<br>
       valid_lft forever preferred_lft forever<br>
    inet6 fe80::20c:29ff:fe7f:493c/64 scope link<br>
       valid_lft forever preferred_lft forever<br>
3: yes: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue state UP group default qlen 1000<br>
    link/ether 00:16:3e:ed:3c:a6 brd ff:ff:ff:ff:ff:ff<br>
    inet 10.146.218.1/24 scope global yes<br>
       valid_lft forever preferred_lft forever<br>
    inet6 fd42:4123:b051:de38::1/64 scope global<br>
       valid_lft forever preferred_lft forever<br>
    inet6 fe80::216:3eff:feed:3ca6/64 scope link<br>
       valid_lft forever preferred_lft forever<br>
5: veth7696af45@if4: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue master yes state UP group default qlen 1000<br>
    link/ether 2a:18:69:e7:56:2f brd ff:ff:ff:ff:ff:ff link-netnsid 0*<br>
Выполняя причинно-следственную диагностику, первое, на что следует обратить внимание, - наличие слова UP в первой строке с информацией о каждом интерфейсе,<br>
указывающего, что сетевой интерфейс включен, и присутствие допустимого IP-адреса в поле inet в третьей строке. Для систем использующих DHCP (протокол<br>
динамической настройки хостов), наличие IP адреса в этом поле подтвердит нормальную работу DHCP.<br>
## netstat
Используется для исследования различных настроек сети и статистик. С помощью множества параметров этой команды можно просматривать самые разные аспекты<br>
настройки сети. С помощью параметра **-ie**, например, можно исследовать сетевые интерфейсы в системе:<br>
*catware@ubuntu:~$ netstat -ie<br>
Kernel Interface table<br>
ens33: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500<br>
        inet 192.168.121.128  netmask 255.255.255.0  broadcast 192.168.121.255<br>
        inet6 fe80::e286:3a2c:deae:d7ec  prefixlen 64  scopeid 0x20\<link><br>
        ether 00:0c:29:84:c1:fc  txqueuelen 1000  (Ethernet)<br>
        RX packets 103385  bytes 150638051 (150.6 MB)<br>
        RX errors 0  dropped 0  overruns 0  frame 0<br>
        TX packets 50161  bytes 3118433 (3.1 MB)<br>
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0<br>
lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536<br>
        inet 127.0.0.1  netmask 255.0.0.0<br>
        inet6 ::1  prefixlen 128  scopeid 0x10\<host><br>
        loop  txqueuelen 1000  (Local Loopback)<br>
        RX packets 846  bytes 75522 (75.5 KB)<br>
        RX errors 0  dropped 0  overruns 0  frame 0<br>
        TX packets 846  bytes 75522 (75.5 KB)<br>
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0*<br>
Использование параметра **-r** позволит получить таблицу маршрутизации ядра. По этой таблице можно судить, как настроена передача пакетов между сетями.<br>
*сatware@ubuntu:~$ netstat -r<br>
Kernel IP routing table<br>
Destination     Gateway         Genmask         Flags   MSS Window  irtt Iface<br>
default         _gateway        0.0.0.0         UG        0 0          0 ens33<br>
link-local      0.0.0.0         255.255.0.0     U         0 0          0 ens33<br>
192.168.121.0   0.0.0.0         255.255.255.0   U         0 0          0 ens33*<br>
## locate
Выполняет быстрый поиск в базе данных имен файлов и выводит все имена, соответствующие искомой строке. Доступим необходимо найти все программами с именами,<br>
начинающимися с zip. Поскольку требуется найти программы, можно предположить, что имя каталога с программами оканчивается на bin/.<br>
*catware@srvubuntu:~$ mlocate bin/zip<br>
/usr/bin/zipdetails*<br>
## find
Сложный способ поиска файлов. В отличие от программы locate, выполняющей поиск файлов по именам, программа **find** ищет файлы согласно заданным атрибутам в<br>
указанном каталоге (и во вложенных подкаталогах).<br>
В простейших случаях программе **find** можно передать одно или несколько имен каталогов для поиска. Например, с ее помощью можно получить список содержимого<br>
домашнего каталога:<br>
*catware@srvubuntu:\~$ find \~<br>
/home/catware<br>
/home/catware/.ansible<br>
/home/catware/.ansible/tmp<br>
/home/catware/.ansible/cp<br>
/home/catware/.ssh<br>
/home/catware/.ssh/known_hosts<br>
/home/catware/.ssh/authorized_keys<br>
/home/catware/.bash_logout<br>
/home/catware/bash_scripts<br>
/home/catware/bash_scripts/test.sh<br>
/home/catware/.bashrc<br>
/home/catware/.profile<br>
/home/catware/snap<br>
/home/catware/snap/lxd<br>
/home/catware/snap/lxd/22526<br>
/home/catware/snap/lxd/22526/.local<br>
/home/catware/snap/lxd/22526/.local/share<br>
/home/catware/snap/lxd/22526/.local/share/nano<br>
/home/catware/snap/lxd/current<br>
/home/catware/snap/lxd/22753<br>
/home/catware/snap/lxd/22753/.local<br>
/home/catware/snap/lxd/22753/.local/share<br>
/home/catware/snap/lxd/22753/.local/share/nano<br>
/home/catware/snap/lxd/common<br>
/home/catware/snap/lxd/common/config<br>
/home/catware/snap/lxd/common/config/config.yml*<br>
Подсчитаем число файлов:<br>
*catware@srvubuntu:\~$ find \~ | wc -l<br>
222*<br>
Команду **find** можно использовать для поиска файлов, соответствующих определенным критериям. Она делает посредством применения *проверок*,*операций*<br
и *параметров*.<br>
Допустим мы хотим получить список каталогв:
*catware@srvubuntu:\~$ find \~ -type d | wc -l<br>
99*<br>
Добавив проверку **-type d**, ограничиваемся только поиском каталогов. Также можно ограничить поиск только обычными файлами:<br>
*catware@srvubuntu:\~$ find \~ -type f | wc -l
122*<br>
Проверки типо файлов в find:<br>
**b** - специальный файл блочного устройства<br>
**с** - специальный файл символьного устройства<br>
**d** - каталог<br>
**f** - обычный файл<br>
**l** - символическая ссылка<br>
Добавив дополнительные проверки, можно выполнять поиск файлов по размеру и имени. Найдем все обычные файлы с именами, соответствующими шаблону \*.txt, и<br>
имеющие размер больше 1 килобайта:
*catware@ubuntu:~$ find ~ -type f -name "*.txt" -size +1k | wc -l<br>
10*<br>
Тут добавлена проверка **-name** с шаблоном имени файла, затем добавлена проверка **-size** со строкой **+1k**. Начальный символ **+** указывает, что требуется<br>
искать файлы, размер которых превышает указанное число. Начальный символ **-** изменил бы значение строки на противоположное - меньше указанного числа.<br>
Единицы измерения, поддерживаемые командой **find**:<br>
**b** - блоки размером по 512 байт (используется по умолчание, если иное не указано явно)<br>
**c** - байты<br>
**w** - 2-байтные слова<br>
**k** - килобайты (блоки по 1024 байт)<br>
**M** - мегабайты (блоки по 1 048 576 байт)<br>
**G** - гигабайты (блоки по 1 073 741 824 байт)<br>
Проверки:<br>
**-cmin n** - соответствует файлам или каталогам, содержимое или атрибуты которых последний раз изменялись точно n минут назад. Чтобы выразить условие<br>
"менее n минут назад", необходимо использовать **-n**, чтобы выразить условие "более n минут назад", необходимо использовать **+n**.<br>
**-cnewer имя** - соответствует файлам или каталогам, содержимое или атрибуты которых последний раз изменялись позже, чем у файла с указанным именем.<br>
**-ctime n** - соответствует файлам или каталогам, содержимое или атрибуты (т.е. разрешения) которых последний раз изменялись более чем n\*24 часов назад.<br>
**-empty** - соответствует пустым файлам и каталогам.<br>
**-group группа** - соотвествует файлам или каталогам, принадлежащим указанной группе. Группа может задаваться именем или числовым идентификатором группы.<br>
**-iname шаблон** - действует так же, как проверка -name, но различает регистр символов.<br>
**-inum n** - соответствует файлам с номером индексоного узла (inode) n. Эту проверку удобно использовать для поиска всех жестких ссылок на определенный индексный<br>
узел.<br>
**-mmin n** - соответствует файлам или каталогам, содержимое которых последний раз изменялось n минут назад.<br>
**-mtime n** - соответствует файлам или каталогам, содержимое которых последний раз изменялось n*24 часов назад.<br>
**-name шаблон** - соответствует файлам или каталогам, имена которых совпадают с заданным шаблоном.<br>
**-newer имя** - соответствует файлам или каталогам, содержимое которых последний раз изменялось позже, чем у файла с указанным имененм. Эта проверка может<br>
пригодится в сценариях, выполняющих резервное копирование файлов. Каждый раз, в процессе создания резервной копии, можно обновлять файл (например файл журнала)<br>
и затем с помощью **find** определять, какие файлы изменились с момента последнего обновления.<br>
**-nouser** - соответствует файлам и каталогам, не принадлежащим какому-либо допустимому пользователю. Эту проверку можно использовать для поиска файлов, <br>
принадлежащих удаленным учетным записям, или для обнаружения следова злоумышленников.<br>
**-nogroup** - соответствует файлам и каталогм, не принадлежащим какой-либо допустимой группе.<br>
**-perm режим** - соответствует файлам или каталогам с указанным режимом доступа. Режим может задаваться восьмеричным числом или иметь символическую форму.<br>
**-samefile имя** - действует также как и проверка **-inum**. Соответсвтует файлам с тем же номером индексного узла (inode), что и файл с указанным именем.<br>
**-size n** - соответствует файлам с размером n.<br>
**-type c** - соответствует файлам с типом с.<br>
**-user имя** - соответствует файлам или каталогам, принадлежащим пользователю с указанным именем. Аргумент имя может быть именем или числовым идентификатором<br>
пользователя.<br>
Для определения логических отношений между проверками в команде **find** используются операторы. Например, в некотором каталоге мы хотим найти все файлы<br>
и подкаталоги с небезопасными разрешениями. Для этого можно было бы выполнить поиск всех файлов с разрешениями, отличающимися от 0600, и каталогов с разрешениями,<br>
отличающимися от 0700. **find** поддерживает возможность комбинирования проверок с помощью логических операторов с целью определить более сложные критерии отбора.<br>
Выразить вышеупомянутую проверку можно так:
*catware@ubuntu:~$ find ~ \( -type f -not -perm 0600 \) -or \( -type d -not -perm 0700 \)<br>
/home/catware<br>
/home/catware/Templates<br>
/home/catware/foo.txt<br>
/home/catware/.bash_logout<br>
/home/catware/newdir<br>
/home/catware/newdir/file1<br>
/home/catware/newdir/file2*<br>
Логические операторы команды find:<br>
**-and** - соотвествует, если выполняются условия в проверках с обеих сторон от оператора. Можно сократить до -a. **В отсутствие операторов по умолчанию<br> подразумевается как -and**.<br>
**-or** - соотвествует, если выполняется условие с одной из сторон от оператора. Можно сократить до -o.<br>
**-not** - соответствует, если условие в проверке, следующей за оператором, не выполняется. Можно сократить до -!.<br>
**()** - группируеют проверки и операторы для формирования крупных выражений. Используются для управления порядком проверок. По умолчанию проверки выполняются<br>
слева на право. Часто используются для изменения порядка проверок по умолчанию, чтобы получить желаемый результат. Даже если скобки не нужны, иногда полезно<br>
включать их, чтобы сделать команды более наглядными. Круглые скобки имеют специальное значение для командной оболочки, поэтому их нужно экранировать, чтобы они<br>
были переданы команде find как аргументы. Экранируются через обратный слеш.<br>
**find** позволяет выполнять наши операции, основываясь на результатах поиска. Предопределенные операции, поддерживаемые команды find:<br>
**-delete** - удаляет текущий найденный файл<br>
**-ls** - действует эквивалентно команде ls<br>
**-print** - выводит полный путь к найденному файлу в стандартный вывод. Эта операция выполняется по умолчанию, если не указана никакая другая.<br>
**-quit** - завершает выполнение команды после обнаружения первого совпадения.<br>
*catware@ubuntu:~$ find ~ -type f -and -name '*.txt' -and -print<br>
/home/catware/foo.txt<br>
/home/catware/.mozilla/firefox/h3jbtdk1.default-release/SecurityPreloadState.txt<br>
/home/catware/ls-result.txt<br>
/home/catware/snap/chromium/common/chromium/ZxcvbnData/1/english_wikipedia.txt<br>
/home/catware/snap/chromium/common/chromium/ZxcvbnData/1/passwords.txt<br>
/home/catware/snap/chromium/common/chromium/ZxcvbnData/1/male_names.txt<br>
/home/catware/snap/chromium/common/chromium/ZxcvbnData/1/surnames.txt<br>
/home/catware/snap/chromium/common/chromium/ZxcvbnData/1/us_tv_and_film.txt<br>
/home/catware/snap/chromium/common/chromium/ZxcvbnData/1/female_names.txt<br>
/home/catware/snap/chromium/common/chromium/Subresource Filter/Unindexed Rules/9.34.0/LICENSE.txt<br>
/home/catware/snap/chromium/1944/.pki/nssdb/pkcs11.txt<br>
/home/catware/ls.txt<br>
/home/catware/.cache/tracker/locale-for-miner-apps.txt<br>
/home/catware/.cache/tracker/last-crawl.txt<br>
/home/catware/.cache/tracker/parser-version.txt<br>
/home/catware/.cache/tracker/db-version.txt<br>
/home/catware/.cache/tracker/db-locale.txt<br>
/home/catware/.cache/tracker/first-index.txt*<br>
Помимо предопределенных операций можно также вызывать произвольные команды. С этой целью используется операция **-exec**, что показано ниже:<br>
**-exec *команда* \{} ;**, где **команда** - это имя команды, {} - символическое представление текущего пути к файлу и точка с запятой - обязательный разделитель,<br>
обозначающий конец команды. Следующий пример демонстрирует использование **-exec** для получения эффекта, аналогичного операции **-delete**:<br>
**-exec rm '{}' ';'**<br>
Если заменить операцию **-exec** операцией **-ok**, перед выполнением каждой указанной команды будет выводиться запрос:<br>
*catware@ubuntu:\~$ find ~ -type f -name 'foo\*' -ok ls -l '{}' ';'<br>
< ls ... /home/catware/foo.txt > ? y<br>
-rw-rw-r-- 1 catware catware 189 Mar 17 11:40 /home/catware/foo.txt*<br>
