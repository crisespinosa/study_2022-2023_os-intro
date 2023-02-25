---
## Front matter
title: "Шаблон отчёта по индивидуальному проекту 1"
subtitle: "Первый этап"
author: "Кристина Микаела Эспиноса Василита"

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

Разместить на Github pages заготовки для персонального сайта.

# Задание


    -Установить необходимое программное обеспечение.
    -Скачать шаблон темы сайта.
    -Разместить его на хостинге git.
    -Установить параметр для URLs сайта.
    -Разместить заготовку сайта на Github pages.



# Выполнение лабораторной работы

Первым шагом было загрузить следующий файл  hugo_extended_0.110.0_linux-amd64.tar.gz и распаковать его. 

![](image/1p.jpg){#fig:001 width=70%}

После этого создайте папку Bin и переместите файл hugo в эту папку. 

![](image/2p.jpg){#fig:001 width=70%}

Затем мы используем Use this Template из репозитория, создаем его с именем "Блог" и клонируем его. 

![](image/3p.jpg){#fig:001 width=70%}

Мы удаляем /public. Мы открываем Web server. 

![](image/5p.jpg){#fig:001 width=70%}

![](image/6p.jpg){#fig:001 width=70%}

![](image/7p.jpg){#fig:001 width=70%}
Мы создаем новый репозиторий со специальным именем: username.github.io, и мы его клонировали.

![](image/8p.jpg){#fig:001 width=70%}

Следующим шагом создала новую ветку main командой git checkout -b main, перед этим перейдя в папку crisespinosa.github.io. После создала файл README.md командой touch. И ввела стандартные команды для согласования информации локального репозитория и Github: git add ., git commit -am "Добавили файл" и git push oridgin main. 

![](image/9p.jpg){#fig:001 width=70%}



Затем было необходимо соединить репозиторий и папку public в каталоге solo. Для этого мы вводим команду git submodule add -b main git@github.com:parfenovaee/parfenovaee.github.io.git public. Ссылка из команды - ссылка на последний из созданных репозиторией (SSH ссылка), в конце указываем папку. Терминал выдал некую ошибку, которая звучит так: "Следующие пути игнорируются одним из ваших файлов .gitignore: public". 

![](image/10p.jpg){#fig:001 width=70%}

После выполненных действий комнада прошла успешно и папка public наполнилась содержимым сайта.

![](image/11p.jpg){#fig:001 width=70%}

После перешла в паку public и снова выполнила три стандартные команды: git add ., git commit -am "Добавили сайт" и git push oridgin main.

![](image/12p.jpg){#fig:001 width=70%}

# Выводы

Мы разместили на Github pages заготовки для персонального сайта


