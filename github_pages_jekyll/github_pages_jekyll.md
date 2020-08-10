* Door: Amsterdam UMC, & Dion Dresschers
* Inspiratie door: [Creating a GitHub Pages site with Jekyll - GitHub Docs](https://docs.github.com/en/github/working-with-github-pages/creating-a-github-pages-site-with-jekyll)
* Datum: 2020-08-07
* Status: Concept
* Revisie: Jaarlijks
* Licentie: [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)
* Desktop Besturingssysteem: Ubuntu 18.04.4 LTS
* Versie: 2020-08-07 18:23:42

# Maak een Repostory aan op GitHub

1. Log in in [GitHub](https://github.com/)
1. Klik op `New` om een nieuwe Repository aan te maken
1. In het veld `Owner` zie je je eigen gebruikersnaam. 
	* In dit geval stellen we ons voor dat de gebruikersnaam `diondresschers` is.
1. In het veld `Repository name` type je je nieuwe {repository_naam}.
	* In dit geval noemen we het `github_paginas`
1. Klik op `Create repository`
1. Klik op `Settings`
1. Scroll naar beneden naar `GitHub Pages`
1. Bij `Source` selecteer `gh-pages`
1. Klik `Save`
1. Scroll weer naar boven waar je ziet staan `Your site is ready to be published at {github_pages_url}`. De {github_pages_url} is bijvoorbeeld ``
1. Noteer die {github_pages_url} 

# Clone de Repostory

1. Zorg dat je git hebt geinstallereerd (hint: `apt install git`) en geconfigureerd.
1. Ga naar je de plek waar je de reeds gemaakte repository wilt clonen. Bijvoorbeeld `/mnt/dhdresschers/git/md`
	* `cd /mnt/dhdresschers/git/md`
1. Open de repository in de browser:
	* `firefox https://github.com/diondresschers/github_paginas`
1. Klik daar op `Code`
1. Copieer daar de URL bv `https://github.com/diondresschers/github_paginas.git`, dit is nu {github_url}
1. In de terminal type:
	* `git clone {github_url}`
1. Maak een nieuwe directory genaamd `docs`
	* `mkdir docs`
1. Ga naar die directory `docs`
	* `cd docs`
1. Bevestig nog dat je in de `git` branch `master` zit:
	* `git branch`	
1. Het resultaat van vorig commando moet zijn:
	* `* master`
1. We gaan serveren vanuit die `gh-pages` branch. We maken een nieuwe branch, zonder geschiedenis of inhoud (door de `--orphan`). 
	* `git checkout --orphan gh-pages`
1. Nu zie je dat je niet meer zin in `master` aangezien de asterisk `*` verdwenen is:
	* `git branch`
1. Wat resulteert in:
	* `  master`
1. Je kan zien in wat voor branch je nu zit:
	* git status | head -n 1
1. Wat resulteert in:
	* `On branch gh-pages`
1. Maak eerste een `Gemfile` aan:
	* `bundle init`
1. Bekijk die `Gemfile`
	* `cat Gemfile`
1. Pas de `Gemfile` aan en voeg `jekyll` toe als een dependency:
	* echo 'gem "jekyll"' >> Gemfile
1. Draai `bundle` om `jekyll` toe te voegen.
	* `bundle`
1. Wat resulteert in:
```
Fetching gem metadata from https://rubygems.org/..........
Fetching gem metadata from https://rubygems.org/.
Resolving dependencies...
Using public_suffix 4.0.5
Using addressable 2.7.0
Using bundler 1.16.1
Using colorator 1.1.0
Using concurrent-ruby 1.1.6
Using eventmachine 1.2.7
Using http_parser.rb 0.6.0
Using em-websocket 0.5.1
Using ffi 1.13.1
Using forwardable-extended 2.6.0
Using i18n 1.8.5
Using sassc 2.4.0
Using jekyll-sass-converter 2.1.0
Using rb-fsevent 0.10.4
Using rb-inotify 0.10.1
Using listen 3.2.1
Using jekyll-watch 2.2.1
Using rexml 3.2.4
Using kramdown 2.3.0
Using kramdown-parser-gfm 1.1.0
Using liquid 4.0.3
Using mercenary 0.4.0
Using pathutil 0.16.2
Using rouge 3.21.0
Using safe_yaml 1.0.5
Using unicode-display_width 1.7.0
Using terminal-table 1.8.0
Using jekyll 4.1.1
Bundle complete! 1 Gemfile dependency, 28 gems now installed.
Use `bundle info [gemname]` to see where a bundled gem is installed.
```

1. Nu kan je bijvoorbeeld zien welke versie van `jekyll` je voor je project hebt:
	* `bundle info jekyll`
1. Geeft als resultaat:
	```
  * jekyll (4.1.1)
	Summary: A simple, blog aware, static site generator.
	Homepage: https://jekyllrb.com
	Path: /home/dhdresschers/gems/gems/jekyll-4.1.1	
	```	
1. Je ziet all dependencies in de gecreerde file `Gemfile.lock`
	* `cat Gemfile.lock`
1. Wat resulteert in:
```
GEM
  remote: https://rubygems.org/
  specs:
    addressable (2.7.0)
      public_suffix (>= 2.0.2, < 5.0)
    colorator (1.1.0)
    concurrent-ruby (1.1.6)
    em-websocket (0.5.1)
      eventmachine (>= 0.12.9)
      http_parser.rb (~> 0.6.0)
    eventmachine (1.2.7)
    ffi (1.13.1)
    forwardable-extended (2.6.0)
    http_parser.rb (0.6.0)
    i18n (1.8.5)
      concurrent-ruby (~> 1.0)
    jekyll (4.1.1)
      addressable (~> 2.4)
      colorator (~> 1.0)
      em-websocket (~> 0.5)
      i18n (~> 1.0)
      jekyll-sass-converter (~> 2.0)
      jekyll-watch (~> 2.0)
      kramdown (~> 2.1)
      kramdown-parser-gfm (~> 1.0)
      liquid (~> 4.0)
      mercenary (~> 0.4.0)
      pathutil (~> 0.9)
      rouge (~> 3.0)
      safe_yaml (~> 1.0)
      terminal-table (~> 1.8)
    jekyll-sass-converter (2.1.0)
      sassc (> 2.0.1, < 3.0)
    jekyll-watch (2.2.1)
      listen (~> 3.0)
    kramdown (2.3.0)
      rexml
    kramdown-parser-gfm (1.1.0)
      kramdown (~> 2.0)
    liquid (4.0.3)
    listen (3.2.1)
      rb-fsevent (~> 0.10, >= 0.10.3)
      rb-inotify (~> 0.9, >= 0.9.10)
    mercenary (0.4.0)
    pathutil (0.16.2)
      forwardable-extended (~> 2.6)
    public_suffix (4.0.5)
    rb-fsevent (0.10.4)
    rb-inotify (0.10.1)
      ffi (~> 1.0)
    rexml (3.2.4)
    rouge (3.21.0)
    safe_yaml (1.0.5)
    sassc (2.4.0)
      ffi (~> 1.9)
    terminal-table (1.8.0)
      unicode-display_width (~> 1.1, >= 1.1.1)
    unicode-display_width (1.7.0)

PLATFORMS
  ruby

DEPENDENCIES
  jekyll

BUNDLED WITH
   1.16.1
```

1. Installeer nu een nieuwe `jekyll` site:
	* `bundle exec jekyll new .`
1. Eigenlijk willen we niet `jekyll` gebruiken, maar jekyll voor `github-pages`. In de file `Gemfile` staat een instructie aangegeven:
	* `cat Gemfile | grep 'GitHub Pages' -A 2
1. Wat resulteert in:
```
# If you want to use GitHub Pages, remove the "gem "jekyll"" above and
# uncomment the line below. To upgrade, run `bundle update github-pages`.
# gem "github-pages", group: :jekyll_plugins
```
1. Voeg dus een hekje `#` toe aan de regel die begint met `gem "jekyll", zodat deze niet actief is. 
	* `vi Gemfile`
1. Pas de regel aan die begint met `# gem github-pages` zodat deze er uit komt te zien als `gem "github-pages", "~> {version}", group: :jekyll_plugins`, waarbij de je {version} invult op basis van het versienummer dat staat bij `github-pages` op de pagina: [Dependency versions | GitHub Pages](https://pages.github.com/versions/)
	* `vi Gemfile`
1. En upgrade dan zoals aangegeven in het `Gemfile` bestand met `bundle update github-pages`
	* `bundle update github-pages`
1. In ons voorbeeld:
	* `cat Gemfile | grep 'gem "github-pages'
1. Resulteert in:
	```
	gem "github-pages", "~> 206", group: :jekyll_plugins
	```
1. Update
	* `bundle update`
1. Draai je site lokaal via `https://127.0.0.1:4000/
	* `bundle exec jekyll serve`
1. Wat resulteert in:
```
Configuration file: /mnt/dhdresschers/git/md/github_paginas/docs/_config.yml
            Source: /mnt/dhdresschers/git/md/github_paginas/docs
       Destination: /mnt/dhdresschers/git/md/github_paginas/docs/_site
 Incremental build: disabled. Enable with --incremental
      Generating... 
       Jekyll Feed: Generating feed for posts
                    done in 0.746 seconds.
 Auto-regeneration: enabled for '/mnt/dhdresschers/git/md/github_paginas/docs'
    Server address: http://127.0.0.1:4000/
  Server running... press ctrl-c to stop.
```
1. Check de site via `firefox`
	* `firefox http://127.0.0.1:4000`
1. Als dit werkt, voeg de repository toe:
	* `git remote add origin https://github.com/{gebruikersnaam}/{repository_naam}.git`
1. Voeg alle nieuwe wijzigen toe aan `git`
	* `git add`
1. Commit alle wijzingen:
	* `git commit -m "jekyll toegevoegd"
1. Probeer met `git push` de nieuwe wijzigingen naar de reeds bestaande repository:
	* `git push`
1. Wat resulteert in:
```
fatal: The current branch gh-pages has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin gh-pages
```
1. Geef het geadviseerde commando:
	
	



# Installeer Jekyll

1. Controlleer of je `gem` hebt:
	* `gem -v`
1. Heb je geen `gem`, installeer het:
	* `apt install gem`
1. Zorg dat je de juiste dependencies hebt:
	* `sudo apt-get install ruby-full build-essential zlib1g-dev`
1. Je kan het beste `gem` niet als `root` draaien. Daarom zetten we extra configuratie bij het waarschijnlijk reeds bestaande `.bashr` bestand in je home directory:
	* `echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc`
	* `echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc`
	* `echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc`
1. Draai nu de extra config in de huidige command shell:
	* `source ~/.bashrc`
1. Nu kan je `bundler` installeren via `gem`
	* `gem install bundler`
1. Nu kan je `jekyll` installeren via `gem` 
	* `gem install jekyll`