---
## Front matter
title: "Отчёт по лабораторной работе №13"
subtitle: "Статическая маршрутизация в Интернете. Планирование"
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

Провести подготовительные мероприятия по организации взаимодействия
через сеть провайдера посредством статической маршрутизации локальной
сети с сетью основного здания, расположенного в 42-м квартале в Москве,
и сетью филиала, расположенного в г. Сочи.

# Задание

1. Внести изменения в схемы L1, L2 и L3 сети, добавив в них информацию
о сети основной территории (42-й квартал в Москве) и сети филиала в г. Сочи.
2. Дополнить схему проекта, добавив подсеть основной территории организации 42-го квартала в Москве и подсеть филиала в г. Сочи.
3. Сделать первоначальную настройку добавленного в проект оборудования.
4. При выполнении работы необходимо учитывать соглашение об именовании.

# Выполнение лабораторной работы

Расположил новые устройства (рис. [-@fig:001])

![Новые устройства](image/1.png){ #fig:001 width=70% }

Поменял модули репитеров (рис. [-@fig:002])

![Модули репитеров](image/2.png){ #fig:002 width=70% }

Соединил новые устройства (рис. [-@fig:003])

![Соединение устройств](image/3.png){ #fig:003 width=70% }

Создал город Sochi (рис. [-@fig:004])

![Город Sochi](image/4.png){ #fig:004 width=70% }

Добавил квартал Q42 (рис. [-@fig:005])

![Квартал Q42](image/5.png){ #fig:005 width=70% }

Добавил здание (рис. [-@fig:006])

![Новое здание](image/6.png){ #fig:006 width=70% }

Поменял местоположение некоторых устройств (рис. [-@fig:007])

![Местоположение некоторых устройств](image/7.png){ #fig:007 width=70% }

Первоначальная настройка маршрутизатора msk-q42-gw-1 (рис. [-@fig:008])

![Первоначальная настройка маршрутизатора msk-q42-gw-1](image/8.png){ #fig:008 width=70% }

Первоначальная настройка маршрутизирующего коммутатора msk-hostel-gw-1 (рис. [-@fig:009])

![Первоначальная настройка msk-hostel-gw-1](image/9.png){ #fig:009 width=70% }

Первоначальная настройка коммутатора msk-q42-sw-1 (рис. [-@fig:010])

![Первоначальная настройка коммутатора msk-q42-sw-1](image/10.png){ #fig:010 width=70% }

Первоначальная настройка коммутатора msk-hostel-sw-1 (рис. [-@fig:011])

![Первоначальная настройка коммутатора msk-hostel-sw-1](image/11.png){ #fig:011 width=70% }

Первоначальная настройка маршрутизирующего коммутатора msk-hostel-gw-1 (рис. [-@fig:012])

![Первоначальная настройка маршрутизирующего коммутатора msk-hostel-gw-1](image/12.png){ #fig:012 width=70% }

# Выводы

Провел подготовительные мероприятия по организации взаимодействия
через сеть провайдера посредством статической маршрутизации локальной
сети с сетью основного здания, расположенного в 42-м квартале в Москве,
и сетью филиала, расположенного в г. Сочи.

# Контрольные вопросы

1. В каких случаях следует использовать статическую маршрутизацию? Примеры.

Статическую маршрутизацию используют, когда:

- Сеть небольшая и несложная, с постоянной топологией.

- Нужно обеспечить стабильные, предсказуемые маршруты без изменений.

- В целях безопасности — чтобы исключить автоматическое изменение маршрутов.

- Для маршрутизации по умолчанию или резервных путей.

Примеры:

- Домашняя сеть с одним маршрутизатором.

- Маршрутизация между двумя офисами по выделенной линии.

- Настройка резервного маршрута на предприятии.

2. Основные принципы статической маршрутизации между VLANs.

- Каждой VLAN назначается свой подсетевой адрес.

- Маршрутизатор или Layer 3 коммутатор настроен с интерфейсами (или подинтерфейсами) для каждой VLAN.

- В статической маршрутизации прописываются маршруты между VLANs вручную.

- Статические маршруты обеспечивают передачу данных между VLANs без динамического обмена маршрутами.

- Необходимо учитывать маршрутизацию по умолчанию для внешнего доступа.

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
