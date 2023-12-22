---
## Front matter
title: "Отчет по лабораторной работе №6"
subtitle: "Архитектура компьютеров"
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

Освоение арифметических инструкций языка ассемблера NASM


# Теоретическое введение

Большинство инструкций на языке ассемблера требуют обработки операндов. Адрес опе-
ранда предоставляет место, где хранятся данные, подлежащие обработке. Это могут быть
данные хранящиеся в регистре или в ячейке памяти. Далее рассмотрены все существующие
способы задания адреса хранения операндов – способы адресации.
Существует три основных способа адресации:
• Регистровая адресация – операнды хранятся в регистрах и в команде используются
имена этих регистров, например: mov ax,bx.
• Непосредственная адресация – значение операнда задается непосредственно в ко-
манде, Например: mov ax,2.
• Адресация памяти – операнд задает адрес в памяти. В команде указывается символи-
ческое обозначение ячейки памяти, над содержимым которой требуется выполнить
операцию.
Например, определим переменную intg DD 3 – это означает, что задается область памяти
размером 4 байта, адрес которой обозначен меткой intg. В таком случае, команда
mov eax,[intg]
копирует из памяти по адресу intg данные в регистр eax. В свою очередь команда
mov [intg],eax
запишет в память по адресу intg данные из регистра eax.
Также рассмотрим команду
mov eax,intg
В этом случае в регистр eax запишется адрес intg. Допустим, для intg выделена память
начиная с ячейки с адресом 0x600144, тогда команда mov eax,intg аналогична команде mov
eax,0x600144 – т.е. эта команда запишет в регистр eax число 0x600144.

# Выполнение лабораторной работы

Создал каталог для программ лабораторной работы № 6, перешел в него и создал файл lab-1.asm (рис. @fig:001).

![Создание файлов](image/лаб61.png){#fig:001 width=70%}

Введите в файл lab6-1.asm текст программы из листинга 6.1.(рис. @fig:002).

![Ввод текста](image/лаб62.png){#fig:002 width=70%}

Создал исполняемый файл и запустил его (рис. @fig:003).

![Запуск файла](image/лаб63.png){#fig:003 width=70%}

Изменил исполняемый файл заменив строки (рис. @fig:004).

![Замена строк в файле](image/лаб64.png){#fig:004 width=70%}

Запустил файл в котором заменил строки (рис. @fig:005).

![Запуск файла](image/лаб65.png){#fig:005 width=70%}

 Создайте файл lab6-2.asm в каталоге ~/work/arch-pc/lab06 (рис. @fig:006).

![Создание файла](image/лаб66.png){#fig:006 width=70%}

Ввел в созданный файл текст (рис. @fig:007).

![Ввод текста](image/лаб67.png){#fig:007 width=70%}

Далее запустил программу и получил результат 106 (рис. @fig:008).

![Запуск и результат](image/лаб68.png){#fig:008 width=70%}

Аналогично предыдущему примеру изменил символы на числа. Потом заменил строки на другие (рис. @fig:009).

![Замена строк](image/лаб69.png){#fig:009 width=70%}

Далее запустил программу и получил результат 10 (рис. @fig:010).

![Запуск и результат](image/лаб610.png){#fig:010 width=70%}

Далее заменил в том же файле функцию iprintLF на iprint(рис. @fig:011).

![Замена функции](image/лаб611.png){#fig:011 width=70%}

Запустил измененную программу и получил результат 10 в той же строке и поняд чем отличается предыдущая программа от этой (рис. @fig:012).

![Запуск новой программы](image/лаб612.png){#fig:012 width=70%}

Создайте файл lab6-3.asm в каталоге ~/work/arch-pc/lab06 (рис. @fig:013).

![Создание файла](image/лаб613.png){#fig:013 width=70%}

Далее ввел в него код для вычисления выражения (рис. @fig:014).

![Ввод кода](image/лаб614.png){#fig:014 width=70%}

После этого я запустил этот файл и получил результат (рис. @fig:015).

![Запуск файла и получение результата](image/лаб615.png){#fig:015 width=70%}

Измените текст программы для вычисления выражения 𝑓(𝑥) = (4 ∗ 6 + 2)/5. (рис. @fig:016).

![Изменение текста программы](image/лаб616.png){#fig:016 width=70%}

Далее запустил измененный текст и получил желаемый результат (рис. @fig:017).

![Запуск измененного файла](image/лаб617.png){#fig:017 width=70%}

Создал файл variant.asm в каталоге ~/work/arch-pc/lab06 (рис. @fig:018).

![Создание файла variant.asm](image/лаб618.png){#fig:018 width=70%}

Внимательно изучил текст программы из листинга 6.4 и ввел в файл variant.asm. (рис. @fig:019).

![Ввод текста в файл variant.asm](image/лаб619.png){#fig:019 width=70%}

Запустил файл и узнал номер своего варианта (рис. @fig:020).

![Вариант 10](image/лаб620.png){#fig:20 width=70%}

#Ответы на вопросы по программе

1. За вывод сообщения “Ваш вариант” отвечают строки кода: mov eax,rem call sprint
2. Инструкция mov ecx, x используется, чтобы положить адрес вводимой стро- ки x в регистр ecx mov edx, 80 - запись в регистр edx длины вводимой строки call sread - вызов подпрограммы из внешнего файла, обеспечивающей ввод сообщения с клавиатуры
3. call atoi используется для вызова подпрограммы из внешнего файла, кото- рая преобразует ascii-код символа в целое число и записывает результат в регистр eax
4. За вычисления варианта отвечают строки: xor edx,edx ; обнуление edx для корректной работы div mov ebx,20 ; ebx = 20 div ebx ; eax = eax/20, edx - остаток от деления inc edx ; edx = edx + 1
5. При выполнении инструкции div ebx остаток от деления записывается в регистр edx
6. Инструкция inc edx увеличивает значение регистра edx на 1
7. За вывод на экран результатов вычислений отвечают строки: mov eax,edx
call iprintLF
#Самостоятельная работа
 
# Вывод
Освоил арифметические инструкции языка NASM 

# Список литературы{.unnumbered}

::: {#refs}
:::
