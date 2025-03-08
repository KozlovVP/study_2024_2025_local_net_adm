---
## Front matter
lang: ru-RU
title: Лабораторная Работа №4
subtitle: Первоначальное конфигурирование сети
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

Провести подготовительную работу по первоначальной настройке коммутаторов сети.

## Задание

Требуется сделать первоначальную настройку коммутаторов сети, представленной на схеме L1. Под первоначальной
настройкой понимается указание имени устройства, его IP-адреса, настройка
доступа по паролю к виртуальным терминалам и консоли, настройка удалённого доступа к устройству по ssh.
При выполнении работы необходимо учитывать соглашение об именовании.

## Разместил коммутаторы, серверы и оконеные устройства согласно схеме L1

![Построение топологии сети по схеме L1](image/1.png){ #fig:001 width=70% }

## Задал ip-адрес 10.128.1.2 для msk-donskaya-vpkozlov-sw-1

![Конфигурация коммутатора msk-donskaya-vpkozlov-sw-1](image/2.png){ #fig:002 width=70% }

## Задал ip-адрес 10.128.1.3 для msk-donskaya-vpkozlov-sw-2

![Конфигурация коммутатора msk-donskaya-vpkozlov-sw-2](image/3.png){ #fig:003 width=70% }

## Задал ip-адрес 10.128.1.4 для msk-donskaya-vpkozlov-sw-3

![Конфигурация коммутатора msk-donskaya-vpkozlov-sw-3](image/4.png){ #fig:004 width=70% }

## Задал ip-адрес 10.128.1.5 для msk-donskaya-vpkozlov-sw-4

![Конфигурация коммутатора msk-donskaya-vpkozlov-sw-4](image/5.png){ #fig:005 width=70% }

## Задал ip-адрес 10.128.1.6 для msk-pavlovskaya-vpkozlov-sw-1

![Конфигурация коммутатора msk-pavlovskaya-vpkozlov-sw-1](image/6.png){ #fig:006 width=70% }

## Выводы

Провел подготовительную работу по первоначальной настройке коммутаторов сети.