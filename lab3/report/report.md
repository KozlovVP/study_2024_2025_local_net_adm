---
## Front matter
title: "Отчёт по лабораторной работе №3"
subtitle: "Планирование локальной сети организации"
author: "Козлов Всеволод Павлович НФИбд-02-22"

## Generic otions
lang: ru-RU
toc-title: "Содержание"

## Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

## Pdf output format
toc: true # Table of contents
toc-depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
## I18n polyglossia
polyglossia-lang:
  name: russian
polyglossia-otherlangs:
  name: english
## I18n babel
babel-lang: russian
babel-otherlangs: english
## Fonts
mainfont: Arial
romanfont: Arial
sansfont: Arial
monofont: Arial
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
## Biblatex
biblatex: true
biblio-style: "gost-numeric"
biblatexoptions:
  - parentracker=true
  - backend=biber
  - hyperref=auto
  - language=auto
  - autolang=other*
  - citestyle=gost-numeric
## Pandoc-crossref LaTeX customization
figureTitle: "Рис."
tableTitle: "Таблица"
listingTitle: "Листинг"
lofTitle: "Список иллюстраций"
lotTitle: "Список таблиц"
lolTitle: "Листинги"
## Misc options
indent: true
header-includes:
  - \usepackage{indentfirst}
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Познакомиться с принципами планирования локальной сети организации.

# Задание

1. Используя графический редактор (например, Dia), требуется повторить
схемы L1, L2, L3, а также сопутствующие им таблицы VLAN, IP-адресов
и портов подключения оборудования планируемой сети.
2. Рассмотренный выше пример планирования адресного пространства сети
базируется на разбиении сети 10.128.0.0/16 на соответствующие подсети.
Требуется сделать аналогичный план адресного пространства для сетей
172.16.0.0/12 и 192.168.0.0/16 с соответствующими схемами сети и сопутствующими таблицами VLAN, IP-адресов и портов подключения оборудования.
3. При выполнении работы необходимо учитывать соглашение об именовании.

# Выполнение лабораторной работы

Построил схему L1 (рис. [-@fig:001])

