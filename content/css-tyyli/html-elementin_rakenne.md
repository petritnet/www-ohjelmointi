+++
Categories = []
Description = ""
Tags = []
Title = "HTML elementin rakenne"
date = "2016-02-10T21:27:26+02:00"
weight = 50

+++

HTML-elementin tyylittelyssä, sijoittelussa ja koon asettelussa on tärkeää ymmärtää
HTML-elementin sisäinen rakenne, miten se näytetään ja miten se suhtautuu sen viereisiin elementteihin.

HTML-elementti koostuu seuraavista osista:

* sisältö
* täyte, eli **padding** (tila sisällön ja reunan välissä)
* reunaviiva, eli **border**
* marginaali, eli **margin** (tila reunan ja ulomman laatikon välissä)

<figure>
<svg xmlns="http://www.w3.org/2000/svg" version="1.1" width="90%" height="auto" viewBox="0 0 800 400" class="chart">
    <rect stroke="#666" stroke-width="1" stroke-dasharray="3,3" fill="#ffa" x="2" y="2" width="700" height="396"></rect>
    <text x="20" y="40" style="font-family: monospace; font-size: 16px; font-weight: bold; fill: black;">marginaali</text>
    <rect stroke="red" stroke-width="2" fill="#fdd" x="80" y="70" width="530" height="270"></rect>
    <text x="150" y="65" style="font-family: monospace; font-size: 16px; font-weight: bold; fill: red;">border eli reunaviiva</text>
    <text x="200" y="100" style="font-family: monospace; font-size: 16px; font-weight: bold; fill: black;">padding eli täyte</text>
    <rect stroke="none" fill="#ccf" x="140" y="120" width="410" height="170"></rect>
    <text x="300" y="220" style="font-family: monospace; font-size: 16px; font-weight: bold; fill: black;">sisältö</text>
</svg>
</figure>

Elementin mitat
===============
Lohkotyyppiselle elementille voidaan määrittää:

- Elementin **leveys** ominaisuudella `width`
- Elementin **korkeus** ominaisuudella `height`

Arvot voidaan antaa absoluuttisina tai suhteellisina arvoina, eli käytössä olevilla yksiköillä, kuten
`px`, `em` ja `%`. Huomattavaa on, että prosentteina annettuna koko on osuutena ulomman "vanhempielementin" koosta.
Kooksi voidaan antaa myös arvo `auto`, joka on ominaisuuden oletusarvo. Esimerkiksi, jos kuvalle annetaan leveys,
mutta korkeus jätetään antamatta tai sen arvoksi määrätään `auto`, skaalautuu korkeus automaattisesti suhteessa
leveyteen.

Ominaisuudet `width` ja `height` vaikuttavat (oletuksena) vain elementin **sisällön** leveyteen ja korkeuteen.
Tämän lisäksi tulevat yleensä vielä marginaali, reunus sekä padding.

Elementille annetut taustavärit ja -kuvat vaikuttavat reunaviivan sisäpuoliseen alueeseen, eli sisältöön ja paddingiin.

```
<img style="width: 400px; height: 50px;" src="ghost-penguin.png">
<img style="width: 400px; height: auto;" src="ghost-penguin.png">
```
<div class="html-example">
<img style="width: 400px; height: 50px;" src="../../images/ghost-penguin.png">
<img style="width: 400px; height: auto;" src="../../images/ghost-penguin.png">
</div>

Marginaalit (margin)
===========

Elementille annetaan `margin`-ominaisuudella marginaali. Tämä määrää, paljonko tyhjää tilaa pitää jättää
elementin ympärille. Marginaali voidaan antaa seuraavissa muodoissa:

- `margin: 3em;` – kaikille sivuille sama 3em-kokoinen marginaali
- `margin: 2em 3em;` – pystysuuntaan (ylä ja alapuolelle) 2em, vaakasuuntaan (oikealle ja vasemmalle) 3em
- `margin: 2em 1em 3em;` – yläpuolelle 2em, vaakasuunnassa 1em ja alapuolelle 3em
- `margin: 1em 2em 3em 4em;`– sivut järjestyksessä top, right, bottom, left (muistisääntö: **tr**ou**bl**e)

Arvot luetellaan siis myötäpäivään ylhäältä alkaen järjestyksessä top, right, bottom, left.

Marginaalit voidaan määrätä kullekin reunalle myös erikseen ominaisuuksilla `margin-top`, `margin-right`,
`margin-bottom` ja `margin-left`.

Marginaalien kanssa huomattavaa on, että keskenään vierekkäisten tai päällekkäisten elementtien marginaalit
menevät keskenään ristiin. Siis, jos elementin alamarginaali on 3em ja seuraavan elementin ylämarginaali
on 2em, ei näiden väliin jää suinkaan 5em verran tyhjää tilaa vaan vain 3em. **Ei kaksinkertaista marginaalia!**

<figure>
<img style="max-width: 90%;" src="../../images/marginaalit.png">
</figure>

Täyte (padding)
===============

