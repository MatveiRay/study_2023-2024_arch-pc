---
## Front matter
title: "Шаблон отчёта по лабораторной работе"
subtitle: "Простейший вариант"
author: "Дмитрий Сергеевич Кулябов"

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

Приобретение практических навыков работы в Midnight Commander. Освоение инструкций языка ассемблера mov и int.

# Задание

4.1 Работа c Midnight Commander 

4.2 Подключение внешнего файла in_out.asm 

4.3 Задание для самостоятельной работы

# Теоретическое введение

Midnight Commander (или просто mc) — это программа, которая позволяет просматривать структуру каталогов и выполнять основные операции по управлению файловой системой, т.е. mc является файловым менеджером. Midnight Commander позволяет сделать работу с файлами более удобной и наглядной. Для активации оболочки Midnight Commander достаточно ввести в командной строке mc и нажать клавишу Enter (рис. 5.1). В Midnight Commander используются функциональные клавиши F1 — F10 , к которым привязаны часто выполняемые операции. 

Программа на языке ассемблера NASM, как правило, состоит из трёх секций: секция кода программы (SECTION .text), секция инициированных (известных во время компиляции) данных (SECTION .data) и секция неинициализированных данных (тех, под которые во время компиляции только отводится память, а значение присваивается в ходе выполнения программы) (SECTION .bss).

# Выполнение лабораторной работы

4.1. Работа c Midnight Commander:

1 Откройте Midnight Commander:

![Прописываю команду mc](image/Lab5-1.jpg)<hr><hr>

![Редактор Midnight Commander](image/Lab5-2.jpg)<hr><hr>

2 Пользуясь клавишами ↑ , ↓ и Enter перейдите в каталог ~/work/arch-pc созданный при выполнении лабораторной работы №4:

![Перешел в каталог,созданный при выполнении 4 лабораторной](image/Lab5-3.jpg)<hr><hr>

3 С помощью функциональной клавиши F7 создайте папку lab05 и перейдите в созданный каталог:

![Создаю папку lab05](image/Lab5-4.jpg)<hr><hr>

![Создал папку lab05](image/Lab5-5.jpg)<hr><hr>

4 Пользуясь строкой ввода и командой touch создайте файл lab5-1.asm:

![Создаю lab5-1.asm с помощью команды touch](image/Lab5-6.jpg)<hr><hr>

![Создал lab5-1.asm с помощью команды touch](image/Lab5-7.jpg)<hr><hr>

5 С помощью функциональной клавиши F4 откройте файл lab5-1.asm для редактирования во встроенном редакторе. Как правило в качестве встроенного редактора Midnight Commander используется редакторы nano или mcedit:

![Midnight Commander открыл текстовый редактор nano](image/Lab5-8.jpg)<hr><hr>

6 Введите текст программы из листинга 5.1 (можно без комментариев), сохраните изменения и закройте файл:

![Текст программы из листинга 5.1 в nano](image/Lab5-9.jpg)<hr><hr>

7 С помощью функциональной клавиши F3 откройте файл lab5-1.asm для просмотра. Убедитесь, что файл содержит текст программы:

![Текст программы из листинга 5.1 в lab5-1.asm](image/Lab5-10.jpg)<hr><hr>

8 Оттранслируйте текст программы lab5-1.asm в объектный файл. Выполните компоновку объектного файла и запустите получившийся исполняемый файл. Программа выводит строку 'Введите строку:' и ожидает ввода с клавиатуры. На запрос введите Ваши ФИО:

![Команда nasm -f elf lab5-1.asm для сборки программы на языке ассемблер](image/Lab5-11.jpg)<hr><hr>

![lab5-1.o был создан](image/Lab5-12.jpg)<hr><hr>

![выполнение линковки объектного файла lab5-1.o и создание исполняемого файла с именем lab5-1 в формате ELF](image/Lab5-13.jpg)<hr><hr>

![lab5-1 создан](image/Lab5-14.jpg)<hr><hr>

![Команда ./lab5-1](image/Lab5-15.jpg)<hr><hr>

![Ввел ФИО](image/Lab5-16.jpg)<hr><hr>

4.2 Подключение внешнего файла in_out.asm:

9 Скачайте файл in_out.asm со страницы курса в ТУИС:

![Скачал файл с ТУИС](image/Lab5-17.jpg)<hr><hr>

10 Подключаемый файл in_out.asm должен лежать в том же каталоге, что и файл с программой, в которой он используется:

![скопировал файл в каталол ~/work/arch-pc/lab05](image/Lab5-18.jpg)<hr><hr>

11 С помощью функциональной клавиши F6 создайте копию файла lab5-1.asm с именем lab5-2.asm. Выделите файл lab5-1.asm, нажмите клавишу F6 , введите имя файла lab5-2.asm и нажмите клавишу Enter:

![lab5-2.asm был создан](image/Lab5-19.jpg)<hr><hr>

