---
## Front matter
lang: ru-RU
title: Лабораторная работа 4
subtitle: "Задание для самостоятельного выполнения"
author:
  - Извекова Мария Петровна
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 22 февраля 2025

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
---

# Информация

## Докладчик

:::::::::::::: {.columns align=center}
::: {.column width="70%"}

  * Извекова Мария Петровна
  * студентка 3-го курса
  * Российский университет дружбы народов
  * [1132226460@pfur.ru](mailto:1132226460@pfur.ru)

:::
::: {.column width="30%"}

![](./image/photo_my.jpg)

:::
::::::::::::::

## Цели и задачи

Выполнить задание для самостоятельного выполнения.

1. Для приведённой схемы разработать имитационную модель в пакете NS-2.
2. Построить график изменения размера окна TCP (в Xgraph и в GNUPlot).
3. Построить график изменения длины очереди и средней длины очереди на первом маршрутизаторе.

## Создание скрипта
::: columns
:::: column
![](image/photo1.jpg){#fig:001 width=70%}
::::

:::: column
![](image/photo2.jpg){#fig:001 width=70%}
::::
::::

## Создание скрипта
::: columns
:::: column
![](image/photo3.jpg){#fig:001 width=70%}
::::

:::: column
![](image/photo4.jpg){#fig:001 width=70%}
::::
::::

## После запуска файла .tcl получаем файлы с нашей симуляцией и графиками

::: columns
:::: column
![](image/photo6.jpg){#fig:001 width=70%}
::::

:::: column
![](image/photo_7.jpg){#fig:001 width=70%}
::::
::::

## Запускаем файл .nam симуляцию и поучаем схему моделируемой сети

![](image/photo5.jpg){#fig:001 width=70%}

## Изменение размера окна TCP на линке 1-го источника при N=22

![](image/photo_10.jpg){#fig:001 width=70%}

## Изменение размера окна TCP на всех источниках при N=22

![](image/photo_11.jpg){#fig:001 width=70%}

## Изменение размера длины очереди на линке (R1–R2) при N=20, qmin = 75, qmax = 150

![](image/photo_13.jpg){#fig:001 width=70%}

## Изменение размера средней длины очереди на линке (R1–R2) при N=20, qmin = 75, qmax = 150

![](image/photo_12.jpg){#fig:001 width=70%}

## Далее напишем скрипт для построение графиков в GNUPlot

![](image/photo_14.jpg){#fig:001 width=70%}

##
::: columns
:::: column
![Изменение размера окна TCP на всех источниках при N=22](image/photo_15.jpg){#fig:001 width=70%}
::::

:::: column
![Изменение размера окна TCP на линке 1-го источника при N=22](image/photo_16.jpg){#fig:001 width=70%}
::::
::::

##
::: columns
:::: column
![Изменение размера длины очереди на линке](image/photo_17.jpg){#fig:001 width=70%}
::::

:::: column
![Изменение размера средней длины очереди на линке](image/photo_18.jpg){#fig:001 width=70%}
::::
::::

## Выводы

В результате выполнения данной лабораторной работы была разработана имитационная модель в пакете NS-2, 
построены графики изменения размера окна TCP, изменения длины очереди и средней длины очереди.
