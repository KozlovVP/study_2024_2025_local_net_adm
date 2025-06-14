---
## Front matter
title: "Отчёт по лабораторной работе №15"
subtitle: "Динамическая маршрутизация"
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

Настроить динамическую маршрутизацию между территориями организации.

# Задание

1. Настроить динамическую маршрутизацию по протоколу OSPF на
маршрутизаторах msk-donskaya-gw-1, msk-q42-gw-1, msk-hostel-gw-1,
sch-sochi-gw-1.
2. Настроить связь сети квартала 42 в Москве с сетью филиала в г. Сочи
напрямую.
3. В режиме симуляции отследить движение пакета ICMP с ноутбука администратора сети на Донской в Москве (Laptop-PT admin) до компьютера
пользователя в филиале в г. Сочи pc-sochi-1.
4. На коммутаторе провайдера отключить временно vlan 6 и в режиме симуляции убедиться в изменении маршрута прохождения пакета ICMP с ноутбука
администратора сети на Донской в Москве (Laptop-PT admin) до компьютера пользователя в филиале в г. Сочи pc-sochi-1.
5. На коммутаторе провайдера восстановить vlan 6 и в режиме симуляции
убедиться в изменении маршрута прохождения пакета ICMP с ноутбука администратора сети на Донской в Москве (Laptop-PT admin) до компьютера
пользователя в филиале в г. Сочи pc-sochi-1.
6. При выполнении работы необходимо учитывать соглашение об именовании.

# Выполнение лабораторной работы

Настройка маршрутизатора msk-donskaya-gw-1 (рис. [-@fig:001])

![Настройка маршрутизатора msk-donskaya-gw-1](image/1.png){ #fig:001 width=70% }

Проверил состояние OSPF (рис. [-@fig:002])

![Состояние OSPF](image/2.png){ #fig:002 width=70% }

Настройка маршрутизатора msk-q42-gw-1 (рис. [-@fig:003])

![Настройка маршрутизатора msk-q42-gw-1](image/3.png){ #fig:003 width=70% }

Настройка маршрутизирующего коммутатора msk-hostel-gw-1 (рис. [-@fig:004])

![Настройка маршрутизирующего коммутатора msk-hostel-gw-1](image/4.png){ #fig:004 width=70% }

Настройка маршрутизатора sch-sochi-gw-1 (рис. [-@fig:005])

![Настройка маршрутизатора sch-sochi-gw-1](image/5.png){ #fig:005 width=70% }

Настройка интерфейсов коммутатора provider-sw-1 (рис. [-@fig:006])

![Настройка интерфейсов коммутатора provider-sw-1](image/6.png){ #fig:006 width=70% }

Настройка маршрутизатора msk-q42-gw-1 (рис. [-@fig:007])

![Настройка маршрутизатора msk-q42-gw-1](image/7.png){ #fig:007 width=70% }

Настройка коммутатора sch-sochi-sw-1 (рис. [-@fig:008])

![Настройка коммутатора sch-sochi-sw-1](image/8.png){ #fig:008 width=70% }

Настройка маршрутизатора sch-sochi-gw-1 (рис. [-@fig:009])

![Настройка маршрутизатора sch-sochi-gw-1](image/9.png){ #fig:009 width=70% }

В режиме симуляции проследим за движением ICMP-пакета при пересылке с администратора на ПК в Сочи: он идет через коммутатор на Донской и коммутатор в 42 квартал.

Движение пакета ICMP от администратора нп ПК в 42 квартал (рис. [-@fig:011])

![Движение пакета ICMP от администратора нп ПК в 42 квартал](image/11.png){ #fig:011 width=70% }

При отключении vlan 5 пакету, чтобы узнать маршрут необходимо дойти до маршрутизатора в Сочи, после чего пакет должен пойти через коммутатор провайдера по связи, настроенной ранее.

Пингование (рис. [-@fig:012])

![Пинг не проходит](image/12.png){ #fig:012 width=70% }

Потом включим vlan 5, и маршрут снова перестраивается на кратчайший (изначальный).

# Выводы

Настроить динамическую маршрутизацию между территориями организации.

# Контрольные вопросы

1. Какие протоколы относятся к протоколам динамической маршрутизации?
Протоколы:

- RIP (Routing Information Protocol)

- OSPF (Open Shortest Path First)

- EIGRP (Enhanced Interior Gateway Routing Protocol)

- IS-IS (Intermediate System to Intermediate System)

- BGP (Border Gateway Protocol)

2. Охарактеризуйте принципы работы протоколов динамической маршрутизации.

- Автоматическое определение и обновление маршрутов.

- Обмен маршрутной информацией между маршрутизаторами.

- Использование метрик (например, количество переходов, стоимость, задержка).

- Адаптация к изменениям сети (например, обрывам связей).

- Обновление таблиц маршрутизации без вмешательства администратора.

3. Опишите процесс обращения устройства из одной подсети к устройству из другой подсети по протоколу динамической маршрутизации.

- Устройство отправляет данные на шлюз (маршрутизатор).

- Маршрутизатор проверяет таблицу маршрутизации, сформированную динамическим протоколом.

- По таблице определяется наилучший маршрут к другой подсети.

- Данные передаются следующему маршрутизатору по цепочке до достижения получателя.

4. Опишите выводимую информацию при просмотре таблицы маршрутизации.

- Сетевой адрес назначения.

- Маска подсети.

- Следующий прыжок (Next Hop).

- Интерфейс выхода.

- Метрика маршрута.

- Тип маршрута (динамический/статический).

- Протокол, который добавил маршрут (например, OSPF, RIP).

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