12 Исправьте текст программы в файле lab5-2.asm с использование подпрограмм из внешнего файла in_out.asm (используйте подпрограммы sprintLF, sread и quit) в соответствии с листингом 5.2. Создайте исполняемый файл и проверьте его работу:

![lab5-2.asm с использование подпрограмм из внешнего файла in_out.asm](image/Lab5-20.jpg)<hr><hr>

13 В файле lab5-2.asm замените подпрограмму sprintLF на sprint. Создайте исполняемый файл и проверьте его работу. В чем разница?

![заменил подпрограмму sprintLF на sprint](image/Lab5-21.jpg)<hr><hr>

sprint – вывод сообщения на экран, перед вызовом sprint в регистр eax необходимо записать выводимое сообщение (mov eax, message),а 
sprintLF также работает, но при выводе на экран добавляет к сообщению символ перевода строки.

4.3 Задание для самостоятельной работы:

1 Создайте копию файла lab5-1.asm. Внесите изменения в программу (без использования внешнего файла in_out.asm), так чтобы она работала по следующему алгоритму:  

• вывести приглашение типа “Введите строку:”; 

• ввести строку с клавиатуры; 

• вывести введённую строку на экран.

![копия файла lab5-1.asm](image/Lab5-22.jpg)<hr><hr>

![Редактировал файл lab5-3.asm](image/Lab5-23.jpg)<hr><hr>

2 Получите исполняемый файл и проверьте его работу. На приглашение ввести строку введите свою фамилию:

![Ввел свою фамилию](image/Lab5-24.jpg)<hr><hr>

3 Создайте копию файла lab5-2.asm. Исправьте текст программы с использование подпрограмм из внешнего файла in_out.asm, так чтобы она работала по следующему алгоритму:  

• вывести приглашение типа “Введите строку:”;  

• ввести строку с клавиатуры;  

• вывести введённую строку на экран.

![Создал копию файла lab5-2.asm](image/Lab5-25.jpg)<hr><hr>

![Исправил текст программы с использованием подпрограмм](image/Lab5-26.jpg)<hr><hr>

4 Создайте исполняемый файл и проверьте его работу:

![Создал и проверил](image/Lab5-27.jpg)<hr><hr>

# Выводы

Изучив Midnight Commander, я осознал, что это мощный инструмент для управления файлами в командной строке. Его удобный интерфейс и эффективные команды позволяют мне легко копировать, перемещать и удалять файлы. Функции архивации, быстрого доступа и встроенные редакторы упрощают работу с содержимым файлов. Изучение Midnight Commander значительно улучшило мой опыт работы с файлами в командной строке, делая процесс более эффективным и удобным.


# Список литературы{.unnumbered}

1. GDB: The GNU Project Debugger. — URL: https://www.gnu.org/software/gdb/.
2. GNU Bash Manual. — 2016. — URL: https://www.gnu.org/software/bash/manual/.
3. Midnight Commander Development Center. — 2021. — URL: https://midnight-commander.
org/.
4. NASM Assembly Language Tutorials. — 2021. — URL: https://asmtutor.com/.
5. Newham C. Learning the bash Shell: Unix Shell Programming. — O’Reilly Media, 2005. —
354 с. — (In a Nutshell). — ISBN 0596009658. — URL: http://www.amazon.com/Learningbash-Shell-Programming-Nutshell/dp/0596009658.
6. Robbins A. Bash Pocket Reference. — O’Reilly Media, 2016. — 156 с. — ISBN 978-1491941591.
7. The NASM documentation. — 2021. — URL: https://www.nasm.us/docs.php.
8. Zarrelli G. Mastering Bash. — Packt Publishing, 2017. — 502 с. — ISBN 9781784396879.
9. Колдаев В. Д., Лупин С. А. Архитектура ЭВМ. — М. : Форум, 2018.
10. Куляс О. Л., Никитин К. А. Курс программирования на ASSEMBLER. — М. : Солон-Пресс,
2017.
11. Новожилов О. П. Архитектура ЭВМ и систем. — М. : Юрайт, 2016.
12. Расширенный ассемблер: NASM. — 2021. — URL: https://www.opennet.ru/docs/RUS/nasm/.
13. Робачевский А., Немнюгин С., Стесик О. Операционная система UNIX. — 2-е изд. — БХВПетербург, 2010. — 656 с. — ISBN 978-5-94157-538-1.
14. Столяров А. Программирование на языке ассемблера NASM для ОС Unix. — 2-е изд. —
М. : МАКС Пресс, 2011. — URL: http://www.stolyarov.info/books/asm_unix.
15. Таненбаум Э. Архитектура компьютера. — 6-е изд. — СПб. : Питер, 2013. — 874 с. —
(Классика Computer Science).
16. Таненбаум Э., Бос Х. Современные операционные системы. — 4-е изд. — СПб. : Питер,
2015. — 1120 с. — (Классика Computer Science).

