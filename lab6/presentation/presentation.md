---
## Front matter
lang: ru-RU
title: Лабораторная Работа №6
subtitle: Статическая маршрутизация VLAN
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

Настроить статическую маршрутизацию VLAN в сети.

## Задание

1. Добавить в локальную сеть маршрутизатор, провести его первоначальную настройку.
2. Настроить статическую маршрутизацию VLAN.
3. При выполнении работы необходимо учитывать соглашение об именовании

## Подсоединил к сети маршрутизатор msk-donskaya-vpkozlov-gw-1

![Подключение msk-donskaya-vpkozlov-gw-1](image/1.png){ #fig:001 width=70% }

## Настроил интерфейс f0/24 на msk-donskaya-vpkozlov-sw-1

![Интерфейс f0/24 на msk-donskaya-vpkozlov-sw-1](image/2.png){ #fig:002 width=70% }

## Настроил интерфейс f0/0 на msk-donskaya-vpkozlov-gw-1

![Интерфейс f0/0 на msk-donskaya-vpkozlov-gw-1](image/3.png){ #fig:003 width=70% }

## Произвел первичную конфигурацию маршрутизатора

![Первичная конфигурация маршрутизатора](image/4.png){ #fig:004 width=70% }

## Произвел конфигурацию VLAN-интерфейсов маршрутизатора, ч1

![Конфигурация VLAN-интерфейсов маршрутизатора](image/5.png){ #fig:005 width=70% }

## Произвел конфигурацию VLAN-интерфейсов маршрутизатора, ч2

![Конфигурация VLAN-интерфейсов маршрутизатора](image/6.png){ #fig:006 width=70% }

## Пропинговал некоторые ip-адреса

![Пингование некоторых ip-адресов](image/7.png){ #fig:007 width=70% }

## Выводы

Настроил статическую маршрутизацию VLAN в сети.