Vastaavasti kuin marginaali, määrätään elementin reunan ja sisällön väliin jäävä tyhjä tila ominaisuudella
`padding` sekä sen alaominaisuuksilla `padding-top`, `padding-right`, `padding-bottom` ja `padding-left`.

- `padding: 3em;` – kaikille sivuille sama 3em-kokoinen täyte
- `padding: 2em 3em;` – pystysuuntaan (ylä ja alapuolelle) 2em, vaakasuuntaan (oikealle ja vasemmalle) 3em
- `padding: 2em 1em 3em;` – yläpuolelle 2em, vaakasuunnassa 1em ja alapuolelle 3em
- `padding: 1em 2em 3em 4em;`– sivut järjestyksessä top, right, bottom, left (muistisääntö: **tr**ou**bl**e)

Toisin kuin marginaalit, vierekkäisten elementtien täytteet eivät "romahda" yhteen päällekkäin, sillä ne
ovat osa itse elementtiä eikä vain sen ympärillä olevaa tyhjää tilaa. Esimerkiksi taustakuva tai -väri
vaikuttavat myös täytteeseen.

Reuna (border)
==============

Reuna eli reunaviiva on marginaalin ja täytteen välinen osuus elementtiä ja sen paksuus on oletuksena nolla.
Reuna määrätään `border`-ominaisuudella ja sen aliominaisuuksilla. `border`-ominaisuus koostuu aliominaisuuksista:

- `border-width` – reunaviivan paksuus
- `border-style` – reunaviivan tyyli
- `border-color` – reunaviivan väri

Aliominaisuudet voidaan kuitenkin määrittää tässä järjestyksessä suoraan `border`-ominaisuudelle.
Reunaviivan tyylin arvoja ovat esimerkiksi:

- `none` – ei reunaviivaa
- `hidden` – reunukset piilossa, vie tilan, mutta ei näy
- `dotted` – pisteviiva
- `dashed` – katkoviiva
- `solid` – yhtenäinen viiva
- `double` – kaksoisviiva

```
<h1 style="border: 2px solid red;">Laatikoitu otsikko</h1>
<h1 style="border-width: 5px 10px 15px 20px;
           border-style: double solid dotted;
           border-color: red blue green;">Laatikoitu otsikko</h1>
```
<div class="html-example">
<h1 style="border: 2px solid red;">Laatikoitu otsikko</h1>
<h1 style="border-width: 5px 10px 15px 20px;
           border-style: double solid dotted;
           border-color: red blue green;">Laatikoitu otsikko</h1>
</div>

Reunojen ominaisuudet voidaan tarvittaessa yksilöidä vielä tarkemmin ominaisuuksilla, joiden nimet ovat tyyliä:
`border-right-style`, `border-top-color`, jne.

margin, border, padding, width, height
=======================

