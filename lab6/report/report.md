---
## Front matter
title: "Отчёт по лабораторной работе №6"
subtitle: "Статическая маршрутизация VLAN"
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

Настроить статическую маршрутизацию VLAN в сети.

# Задание

1. Добавить в локальную сеть маршрутизатор, провести его первоначальную настройку.
2. Настроить статическую маршрутизацию VLAN.
3. При выполнении работы необходимо учитывать соглашение об именовании

# Выполнение лабораторной работы

Подсоединил к сети маршрутизатор msk-donskaya-vpkozlov-gw-1 (рис. [-@fig:001])

![Подключение msk-donskaya-vpkozlov-gw-1](image/1.png){ #fig:001 width=70% }

Настроил интерфейс f0/24 на msk-donskaya-vpkozlov-sw-1 (рис. [-@fig:002])

![Интерфейс f0/24 на msk-donskaya-vpkozlov-sw-1](image/2.png){ #fig:002 width=70% }

Настроил интерфейс f0/0 на msk-donskaya-vpkozlov-gw-1 (рис. [-@fig:003])

![Интерфейс f0/0 на msk-donskaya-vpkozlov-gw-1](image/3.png){ #fig:003 width=70% }

Произвел первичную конфигурацию маршрутизатора (рис. [-@fig:004])

![Первичная конфигурация маршрутизатора](image/4.png){ #fig:004 width=70% }

Произвел конфигурацию VLAN-интерфейсов маршрутизатора, ч1 (рис. [-@fig:005])

![Конфигурация VLAN-интерфейсов маршрутизатора](image/5.png){ #fig:005 width=70% }

Произвел конфигурацию VLAN-интерфейсов маршрутизатора, ч2 (рис. [-@fig:006])

![Конфигурация VLAN-интерфейсов маршрутизатора](image/6.png){ #fig:006 width=70% }

Пропинговал некоторые ip-адреса (рис. [-@fig:007])

![Пингование некоторых ip-адресов](image/7.png){ #fig:007 width=70% }

# Выводы

Настроил статическую маршрутизацию VLAN в сети.

# Контрольные вопросы

1. Охарактеризуйте стандарт IEEE 802.1Q.

IEEE 802.1Q — открытый стандарт, который описывает процедуру тегирования трафика для передачи информации о принадлежности к VLAN по сетям стандарта IEEE 802.3 Ethernet.

Так как 802.1Q не изменяет заголовки кадра (фрейма), то сетевые устройства, которые не поддерживают этот стандарт, могут передавать трафик без учёта его принадлежности к VLAN. Поскольку данный стандарт является открытым, он используется для построения «транковых» портов между оборудованием различных производителей.
802.1Q помещает внутрь фрейма тег, который передает информацию о принадлежности трафика к VLAN.

2. Опишите формат кадра IEEE 802.1Q.

Спецификация 802.1 Q определяет 12 возможных форматов инкапсуляции долнительного поля в кадры МАС-уровня. Эти форматы определяются в зависимости от трех типов кадров (Ethernet II, LLC в нормальном формате, LLC в формате Token Ring), двух типов сетей (802.3/Ethernet или Token Ring/FDDI) и двух типов меток VLAN (неявных или явных). Имеются также определенные правила трансляции исходных кадров Ethernet или Token Ring в помеченные кадры и обратной трансляции помеченных кадров в исходные.

Поле идентификатора протокола меток (Tag Protocol Identifier,TPI) заменило поле EtherType кадра Ethernet, которое заняло место после двухбайтного поля метки VLAN.

В поле метки VLAN имеется три подполя.

Подполе Priority предназначено для хранения трех бит приоритета кадра, что позволяет определить до 8 уровней приоритетов. Однобитный признак TR- Encapsulation показывает, содержат ли данные, переносимые кадром, инкапсулированный кадр формата IEEE (признак равен 1) 802.5 или же они соответствуют типу внешнего кадра (признак равен 0).

С помощью этого признака можно туннелировать трафик сетей Token Ring на коммутируемых магистралях Ethernet.

12-битный идентификатор VLAN (VID) уникально идентифицирует VLAN, к которой относится данный кадр.

Максимальный размер кадра Ethernet увеличивается при применении спецификации IEEE 802.1 Q не 4 байта- с 1518 байт до 1522 байт.

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
