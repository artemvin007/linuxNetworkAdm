# D02_Linux_Network

## **== Задание 1==**

### Подними виртуальную машину (далее -- ws1)

### 1.1. Сети и маски

### Определи и запиши в отчёт:

### 1) Адрес сети *192.167.38.54/13*

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled.png)

Скриншот 1 - адрес сети

### 2) Перевод маски *255.255.255.0* в префиксную и двоичную запись, */15* в обычную и двоичную, *11111111.11111111.11111111.11110000* в обычную и префиксную

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%201.png)

Скриншот 2 - 255.255.255.0 в префиксной и двоичной записи 

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%202.png)

Скриншот 3 - /15 в обычном и двоичном виде

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%203.png)

Скриншот 4 - *11111111.11111111.11111111.11110000* в обычной и префиксной форме

*11111111.11111111.11111111.11110000*  в префиксном виде выглят, как /28 поскольку составляет 3 полных октета и ещё 4 бита

### 3) Минимальный и максимальный хост в сети *12.167.38.4* при масках: */8*, *11111111.11111111.00000000.00000000*, *255.255.254.0* и */4*

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%204.png)

Скриншот 5 - Минимальный и максимальный хост в сети *12.167.38.4* при маске */8*

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%205.png)

Скриншот 6 - Минимальный и максимальный хост в сети *12.167.38.4* при маске *11111111.11111111.00000000.000000*

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%206.png)

Скриншот 6 - Минимальный и максимальный хост в сети *12.167.38.4* при маске /4

### 1.2. localhost

### Определи и запиши в отчёт, можно ли обратиться к приложению, работающему на localhost, со следующими IP: *194.34.23.100*, *127.0.0.2*, *127.1.0.1*, *128.0.0.1*

*194.34.23.100 - нет*

*127.0.0.2 - да*

*127.1.0.1 - да*

*128.0.0.1 - нет*

Те адреса, к которым можно обратиться имеют строчку loopback в выводе ipcalc

### 1.3. Диапазоны и сегменты сетей

### Определи и запиши в отчёт:

### 1) Какие из перечисленных IP можно использовать в качестве публичного, а какие только в качестве частных:

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%207.png)

Скриншот 7 - Вывод ipcalc с частным ip

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%208.png)

Сркиншот 8 - Вывод ipcalc с публичными ip

*10.0.0.45 - частный*

*134.43.0.2 - публичный*

*192.168.4.2 - частный*

*172.20.250.4 - частный*

1*72.0.2.1 - публичный*

*192.172.0.1- публичный*

*172.68.0.2 - публичный*

*172.16.255.255 - частный*

*10.10.10.10 - частный*

*192.169.168.1 - публичный*

### 2) Какие из перечисленных IP адресов шлюза возможны у сети *10.10.0.0/18*: *10.0.0.1*, *10.10.0.2*, *10.10.10.10*, *10.10.100.1*, *10.10.1.255*

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%209.png)

Скриншот 9 - HostMin и HostMax данной сети

Видим, что ip в сети возможны адреса от 10.10.0.1 до 10.10.63.254.  Потому возможные ip - 10.10.0.2, 10.10.10.10, 10.10.1.255.

## **== Задание 2==**

### Подними две виртуальные машины (далее -- ws1 и ws2).

### С помощью команды `ip a` посмотри существующие сетевые интерфейсы.

- В отчёт помести скрин с вызовом и выводом использованной команды.

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2010.png)

Скриншот 10 - ip a

### Опиши сетевой интерфейс, соответствующий внутренней сети, на обеих машинах и задать следующие адреса и маски: ws1 - *192.168.100.10*, маска */16*, ws2 - *172.24.116.8*, маска */12*.

- В отчёт помести скрины с содержанием изменённого файла *etc/netplan/00-installer-config.yaml* для каждой машины.

### Выполни команду `netplan apply` для перезапуска сервиса сети.

- В отчёт помести скрин с вызовом и выводом использованной команды.

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2011.png)

Скриншот 11 - *etc/netplan/00-installer-config.yaml*  и `netplan apply` 

### 2.1. Добавление статического маршрута вручную

### Добавь статический маршрут от одной машины до другой и обратно при помощи команды вида `ip r add`.

### Пропингуй соединение между машинами.

- В отчёт помести скрин с вызовом и выводом использованных команд.

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2012.png)

Скриншот 12 - пинг между машинами

### 2.2. Добавление статического маршрута с сохранением

