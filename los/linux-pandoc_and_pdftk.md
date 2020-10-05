pandoc --latex-engine=xelatex --include-in-header=fontoptions.tex allMacroeconomics.md -o allMacroeconomics.pdf

pandoc --latex-engine=xelatex --variable geometry:landscape -V papersize:a4 --include-in-header=fontoptions.tex allMacroeconomics.md -o allMacroeconomics.pdf

pdftk 1.pdf 2.pdf 3.pdf output outputfile.pdf
pdftk *.pdf cat output outputfile.pdf

# Install pandoc

`sudo apt install pandoc`

# Install texlive

`
dhdresschers@ubuntu-vm:/mnt/data/git/md/ptvd$ pandoc --latex-engine=xelatex --variable geometry:landscape -V papersize:a4 --include-in-header=fontoptions.tex inventory.md -o inventory.pdf
pandoc: xelatex not found. xelatex is needed for pdf output.
`

To solve this:

`sudo apt-get install texlive-xetex`

Then it works:

```
dhdresschers@ubuntu-vm:/mnt/data/git/md/ptvd$ pandoc --latex-engine=xelatex --variable geometry:landscape -V papersize:a4 --include-in-header=fontoptions.tex inventory.md -o inventory.pdf
dhdresschers@ubuntu-vm:/mnt/data/git/md/ptvd$
```

And you can open the generated PDF file:

```
dhdresschers@ubuntu-vm:/mnt/data/git/md/ptvd$ gio open inventory.pdf 
```



