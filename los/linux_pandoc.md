* Title: Linux Pandoc
* Date: 2019-10-23
* By: Dion Dresschers
* Scope: Intergalactic
* License: [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)
* File: cheatsheet\linux_pandoc.md
* Version: 2019-10-23T17:54

---

# pandoc

Convert a `markdown` file to a `pdf` file:

`pandoc --latex-engine=xelatex allMacroeconomics.md -o allMacroeconomics.pdf`

Convert a `markdown` file to a `pdf` file, and use other fonts via the `fontoptions.tex` file:

`pandoc --latex-engine=xelatex --include-in-header=fontoptions.tex allMacroeconomics.md -o allMacroeconomics.pdf`
  
Convert a `markdown` file to a `pdf` file, and use other fonts via the `fontoptions.tex` file, and make it in `landscape` mode and make sure it's `a4` format.

```
dion@desktop:~/data/04projectsdone/mbaMacroeconomicsBus1104$ cat fontoptions.tex 
% filename: fontoptions.tex
\setmainfont[
BoldFont = Ubuntu-B.ttf,
ItalicFont = Ubuntu-LI.ttf,
BoldItalicFont = Ubuntu-BI.ttf,
]{Ubuntu-L.ttf}
```

`pandoc --latex-engine=xelatex --variable geometry:landscape -V papersize:a4 --include-in-header=fontoptions.tex allMacroeconomics.md -o allMacroeconomics.pdf`

## pandoc - install 

Make sure you install these in Ubuntu 18.04, before you install `pandoc`:

`sudo apt-get install texlive-xetex`