### Перезапусти машины.

### Добавь статический маршрут от одной машины до другой с помощью файла */etc/netplan/00-installer-config.yaml*.

- В отчёт помести скрин с содержанием изменённого файла */etc/netplan/00-installer-config.yaml*.

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2013.png)

Скриншот 13 - */etc/netplan/00-installer-config.yaml со статическим маршрутом*

### Пропингуй соединение между машинами.

- В отчёт помести скрин с вызовом и выводом использованной команды.

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2014.png)

Скриншот 14 - пинг 

## **== Задание 3==**

*В данном задании используются виртуальные машины ws1 и ws2 из Части 2*

### 3.1. Скорость соединения

### Переведи и запиши в отчёт:

8 Mbps = 1MB/s

100 MB/s = 800000 kbps

1 Gbps  = 1000 Mbps.

### 3.2. Утилита **iperf3**

### Измерь скорость соединения между ws1 и ws2.

- В отчёт помести скрины с вызовом и выводом использованных команд.

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2015.png)

Скриншот 15 - сервер на  ws1, измерение скорости на ws2

## **== Задание 4==**

*В данном задании используются виртуальные машины ws1 и ws2 из Части 2*

### 4.1. Утилита **iptables**

### Создай файл */etc/firewall.sh*, имитирующий фаерволл, на ws1 и ws2:

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2016.png)

Скриншот 16 - */etc/firewall.sh*

### Нужно добавить в файл подряд следующие правила:

### 1) На ws1 примени стратегию, когда в начале пишется запрещающее правило, а в конце пишется разрешающее правило (это касается пунктов 4 и 5).

### 2) На ws2 примени стратегию, когда в начале пишется разрешающее правило, а в конце пишется запрещающее правило (это касается пунктов 4 и 5).

### 3) Открой на машинах доступ для порта 22 (ssh) и порта 80 (http).

### 4) Запрети *echo reply* (машина не должна «пинговаться», т.е. должна быть блокировка на OUTPUT).

### 5) Разреши *echo reply* (машина должна «пинговаться»).

- В отчёт помести скрины с содержанием файла */etc/firewall* для каждой машины.

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2017.png)

Скриншот 17 - */etc/firewall* для каждой машины

### Запусти файлы на обеих машинах командами `chmod +x /etc/firewall.sh` и `/etc/firewall.sh`.

- В отчёт помести скрины с запуском обоих файлов;

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2018.png)

Скриншот 18 - /etc/firewall.sh на обоих машинах

- В отчёте опиши разницу между стратегиями, применёнными в первом и втором файлах.

Если правила конфликтуют, то выполняется последнее, что было указано, потому c ws1 можно послать ping на ws2, а в обратную сторону нет

### 4.2. Утилита **nmap**

### Командой **ping** найди машину, которая не «пингуется», после чего утилитой **nmap** покажи, что хост машины запущен.

*Проверка: в выводе nmap должно быть сказано: `Host is up`*.

- В отчёт помести скрины с вызовом и выводом использованных команд **ping** и **nmap**.

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2019.png)

Скриншот 19 - на обеих машинах nmap показыват Host is up

### Сохрани дампы образов виртуальных машин

**P.S. Ни в коем случае не сохраняй дампы в гит!**

## **== Задание 5==**

Сеть:

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2020.png)

### Подними пять виртуальных машин (3 рабочие станции (ws11, ws21, ws22) и 2 роутера (r1, r2)).

### 5.1. Настройка адресов машин

### Настрой конфигурации машин в *etc/netplan/00-installer-config.yaml* согласно сети на рисунке.

- В отчёт помести скрины с содержанием файла *etc/netplan/00-installer-config.yaml* для каждой машины.

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2021.png)

Скришот 20 - ws11

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2022.png)

Скришот 21 - ws21

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2023.png)

Скришот 22 - ws22

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2024.png)

Скришот 23 - r1

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2025.png)

Скришот 24 - r2

### Перезапусти сервис сети. Если ошибок нет, то командой `ip -4 a` проверь, что адрес машины задан верно. Также пропингуй ws22 с ws21. Аналогично пропингуй r1 с ws11.

- В отчёт помести скрины с вызовом и выводом использованных команд.

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2026.png)

Скриншот 25 - ws11

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2027.png)

Скриншот 26 - ws21

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2028.png)

Скриншот 27 - ws22

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2029.png)

Скришот 28 - r1

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2030.png)

