---
## Front matter
lang: ru-RU
title: Лабораторная работа 7
subtitle: "Модель M|M|1|"
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

Рассмотреть пример моделирования в xcos системы массового обслуживания типа M|M|1|∞.

# Задание

1. Реализовать модель системы массового обслуживания типа M|M|1|∞.

2. Построить график поступления и обработки заявок;
3. Построить график динамики размера очереди.

# Выполнение лабораторной работы

| ![Фиксируем параметр лямбда](image/photo_7.png){#fig:001 width=30%} | ![Фиксируем параметр мю](image/photo_6.png){#fig:002 width=30%} | ![Фиксируем параметр z](image/photo_8.png){#fig:003 width=30%}


#

::: columns
::: column
![Суперблок для поступления заявок](image/photo_2.png){#fig:004 width=60%}
::::

::: column
![Вывод суперблока](image/photo_3.png){#fig:005 width=40%}
::: 
:::


#

::: columns
::: column
![Суперблок для обработки заявок](image/photo_5.png){#fig:006 width=60%}
::::

::: column
![Вывод второго суперблока](image/photo_4.png){#fig:007 width=40%}
::: 
:::

#

![Готовая модель](image/photo_9.png){#fig:008 width=45%}

#

|![Измененные параметры суммы](image/photo_12.png){#fig:009 width=30%} | ![Изменения параметра блока регистрирующая очередь](image/photo_13.png){#fig:010 width=30%} | ![Изменения параметра блока регистрирующая события](image/photo_14.png){#fig:011 width=30%}


#

::: columns
::: column
![Размер очереди](image/photo_10.png){#fig:012 width=40%}
::::

::: column
![Поступление заявок](image/photo_11.png){#fig:013 width=40%}
:::
:::

# Вывод

В процессе выполнения данной лабораторной работы я рассмотрела пример моделирования в xcos системы массового обслуживания типа M|M|1|∞.