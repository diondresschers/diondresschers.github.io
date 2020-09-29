# CSS Grid vs Flexbox

* Datum: 2020-08-06
* Inspiratie: [CSS Grid vs Flexbox - YouTube](https://www.youtube.com/watch?v=RSIclWvNTdQ)
* Door: Amsterdam UMC, Apotheek I&A, & Dion Dresschers
* Licentie: [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/legalcode)
* Versie: 2020-08-06 14:32:59

# Startbestanden

1. Zorg dat je startbestanden er zo uit ziet dat het commando:
    * `cat index.html`
    * dit resultaat geeft:
    
    ```
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>Titel</title>
        <link rel="stylesheet" href="main.css">
    </head>
    <body>
        <header>
            <ul class="navigation-list">
                <li class="navigation-item"><a href="#">Menu 1</a></li>
                <li class="navigation-item"><a href="#">Menu 2</a></li>
                <li class="navigation-item"><a href="#">Menu 3</a></li>
            </ul>
        </header>
        <aside>
            <p>ASIDE</p>
        </aside>
        <main>
            <p>MAIN</p>
        </main>
        <footer>
            <ul class="navigation-list">
                <li class="navigatie-item"><a href="#">Een</a></li>
                <li class="navigatie-item"><a href="#">Twee</a></li>
            </ul>
        </footer>
    </body>
    </html>
    ```
1. En het commando:
    * `cat main.css`
    * dit resultaat geeft:
    ```
    * {
        box-sizing: border-box;
    }

    body {
        margin: 0;
    }

    header,
    aside,
    main,
    footer {
        padding: 16px;
        text-align: center;
    }

    header {
        background: red;
    }

    aside {
        background: orange;
    }

    footer {
        background: yellow;
    }

    .navigation-list {
        list-style: none;
        margin: 0;
        padding: 0;
    }

    .navigation-item a {
        text-decoration: none;
        color: green;
    }

    .navigation-item a:hover,
    .navigation-item a:active {
        color: indigo;
    }
    ```    
1. Alhoewel de `<body>` standaard een `grid` gebruikt, kan je het forceren om grid te gebruiken door de CSS code:
    ```
    body {
        display: grid;
    }
    ```
1. Je kan nu de Grid gaan inrichten:
    ```
    body {
    margin: 0;
    display: grid;
    grid-template-columns: 30% auto;
    grid-template-rows: 60px auto 60px;
    }
    ```
1. Bovenstaande wilt zeggen dat we twee kolommen hebben. De eerste kolom is 30% breed en de tweede is automatisch 70% breed.
1. De rijen zijn 60 pixels hoog, dan automatsich en dan 60 pixels.
1. Aangezie we 

# CSS Flexbox

Flexbox is eendimensionaal met alleen maar kolommen. Als de pagina vol is, wordt op de nieuwe regel verder gegaan met de eerstvolgende kolom.


