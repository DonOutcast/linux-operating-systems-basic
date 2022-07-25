## Part1. Установка ОС

1. ![Check Ubuntu version](/images/cron1.png)

## Part2. Создание пользователя

1. Создагие нового пользователя дать ему права для прочтения логов
![Creating user](/images/cron2.png)

2. Вывести информацию о пользователи с командой cat /etc/passwd
![The new user](/images/cron3.png)

## Part3. Настройка сети ОС

1. Изменить имя машины на user-1 
![madchine name is a user-1](/images/cron4.png)

2. Установка временной зоны соотвутсвующей моей
![timezone](/images/cron5.png)

3. Название ситевых интерфейсов  с помощью консольной команды ip a
![loopback](/images/cron6.png)

4. loopback (коротко говоря lo) — это аппаратный или программный метод, который направляет полученный сигнал или данные обратно отправителю. Он используется как дополнительное средство в исправлении проблем физического соединения.

5. С помощью команды ip a получаем ip адресс устройства 
![ip](/images/cron7.png)

6. DHCP - это клиент-серверный протокол динамической конфигурации хоста (Dynamic Host Configuration Protocol), с помощью которого в ИТ-инфраструктуре сетевые параметры каждого нового устройства прописываются автоматически. Использование DHCP существенно упрощает работу системных администраторов в случаях расширения сети.
7. Определить и вывести на экран внешний ip-адрес шлюза (ip) и внутренний IP-адрес шлюза, он же ip-адрес по умолчанию (gw).
![ip-adress](/images/cron7.png)

8.  Задать статичные (заданные вручную, а не полученные от DHCP сервера) настройки ip, gw, dns
![change ip, gw, dns](/images/cron8.png)
9. Перезагрузить виртуальную машину командой ребут, убедитесь что заданные статичные сетивые настройки соответсвуют заданным в предыдущем пункте.
![reboot](/images/cron9.png)

10. Успешно пропиговать хосты 1.1.1.1 и ya.
![ping](/images/cron10.png)

## Part 4. Обнавление ОС.

1. Обновление системы командами apdate и upgrade
![upgrade system](/images/cron11.png)