Скриншот 29 - r2

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2031.png)

Скриншот 30 - ping ws21 ws22

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2032.png)

Скришот 31 - ping ws11 r1

### 5.2. Включение переадресации IP-адресов

### Для включения переадресации IP, выполни команду на роутерах:

`sysctl -w net.ipv4.ip_forward=1`*При таком подходе переадресация не будет работать после перезагрузки системы.*

- В отчёт помести скрин с вызовом и выводом использованной команды.

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2033.png)

Скриншот 32 - `sysctl -w net.ipv4.ip_forward=1`

### Открой файл */etc/sysctl.conf* и добавь в него следующую строку:

`net.ipv4.ip_forward = 1`*При использовании этого подхода, IP-переадресация включена на постоянной основе.*

- В отчёт помести скрин с содержанием изменённого файла */etc/sysctl.conf*.

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2034.png)

Скриншот 33 - */etc/sysctl.conf*

### 5.3. Установка маршрута по-умолчанию

Пример вывода команды `ip r` после добавления шлюза:

`default via 10.10.0.1 dev eth0
10.10.0.0/18 dev eth0 proto kernel scope link src 10.10.0.2`

### Настрой маршрут по-умолчанию (шлюз) для рабочих станций. Для этого добавь `default` перед IP роутера в файле конфигураций.

- В отчёт помести скрин с содержанием файла *etc/netplan/00-installer-config.yaml*;

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2035.png)

Скриншот 34 - ws11

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2036.png)

Скриншот 34 - ws21

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2037.png)

Скриншот 35 - ws22

### Вызови `ip r` и покажи, что добавился маршрут в таблицу маршрутизации.

- В отчёт помести скрин с вызовом и выводом использованной команды.

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2038.png)

Скриншот 34 - ws11

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2039.png)

Скриншот 34 - ws21

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2040.png)

Скриншот 35 - ws22

### Пропингуй с ws11 роутер r2 и покажи на r2, что пинг доходит. Для этого используй команду:

`tcpdump -tn -i eth0`

- В отчёт помести скрин с вызовом и выводом использованных команд.

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2041.png)

Скриншот 36 - ping ws11 r2

### 5.4. Добавление статических маршрутов

### Добавь в роутеры r1 и r2 статические маршруты в файле конфигураций. Пример для r1 маршрута в сетку 10.20.0.0/26:

`# Добавь в конец описания сетевого интерфейса eth1:- to: 10.20.0.0
  via: 10.100.0.12`

- В отчёт помести скрины с содержанием изменённого файла *etc/netplan/00-installer-config.yaml* для каждого роутера.

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2042.png)

Скриншот 37 - netplan

### Вызови `ip r` и покажи таблицы с маршрутами на обоих роутерах. Пример таблицы на r1:

`10.100.0.0/16 dev eth1 proto kernel scope link src 10.100.0.11
10.20.0.0/26 via 10.100.0.12 dev eth1
10.10.0.0/18 dev eth0 proto kernel scope link src 10.10.0.1`

- В отчёт помести скрин с вызовом и выводом использованной команды.

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2043.png)

Сркриншот 38 - ip r

### Запусти команды на ws11:

`ip r list 10.10.0.0/[маска сети]` и `ip r list 0.0.0.0/0`

- В отчёт помести скрин с вызовом и выводом использованных команд;
- В отчёте объясни, почему для адреса 10.10.0.0/[маска сети] был выбран маршрут, отличный от 0.0.0.0/0, хотя он попадает под маршрут по-умолчанию.

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2044.png)

Скриншот 39 - ip r list

Потому что системой был выбран наиболее точный маршрут.

### 5.5. Построение списка маршрутизаторов

Пример вывода утилиты **traceroute** после добавления шлюза:

`1 10.10.0.1 0 ms 1 ms 0 ms
2 10.100.0.12 1 ms 0 ms 1 ms
3 10.20.0.10 12 ms 1 ms 3 ms`

### Запусти на r1 команду дампа:

`tcpdump -tnv -i eth0`

Скриншот 40 - `tcpdump -tnv -i eth0`

### При помощи утилиты **traceroute** построй список маршрутизаторов на пути от ws11 до ws21.

- В отчёт помести скрины с вызовом и выводом использованных команд (tcpdump и traceroute);
- В отчёте, опираясь на вывод, полученный из дампа на r1, объясни принцип работы построения пути при помощи **traceroute**.

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2045.png)

