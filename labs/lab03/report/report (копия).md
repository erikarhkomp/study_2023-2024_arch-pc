---
## Front matter
title: "Отчет по лабораторной работе №3"
subtitle: "Архитектура компьютера"
author: "Арутюнян Эрик Левонович"

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
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
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

Освоение процедуры оформления отчетов с помощью легковесного языка разметки Markdown.





# Выполнение лабораторной работы
Открываю терминал. Перехожу в каталог курса, сформированный при выполнении прошлой лабораторной работы  (рис. @fig:001).

![Перемещение между директориями](/image/снимок1.png){#fig:001 width=70%}

Обновляю локальный репозиторий, скачав изменения из удаленного репозитория с помощью команды git pull, также после этого перехожу в каталог с шаблоном отчета по лабораторной работе №3 с помощью cd (рис. @fig:002).
![Обновление локального репозитория и перемещение между директориями](/image/2.png){#fig:002 width=70%}

Компилирую шаблон с использованием Makefile, вводя команду make (рис. @fig:003).
![Компиляция шаблона](/image/3.png){#fig:003 width=70%}

Открываю сгенерированный файл в LibreOffice (рис. @fig:004)
![Открытие файла](/image/4.png){#fig:004 width=70%}

Открываю сгенерированный файл в pdf (рис. @fig:005)
![Открытие файла в pdf](/image/5.png){#fig:005 width=70%}

Удаляю полученные файлы с использованием команды make clean (рис. @fig:006)
![Удаление файлов](/image/6.png){#fig:006 width=70%}

С помощью команды ls проверяю, удалились ли созданные файлы.(рис. @fig:007)
![Удаление файлов ](/image/7.png){#fig:007 width=70%}

Открываю файл report.md с помощью любого текстового редактора (рис. @fig:008)
![Открытие файла report.md ](/image/8.png){#fig:008 width=70%}

Начинаю заполнять отчет с помощью языка разметки Markdown в скопированном файле(рис. @fig:009)
![Заполнение отчета ](/image/9.png){#fig:009 width=70%}
 
 
# Выполнение самостоятельной работы 

# Выводы

Здесь кратко описываются итоги проделанной работы.

# Список литературы{.unnumbered}

::: {#refs}
:::
