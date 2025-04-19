---
## Front matter
title: "Отчёт по лабораторной работе №9"
subtitle: "Использование протокола STP. Агрегирование каналов"
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

Изучение возможностей протокола STP и его модификаций по обеспечению
отказоустойчивости сети, агрегированию интерфейсов и перераспределению
нагрузки между ними.

# Задание

1. Сформируйте резервное соединение между коммутаторами msk-donskayasw-1 и msk-donskaya-sw-3.
2. Настройте балансировку нагрузки между резервными соединениями.
3. Настройте режим Portfast на тех интерфейсах коммутаторов, к которым
подключены серверы.
4. Изучите отказоустойчивость резервного соединения.
5. Сформируйте и настройте агрегированное соединение интерфейсов Fa0/20
– Fa0/23 между коммутаторами msk-donskaya-sw-1 и msk-donskaya-sw-4.
6. При выполнении работы необходимо учитывать соглашение об именовании.

# Выполнение лабораторной работы

Логическая схема сети с резервным соединением (рис. [-@fig:001])

![Логическая схема сети с резервным соединением](image/1.png){ #fig:001 width=70% }

Настроил f0/23 на msk-donskaya-vpkozlov-sw-1 (рис. [-@fig:002])

![f0/23 на msk-donskaya-vpkozlov-sw-1](image/2.png){ #fig:002 width=70% }

Настроил f0/23 на msk-donskaya-vpkozlov-sw-4 (рис. [-@fig:003])

![f0/23 на msk-donskaya-vpkozlov-sw-4](image/3.png){ #fig:003 width=70% }

Проверил пингование (рис. [-@fig:004])

![Проверка пингования](image/4.png){ #fig:004 width=70% }

Отследил движение пакетов (рис. [-@fig:005])

![Движение пакетов](image/5.png){ #fig:005 width=70% }

На коммутаторе msk-donskaya-sw-2 посмотрел состояние протокола STP для vlan 3 (рис. [-@fig:006])

![Состояние протокола STP для vlan 3](image/6.png){ #fig:006 width=70% }

В качестве корневого коммутатора STP настроил коммутатор mskdonskaya-sw-1 (рис. [-@fig:007])

![Корневой коммутатор STP](image/7.png){ #fig:007 width=70% }

Отследил движение пакетов (рис. [-@fig:008])

![Движение пакетов](image/8.png){ #fig:008 width=70% }

Настроил режим Portfast на тех интерфейсах коммутаторов, к которым подключены серверы (рис. [-@fig:009])

![Режим Portfast на тех интерфейсах](image/9.png){ #fig:009 width=70% }

Сделал shutdown на g0/2 (рис. [-@fig:010])

![shutdown на g0/2](image/10.png){ #fig:010 width=70% }

Отключил shutdown на g0/2 (рис. [-@fig:011])

![Отключение shutdown на g0/2](image/11.png){ #fig:011 width=70% }

Переключил коммутаторы на режим работы по протоколу Rapid PVST+ (рис. [-@fig:012])

![Режим работы по протоколу Rapid PVST+](image/12.png){ #fig:012 width=70% }

Сделал shutdown на g0/2 (рис. [-@fig:013])

![shutdown на g0/2](image/13.png){ #fig:013 width=70% }

Время восстановления соединения (рис. [-@fig:014])

![Время восстановления соединения](image/14.png){ #fig:014 width=70% }

Настроил агрегирование каналов на msk−donskaya-vpkozlov−sw−1 (рис. [-@fig:015])

![Агрегирование каналов на msk−donskaya-vpkozlov−sw−1](image/15.png){ #fig:015 width=70% }

Настроил агрегирование каналов на msk−donskaya-vpkozlov−sw−2 (рис. [-@fig:016])

![Агрегирование каналов на msk−donskaya-vpkozlov−sw−2](image/16.png){ #fig:016 width=70% }

# Выводы

Изучил возможностей протокола STP и его модификации по обеспечению
отказоустойчивости сети, агрегированию интерфейсов и перераспределению
нагрузки между ними.

# Контрольные вопросы

1. Какую информацию можно получить, воспользовавшись командой определения состояния протокола STP для VLAN (на корневом и не на корневом устройстве)? Приведите примеры вывода подобной информации на устройствах.

С помощью этой команды вы можете просмотреть общую информацию о протоколе ST на коммутаторе. Вы можете просмотреть идентификатор Root, корневой мост и интерфейсные порты коммутатора, а также просмотреть состояния портов интерфейсов коммутатора.

Кроме того, если корневой мост настроен вручную, вы можете проверить значение приоритета коммутатора с помощью этой команды.

2. При помощи какой команды можно узнать, в каком режиме, STP или
Rapid PVST+, работает устройство? Приведите примеры вывода подобной
информации на устройствах.

При помощи команды `show ru` просмотр текущей конфигурации.

3. Для чего и в каких случаях нужно настраивать режим Portfast?

Portfast -- функция, которая позволяет порту пропустить состояния listening и learning и сразу же перейти в состояние forwarding. Настраивается на портах уровня доступа, к которым подключены пользователи или сервера. Цель функции PortFast минимизировать время, которое необходимо для того чтобы порт перешел в состояние forward. Поэтому она эффективна только когда применена к портам, к которым подключены хосты.

4. В чем состоит принцип работы агрегированного интерфейса? Для чего он
используется?

Агрегирование каналов — это технология объединения нескольких параллельных каналов передачи данных в сетях Ethernet в один логический. Она позволяет увеличить пропускную способность и повысить надёжность.

Основное применение технологии агрегации — объединение каналов в сетевых коммутаторах. Также можно настроить агрегирование для компьютерных сетевых адаптеров.

5. В чём принципиальные отличия при использовании протоколов LACP (Link Aggregation Control Protocol), PAgP (Port Aggregation Protocol) и статического агрегирования без использования протоколов?

LACP и PAgP - динамические протоколы, управляющие созданием и управлением агрегированных соединений. Статическое агрегирование настраивается вручную без использования протоколов.

6. При помощи каких команд можно узнать состояние агрегированного канала
EtherChannel?

Команды `show etherchannel summary` и `show etherchannel port-channel`.

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
