---
## Front matter
lang: ru-RU
title:  "Лабораторная работа 12"
subtitle: "Пример моделирования простого протокола передачи данных"
author:
  - Извекова Мария Петровна
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 19 апрель 2025

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

# Докладчик

:::::::::::::: {.columns align=center}
::: {.column width="70%"}

  * Извекова Мария Петровна
  * студентка 3-го курса
  * Российский университет дружбы народов
  * [1132226460@pfur.ru](mailto:1132226460@pfur.ru)

:::
::: {.column width="30%"}

![](./image/my_photo.jpg)

:::
::::::::::::::

# Цель работы

Реализовать простой протокол передачи данных в CPN Tools.

# Задание

1. Реализовать простой протокол передачи данных в CPN Tools.
2. Вычислить пространство состояний, сформировать отчет о нем и построить граф.

# Выполнение лабораторной работы

![Задаем декларацию модели](image/2.png){#fig:001 width=50%}

#

![Начальный граф](image/1.png){#fig:002 width=70%}

#

![Граф со вспомогательными состояниями](image/3.png){#fig:003 width=70%}

#
::: columns
::: column
![Дополнительная декларация](image/4.png){#fig:004 width=70%}
::::

::: column
![Функция](image/5.png){#fig:005 width=70%}
::: 
:::

#

![Готовая модель](image/9.png){#fig:006 width=70%}

#

![Готовая модель в запущенном состоянии](image/8.png){#fig:007 width=70%}

# Упражнение

![Файл отчета](image/13.png){#fig:008 width=70%}

#

![Граф состояний](image/11.png){#fig:009 width=70%}

# Вывод

В процессе выполнения данной лабораторной работы я реализовала простой протокол передачи данных в CPN Tools и проведен анализ его пространства состояний.

# Библиография

1. Зайцев Д. А., Шмелева Т. Р. Моделирование телекоммуникационных систем
в CPN Tools. — Одесса : Одесская национальная академия связи им. А.С. Попова,
2008.

2. CPN Tool. — 2014. — URL: http://cpntools.org.

