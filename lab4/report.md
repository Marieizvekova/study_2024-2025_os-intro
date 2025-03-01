---
## Front matter
title: "Задание для самостоятельного выполнения"
author: "Извекова Мария ПЕтровна"

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
  options:
	- spelling=modern
	- babelshorthands=true
polyglossia-otherlangs:
  name: english
## I18n babel
babel-lang: russian
babel-otherlangs: english
## Fonts
mainfont: IBM Plex Serif
romanfont: IBM Plex Serif
sansfont: IBM Plex Sans
monofont: IBM Plex Mono
mathfont: STIX Two Math
mainfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
romanfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
sansfontoptions: Ligatures=Common,Ligatures=TeX,Scale=MatchLowercase,Scale=0.94
monofontoptions: Scale=MatchLowercase,Scale=0.94,FakeStretch=0.9
mathfontoptions:
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

Выполнить задание для самостоятельного выполнения.

# Задание

1. Для приведённой схемы разработать имитационную модель в пакете NS-2.

2. Построить график изменения размера окна TCP (в Xgraph и в GNUPlot).

3. Построить график изменения длины очереди и средней длины очереди на первом маршрутизаторе.



# Выполнение лабораторной работы

Описание моделируемой сети:
– сеть состоит из N TCP-источников, N TCP-приёмников, двух маршрутизаторов
R1 и R2 между источниками и приёмниками (N — не менее 20);
– между TCP-источниками и первым маршрутизатором установлены дуплексные
соединения с пропускной способностью 100 Мбит/с и задержкой 20 мс очередью
типа DropTail;
– между TCP-приёмниками и вторым маршрутизатором установлены дуплексные
соединения с пропускной способностью 100 Мбит/с и задержкой 20 мс очередью
типа DropTail;
– между маршрутизаторами установлено симплексное соединение (R1–R2) с пропускной способностью 20 Мбит/с и задержкой 15 мс очередью типа RED,
размером буфера 300 пакетов; в обратную сторону — симплексное соединение (R2–R1) с пропускной способностью 15 Мбит/с и задержкой 20 мс очередью
типа DropTail;
– данные передаются по протоколу FTP поверх TCPReno;
– параметры алгоритма RED: qmin = 75, qmax = 150, qw = 0, 002, pmax = 0.1;
– максимальный размер TCP-окна 32; размер передаваемого пакета 500 байт; время


Создаем файл .tcl ндля построения сети. Зададим N = 22 TCP-источников, N = 2 TCP-приёмников, 
два маршрутизатора r1 и r2 между источниками и приёмниками. Между TCP-источниками и первым маршрутизатором устанавливаем 
дуплексные соединения с пропускной способностью 100 Мбит/с и задержкой 20 мс очередью типа DropTail; между TCP-приёмниками и 
вторым маршрутизатором устанавливаем дуплексные соединения с пропускной способностью 100 Мбит/с и задержкой 20 мс очередью типа 
DropTail; между маршрутизаторами установлено симплексное соединение (R1–R2) с пропускной способностью 20 Мбит/с и задержкой 15 мс 
очередью типа RED, размером буфера 300 пакетов; в обратную сторону - симплексное соединение (R2–R1) с пропускной способностью 15 Мбит/с 
и задержкой 20 мс очередью типа DropTail. Данные передаются по протоколу FTP поверх TCPReno; параметры алгоритма RED: 
qmin = 75, qmax = 150, qw = 0, 002, pmax = 0.1. Данный скрипт будет выглядеть следующим образом


![](image/photo1.jpg){#fig:001 width=70%}

![](image/photo2.jpg){#fig:001 width=70%}

![](image/photo3.jpg){#fig:001 width=70%}

![](image/photo4.jpg){#fig:001 width=70%}

После запуска файла .tcl получаем файлы с нашей симуляцией и графиками

![](image/photo6.jpg){#fig:001 width=70%}

![](image/photo_7.jpg){#fig:001 width=70%}


Запускаем файл .nam симуляцию и поучаем схему моделируемой сети

![](image/photo5.jpg){#fig:001 width=70%}

Полученный графики:

Изменение размера окна TCP на линке 1-го источника при N=22

![](image/photo_10.jpg){#fig:001 width=70%}

Изменение размера окна TCP на всех источниках при N=22

![](image/photo_11.jpg){#fig:001 width=70%}

Изменение размера длины очереди на линке (R1–R2)
при N=20, qmin = 75, qmax = 150

![](image/photo_13.jpg){#fig:001 width=70%}

Изменение размера средней длины очереди на линке (R1–R2)
при N=20, qmin = 75, qmax = 150

![](image/photo_12.jpg){#fig:001 width=70%}


Далее напишем скрипт для построение графиков в GNUPlot

![](image/photo_14.jpg){#fig:001 width=70%}

Результаты:

![Изменение размера окна TCP на всех источниках при N=22](image/photo_15.jpg){#fig:001 width=70%}

![Изменение размера окна TCP на линке 1-го источника при N=22](image/photo_16.jpg){#fig:001 width=70%}

![Изменение размера длины очереди на линке](image/photo_17.jpg){#fig:001 width=70%}

![Изменение размера средней длины очереди на линке](image/photo_18.jpg){#fig:001 width=70%}



# Выводы

В результате выполнения данной лабораторной работы была разработана имитационная модель в пакете NS-2, 
построены графики изменения размера окна TCP, изменения длины очереди и средней длины очереди.