<figure>
<svg xmlns="http://www.w3.org/2000/svg" version="1.1" width="90%" height="auto" viewBox="0 0 800 400" class="chart">
    <defs>
        <marker id="arrowstart" markerWidth="13" markerHeight="13" refX="3" refY="6" orient="auto">
            <path d="M11,2 L11,11 L3,6z" style="fill: black;" />
        </marker>
        <marker id="arrowend" markerWidth="13" markerHeight="13" refX="10" refY="6" orient="auto">
            <path d="M2,2 L2,11 L10,6z" style="fill: black;" />
        </marker>
    </defs>
    <rect stroke="#666" stroke-width="1" stroke-dasharray="3,3" fill="#ffa" x="2" y="2" width="700" height="396"></rect>
    <path marker-start="url(#arrowstart)" marker-end="url(#arrowend)" stroke="black" stroke-width="1" fill="none" d="M500,2 l0,67" />
    <text x="350" y="40" text-anchor="middle" style="font-family: monospace; font-size: 16px; font-weight: bold; fill: black;">margin-top</text>
    <path marker-start="url(#arrowstart)" marker-end="url(#arrowend)" stroke="black" stroke-width="1" fill="none" d="M500,340 l0,58" />
    <text x="350" y="380" text-anchor="middle" style="font-family: monospace; font-size: 16px; font-weight: bold; fill: black;">margin-bottom</text>
    <path marker-start="url(#arrowstart)" marker-end="url(#arrowend)" stroke="black" stroke-width="1" fill="none" d="M3,100 l75,0" />
    <text x="30" y="200" text-anchor="middle" transform="rotate(-90 30,200)" style="font-family: monospace; font-size: 16px; font-weight: bold; fill: black;">margin-left</text>
    <path marker-start="url(#arrowstart)" marker-end="url(#arrowend)" stroke="black" stroke-width="1" fill="none" d="M610,100 l90,0" />
    <text x="670" y="200" text-anchor="middle" transform="rotate(90 670,200)" style="font-family: monospace; font-size: 16px; font-weight: bold; fill: black;">margin-right</text>
    <rect stroke="red" stroke-width="2" fill="#fdd" x="80" y="70" width="530" height="270"></rect>
    <text x="350" y="65" text-anchor="middle" style="font-family: monospace; font-size: 16px; font-weight: bold; fill: red;">border-top</text>
    <text x="350" y="354" text-anchor="middle" style="font-family: monospace; font-size: 16px; font-weight: bold; fill: red;">border-bottom</text>
    <text x="75" y="200" text-anchor="middle" transform="rotate(-90 75,200)" style="font-family: monospace; font-size: 16px; font-weight: bold; fill: red;">border-left</text>
    <text x="615" y="200" text-anchor="middle" transform="rotate(90 615,200)" style="font-family: monospace; font-size: 16px; font-weight: bold; fill: red;">border-right</text>
    <path marker-start="url(#arrowstart)" marker-end="url(#arrowend)" stroke="black" stroke-width="1" fill="none" d="M260,70 l0,49" />
    <text x="350" y="100" text-anchor="middle" style="font-family: monospace; font-size: 16px; font-weight: bold; fill: black;">padding-top</text>
    <path marker-start="url(#arrowstart)" marker-end="url(#arrowend)" stroke="black" stroke-width="1" fill="none" d="M260,290 l0,48" />
    <text x="350" y="320" text-anchor="middle" style="font-family: monospace; font-size: 16px; font-weight: bold; fill: black;">padding-bottom</text>
    <path marker-start="url(#arrowstart)" marker-end="url(#arrowend)" stroke="black" stroke-width="1" fill="none" d="M80,130 l60,0" />
    <text x="110" y="210" text-anchor="middle" transform="rotate(-90 110,210)" style="font-family: monospace; font-size: 16px; font-weight: bold; fill: black;">padding-left</text>
    <path marker-start="url(#arrowstart)" marker-end="url(#arrowend)" stroke="black" stroke-width="1" fill="none" d="M550,130 l60,0" />
    <text x="580" y="210" text-anchor="middle" transform="rotate(90 580,210)" style="font-family: monospace; font-size: 16px; font-weight: bold; fill: black;">padding-right</text>
    <rect stroke="none" fill="#ccf" x="140" y="120" width="410" height="170"></rect>
    <path marker-start="url(#arrowstart)" marker-end="url(#arrowend)" stroke="black" stroke-width="1" fill="none" d="M140,150 l410,0" />
    <text x="350" y="170" text-anchor="middle" style="font-family: monospace; font-size: 16px; font-weight: bold; fill: black;">width</text>
    <path marker-start="url(#arrowstart)" marker-end="url(#arrowend)" stroke="black" stroke-width="1" fill="none" d="M210,120 l0,170" />
    <text x="200" y="240" text-anchor="middle" transform="rotate(-90 200,240)" style="font-family: monospace; font-size: 16px; font-weight: bold; fill: black;">height</text>
</svg>
</figure>

```
<div>
    <h1>Otsikko</h1>
    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.
    Donec quis risus non velit imperdiet laoreet. Nulla molestie a ante id pharetra.
    Morbi finibus sed elit tincidunt laoreet. Etiam elementum malesuada nisl ut sodales.</p>
    <ul style="border: 1px solid green;">
        <li style="background-color: #ffa;">yksi</li>
        <li>kaksi</li>
    </ul>
</div>
<div style="margin: 0 4em; border-right: 3px solid red; border-left: 1px dashed black;">
    <h1 style="margin: 1em 3em 3em; padding: 1em 2em; background-color: #faa;">Otsikko</h1>
    <p style="border-top: 1px solid blue; border-bottom: 1px solid blue;">Lorem ipsum dolor sit amet, consectetur adipiscing elit.
    Donec quis risus non velit imperdiet laoreet. Nulla molestie a ante id pharetra.
    Morbi finibus sed elit tincidunt laoreet. Etiam elementum malesuada nisl ut sodales.</p>
    <ul style="margin: 0; padding: 0; border: 1px solid green;">
        <li style="background-color: #ffa;">yksi</li>
        <li>kaksi</li>
    </ul>
</div>
```
<div class="html-example">
<div>
    <h1>Otsikko</h1>
    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.
    Donec quis risus non velit imperdiet laoreet. Nulla molestie a ante id pharetra.
    Morbi finibus sed elit tincidunt laoreet. Etiam elementum malesuada nisl ut sodales.</p>
    <ul style="border: 1px solid green;">
        <li style="background-color: #ffa;">yksi</li>
        <li>kaksi</li>
    </ul>
</div>
<div style="margin: 0 4em; border-right: 3px solid red; border-left: 1px dashed black;">
    <h1 style="margin: 1em 3em 3em; padding: 1em 2em; background-color: #faa;">Otsikko</h1>
    <p style="border-top: 1px solid blue; border-bottom: 1px solid blue;">Lorem ipsum dolor sit amet, consectetur adipiscing elit.
    Donec quis risus non velit imperdiet laoreet. Nulla molestie a ante id pharetra.
    Morbi finibus sed elit tincidunt laoreet. Etiam elementum malesuada nisl ut sodales.</p>
    <ul style="margin: 0; padding: 0; border: 1px solid green;">
        <li style="background-color: #ffa;">yksi</li>
        <li>kaksi</li>
    </ul>
</div>
</div>