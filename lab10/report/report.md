---
## Front matter
title: "Отчёт по лабораторной работе №10"
subtitle: "Настройка списков управления доступом (ACL)"
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

Освоить настройку прав доступа пользователей к ресурсам сети

# Задание

1. Требуется настроить следующие правила доступа:
1) web-сервер: разрешить доступ всем пользователям по протоколу HTTP
через порт 80 протокола TCP, а для администратора открыть доступ
по протоколам Telnet и FTP;
2) файловый сервер: с внутренних адресов сети доступ открыт по портам
для общедоступных каталогов, с внешних — доступ по протоколу FTP;
3) почтовый сервер: разрешить пользователям работать по протоколам
SMTP и POP3 (соответственно через порты 25 и 110 протокола TCP),
а для администратора — открыть доступ по протоколам Telnet и FTP;
4) DNS-сервер: открыть порт 53 протокола UDP для доступа из внутренней сети;
5) разрешить icmp-сообщения, направленные в сеть серверов;
6) запретить для сети Other любые запросы за пределы сети, за исключением администратора;
7) разрешить доступ в сеть управления сетевым оборудованием только
администратору сети.
2. Требуется проверить правильность действия установленных правил доступа.
3. Требуется выполнить задание для самостоятельной работы по настройке
прав доступа администратора сети на Павловской.
4. При выполнении работы необходимо учитывать соглашение об именовании.

# Выполнение лабораторной работы

Подключил ноутбук администратора (рис. [-@fig:001])

![Ноутбук администратора](image/1.png){ #fig:001 width=70% }

Настроил конфигурацию ноутбука администратора (рис. [-@fig:002])

![Конфигурация ноутбука администратора](image/2.png){ #fig:002 width=70% }

Проверка работоспособности соединения ноутбука admin (рис. [-@fig:003])

![Проверка работоспособности соединения ноутбука admin](image/3.png){ #fig:003 width=70% }

Настройка доступа к web-серверу по порту tcp 80 (рис. [-@fig:004])

![Настройка доступа к web-серверу по порту tcp 80](image/4.png){ #fig:004 width=70% }

Добавление списка управления доступом к интерфейсу (рис. [-@fig:005])

![Добавление списка управления доступом к интерфейсу](image/5.png){ #fig:005 width=70% }

Проверка недоступности web-сервера через ping (рис. [-@fig:006])

![Недоступность web-сервера через ping](image/6.png){ #fig:006 width=70% }

Дополнительный доступ для администратора по протоколам Telnet и FTP (рис. [-@fig:007])

![Дополнительный доступ для администратора по протоколам Telnet и FTP](image/7.png){ #fig:007 width=70% }

Попытка подключения по FTP (рис. [-@fig:008])

![Попытка подключения по FTP](image/8.png){ #fig:008 width=70% }

Настройка доступа к файловому серверу (рис. [-@fig:009])

![Настройка доступа к файловому серверу](image/9.png){ #fig:009 width=70% }

Настройка доступа к почтовому серверу (рис. [-@fig:010])

![Настройка доступа к почтовому серверу](image/10.png){ #fig:010 width=70% }

Настройка доступа к DNS-серверу (рис. [-@fig:011])

![Настройка доступа к DNS-серверу](image/11.png){ #fig:011 width=70% }

Проверил доступность web-сервера в браузере (рис. [-@fig:012])

![Доступность web-сервера в браузере](image/12.png){ #fig:012 width=70% }

Разрешение icmp-запросов (рис. [-@fig:013])

![Разрешение icmp-запросов](image/13.png){ #fig:013 width=70% }

Посмотрел правила в списке контроля доступа (рис. [-@fig:014])

![Правила в списке контроля доступа](image/14.png){ #fig:014 width=70% }

Проверил пингование (рис. [-@fig:015])

![Проверка пингования](image/15.png){ #fig:015 width=70% }

Настройка доступа для сети Other (рис. [-@fig:016])

![Настройка доступа для сети Other](image/16.png){ #fig:016 width=70% }

# Самостоятельная работа

Пингование с устройства dep-donskaya-vpkozlov-1 (рис. [-@fig:017])

![Пингование с устройства dep-donskaya-vpkozlov-1](image/17.png){ #fig:017 width=70% }

Пингование с устройства dk-donskaya-vpkozlov-1 (рис. [-@fig:018])

![Пингование с устройства dk-donskaya-vpkozlov-1](image/18.png){ #fig:018 width=70% }

Размещение ноутбука admin на Павловской (рис. [-@fig:0181])

![Размещение ноутбука admin на Павловской](image/181.png){ #fig:0181 width=70% }

Настройка доступа для admin-pavlovskaya (рис. [-@fig:019])

![Настройка доступа для admin-pavlovskaya](image/19.png){ #fig:019 width=70% }

Список контроля доступа (рис. [-@fig:020])

![Список контроля доступа](image/20.png){ #fig:020 width=70% }

Проверка корректности настроенного доступа (рис. [-@fig:021])

![Проверка корректности настроенного доступа](image/21.png){ #fig:021 width=70% }

# Выводы

Освоил настройку прав доступа пользователей к ресурсам сети

# Контрольные вопросы

1. Как задать действие правила для конкретного протокола?

Например, `permit tcp any host 10.128.0.4 eq pop3`.

2. Как задать действие правила сразу для нескольких портов?

Для этого нужна команда `interface range`.

3. Как узнать номер правила в списке прав доступа?

С помощью команды `show access-lists`.

4. Каким образом можно изменить порядок применения правил в списке
контроля доступа?

Команда `access-list <номер в списке> permit`.

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
