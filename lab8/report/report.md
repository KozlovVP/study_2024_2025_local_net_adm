---
## Front matter
title: "Отчёт по лабораторной работе №8"
subtitle: "Настройка сетевых сервисов. DHCP"
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

Приобретение практических навыков по настройке динамического распределения IP-адресов посредством протокола DHCP (Dynamic Host Configuration Protocol) [5] в локальной сети.

# Задание

1. Добавить DNS-записи для домена donskaya.rudn.ru на сервер dns.
2. Настроить DHCP-сервис на маршрутизаторе.
3. Заменить в конфигурации оконечных устройствах статическое распределение адресов на динамическое.
4. При выполнении работы необходимо учитывать соглашение об именовании.

# Выполнение лабораторной работы

Добавил dns-сервер (рис. [-@fig:001])

![dns-server](image/1.png){ #fig:001 width=70% }

Настроил конфигурацию dns-сервера (рис. [-@fig:002])

![Конфигурация dns-сервера](image/2.png){ #fig:002 width=70% }

Добавил dns-записи на сервер (рис. [-@fig:003])

![dns-записи](image/3.png){ #fig:003 width=70% }

Настроил DHCP, часть 1 (рис. [-@fig:004])

![Настройка DHCP](image/4.png){ #fig:004 width=70% }

Настроил DHCP, часть 2 (рис. [-@fig:005])

![Настройка DHCP](image/5.png){ #fig:005 width=70% }

Посмотрел информацию о пулах DHCP (рис. [-@fig:006])

![Информация о пулах DHCP](image/6.png){ #fig:006 width=70% }

Настроил interface f0/2 на msk−donskaya-vpkozlov−gw −1 (рис. [-@fig:007])

![Настройка interface f0/2](image/7.png){ #fig:007 width=70% }

На оконечных устройствах заменил в настройках статическое распределение адресов на динамическое (рис. [-@fig:008])

![Динамическое распределение адресов](image/8.png){ #fig:008 width=70% }

Пропинговал www.donskaya.rudn.ru (рис. [-@fig:009])

![Пингование www.donskaya.rudn.ru](image/9.png){ #fig:009 width=70% }

Открыл www.donskaya.rudn.ru в браузере (рис. [-@fig:010])

![www.donskaya.rudn.ru в браузере](image/10.png){ #fig:010 width=70% }

# Выводы

Приобрел практические навыки по настройке динамического распределения IP-адресов посредством протокола DHCP (Dynamic Host Configuration Protocol) [5] в локальной сети.

# Контрольные вопросы

1. За что отвечает протокол DHCP?

Протокол DHCP — это стандартный протокол, определяемый RFC 1541 (который заменяется RFC 2131), позволяющий серверу динамически распределять IP-адреса и сведения о конфигурации клиентам.

2. Какие типы DHCP-сообщений передаются по сети?

По данным источника, в DHCP-протоколе используются следующие типы сообщений:

* DHCPDISCOVER — клиент отправляет пакет, пытаясь найти сервер DHCP в сети.

* DHCPOFFER — сервер отправляет пакет, включающий предложение использовать уникальный IP-адрес.

* DHCPREQUEST — клиент отправляет пакет с просьбой выдать в аренду предложенный уникальный адрес.

* DHCPACK — сервер отправляет пакет, в котором утверждается запрос клиента на использование IP-адреса.

3. Какие параметры могут быть переданы в сообщениях DHCP?

Параметры DHCP могут включать IP-адреса, шлюзы, DNS-серверы, временные интервалы аренды и другие настройки сети.

4. Что такое DNS?

DNS (Система доменных имён, англ. Domain Name System) — это иерархическая децентрализованная система именования для интернет-ресурсов подключённых к Интернет, которая ведёт список доменных имён вместе с их числовыми IP-адресами или местонахождениями. DNS позволяет перевести простое запоминаемое имя хоста в IP-адрес.

5. Какие типы записи описания ресурсов есть в DNS и для чего они используются? 
 
Основными ресурсными записями DNS являются:

* A-запись — одна из самых важных записей. Именно эта запись указывает на IP-адрес сервера, который привязан к доменному имени.
* MX-запись — указывает на сервер, который будет использован при отсылке доменной электронной почты.
* NS-запись — указывает на DNS-сервер домена.
* CNAME-запись — позволяет одному из поддоменов дублировать DNS-записи своего родителя.

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
