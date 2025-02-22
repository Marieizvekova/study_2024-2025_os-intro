---
## Front matter
lang: ru-RU
title: Лабораторная работа 2
subtitle: Исследование протокола TCP и алгоритма управления очередью RED
author:
  - Извекова Мария Петровна
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 22 февраля 2022

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
  * группа НФИбд-01-22
  * Российский университет дружбы народов


:::
::: {.column width="30%"}

![](./image/photo_my.jpg)

:::
::::::::::::::

## Теоретическая часть

Протокол управления передачей (Transmission Control Protocol, TCP) имеет средства управления потоком и коррекции ошибок, ориентирован на установление соединения.

TCP Reno:
– медленный старт (Slow-Start);
– контроль перегрузки (Congestion Avoidance);
– быстрый повтор передачи (Fast Retransmit);
– процедура быстрого восстановления (Fast Recovery);
– метод оценки длительности цикла передачи (Round Trip Time, RTT), используемой для установки таймера повторной передачи (Retransmission TimeOut, RTO).

# Выполнение лабораторной работы

## Создаем скрипт где прописываем все соединения узлов

![](image/photo1.jpg)

##  В скрипте прописываем мониторинг размера окна и очереди -- то, что исследуем

![](image/photo2.jpg)


## Прописываем часть, отвечающая за вывод результата в Xgraph. результаты их временных таблиц переносим в temp.queue

![](image/photo3.jpg)

## Сначала рассматриваем протокол TCP Reno

![](image/photo4.jpg)

## 

::: columns
:::: column
![Динамика размеры окна](image/photo6.jpg){#fig:005 width=60%}
::::

:::: column
![Мониторинг очереди](image/photo5.jpg){#fig:006 width=60%}
::::
::::

## Рассматриваем протокол TCP NewReno

![](image/photo7.jpg)

## 
::: columns
:::: column
![Динамика размеры окна](image/photo8.jpg){#fig:005 width=60%}
::::

:::: column
![Мониторинг очереди](image/photo9.jpg){#fig:006 width=60%}
::::
::::

## Рассматриваем протокол TCP Vegas


![](image/photo10.jpg)

::: columns
:::: column
![Динамика размеры окна](image/photo11.jpg){#fig:005 width=60%}
::::

:::: column
![Мониторинг очереди](image/photo12.jpg){#fig:006 width=60%}
::::
::::

## Вывод
Ознакомиться с протоколом TCP и очередью RED, построить сценарий на симмуляторе и изобразить результате в Xgraph. Так же мы рассмотрели, что
протоколы TCP Reno и NewReno реагируют на изменения, только после потерей пакетов, как протокол Vegas замечает это до, из-за чего его линии моментами не меняют направление.

# Спасибо за внимание!

