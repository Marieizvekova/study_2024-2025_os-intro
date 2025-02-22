---
## Front matter
title: "Лабораторная работа 3"
subtitle: "Моделирование стохастических процессов"
author: "Извекова Мария Петровна"

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
## Misc options
indent: true
header-includes:
  - \usepackage{indentfirst}
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Ознакомиться с одной из систем массового обслуживания M|M|1 и реализовать модель на NS-2

# Задание

Реализовать модель на NS-2 и построить график на GNUplot.

# Теоретическое введение

M|M|1 — однолинейная СМО с накопителем бесконечной ёмкости. Поступающий поток заявок — пуассоновский с интенсивностью λ. Времена обслуживания
заявок — независимые в совокупности случайные величины, распределённые по
экспоненциальному закону с параметром µ.

# Выполнение лабораторной работы

1. Создаем скрипт для создание симуляции модели СМО. В скрипте прописываем узлы, поступление пакетов, их размер и интервал поступления
Задаем агентов, присоединенных к источнику, задаем агентов приемник. (рис. [-@fig:001]) Задаем процедуру случайного генерирования пакетов. (рис. [-@fig:002])

![Скрипт 1](image/photo1.jpg){#fig:001 width=70%}

![Скрипт 2](image/photo2.jpg){#fig:002 width=70%}

2. Задаем расчет загрузки системы и вероятность потери пакетов(рис. [-@fig:003])

![Расчет](image/photo3.jpg){#fig:003 width=70%}

3. Выводим этот результат в терминале командой ns <название_файла.tcl>(рис. [-@fig:004])

![Вывод результата](image/photo4.jpg){#fig:004 width=70%}

4. Пишем скрипт для вывода графика на GNUplot и выводим результат c помощью одноименной команды(рис. [-@fig:005])

![Скрипт графика](image/photo5.jpg){#fig:005 width=70%}

5. Выводим этот график на экран. На нем представлены Размер очереди в пакетах, приближение сплайном и Приближение Безье (рис. [-@fig:006])

![График](image/photo6.jpg){#fig:006 width=70%}

# Выводы

Ознакомились с одним из представителей смо M|M|1, а так же построили ее модель на симмуляции


::: {#refs}
:::