Скриншот 40 - tcpdump и traceroute

***Утилита Traceroute вместо ICMP-запроса отправляет 3 UDP-пакета на определенный порт целевого хоста и ожидает ответа о недоступности этого порта. Первый пакет отправляется с TTL=1, второй с TTL=2 и так далее, пока запрос не попадёт адресату. Так как вместо ICMP-запроса он отправляет UDP-запрос, в каждом запросе есть порт отправителя и порт получателя. По умолчанию запрос отправляется на закрытый порт 34434. Когда запрос попадёт на хост назначения, этот хост отправит ответ о недоступности порта «Destination port unreachable» (порт назначения недоступен). Это значит, что адресат получил запрос. Traceroute воспримет этот ответ как завершение трассировки.***

### 5.6. Использование протокола **ICMP** при маршрутизации

### Запусти на r1 перехват сетевого трафика, проходящего через eth0 с помощью команды:

`tcpdump -n -i eth0 icmp`

### Пропингуй с ws11 несуществующий IP (например, *10.30.0.111*) с помощью команды:

`ping -c 1 10.30.0.111`

- В отчёт помести скрин с вызовом и выводом использованных команд.

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2046.png)

Скриншот 41 -  tcpdump и ping

### Сохрани дампы образов виртуальных машин.

**P.S. Ни в коем случае не сохраняй дампы в гит!**

## **== Задание 6==**

*В данном задании используются виртуальные машины из Части 5.*

### Для r2 настрой в файле */etc/dhcp/dhcpd.conf* конфигурацию службы **DHCP**:

### 1) Укажи адрес маршрутизатора по-умолчанию, DNS-сервер и адрес внутренней сети. Пример файла для r2:

`subnet 10.100.0.0 netmask 255.255.0.0 {}subnet 10.20.0.0 netmask 255.255.255.192
{    range 10.20.0.2 10.20.0.50;    option routers 10.20.0.1;    option domain-name-servers 10.20.0.1;}`

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2047.png)

Скриншот 42 - dhcpd.conf

### 2) В файле *resolv.conf* пропиши `nameserver 8.8.8.8`.

- В отчёт помести скрины с содержанием изменённых файлов.

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2048.png)

Скриншот 43 - resolve.conf

### Перезагрузи службу **DHCP** командой `systemctl restart isc-dhcp-server`. Машину ws21 перезагрузи при помощи `reboot` и через `ip a` покажи, что она получила адрес. Также пропингуй ws22 с ws21.

- В отчёт помести скрины с вызовом и выводом использованных команд.

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2049.png)

Скриншот 44 - `systemctl restart isc-dhcp-server`

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2050.png)

Скриншот 45 - ip a, ping

### Укажи MAC адрес у ws11, для этого в *etc/netplan/00-installer-config.yaml* надо добавить строки: `macaddress: 10:10:10:10:10:BA`, `dhcp4: true`.

- В отчёт помести скрин с содержанием изменённого файла *etc/netplan/00-installer-config.yaml*.

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2051.png)

Скриншот 44 - netplan

### Для r1 настрой аналогично r2, но сделай выдачу адресов с жесткой привязкой к MAC-адресу (ws11). Проведи аналогичные тесты.

- В отчёте этот пункт опиши аналогично настройке для r2.

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2052.png)

Скриншот 45 - dhcpd.conf

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2053.png)

Скриншот 46 - `systemctl restart isc-dhcp-server`

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2054.png)

Скриншот 47 - ip a, ping

### Запроси с ws21 обновление ip адреса.

- В отчёте помести скрины ip до и после обновления.
- В отчёте опиши, какими опциями **DHCP** сервера пользовался в данном пункте.

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2055.png)

Скриншот 48 - Старый ip

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2056.png)

Скриншот 49 - Новый ip

- ***Какими опциями DHCP сервера пользовались в данном пункте:***
    
    ***Настройка конфигурации службы DHCP (адрес маршрутизатора по-умолчанию, DNS-сервер, адрес внутренней сети, привязка к MAC-адресу)***
    
    ***Клиент протокола динамической конфигурации хоста (команда dhclient) для обновления или освобождения IP-адреса***
    

### Сохрани дампы образов виртуальных машин.

**P.S. Ни в коем случае не сохраняй дампы в гит!**

## **== Задание 7==**

*В данном задании используются виртуальные машины из Части 5.*

