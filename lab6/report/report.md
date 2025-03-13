---
## Front matter
title: "Лабораторная работа 6"
subtitle: "Модель хищник-жертва"
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

Реализовать модель "хищник-жертва" в xcos.

# Задание

1. Реализовать модель "хищник-жертва" в xcos;
2. Реализовать модель "хищник-жертва" с помощью блока Modelica generic в xcos;
3. Реализовать модель "хищник-жертва" в OpenModelica



# Выполнение лабораторной работы

Модель «хищник–жертва» (модель Лотки — Вольтерры) представляет собой модель межвидовой конкуренции. В математической форме модель имеет вид:

$$
\begin{cases}
\dot{x} = ax - bxy \\
\dot{y} = cxy - dy
\end{cases}
$$

где x — количество жертв; y — количество хищников; a,b , c,d — коэффициенты, отражающие взаимодействия между видами: a— коэффициент рождаемости жертв; b — коэффициент убыли жертв; c— коэффициент рождения хищников; d— коэффициент убыли хищников.


Зафиксируем начальные данные: a = 2, b = 1, c = 0, 3, d = 1, x(0) = 2, y(0) = 1.
В меню Моделирование, Задать переменные окружения зададим значения коэффициентов a, b, c, d  (рис. [-@fig:001]).

![](image/photo_1.jpg){#fig:001 width=70%}


Для реализации модели в дополнение к блокам CLOCK_c, CSCOPE, TEXT_f, MUX, INTEGRAL_m, GAINBLK_f, SUMMATION, PROD_f потребуется

![](image/photo_2.jpg){#fig:002 width=70%}


Готовая модель «хищник–жертва» представлена на рис. (рис. [-@fig:002]).

![](image/photo_3.jpg){#fig:003 width=70%}


В параметрах блоков интегрирования необходимо задать начальные значения x(0) = 2, y(0) = 1 

![](image/photo_7.jpg){#fig:004 width=70%}

![](image/photo_6.jpg){#fig:005 width=70%}

В меню Моделирование, Установка необходимо задать конечное время интегрирования, равным времени моделирования: 30.

![](image/photo_8.jpg){#fig:006 width=70%}

Результат моделирования представлен на рис (рис. [-@fig:007])

![](image/photo_4.jpg){#fig:007 width=70%}

На рис. 2 приведён фазовый портрет модели .
Фазовый портрет — графическое изображение системы на фазовой плоскости
(или в многомерном пространстве), по координатным осям которого отложены значения величин переменных системы.


# Реализация модели с помощью блока Modelica в xcos

Для реализации модели (рис. [-@fig:002]) с помощью языка Modelica потребуются следующие
блоки xcos: CLOCK_c, CSCOPE, CSCOPXY, TEXT_f, MUX, CONST_m и MBLOCK (Modelica
generic).

![](image/photo_5.jpg){#fig:008 width=70%}

Как и ранее, задаём значения коэффициентов a, b, c, d

![](image/photo_1.jpg){#fig:009 width=70%}

Параметры блока Modelica представлены на (рис. [-@fig:010]) . Переменные на входе (“a”,
“b”, “c”, “d”) и выходе (“x”, “y”) блока заданы как внешние (“E”).

![](image/photo_9.jpg){#fig:010 width=70%}

Код на языке Modelica

class generic
////automatically generated ////
//input variables
Real a,b,c,d;
//output variables
// Real x,y;
////do not modif above this line ////
Real x(start=2), y(start=1);
// Модель хищник-жертва
equation
der(x)=a*x-b*x*y;
der(y)=c*x*y-d*y;
end generic;


Готовая модель «хищник–жертва» представлена на рис.  [-@fig:011]

![](image/photo_10.jpg){#fig:011 width=70%}

Результат второго моделирования представлен на рис (рис. [-@fig:012])

![](image/photo_11.jpg){#fig:012 width=70%}

# Реализовать модель "хищник-жертва" в OpenModelica

Реализуем модель «хищник – жертва» в OpenModelica. Построим графики изменения численности популяций и фазовый портрет.

![](image/photo_12.jpg){#fig:012 width=70%}

Выполним симуляцию, поставим конечное время 30с. Получим график изменения численности хищников и жертв (рис. [-@fig:014]), а также фазовый портрет (рис. [-@fig:015]).

![](image/photo_13.jpg){#fig:013 width=70%}

![](image/photo_14.jpg){#fig:014 width=70%}

![](image/photo_15.jpg){#fig:015 width=70%}

# Вывод

В процессе выполнения данной лабораторной реализована модель "хищник-жертва" в xcos.
