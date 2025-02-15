---
## Front matter
title: "Лабораторная работа 1"
subtitle: "Простые модели компьютерной сети"
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

Приобретение навыков моделирования сетей передачи данных с помощью средства имитационного моделирования NS-2, а также анализ полученных результатов
моделирования.

# Задание

1. Создание шаблона сценария для NS-2
2. Построение топологии сети из двух узлов и одного соединения
3. Построение усложненной топологиии сети
4. Построение кольцевой топологии сети

# Теоретическое введение

Network Simulator (NS-2) — один из программных симуляторов моделирования
процессов в компьютерных сетях. NS-2 позволяет описать топологию сети, конфигурацию источников и приёмников трафика, параметры соединений (полосу
пропускания, задержку, вероятность потерь пакетов и т.д.) и множество других
параметров моделируемой системы. Данные о динамике трафика, состоянии соединений и объектов сети, а также информация о работе протоколов фиксируются
в генерируемом trace-файле.

Объекты типа NODE
– $node id — возвращает идентификатор узла;
– $node neighbors — возвращает список соседних узлов;
– $node attach agent — прикрепляет агент типа agent к узлу;
– $node detach agent — отменяет прикрепление агента типа agent к узлу;
– $node agent port — возвращает ссылку на агента, прикреплённого к порту
port на данном узле, или пустую строку, если порт не используется.
– $node reset port — отменяет прикрепление всех агентов на данном узле и реинициализирует все переменные, связанные с агентами данного узла.
– $node join-group agent group — добавляет объект, определяемый объектной ссылкой agent для многопользовательской группы с адресом group. Это
также приводит к выделению соответствующего многопользовательского трафика протоколом групповой работы для обеспечения работы агента agent.
– $node allocaddr — возвращает адреса в многопользовательской группе в возрастающем порядке для каждого соединения, начиная с 0x8000 и заканчивая
0xFFFF.


# Выполнение лабораторной работы

В своём рабочем каталоге создайте директорию mip, к которой будут выполняться лабораторные работы. Внутри mip создайте директорию lab-ns, а в ней файл
shablon.tcl: (рис. [@fig:001] - [@fig:002]).

![Создание директории](image/photo_1.jpg){#fig:001 width=70%}

![Создание файла](image/photo_2.jpg){#fig:002 width=70%}

Создаем скрипт, с помощью которого будет создаваться шаблон, который  можно использовать в дальнейшем в большинстве разрабатываемых скриптов NS-2, добавляя в него до строки $ns at 5.0 "finish"
описание объектов и действий моделируемой системы. (рис. [-@fig:003] - [-@fig:004])

![Скрипт](image/photo_3.jpg){#fig:003 width=70%}

![Шаблон](image/photo_4.jpg){#fig:004 width=70%}

![Запуск скрипта](image/photo_7.jpg){#fig:005 width=70%}

Запускаем файл out.nam с помощью команды nam, сам скрипт запускается с помощью команды ns

Моделируем сеть передачи данных, состоящую из двух узлов, соединённых дуплексной линией связи с полосой пропускания 2
Мб/с и задержкой 10 мс, очередью с обслуживанием типа DropTail.  (рис. [-@fig:005])

![Реализация модели](image/photo_5.jpg){#fig:006 width=70%}

![Сама реализация](image/photo_6.jpg){#fig:007 width=70%}

На картинке [-@fig:006]  можно увидеть два узла, между которыми поисходит передача данных.

Усложняем нашу цепь: добавляем два узла,
– между узлами n0 и n2, n1 и n2 установлено дуплексное соединение с пропускной
способностью 2 Мбит/с и задержкой 10 мс;
– между узлами n2 и n3 установлено дуплексное соединение с пропускной способностью 1,7 Мбит/с и задержкой 20 мс;

![Скрипт](image/photo_8.jpg){#fig:008 width=70%}

![Скрипт](image/photo_9.jpg){#fig:009 width=70%}

![Скрипт](image/photo_10.jpg){#fig:010 width=70%}

Так как из узлов 0 и 1 выходят данные одновременно, после прохождения узла 2 данные теряются, так как соединение 2-3 имееть полосу лишь 1 Mb, когда из узлов 0 и 1 суммарно идет 1.6 Mb

Кольцевая топология

![Скрипт](image/photo_11.jpg){#fig:011 width=70%}

![Скрипт](image/photo_12.jpg){#fig:012 width=70%}

У нас получается передача данных от узла 0 к узлу 3. Происходит потеря данных и узел 1-2 обрывается, данные передаются от 0 к 1
![Скрипт](image/photo_13.jpg){#fig:013 width=70%}

Добавив в начало скрипта после команды создания объекта Simulator:
ns rtproto DV
увидим, что сразу после запуска в сети отправляется небольшое количество
маленьких пакетов, используемых для обмена информацией, необходимой для маршрутизации между узлами

![Скрипт](image/photo_14.jpg){#fig:014 width=70%}

![Реализация](image/photo_17.jpg){#fig:015 width=70%}

Задание
Необходимо построить сеть из 6 узлов, где будет кольцевая и один внешний узел

![Скрипт](image/photo_18.jpg){#fig:016 width=70%}

![Реализация](image/photo_19.jpg){#fig:017 width=70%}

![Реализация](image/photo_20.jpg){#fig:018 width=70%}

Видим что на рисунке 17 у нас данные от 0 до 5 идут по кратчайшему пути. После обрыва сети один меняют свое направление

# Выводы

Приобретели навыкы моделирования сетей передачи данных с помощью средства имитационного моделирования NS-2, а также проанализировали полученные результаты моделирования.

# Список литературы{.unnumbered}

::: Теоретические сведения по имитационному моделированию часть 1