## Part 5. Использование команды sudo.
- Команда sudo ( substitute user and do, подменить пользователя и выполнить ) позволяет строго определенным пользователям выполнять указанные программы с административными привилегиями без ввода пароля суперпользователя root.
1. Разрешить пользователю, созданному в [Part 2](#part-2), выполнять команду sudo.
![usermod](/images/cron12.png)

2. Поменять hostname ОС от имени пользователя, созданного в пункте [Part 2](#part-2-создание-пользователя). (используя sudo).
- Вставить скрин с изменённым hostname в отчёт.
![change hostname](/images/cron12.png)
## Part 6. Установка и настройка службы времени.
- Устанавливаем Network time protocol `sudo apt install ntp`
- Вывод времени часового пояса в котором  я сейчас нахожусь
![show time](/images/cron13.png)

## Part 7. Установка и использование текстовых редакторов
- Установка текстового редактора vim `sudo apt install vim`
- Установка текстового редактора nano `sudo apt install nano`
- Установка текстового редактора mcedit `sudo apt install mc`
- Создане файла test_vim.txt  `sudo vim test_vim.txt`, для выхода из редактора с сохранением `Esc`, `:`, `wq`.
![test_vim](/images/cron14.png)
- Создание текстового файла test_nano.txt `sudo nano test_nano.txt`, для выхода из редактора с сохранением `Ctrl+0`, `Ctrl+x`
![test_nano](/images/cron15.png)
- Создание текстого файла test_mcedi.txt `sudo mcedit test_mcedit.txt` для выхода из редактора с сохранением `F-2`, `F-10`
![test_mcedit](/images/cron16.png)
 - Открытие файла test_vim.txt `sudo vim test_vim.txt`, `R` для редактирования `i`, для выхода из файла без сохраненией `Esc`, `:`, `q`
 ![edit_vim](/images/cron17.png)
 - Вывод содержимого `cat test_vim.txt`
 ![cat_vim](/images/cron18.png)
 - Открытие файла test_nano.txt `sudo nano test_nano.txt`, для редактирования, выходим без сохранения `Ctrl+X`, `n`
 ![edit_nano](/images/cron19.png)
 - Вывод содержимого `cat test_nano.txt`
  ![cat_nano](/images/cron20.png)
 -  Открытие файла test_mcedit.txt, `sudo mcedit test_mcedit.txt`, для редакттрования, выходим без сохранения `F-10`
 ![edit_mcedit](/images/cron21.png)
 - Вывдо содержимого файла `cat test_mcedit.txt`
 ![cat_mcedit](/images/cron22.png)
 - Открытие файла `sudo vim test_vim_txt`, поиск слова и замена искоемого `:/School`
 ![serach_vim](/images/cron23.png)
 - Команда для замены искоемого слова `:s/School/Shamil`
 ![cahnge_vim](/images/cron24.png)
 - Открытие файла `sudo nano test_nano.txt`, поиск слова `Ctrl + W`
 ![search_nano](/images/cron25.png)
 - Комада для замены искоемого слова `CTRL + R`, `new word`, `Y`
 ![change_nano](/images/cron26.png)
 - Открытие файла `sudo mcedit test_mcedit.txt`, поиск слова `F-7`
 ![search_mceditor](/images/cron27.png)
 - Команда для замены исвкоемого слова `F-4`, `replace`
 ![change_mceditor](/images/cron28.png)

 ## Part 8. Установка и базовая настройка сервиса SSHD
 - Установить пакет openssh `sudo apt install openssh-server`
 - Добавьте пакет SSH-сервера в автозагрузку `sudo systemctl enable sshd`
 - Проверьте работу SSH `systemctl status sshd `
 - Изиенение порта на 2022 `sudo vim /etc/ssh/sshd_config`
 - С помощью команды ps показать наличие sshd 
 ![ps sshd](/images/cron29.png)
 - ключ -С который фильтрует по имени процесса -A, -e, (a) - выбрать все процессы;
-a - выбрать все процессы, кроме фоновых;
-d, (g) - выбрать все процессы, даже фоновые, кроме процессов сессий;
-N - выбрать все процессы кроме указанных;
-С - выбирать процессы по имени команды;
-G - выбрать процессы по ID группы;
-p, (p) - выбрать процессы PID;
--ppid - выбрать процессы по PID родительского процесса;
-s - выбрать процессы по ID сессии;
-t, (t) - выбрать процессы по tty;
-u, (U) - выбрать процессы пользователя.
Опции форматирования:
-с - отображать информацию планировщика;
-f - вывести максимум доступных данных, например, количество потоков;
-F - аналогично -f, только выводит ещё больше данных;
-l - длинный формат вывода;
-j, (j) - вывести процессы в стиле Jobs, минимум информации;
-M, (Z) - добавить информацию о безопасности;
-o, (o) - позволяет определить свой формат вывода;
--sort, (k) - выполнять сортировку по указанной колонке;
-L, (H)- отображать потоки процессов в колонках LWP и NLWP;
-m, (m) - вывести потоки после процесса;
-V, (V) - вывести информацию о версии;
-H - отображать дерево процессов;
- Вывод команды netstat -tan должен содержать
![net-tools](/images/cron30.png)
-n служит для печати IP-адресов вместо имен хостов;
-a показывает состояние всех сокетов; 
-t показывает только tcp соединения;
Значения столбцов:
Proto - протокол, используемый сокетом;
Recv-Q - количество байтов, не скопированных пользовательской программой, подключенной к этому сокету;
Local Address - локальный адрес (имя локального хоста) и номер порта сокета
Foreign Address - удаленный адрес (имя удаленного хоста) и номер порта сокета
State - состояние сокета
0.0.0.0 в этом контексте означает "все IP-адреса на локальной машине"
## Part 9.  Установка и запуск утилиты top и htop.
top - интерактивный просмотрщик процессов. htop аналог top.
1. 
![top](/images/cron31.png)
- uptime 31
- авторизовано 1 user
- total system load 0,00
- total number of processes 96
- cpu load  0.0
- memory load 147.6
- pid процессора занимающего больше всего памяти `shift + m` 645 root
- pid процесса занимающего больше всего проыессорного времени 1336 
2. 
![htop](/images/cron31.png)
- Отчёт отсортированный по PID
![PID](/images/cron32.png)
- Отчёь отсортированный по PERCENT_CPU
![CPU](/images/cron33.png)
-  Отчёт отсортированный по PERCENT_MEM,
![PERCENT_MEM](/images/cron34.png)
- Отчёт отсортированный по TIME
![TIME](/images/cron35.png)
- Отчёт отфильтрованный по sshd
![filter_sshd]!(/images/cron36.png)
- Отчёт отфильтрованынй по syslog
![filter_syslog](/images/cron37.png)
- Отчёт с добавлением hostname , clock. uptime
![clock, uptime, hostname](/images/cron38.png)

## Part 10. fdisk

1. Запустите команду fdisk -l
![fdisk](/images/cron39.png)
- Disk model: VBOX HARDDISK
- 11.2 GiB, 11830034432 bytes
- 23105536 sectors
- Swap: 0B 

## Part 11. df

1. Запустить команду df 
![df](/images/cron40.png)
- size 10255636
- used 4642228
- available 5072736
- Use% 48%
- 1k-blocks

2. Запустить команду df -Th
![df -Th](/images/cron41.png)
- size 9.8G
- used 4.5G
- avail 4.9G
- Use% 48%
- Type ext4

## Part 12. du
1. Запустите команду du
![du](/images/cron42.png)
- Вывести размер папок /home, /var, /var/log (в байтах, в человекочитаемом виде)
![du/home](/images/cron43.png)
![du/var](/images/cron44.png)
![du/var/log](/images/cron45.png)
- Вывести размер всего содержимого в /var/log (не общее, а каждого вложенного элемента, используя *)
![*](/images/cron46.png)
## Part 13. ncdu
1. Устанавливаем утилиту ncdu `sudo apt install ncdu`
2. Вывести размер папок /home, /var, /var/log.
![ncdu home](/images/cron47.png)
![ncdu var](/images/cron48.png)
![ncdu var/log](/images/cron49.png)
## Part 14. Работа с системными журналами. 

1. Написать в отчёте время последней успешной авторизации, имя пользователя и метод входа в систему.
![systems](/images/cron50.png)
- Время авторизации: 20 июня, 14:48
- Имя пользователя: don
- Метод входа в систему: tty1
Перезапустить службу SSHd: sudo /etc/init.d/ssh restart
2. Сообщение о рестарте службы: sudo cat /var/log/syslog
![restart](/images/cron51.png)
## Part 15. CRON
1. 
2. Используя планировщик заданий, запустите команду uptime через каждые 2 минуты
![cron3](/images/cron54.png)
3. Найти в системных журналах строчки (минимум две в заданном временном диапазоне) о выполнении.
![crontab](/images/cron52.png)
4. В отчёт вставьте скрин со списком текущих заданий для CRON.
![no crontab](/images/cron53.png)