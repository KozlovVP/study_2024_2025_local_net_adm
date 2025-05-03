---
## Front matter
title: "Отчёт по лабораторной работе №12"
subtitle: "Настройка NAT"
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

Приобретение практических навыков по настройке доступа локальной сети
к внешней сети посредством NAT.

# Задание

1. Сделать первоначальную настройку маршрутизатора provider-gw-1 и коммутатора provider-sw-1 провайдера: задать имя, настроить доступ по
паролю и т.п.
2. Настроить интерфейсы маршрутизатора provider-gw-1 и коммутатора
provider-sw-1 провайдера.
3. Настроить интерфейсы маршрутизатора сети «Донская» для доступа к сети
провайдера.
4. Настроить на маршрутизаторе сети «Донская» NAT с правилами, указанными в разделе 12.2.
5. Настроить доступ из внешней сети в локальную сеть организации, как
указано в разделе 12.2.
6. Проверить работоспособность заданных настроек.
7. При выполнении работы необходимо учитывать соглашение об именовании.

# Выполнение лабораторной работы

Провел первоначальную настройку маршрутизатора provider-gw-1 (рис. [-@fig:001])

![Первоначальная настройка маршрутизатора provider-gw-1](image/1.png){ #fig:001 width=70% }

Провел настройку маршрутизатора provider-gw-1 (рис. [-@fig:002])

![Настройка интерфейсов маршрутизатора provider-gw-1](image/2.png){ #fig:002 width=70% }

Провел первоначальную настройку коммутатора provider-sw-1 (рис. [-@fig:003])

![Первоначальная настройка коммутатора provider-sw-1](image/3.png){ #fig:003 width=70% }

Провел настройку интерфейсов коммутатора provider-sw-1 (рис. [-@fig:004])

![Настройка интерфейсов коммутатора provider-sw-1](image/4.png){ #fig:004 width=70% }

Настройка интерфейсов маршрутизатора msk-donskaya-gw-1 (рис. [-@fig:005])

![Настройка интерфейсов маршрутизатора msk-donskaya-gw-1](image/5.png){ #fig:005 width=70% }

Настроил пул адресов для NAT (рис. [-@fig:006])

![Пул адресов для NAT](image/6.png){ #fig:006 width=70% }

Настройка списка доступа для NAT (рис. [-@fig:007])

![Настройка списка доступа для NAT](image/7.png){ #fig:007 width=70% }

Настроил сеть дисплейных классов, кафедр и тп (рис. [-@fig:008])

![Настройка сетей](image/8.png){ #fig:008 width=70% }

Настройка NAT (рис. [-@fig:009])

![Настройка NAT](image/9.png){ #fig:009 width=70% }

Проверка доступности маршрутизаторов (рис. [-@fig:010])

![Проверка доступности маршрутизаторов](image/10.png){ #fig:010 width=70% }

Проверка доступности www.yandex.ru (рис. [-@fig:011])

![Проверка доступности www.yandex.ru](image/11.png){ #fig:011 width=70% }

Настройка доступа из Интернета (WWW-сервер, Файловый сервер) (рис. [-@fig:012])

![Настройка доступа из Интернета (WWW-сервер, Файловый сервер)](image/12.png){ #fig:012 width=70% }

Настройка доступа из Интернета (Почтовый сервер, Доступ по RDP) (рис. [-@fig:013])

![Настройка доступа из Интернета (WWW-сервер, Файловый сервер)](image/13.png){ #fig:013 width=70% }

Добавил ноутбук к internet (рис. [-@fig:014])

![Добавление ноутбука к internet](image/14.png){ #fig:014 width=70% }

Проверка доступа по ftp (рис. [-@fig:015])

![Проверка доступа по ftp](image/15.png){ #fig:015 width=70% }

Проверка доступа к веб-серверу (рис. [-@fig:016])

![Проверка доступа к веб-серверу](image/16.png){ #fig:016 width=70% }

# Выводы

Приобрел практические навыки по настройке доступа локальной сети
к внешней сети посредством NAT.

# Контрольные вопросы

1. В чём состоит основной принцип работы NAT (что даёт наличие NAT в сети
организации)?

Идея NAT заключается в том, чтобы осуществлять перевод частного локального IP-адреса в общедоступный глобальный IP-адрес и наоборот. Это необходимо для обеспечения доступа к Интернету локальным узлам, использующим частные адреса.

Наличие NAT в сети организации позволяет экономить публичные IP-адреса и повышать безопасность защитой внутренних устройств от прямого доступа извне.

2. В чём состоит принцип настройки NAT (на каком оборудовании и что
нужно настроить для из локальной сети во внешнюю сеть через NAT)?

Как правило, граничный маршрутизатор настроен для NAT, то есть маршрутизатор, который имеет один интерфейс в локальной (внутренней, inside) сети и один интерфейс в глобальной (внешней, outside) сети. Когда пакет проходит за пределы локальной (inside) сети, NAT преобразует локальный (частный, private) IP-адрес в глобальный (публичный, public) IP-адрес. Когда пакет входит в локальную сеть, глобальный (public) IP-адрес преобразуется в локальный (private) IP-адрес. Граничный маршрутизатор выступает в роли шлюза между внутренней корпоративной сетью и внешней сетью, например, Интернетом.

3. Можно ли применить Cisco IOS NAT к субинтерфейсам?

Да. Преобразования NAT источника или назначения могут применяться к любому интерфейсу или подинтерфейсу с
IP-адресом (включая интерфейсы программы набора номера).

4. Что такое пулы IP NAT?

Пул NAT — это набор из одного или нескольких общедоступных IPv4-адресов, которые используются в маршрутизаторе NAT.

При отправке трафика устройством из внутренней сети во внешнюю сеть маршрутизатор преобразует его внутренний IPv4-адрес в один из адресов, входящих в состав пула.

В результате действия такого механизма весь исходящий из сети трафик внешние устройства «видят» с общедоступным адресом IPv4, который можно назвать NAT IP-адресом.

5. Что такое статические преобразования NAT?

Статическое преобразование сетевых адресов (NAT) выполняет взаимно однозначное преобразование внутренних IP-адресов во внешние. Это позволяет преобразовать IP-адрес внутренней сети во внешний IP-адрес. Статический NAT позволяет устанавливать соединения как внутренним, так и внешним системам, например, хостам Internet.

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
