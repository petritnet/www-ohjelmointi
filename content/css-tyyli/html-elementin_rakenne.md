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
