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

#Цель работы
Целью данной работы является приобретение практических навыков установки операционной системы на виртуальную машину, настройки минимально необходимых для дальнейшей работы сервисов
Здесь приводится формулировка цели лабораторной работы. Формулировки цели для каждой лабораторной работы приведены в методических указаниях.

#Указания к работе

#Техническое обеспечение

    Лабораторная работа подразумевает установку на виртуальную машину VirtualBox (https://www.virtualbox.org/) операционной системы Linux (дистрибутив Fedora).
    Выполнение работы возможно как в дисплейном классе факультета физико-математических и естественных наук РУДН, так и дома. Описание выполнения работы приведено для дисплейного класса со следующими характеристиками техники:
        Intel Core i3-550 3.2 GHz, 4 GB оперативной памяти, 80 GB свободного места на жёстком диске;
        ОС Linux Gentoo (http://www.gentoo.ru/);
        VirtualBox версии 7.0 или новее.
    Для установки в виртуальную машину используется дистрибутив Linux Fedora (https://getfedora.org), вариант с менеджером окон i3 (https://spins.fedoraproject.org/i3/).
    При выполнении лабораторной работы на своей технике вам необходимо скачать необходимый образ операционной системы (https://spins.fedoraproject.org/i3/download/index.html).



#Выполнение лабораторной работы

1. Обновления
Обновить все пакеты 
 ![Обновления](image/1.jpg){#fig:001 width=70%} 

2. Повышение комфорта работы

    Программы для удобства работы в консоли:
    ![](image/2.jpg){#fig:001 width=70%} 
3. Автоматическое обновление

    При необходимости можно использовать автоматическое обновление.

    Установка программного обеспечения:
  ![](image/3.jpg){#fig:001 width=70%} 
4. Задаёте необходимую конфигурацию в файле /etc/dnf/automatic.conf.

Запустите таймер:
![](image/4.jpg){#fig:001 width=70%} 
5. Отключение SELinux

    В данном курсе мы не будем рассматривать работу с системой безопасности SELinux.
    Поэтому отключим его.

    В файле /etc/selinux/config замените значение

    SELINUX=enforcing

    на значение

    SELINUX=permissive

    Перегрузите виртуальную машину:

    reboot
    ![](image/5.jpg){#fig:001 width=70%} 
6. Установка драйверов для VirtualBox

    Войдите в ОС под заданной вами при установке учётной записью.
    Нажмите комбинацию Win+Enter для запуска терминала.

    Запустите терминальный мультиплексор tmux:

    tmux

    Переключитесь на роль супер-пользователя:

    sudo -i

    Установите пакет DKMS:

    dnf -y install dkms

    В меню виртуальной машины подключите образ диска дополнений гостевой ОС.
   
7. Установка имени пользователя и названия хоста

    Если при установке виртуальной машины вы задали имя пользователя или имя хоста, не удовлетворяющее соглашению об именовании, то вам необходимо исправить это.
    Запустите виртуальную машину и залогиньтесь.
    Нажмите комбинацию Win+Enter для запуска терминала.

    Запустите терминальный мультиплексор tmux:
    Подмонтируйте диск:

    mount /dev/sr0 /media

    Установите драйвера:

    /media/VBoxLinuxAdditions.run

    Перегрузите виртуальную машину:

    reboot
   ![](image/5.jpg){#fig:001 width=70%} 

8. Настройка раскладки клавиатуры

    Войдите в ОС под заданной вами при установке учётной записью.
    Нажмите комбинацию Win+Enter для запуска терминала.

    Запустите терминальный мультиплексор tmux:

    tmux

    Переключитесь на роль супер-пользователя:

    sudo -i

    Отредактируйте конфигурационный файл /etc/X11/xorg.conf.d/00-keyboard.conf:

    Section "InputClass"
            Identifier "system-keyboard"
            MatchIsKeyboard "on"
            Option "XkbLayout" "us,ru"
            Option "XkbVariant" ",winkeys"
            Option "XkbOptions" "grp:rctrl_toggle,compose:ralt,terminate:ctrl_alt_bksp"
    EndSection

    Для этого можно использовать файловый менеджер mc и его встроенный редактор.

    Перегрузите виртуальную машину:

    reboot

9. Установка программного обеспечения для создания документации

10. pandoc и texlive
![](image/11.jpg){#fig:001 width=70%}
![](image/12.jpg){#fig:001 width=70%} 
![](image/10.jpg){#fig:001 width=70%} 


#Выводы
Мы приобрели практические навыки установки операционной системы на виртуальную машину, настройки минимально необходимых для дальнейшей работы сервисов.

