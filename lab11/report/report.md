---
## Front matter
title: "Отчёт по лабораторной работе №11"
subtitle: "Настройка NAT. Планирование"
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

Провести подготовительные мероприятия по подключению локальной сети
организации к Интернету.

# Задание

1. Построить схему подсоединения локальной сети к Интернету.
2. Построить модельные сети провайдера и сети Интернет.
3. Построить схемы сетей L1, L2, L3.
4. При выполнении работы необходимо учитывать соглашение об именовании.

# Выполнение лабораторной работы

Добавил новые устройства (рис. [-@fig:001])

![Добавление устройств](image/1.png){ #fig:001 width=70% }

Переместил internet-vpkozlov-mc-1 на internet (рис. [-@fig:002])

![Перемещение internet-vpkozlov-mc-1](image/2.png){ #fig:002 width=70% }

Переместил серверы (рис. [-@fig:003])

![Перемещение серверов](image/3.png){ #fig:003 width=70% }

Пересобрал репитеры (рис. [-@fig:004])

![Пересборка репитеров](image/4.png){ #fig:004 width=70% }

Соединил добавленные устройства (рис. [-@fig:005])

![Соединение устройств](image/5.png){ #fig:005 width=70% }

Изменил config серверов (рис. [-@fig:006])

![Изменение config'а серверов](image/6.png){ #fig:006 width=70% }

Добавил dns-адреса на сервер (рис. [-@fig:007])

![Добавление dns-адресов на сервер](image/7.png){ #fig:007 width=70% }

Добавил лэйблы (рис. [-@fig:008])

![ЛДобавление лэйблов](image/8.png){ #fig:008 width=70% }

# Выводы

Провел подготовительные мероприятия по подключению локальной сети
организации к Интернету.

# Контрольные вопросы

1. Что такое Network Address Translation (NAT)?

Network Address Translation (NAT) — механизм преобразования IP-адресов транзитных пакетов. В частности, механизм NAT используется для обеспечения доступа устройств локальных сетей с внутренними IP-адресами к сети Интернет.

2. Как определить, находится ли узел сети за NAT?

Проанализирорвать конфигурации маршрутизатора или другого сетевого оборудования, которое может выполнять функции NAT. 

3. Какое оборудование отвечает за преобразование адреса методом NAT?

Преобразование адреса методом NAT может производиться почти любым маршрутизирующим устройством — маршрутизатором, сервером доступа, межсетевым экраном. Наиболее популярным является SNAT, суть механизма которого состоит в замене адреса источника (англ. source) при прохождении пакета в одну сторону и обратной замене адреса назначения (англ. destination) в ответном пакете.

4. В чём отличие статического, динамического и перегруженного NAT?

Статический осуществляет преобразование адресов по принципу 1:1, динамический 1:N, а перегруженный N:1.

5. Охарактеризуйте типы NAT.

Типы NAT:
- статический NAT (Static NAT, SNAT) -- осуществляет преобразование адресов по принципу 1:1 (в частности, один локальный IP-адрес преобразуется во внешний адрес, выделенный, например, провайдером);
- динамический NAT (Dynamic NAT, DNAT) -- осуществляет преобразование адресов по принципу 1:N (например, один адрес устройства локальной сети преобразуется в один из адресов диапазона внешних адресов);
- NAT Overload (или NAT Masquerading, или Port Address Translation, PAT) -- осуществляет преобразование адресов по принципу N:1 (например, адреса группы устройств локальной подсети преобразуются в один внешний адрес, при этом дополнительно используется механизм адресации через номера портов).

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