### В файле */etc/apache2/ports.conf* на ws22 и r1 измени строку `Listen 80` на `Listen 0.0.0.0:80`, то есть сделай сервер Apache2 общедоступным.

- В отчёт помести скрин с содержанием изменённого файла.

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2057.png)

Скриншот 49 - ports.conf

### Запусти веб-сервер Apache командой `service apache2 start` на ws22 и r1.

- В отчёт помести скрины с вызовом и выводом использованной команды.

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2058.png)

Скриншот 50 - apache2 start

### Добавь в фаервол, созданный по аналогии с фаерволом из Части 4, на r2 следующие правила:

### 1) Удаление правил в таблице filter - `iptables -F`;

### 2) Удаление правил в таблице "NAT" - `iptables -F -t nat`;

### 3) Отбрасывать все маршрутизируемые пакеты - `iptables --policy FORWARD DROP`.

### Запусти файл также, как в Части 4.

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2059.png)

Скриншот 51 - firewall.sh

### Проверь соединение между ws22 и r1 командой `ping`.

*При запуске файла с этими правилами, ws22 не должна «пинговаться» с r1.*

- В отчёт помести скрины с вызовом и выводом использованной команды.

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2060.png)

Сриншот 52 - ping r1 c ws22

### Добавь в файл ещё одно правило:

### 4) Разрешить маршрутизацию всех пакетов протокола **ICMP**.

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2061.png)

Скриншот 53 - разрешение всех icmp

### Запусти файл также, как в Части 4.

### Проверь соединение между ws22 и r1 командой `ping`.

*При запуске файла с этими правилами, ws22 должна «пинговаться» с r1.*

- В отчёт помести скрины с вызовом и выводом использованной команды.

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2062.png)

### Добавь в файл ещё два правила:

### 5) Включи **SNAT**, а именно маскирование всех локальных ip из локальной сети, находящейся за r2 (по обозначениям из Части 5 - сеть 10.20.0.0).

*Совет: стоит подумать о маршрутизации внутренних пакетов, а также внешних пакетов с установленным соединением.*

### 6) Включи **DNAT** на 8080 порт машины r2 и добавить к веб-серверу Apache, запущенному на ws22, доступ извне сети.

*Совет: стоит учесть, что при попытке подключения возникнет новое tcp-соединение, предназначенное ws22 и 80 порту.*

- В отчёт помести скрин с содержанием изменённого файла.

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2063.png)

### Запусти файл также, как в Части 4.

*Перед тестированием рекомендуется отключить сетевой интерфейс **NAT** (его наличие можно проверить командой `ip a`) в VirtualBox, если он включен.*

### Проверь соединение по TCP для **SNAT**: для этого с ws22 подключиться к серверу Apache на r1 командой:

`telnet [адрес] [порт]`

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2064.png)

### Проверь соединение по TCP для **DNAT**: для этого с r1 подключиться к серверу Apache на ws22 командой `telnet` .

- В отчёт помести скрины с вызовом и выводом использованных команд.

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2065.png)

### Сохрани дампы образов виртуальных машин.

**P.S. Ни в коем случае не сохраняй дампы в гит!**

## **== Задание ==**

*В данном задании используются виртуальные машины из Части 5.*

### Запусти на r2 фаервол с правилами из Части 7.

### Запусти веб-сервер **Apache** на ws22 только на localhost (то есть в файле */etc/apache2/ports.conf* измени строку `Listen 80` на `Listen localhost:80`).

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2066.png)

### Воспользуйся *Local TCP forwarding* с ws21 до ws22, чтобы получить доступ к веб-серверу на ws22 с ws21.

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2067.png)

### Воспользуйся *Remote TCP forwarding* c ws11 до ws22, чтобы получить доступ к веб-серверу на ws22 с ws11.

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2068.png)

ssh -R 8888:localhost:22 10.20.0.20

### Для проверки, сработало ли подключение в обоих предыдущих пунктах, перейди во второй терминал (например, клавишами Alt + F2) и выполни команду:

`telnet 127.0.0.1 [локальный порт]`

- В отчёте опиши команды, необходимые для выполнения этих четырёх пунктов, а также приложи скриншоты с их вызовом и выводом.

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2069.png)

telnet 9999 на ws21

![Untitled](D02_Linux_Network%20fa37ec2ca3e84a16aba85d1b520aa6b3/Untitled%2070.png)

telnet 8888 на ws22

### Сохрани дампы образов виртуальных машин.

**P.S. Ни в коем случае не сохраняй дампы в гит!**