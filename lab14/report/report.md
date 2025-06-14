---
## Front matter
title: "Отчёт по лабораторной работе №14"
subtitle: "Статическая маршрутизация в Интернете. Настройка"
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

Настроить взаимодействие через сеть провайдера посредством статической
маршрутизации локальной сети организации с сетью основного здания, расположенного в 42-м квартале в Москве, и сетью филиала, расположенного
в г. Сочи.

# Задание

1. Настроить связь между территориями.
2. Настроить оборудование, расположенное в квартале 42 в Москве.
3. Настроить оборудование, расположенное в филиале в г. Сочи.
4. Настроить статическую маршрутизацию между территориями.
5. Настроить статическую маршрутизацию на территории квартала 42 в г.
Москве.
6. Настроить NAT на маршрутизаторе msk-donskaya-gw-1.
7. При выполнении работы необходимо учитывать соглашение об именовании.

# Выполнение лабораторной работы

Настройка интерфейсов коммутатора provider-sw-1 (рис. [-@fig:001])

![Настройка интерфейсов коммутатора provider-sw-1](image/1.png){ #fig:001 width=70% }

Настройка интерфейсов маршрутизатора msk-donskaya-gw-1 (рис. [-@fig:002])

![Настройка интерфейсов маршрутизатора msk-donskaya-gw-1](image/2.png){ #fig:002 width=70% }

Настройка интерфейсов маршрутизатора msk-q42-gw-1 (рис. [-@fig:003])

![Настройка интерфейсов маршрутизатора msk-q42-gw-1](image/3.png){ #fig:003 width=70% }

Настройка интерфейсов коммутатора sch-sochi-sw-1 (рис. [-@fig:004])

![Настройка интерфейсов коммутатора sch-sochi-sw-1](image/4.png){ #fig:004 width=70% }

Настройка интерфейсов маршрутизатора sch-sochi-gw-1 (рис. [-@fig:005])

![Настройка интерфейсов маршрутизатора sch-sochi-gw-1](image/5.png){ #fig:005 width=70% }

Настройка интерфейсов маршрутизатора msk-q42-gw-1 (рис. [-@fig:006])

![Настройка интерфейсов маршрутизатора msk-q42-gw-1](image/6.png){ #fig:006 width=70% }

Настройка интерфейсов коммутатора msk-q42-sw-1 (рис. [-@fig:007])

![Настройка интерфейсов коммутатора msk-q42-sw-1](image/7.png){ #fig:007 width=70% }

Пропинговал 10.128.0.1 (рис. [-@fig:008])

![Пингование 10.128.0.1](image/8.png){ #fig:008 width=70% }

Настройка интерфейсов маршрутизирующего коммутатора msk-hostel-gw-1 (рис. [-@fig:009])

![Настройка интерфейсов маршрутизирующего коммутатора msk-hostel-gw-1](image/9.png){ #fig:009 width=70% }

Настройка интерфейсов коммутатора msk-hostel-sw-1 (рис. [-@fig:010])

![Настройка интерфейсов коммутатора msk-hostel-sw-1](image/10.png){ #fig:010 width=70% }

Настройка интерфейсов маршрутизатора sch-sochi-gw-1 (рис. [-@fig:011])

![Настройка интерфейсов маршрутизатора sch-sochi-gw-1](image/11.png){ #fig:011 width=70% }

Настройка интерфейсов коммутатора sch-sochi-sw-1 (рис. [-@fig:012])

![Настройка интерфейсов коммутатора sch-sochi-sw-1](image/12.png){ #fig:012 width=70% }

Настройка маршрутизатора msk-donskaya-gw-1 (рис. [-@fig:013])

![Настройка маршрутизатора msk-donskaya-gw-1](image/13.png){ #fig:013 width=70% }

Настройка маршрутизатора msk-q42-gw-1 (рис. [-@fig:014])

![Настройка маршрутизатора msk-q42-gw-1](image/14.png){ #fig:014 width=70% }

Настройка маршрутизатора sch-sochi-gw-1 (рис. [-@fig:015])

![Настройка маршрутизатора sch-sochi-gw-1](image/15.png){ #fig:015 width=70% }

Настройка маршрутизатора msk-q42-gw-1 (рис. [-@fig:016])

![Настройка маршрутизатора msk-q42-gw-1](image/16.png){ #fig:016 width=70% }

Настройка интерфейсов маршрутизирующего коммутатора msk-hostel-gw-1 (рис. [-@fig:017])

![Настройка интерфейсов маршрутизирующего коммутатора msk-hostel-gw-1](image/17.png){ #fig:017 width=70% }

Настройка NAT на маршрутизаторе msk-donskaya-gw-1 (рис. [-@fig:018])

![Настройка NAT на маршрутизаторе msk-donskaya-gw-1](image/18.png){ #fig:018 width=70% }

# Выводы

Настроил взаимодействие через сеть провайдера посредством статической
маршрутизации локальной сети организации с сетью основного здания, расположенного в 42-м квартале в Москве, и сетью филиала, расположенного
в г. Сочи.

# Контрольные вопросы

1. Приведите пример настройки статической маршрутизации между двумя подсетями организации.

ip route 192.168.2.0 255.255.255.0 10.0.0.2

(На Router1 для маршрута в подсеть 192.168.2.0 через интерфейс 10.0.0.2)

2. Опишите процесс обращения устройства из одного VLAN к устройству из другого VLAN.

Через маршрутизатор или L3-коммутатор — данные идут сначала к шлюзу, он пересылает их в другую VLAN.

3. Как проверить работоспособность маршрута?

С помощью ping и traceroute (или tracert на Windows).

4. Как посмотреть таблицу маршрутизации?

- Windows: route print

- Linux: ip route

- Cisco: show ip route

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
