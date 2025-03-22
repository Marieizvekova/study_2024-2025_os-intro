---
## Front matter
title: "Лабораторная работа 7"
subtitle:  "Модель M|M|1|"
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

Рассмотреть пример моделирования в xcos системы массового обслуживания типа M|M|1|∞.

# Задание

1. Реализовать модель системы массового обслуживания типа M|M|1|∞.

2. Построить график поступления и обработки заявок;
3. Построить график динамики размера очереди.

# Выполнение лабораторной работы

Зафиксируем начальные данные: 
λ=0.3; μ=0.35;z0=6. В меню Моделирование, Установить контекст зададим значения коэффициентов (рис. [-@fig:001] - [-@fig:003]).
Так как я создавала супер блоки уже в организованном суперблоке, то установку контекста я делала 3 раза 

![Фиксируем параметр лямбда](image/photo_7.png){#fig:001 width=70%}

![Фиксируем параметр мю](image/photo_6.png){#fig:002 width=70%}

![Фиксируем параметр z](image/photo_8.png){#fig:003 width=70%}


Суперблок, моделирующий поступление заявок, представлен на рис. [-@fig:004]. Тут у нас заявки поступают в систему по пуассоновскому закону. Поступает заявка в суперблок, идет в синхронизатор входных и выходных сигналов, происходит равномерное распределение на интервале 
[0;1](также заявка идет в обработчик событий), далее идет преобразование в экспоненциальное распределение с параметром λ, далее заявка опять попадает в обработчик событий и выходит из суперблока.

![Суперблок для поступления заявок](image/photo_2.png){#fig:004 width=70%}

![Вывод суперблока](image/photo_3.png){#fig:005 width=70%}

Суперблок, моделирующий процесс обработки заявок, представлен на рис. [-@fig:006]. Тут происходит обработка заявок в очереди по экспоненциальному закону.

![Суперблок для обработки заявок](image/photo_5.png){#fig:006 width=70%}

![Вывод второго суперблока](image/photo_4.png){#fig:007 width=70%}

Готовая модель$M|M|1|\infty$ представлена на рис. [-@fig:008]. Тут есть селектор, два суперблока, построенных ранее, первоначальное событие на вход в суперблок, суммирование, оператор задержки (имитация очереди), также есть регистрирующие блоки: регистратор размера очереди и регистратор событий.

![Готовая модель](image/photo_9.png){#fig:008 width=70%}

![Измененные параметры суммы](image/photo_12.png){#fig:009 width=70%}

![Изменения параметра блока регистрирующая очередь](image/photo_13.png){#fig:010 width=70%}

![Изменения параметра блока регистрирующая события](image/photo_14.png){#fig:011 width=70%}

Результат моделирования представлен на рис. [-@fig:012] и [-@fig:013]. График динамики размера очереди и поступление заявок.

![Размер очереди](image/photo_10.png){#fig:012 width=70%}

![Поступление заявок](image/photo_11.png){#fig:013 width=70%}

# Вывод

В процессе выполнения данной лабораторной работы я рассмотрела пример моделирования в xcos системы массового обслуживания типа M|M|1|∞.

