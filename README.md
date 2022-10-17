## Введение

Руководство пользователя Manjaro Linux для начинающих набрано в LaTeX (с использованием LyX).

Используемый стиль - [tufte-book](http://wiki.lyx.org/Layouts/Tufte-book). Это обеспечивает очень профессиональную верстку с минимальными затратами.

## Скачать

Хотите PDF вместо исходника? Возьмите его на [OSDN.net](https://osdn.net/projects/manjaro/storage/).

## Установка

Чтобы включить макет tufte-book в LyX на Manjaro, вам нужно установить следующие пакеты:

    sudo pacman -S lyx texlive-latexextra texlive-pictures ttf-comfortaa ghostscript

Установка LyX подхватит базовые зависимости; tufte-book требует дополнительных библиотек. Не забудьте переконфигурировать LyX после установки новых библиотек!

## Обложка

Текущие обложки создаются в Inkscape. LyX аккуратно вставляет/дополняет PDF-файлы - поэтому для упрощения работы обложки должны быть экспортированы как PDF-документ.

![Manjaro User Guide cover](https://raw.githubusercontent.com/manjaro/manjaro-user-guide/master/cover.png)

## Генерация

Установите ascii doc с помощью:
```
pacman -S asciidoc
```
затем
```
gem install Ascii85 -v 1.1.0
```
### To Generate latex source
Вы можете открыть терминал внутри папки asciidoc, затем
```
asciidoctor-latex manjaro-user-guide-2020-ru-6.adoc
```
или
```
a2x -a lang=de -dbook  -v manjaro-user-guide-2020-ru*.adoc
```
### Для создания pdf
```
asciidoctor-pdf -dbook -a lang=ru -vv manjaro-user-guide-2020-ru-6.adoc
```
или
```
a2x -v -I manjaro-user-guide-2020-ru-6.a2x
```

## Генерация (OLD)

Чтобы сгенерировать PDF из командной строки, а не экспортировать из LyX, вы можете использовать следующее:

    lyx --export pdflatex manjaro-user-guide.lyx
    pdflatex manjaro-user-guide
    texindy --language russian manjaro-user-guide.idx
    pdflatex manjaro-user-guide
    pdflatex manjaro-user-guide
    gs -dNOPAUSE -dBATCH -sDEVICE=pdfwrite -dCompatibilityLevel=1.4 -dPDFSETTINGS=/printer -sOutputFile=manjaro-user-guide-printer.pdf manjaro-user-guide.pdf

Да ``pdflatex`` требует многократного запуска.

## Соавторы

K. Günther(перевел последний английский исходный код в asciidoc и сделал перевод. Также он добавил некоторые улучшения и обновления и сделал немецкую версию руководства).

Не стесняйтесь разрабатывать стиль для более красивого вывода!
