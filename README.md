# The `xsavebox` LaTeX Package

© 2016--`\today` Alexander Grahn

**Notice:** I moved to [GitLab](https://gitlab.com/agrahn/xsavebox) recently.

## Description

This package defines commands for saving content that can be repeatedly placed into the document without replicating DVI/PDF code in the output file, allowing for smaller file size of the final PDF and improved content caching for faster display in certain PDF viewers. The method makes use of "Form XObjects" defined in the PDF specification.

The user commands are modelled after the standard LaTeX commands `\savebox`, `\sbox`, `\usebox` and the `lrbox` environment.

All common TeX engines and back-ends are supported:
* pdfLaTeX, LuaLaTeX
* LaTeX &rArr; dvips &rArr; ps2pdf/Distiller
* (Xe)LaTeX &rArr; (x)dvipdfmx

## User commands

* content saving:

````latex
\xsavebox{<name>}[<width>][<position>]{...}
\xsavebox*{<name>}[<width>][<position>]{...}

\xsbox{<name>}{...}

\begin{xlrbox}{<name>}...\end{xlrbox}
\begin{xlrbox*}{<name>}...\end{xlrbox*}
````

`<name>` is an identifier (not a command!) composed of arbitrary non-active characters, including spaces and numbers. A command for the declaration of `<name>` does not exist.

Starred (`*`) variants allow for colour injection (pdfLaTeX/LuaLaTeX only).

* content insertion (referencing):

````latex
\xusebox{<name>}
\the<name>
````

The second, short form is useable if `<name>` is composed of `[a-zA-Z]`.


The package was written in the LaTeX3 syntax.

## License

This material is subject to the [LaTeX Project Public License](http://mirrors.ctan.org/macros/latex/base/lppl.txt).