![Схема L1: физические устройства сети с номерами портов](image/1.png){ #fig:001 width=70% }

Создал таблицу VLAN (рис. [-@fig:002])

![Таблица VLAN](image/2.png){ #fig:002 width=70% }

Построил схему L2 (рис. [-@fig:003])

![Схема L2: VLAN сети](image/3.png){ #fig:003 width=70% }

Построил схему L3 для сети 10.128.0.0/16 (рис. [-@fig:004])

![Схема L3: маршрутизация сети 10.128.0.0/16](image/4.png){ #fig:004 width=70% }

Создал таблицу IP для сети 10.128.0.0/16 (рис. [-@fig:005])

![Таблица IP для сети 10.128.0.0/16](image/5.png){ #fig:005 width=70% }

Создал таблицу портов (рис. [-@fig:006])

![Таблица портов](image/6.png){ #fig:006 width=70% }

Разработал регламент выделения IP-адресов для сети класса A - 10.128.0.0/16 (рис. [-@fig:007])

![Регламент выделения IP-адресов для 10.128.0.0/16](image/7.png){ #fig:007 width=70% }

Таблицы VLAN и портов, схемы L1 и L2 не изменяются при смене ip-адреса сети

Построил схему L3 для сети 172.16.0.0/12 (рис. [-@fig:008])

![Схема L3: маршрутизация сети 172.16.0.0/12](image/8.png){ #fig:008 width=70% }

Создал таблицу IP для сети 172.16.0.0/12 (рис. [-@fig:009])

![Таблица IP для сети 172.16.0.0/12](image/9.png){ #fig:009 width=70% }

Разработал регламент выделения IP-адресов для сети класса B - 172.16.0.0/12 (рис. [-@fig:010])

![Регламент выделения IP-адресов для 172.16.0.0/12](image/10.png){ #fig:010 width=70% }

Построил схему L3 для сети 192.168.0.0/16 (рис. [-@fig:011])

![Схема L3: маршрутизация сети 192.168.0.0/16](image/11.png){ #fig:011 width=70% }

Создал таблицу IP для сети 192.168.0.0/16 (рис. [-@fig:012])

![Таблица IP для сети 192.168.0.0/16](image/12.png){ #fig:012 width=70% }

Разработал регламент выделения IP-адресов для сети класса C - 192.168.0.0/16 (рис. [-@fig:013])

![Регламент выделения IP-адресов для 192.168.0.0/16](image/13.png){ #fig:013 width=70% }

# Выводы

Познакомился с принципами планирования локальной сети организации.

# Ответы на контрольные вопросы

1. Модель OSI (Open System Interconnection), или эталонная модель взаимодействия открытых систем описывает, как устройства в локальных и глобальных 
сетях обмениваются данными и что происходит с этими данными. Она имеет 7 уровней:
- Физический (способ передачи сигналов)
- Канальный (проверка целостности полученных данных и исправление ошибок)
- Сетевой (маршрутизация данных внутри сети между компьютерами)
- Транспортный (способ передачи данных - с гарантией (TCP) /без гарантии (UDP)
- Сеансовый (управление сессиями)
- Представления (кодирование, сжатие, шифрование)
- Прикладной (работа с сетевыми службами)
 
2. Коммутатор объединяет различные сетевые устройства в единый сегмент сети и позволяет передавать данные только от одного узла к другому, если сообщение не широковещательное и узел-получатель 
закреплён к порту коммутатора

3. Маршрутизатор ведёт таблицы маршрутизации, определяет маршруты, фильтрует пакеты, управляет очередями, преобразовывает сетевые адреса в локальные.

4. Коммутатор уровня 2 работает только с MAC-адресами, игнорируя IP-адреса и элементы более высоких уровней. Коммутатор уровня 3 выполняет все функции коммутатора уровня 2.
 Кроме того, он может осуществлять статическую и динамическую маршрутизацию.

5. Сетевой интерфейс - это точка подключения двух частей сетевого оборудования

6. Сетевые порты - это виртуальные конечные точки, которые соединяют передачу данных между несколькими приложениями, службами или устройствами в сети. 

7. Ethernet: скорость передачи данных - 10 мбит/c , максимальная длина сегмента - 3,6 км;
FastEthernet: скорость передачи данных - 100 мбит/c , максимальная длина сегмента - 10 км;
GigabitEthernet: скорость передачи данных - 1000 мбит/c , максимальная длина сегмента - 70 км;

8. IP-адрес - это 32-битный номер, уникально идентифицирующий хост в сети TCP/IP.
Сеть - это совокупность соединённых между собой узлов, которые обмениваются информацией.
Подсеть - это сеть меньшего размера, созданная путём деления более крупной сети.
Маска подсети - 32-битное число, служащее битовой маской для разделения сетевой части (адреса подсети) и части хоста IP-адреса.

9. VLAN - это логическая сеть, которая создается внутри более крупной физической сети. 
Виртуальные сети VLAN позволяют сегментировать сеть на более мелкие виртуальные подсети, которые можно использовать для изоляции трафика и повышения производительности сети.

10. Trunk Port в отличие от Access Port тегирует данные, позволяя передавать данные из одного порта в разные VLAN.

# Список литературы
1. 802.1D-2004 - IEEE Standard for Local and Metropolitan Area Networks.
Media Access Control (MAC) Bridges : тех. отч. / IEEE. — 2004. — С. 1—
277. — DOI: 10.1109/IEEESTD.2004.94569. — URL: http://ieeexplore.
ieee.org/servlet/opac?punumber=9155.
2. 802.1Q - Virtual LANs. — URL: http://www.ieee802.org/1/pages/802.
1Q.html.
3. A J. Packet Tracer Network Simulator. — Packt Publishing, 2014. —
ISBN 9781782170426. — URL: https://books.google.com/books?id=
eVOcAgAAQBAJ&dq=cisco+packet+tracer&hl=es&source=gbs_navlinks_
s.
4. Cotton M., Vegoda L. Special Use IPv4 Addresses : RFC / RFC Editor. —
01.2010. — С. 1—11. — № 5735. — DOI: 10.17487/rfc5735. — URL: https:
//www.rfc-editor.org/info/rfc5735.
5. Droms R. Dynamic Host Configuration Protocol : RFC / RFC Editor. —
03.1997. — С. 1—45. — № 2136. — DOI: 10.17487/rfc2131. — URL: https:
//www.ietf.org/rfc/rfc2131.txt%20https://www.rfc-editor.org/
info/rfc2131.
6. McPherson D., Dykes B. VLAN Aggregation for Efficient IP Address
Allocation, RFC 3069. — 2001. — URL: http : / / www . ietf . org / rfc /
rfc3069.txt.
7. Moy J. OSPF Version 2 : RFC / RFC Editor. — 1998. — С. 244. — DOI: 10.
17487/rfc2328. — URL: https://www.rfc-editor.org/info/rfc2328.
8. NAT Order of Operation. — URL: https://www.cisco.com/c/en/us/
support/docs/ip/network-address-translation-nat/6209-5.html.
9. NAT: вопросы и ответы / Сайт поддержки продуктов и технологий
компании Cisco. — URL: https://www.cisco.com/cisco/web/support/
RU/9/92/92029_nat-faq.html.
10. Neumann J. C. Cisco Routers for the Small Business A Practical Guide for
IT Professionals. — Apress, 2009.
