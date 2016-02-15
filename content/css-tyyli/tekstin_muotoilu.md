+++
Categories = []
Description = ""
Tags = []
Title = "Tekstin muotoilu"
date = "2016-02-10T21:25:26+02:00"
weight = 20

+++

{{% jessyink src="css-johdanto.svg" %}}
{{% /jessyink %}}

Tutustutaan ensin joihinkin tekstielementtien ulkoasuun vaikuttaviin ominaisuuksiin.

Tekstin väri
============
Tekstin väri määritellään CSS:llä `color`-ominaisuutta käyttämällä.
Tälle ominaisuudelle voidaan antaa arvo useammassa eri muodossa:

- varatulla väriin viittaavalla **nimellä**
  (<span style="color: black;">black</span>, <span style="color: red;">red</span>,
  <span style="color: green;">green</span>, <span style="color: blue;">blue</span>,
  <span style="color: yellow;">yellow</span>, <span style="color: white; background-color: black;">white</span>,
  jne.)
- **heksamuotoisella RGB-koodilla**, joka koostuu #-merkistä ja kolmesta tai kuudesta merkistä
  (<span style="color: black;">#000, #000000</span>, <span style="color: red;">#f00, #ff0000</span>,
  <span style="color: #a01122;">#a01122</span>, <span style="color: #89a02c;">#89a02c</span>, 
  <span style="color: green;">#0f0, #00ff00</span>, <span style="color: blue;">#00f, #0000ff</span>,
  <span style="color: yellow;">#ff0, #ffff00</span>, <span style="color: #F8C12A;">#f8c12a</span>, <span style="color: white; background-color: black;">#fff, #ffffff</span>,
  jne.)
- **RGB-koodilla desimaalimuodossa** (<span style="color: rgb(200,82,132);">rgb(200,82,132)</span>,
  <span style="color: rgb(170,20,180);">rgb(170,20,180)</span>)
- **RGBA-koodilla**, jossa neljäs komponentti on läpinäkyvyys
  (<span style="color: rgba(20,20,170,0.2);">rgb(20,20,170,0.2)</span>,
  <span style="color: rgba(20,20,170,0.5);">rgb(20,20,170,0.5)</span>,
  <span style="color: rgba(20,20,170,0.9);">rgb(20,20,170,0.9)</span>)

Sopivia arvoja väreille voi etsiä esimerkiksi kuvankäsittelyohjelmalla tai jollain
[Color Picker](http://www.colorpicker.com/)-sovelluksella. Firefox- ja Chrome-selaimille
on saatavilla myös [ColorZilla](http://www.colorzilla.com/)-lisäosa.

```
<article>
    <h1 style="color: red;">Otsikko</h1>
    <p>Lorem <span>ipsum</span> sit dolor amet...</p>
</article>
```
```
p {color: #555;}
span {color: green;}
```
<div class="html-example">
<article>
    <h1 style="color: red;">Otsikko</h1>
    <p style="color: #555;">Lorem <span style="color: green;">ipsum</span> sit dolor amet...</p>
</article>
</div>

Korostukset
===========
Tekstiä voi korostaa esimerkiksi **lihavoimalla** ja *kursivoimalla*.

Jotkin tagit, kuten `<strong>` sekä eritasoiset otsikkoelementit ovat oletuksena
lihavoituja. Mille tahansa elementille voi lihavoinnin laittaa käyttöön tai pois
määrittelemällä  CSS:n `font-weight`-ominaisuuden arvon. Yleisimmin käytetyt arvot
ovat `normal` ja `bold`, mutta näiden lisäksi voidaan käyttää painokertoimia, kuten
`200` tai `600`, taikka muita avainsanoja, kuten `bolder` ja `lighter`. Erilaisten
arvojen tuki riippuu kuitenkin suurelta osin selaimesta sekä käytetyistä kirjasimista.
Yleensä selaimissa vain `normal`- ja `bold`-arvot antavat erottuvat tulokset ja
luku 600 ja sitä suuremmat vastaavat `bold`-arvoa.

```
<p>
    <span style="font-weight: 500;">Lorem</span>
    <span style="font-weight: bold;">ipsum</span> sit
    <strong style="font-weight: lighter;">dolor</strong> amet...
</p>
```
<div class="html-example">
<p><span style="font-weight: 500;">Lorem</span> <span style="font-weight: bold;">ipsum</span> sit <strong style="font-weight: lighter;">dolor</strong> amet...</p>
</div>

Kursivointi on oletuksena päällä `<em>`-tagilla ja esimerkiksi `<address>`-tagilla.
Kursivoinnin voi asettaa käyttöön tai pois käytöstä CSS-ominaisuudella
`text-style`, jonka arvoiksi ovat tarjolla `normal`, `italic` ja `oblique`.
Näistä `italic` ja `oblique` ovat molemmat kursivoituja, mutta `italic` pyrkii
käyttämään kursiiviksi suunniteltua kirjasintyyppiä (fonttia), jos sellainen
suinkin on järjestelmässä tarjolla. `oblique` sen sijaan tyypillisesti vain
"vääntää" normaalin pystyfontin muutaman asteen verran vinoon. Usein näillä ei
kuitenkaan ole eroa.

```
<p>
    <address>Lorem</address>
    <span style="font-style: italic;">ipsum</span> sit
    <em style="font-style: normal;">dolor</strong>
    <span style="font-style: oblique;">amet</span>...
</p>
```
<div class="html-example">
<p>
    <address>Lorem</address>
    <span style="font-style: italic;">ipsum</span> sit
    <em style="font-style: normal;">dolor</strong>
    <span style="font-style: oblique;">amet</span>...
</p>
</div>


Tekstin koko
============


Kirjasinperhe
=============


Tekstin "koristelu"
==================


Tekstin tasaus elementissä
==========================


Tekstin muunnokset
==================


Tekstin varjostus
=================


