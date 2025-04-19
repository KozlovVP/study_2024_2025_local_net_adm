---
## Front matter
lang: ru-RU
title: Лабораторная Работа №9
subtitle: Использование протокола STP. Агрегирование каналов
author:
  - Козлов В.П.
institute:
  - Российский университет дружбы народов им. Патриса Лумумбы, Москва, Россия

## i18n babel
babel-lang: russian
babel-otherlangs: english

## Formatting pdf
toc: false
toc-title: Содержание
slide_level: 2
aspectratio: 169
section-titles: true
theme: metropolis
header-includes:
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
 - '\makeatletter'
 - '\makeatother'

## Fonts
mainfont: Arial
romanfont: Arial
sansfont: Arial
monofont: Arial
---


## Докладчик

  * Козлов Всеволод Павлович
  * НФИбд-02-22
  * Российский университет дружбы народов
  * [1132226428@pfur.ru]
  
# Выполнение лабораторной работы

## Цель работы

Изучение возможностей протокола STP и его модификаций по обеспечению
отказоустойчивости сети, агрегированию интерфейсов и перераспределению
нагрузки между ними.

## Задание

1. Сформируйте резервное соединение между коммутаторами msk-donskayasw-1 и msk-donskaya-sw-3.
2. Настройте балансировку нагрузки между резервными соединениями.
3. Настройте режим Portfast на тех интерфейсах коммутаторов, к которым
подключены серверы.
4. Изучите отказоустойчивость резервного соединения.
5. Сформируйте и настройте агрегированное соединение интерфейсов Fa0/20
– Fa0/23 между коммутаторами msk-donskaya-sw-1 и msk-donskaya-sw-4.
6. При выполнении работы необходимо учитывать соглашение об именовании.

## Логическая схема сети с резервным соединением

![Логическая схема сети с резервным соединением](image/1.png){ #fig:001 width=70% }

## Настроил f0/23 на msk-donskaya-vpkozlov-sw-1

![f0/23 на msk-donskaya-vpkozlov-sw-1](image/2.png){ #fig:002 width=70% }

## Настроил f0/23 на msk-donskaya-vpkozlov-sw-4

![f0/23 на msk-donskaya-vpkozlov-sw-4](image/3.png){ #fig:003 width=70% }

## Проверил пингование

![Проверка пингования](image/4.png){ #fig:004 width=70% }

## Отследил движение пакетов

![Движение пакетов](image/5.png){ #fig:005 width=70% }

## На коммутаторе msk-donskaya-sw-2 посмотрел состояние протокола STP для vlan 3

![Состояние протокола STP для vlan 3](image/6.png){ #fig:006 width=70% }

## В качестве корневого коммутатора STP настроил коммутатор mskdonskaya-sw-1

![Корневой коммутатор STP](image/7.png){ #fig:007 width=70% }

## Отследил движение пакетов

![Движение пакетов](image/8.png){ #fig:008 width=70% }

## Настроил режим Portfast на тех интерфейсах коммутаторов, к которым подключены серверы

![Режим Portfast на тех интерфейсах](image/9.png){ #fig:009 width=70% }

## Сделал shutdown на g0/2

![shutdown на g0/2](image/10.png){ #fig:010 width=70% }

## Отключил shutdown на g0/2

![Отключение shutdown на g0/2](image/11.png){ #fig:011 width=70% }

## Переключил коммутаторы на режим работы по протоколу Rapid PVST+

![Режим работы по протоколу Rapid PVST+](image/12.png){ #fig:012 width=70% }

## Сделал shutdown на g0/2

![shutdown на g0/2](image/13.png){ #fig:013 width=70% }

## Время восстановления соединения

![Время восстановления соединения](image/14.png){ #fig:014 width=70% }

## Настроил агрегирование каналов на msk−donskaya-vpkozlov−sw−1

![Агрегирование каналов на msk−donskaya-vpkozlov−sw−1](image/15.png){ #fig:015 width=70% }

## Настроил агрегирование каналов на msk−donskaya-vpkozlov−sw−2

![Агрегирование каналов на msk−donskaya-vpkozlov−sw−2](image/16.png){ #fig:016 width=70% }

## Выводы

Изучил возможности протокола STP и его модификации по обеспечению
отказоустойчивости сети, агрегированию интерфейсов и перераспределению
нагрузки между ними.