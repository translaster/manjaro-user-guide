## Introduction

The Manjaro Linux Beginner's User Guide typeset in LaTeX (using LyX).

The style in use is [tufte-book](http://wiki.lyx.org/Layouts/Tufte-book). This provides a very professional layout with minimal fuss.

## Download

Want a PDF instead of the source? Grab it on [OSDN.net](https://osdn.net/projects/manjaro/storage/).

## Installation

To enable the tufte-book layout within LyX on Manjaro you will need to install the following packages:

    sudo pacman -S lyx texlive-latexextra texlive-pictures ttf-comfortaa ghostscript

Installing LyX should pick up the base dependencies; tufte-book requires the extra libraries. Remember to reconfigure LyX after installing the new libraries!

## Cover art

Current cover art is created in Inkscape. LyX will neatly insert/append PDF files - to make things easy cover art should therefore be exported as a PDF document.

![Manjaro User Guide cover](https://raw.githubusercontent.com/manjaro/manjaro-user-guide/master/cover.png)

## Generation 

Install ascii doc with:
```
pacman -S asciidoc
```
then 
```
gem install Ascii85 -v 1.1.0
```
### To Generate latex source
You can open terminal inside of asciidoc folder then
```
asciidoctor-latex manjaro-user-guide-2020-de-6.adoc
```
or
```
a2x -a lang=de -dbook  -v manjaro-user-guide-2020-de*.adoc
```
### To generate pdf
```
asciidoctor-pdf -dbook -a lang=de -vv manjaro-user-guide-2020-de-6.adoc
```
or
```
a2x -v -I manjaro-user-guide-2020-de-6.a2x
```
## Generation(OLD)

To generate the PDF from a command line rather than exporting from within LyX you can use the following:

    lyx --export pdflatex manjaro-user-guide.lyx
    pdflatex manjaro-user-guide
    texindy --language english manjaro-user-guide.idx
    pdflatex manjaro-user-guide
    pdflatex manjaro-user-guide
    gs -dNOPAUSE -dBATCH -sDEVICE=pdfwrite -dCompatibilityLevel=1.4 -dPDFSETTINGS=/printer -sOutputFile=manjaro-user-guide-printer.pdf manjaro-user-guide.pdf

Yes, ```pdflatex``` does require multiple runs.


## Contributors

K. Günther(converted the latest english source code to asciidoc and make than a translation. Also, He added some enhancements and updates and made German version of the guide.)


Feel free to develop a style for better looking output!






