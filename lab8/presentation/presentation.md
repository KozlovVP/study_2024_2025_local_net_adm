---
## Front matter
lang: ru-RU
title: Лабораторная Работа №8
subtitle: Настройка сетевых сервисов. DHCP
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

Приобретение практических навыков по настройке динамического распределения IP-адресов посредством протокола DHCP (Dynamic Host Configuration Protocol) [5] в локальной сети.

## Задание

1. Добавить DNS-записи для домена donskaya.rudn.ru на сервер dns.
2. Настроить DHCP-сервис на маршрутизаторе.
3. Заменить в конфигурации оконечных устройствах статическое распределение адресов на динамическое.
4. При выполнении работы необходимо учитывать соглашение об именовании.

## Добавил dns-сервер

![dns-server](image/1.png){ #fig:001 width=70% }

## Настроил конфигурацию dns-сервера

![Конфигурация dns-сервера](image/2.png){ #fig:002 width=70% }

## Добавил dns-записи на сервер

![dns-записи](image/3.png){ #fig:003 width=70% }

## Настроил DHCP, часть 1

![Настройка DHCP](image/4.png){ #fig:004 width=70% }

## Настроил DHCP, часть 2

![Настройка DHCP](image/5.png){ #fig:005 width=70% }

## Посмотрел информацию о пулах DHCP

![Информация о пулах DHCP](image/6.png){ #fig:006 width=70% }

## Настроил interface f0/2 на msk−donskaya-vpkozlov−gw −1

![Настройка interface f0/2](image/7.png){ #fig:007 width=70% }

## На оконечных устройствах заменил в настройках статическое распределение адресов на динамическое

![Динамическое распределение адресов](image/8.png){ #fig:008 width=70% }

## Пропинговал www.donskaya.rudn.ru

![Пингование www.donskaya.rudn.ru](image/9.png){ #fig:009 width=70% }

## Открыл www.donskaya.rudn.ru в браузере

![www.donskaya.rudn.ru в браузере](image/10.png){ #fig:010 width=70% }

## Выводы

Приобрел практические навыки по настройке динамического распределения IP-адресов посредством протокола DHCP (Dynamic Host Configuration Protocol) [5] в локальной сети.