# VIM Cheat Sheet

* License:  [Creative Commons - CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)
* By: Dion Dresschers
* Version: 2020-03-14 08:43:03 

up:

* gg = top
* ^u = 1/2 page
* k  = one line

down:

* j  = one line
* ^d = 1/2 page
* G  = bottom

left:

* h  = previous character
* b  = Back one word
* 0  = 0th character of the line
* ^  = first non-blank character

right:

* l  = next character 
* e  = End of word
* w  = beginning of next Word
* E  = End of next word
* $  = end of next line

## Search

<ESC> + /
Type the searchword and then <ENTER>
Use 'n' for Next and 'N' for previous hit.

## Search&Replace

<ESC> + :

### Search&Replace

:%s/hit/hitje
        ^ replace with the word hitje, but only the first hit on each line, as there is no 'g' for Globallt after the last slash '/'
    ^ search for the word 'hit'
  ^ search
 ^ the whole document
       
:10,20s/hit/hitje
 ^ only search and replace between line 10 and 20

:10,20s/hit/hitje/g
                  ^ replace all hits at each line, because of the Global 'g'-keyword

:10,20s/hit/hitje/i
                  ^ search case Insensative (default is case sensative)

:10,20s/hit/hitje/c
                  ^ ask for Confirmantion (y = yes, n = no, q = quit, l = last change and Quit, ^E = go up ^Y is go down)

### Search & Replace - Lowercase and Uppercase

Switch all to Lowercase:

:%s/[A-Z]/\L&/g

Switch all to Uppercase:

:%s/[A-Z]/\U&/g











