+++
Categories = []
Description = ""
Tags = []
Title = "Media ja kuvat"
date = "2016-02-07T16:26:09+02:00"
weight = 85

+++

HTML5:n mukana tulivat käyttöön uudet mediaelementit, joilla voi sivulle upottaa
ääntä ja videota samaan tapaan kuin kuvia on voinut upottaa jo aiemmin. HTML5 toi
mukanaan myös virallisen tuen skaalattavalle vektorigrafiikalle, eli SVG-muotoisille
kuville.

Audio
=====

[Audion][Audio] liittäminen sivulle tapahtuu `<audio>`-tagilla. Soitettava äänitiedosto annetaan
tagille `src`-attribuutilla tiedoston osoitteena. Tarvittaessa mediatiedosto voidaan kertoa `src`-attribuutin sijaan
aloitus- ja lopetustagien väliin kirjoitettavalla `<source>`-tagilla ja sen `src`-attribuutilla. Erillistä `<source>`-tagia
tarvitaan esimerkiksi siinä tapauksessa, että kaikki selaimet eivät tue samoja tiedostomuotoja.
Tällöin äänitiedostoja voi olla useammassa vaihtoehtoisessa tiedostomuodossa, jotka kukin luetellaan
omalla `<source>`-tagillaan. Selain käyttää ensimmäistä äänitiedostoa, joka on sen tukemassa muodossa.

Elementille voidaan antaa attribuutti `controls`, jonka läsnäolo vaikuttaa sen, että selain näyttää
äänen soittamiseen tarvittavat ohjaimet, kuten *play*/*pause*-nappulan, äänenvoimakkuuden säädöt sekä
liukusäätimen soittokohdan valitemiseksi. Ilman `controls`-attribuuttia audioelementti on näkymätön ja
sen sisältöä voidaan soittaa vain joko automaattisena soittona tai Javascriptillä käskyttämällä.
`control`-attribuutti ei vaadi minkään arvon asettamista vaan pelkkä sen olemassaolo riittää.

Toinen elementille annettavissa oleva varsinaista arvoa tarvitsematon attribuutti on `autoplay`.
Tämän olemassaolo saa aikaan sen, että äänitiedostoa aletaan soittaa välittömästi ja automaattisesti
ilman käyttäjän toimintoja, kun sivua ja tiedostoa on ladattu riittävästi.

Kolmas hyödyllinen attribuutti on `loop`, jolla audion saa toistumaan silmukkana uudelleen ja uudelleen.

Audio-elementille näytettävä käyttöliittymä riippuu selaimesta, mutta toteutukset ovat kaikki melko samanlaisia.

```
<audio src="sting.ogg" controls>

<audio controls autoplay>
    <source src="sting.ogg" type="audio/ogg">
    <source src="sting.mp3" type="audio/mp3">
    Selaimesi ei tue audioelementtiä.
</audio>
```
<div class="html-example">
<audio src="../../media/sting.ogg" controls></audio>

<audio controls>
    <source src="../../media/sting.ogg" type="audio/ogg">
    <source src="../../media/sting.mp3" type="audio/mp3">
    Selaimesi ei tue audioelementtiä.
</audio>
</div>

Video
=====

[Videon][Video] liittäminen sivulle tapahtuu hyvin samaan tapaan kuin audionkin. Sitä varten on käytettävissä
`<video>`-tagi, joka toimii samoin kuin `<audio>`-tagi.

```
<video src="https://upload.wikimedia.org/wikipedia/commons/0/01/Apollo11_Saturn_V_separation.ogv"></video>

<video controls>
    <source src="https://upload.wikimedia.org/wikipedia/commons/0/01/Apollo11_Saturn_V_separation.ogv" type="video/ogg">
</video>
```
<div class="html-example">
<video src="https://upload.wikimedia.org/wikipedia/commons/0/01/Apollo11_Saturn_V_separation.ogv"></video>

<video controls>
    <source src="https://upload.wikimedia.org/wikipedia/commons/0/01/Apollo11_Saturn_V_separation.ogv" type="video/ogg">
</video>
</div>


SVG-kuvat
=========
SVG-kuvat ovat vektorimuotoisia kuvia, eli ne eivät koostu pienistä pisteistä vaan kuvan piirtämiseen tarvittavista ohjeista
koordinaatteineen, pituuksineen, leveyksineen, väreineen sekä muine ominaisuuksineen.

* SVG tarkoittaa: **S**calable **V**ector **G**raphics
* Vektoripohjaista grafiikkaa erityisesti verkkokäyttöön
* Määritelty HTML:n kaltaisena XML-tiedostomuotona
* Eivät menetä tarkkuutta zoomattaessa tai skaalattaessa
* SVG-kuvan elementit ja ominaisuudet ovat animoitavissa
* Myös SVG on W3C:n suositus
* Esimerkiksi Wikipedian piirroskuvien, karttojen, logojen yms. suositeltu kuvamuoto

SVG-kuvia voi upottaa HTML5-sivuun monella tavalla:

* `<img>`-tagilla, kuten muitakin kuvia
* Kirjoittamalla SVG-kuvan XML-koodin suoraan HTML-koodin sekaan
* Upottamalla `<object>`-tagilla tai `<iframe>`-tagilla.

SVG-kuvia voi käyttää myös CSS-tyylien kanssa taustakuvana. (Tutustutaan myöhemmin tarkemmin taustakuviin.)

Koska SVG-kuvat ovat animoitavissa ja ohjelmoitavissa Javascriptillä, niitä voidaan käyttää moneen vastaavaan käyttöön, joihin
aiemmin on käytetty Flash-sovelluksia. Esimerkiksi tämän kurssin kalvoesitykset ovat SVG-tiedostoja.

```
<svg width="100" height="100" viewBox="0 0 100 100">
    <circle cx="50" cy="50" r="40" stroke="green" stroke-width="4" fill="yellow" />
    <rect x="60" y="60" width="35" height="35" stroke="blue" stroke-width="2" fill="red" />
    <path stroke="black" stroke-width="3" fill="none" d="M5 60 l0 -30 a20 20 0 0 1 20 -20 c40 0 0 20 70 30" />
</svg>

<svg width="100" height="100" viewBox="0 0 50 50">
    <path stroke="none" fill="black" d="M35 5 a12 12 0 1 0 9 9 l-9 9 a10 10 0 0 1 -9 -9 l9 -9z m-15 17.5 l-17 17 a2 2 0 0 0 7 7 l17 -17z m-16 18 a2 2 0 0 1 5 5 a2 2 0 0 1 -5 -5z"></path>
</svg>

<img src="html5.svg" alt="html5-logo" width="100" height="100">
```
<div class="html-example">
<svg width="100" height="100" viewBox="0 0 100 100">
    <circle cx="50" cy="50" r="40" stroke="green" stroke-width="4" fill="yellow" />
    <rect x="60" y="60" width="35" height="35" stroke="blue" stroke-width="2" fill="red" />
    <path stroke="black" stroke-width="3" fill="none" d="M5 60 l0 -30 a20 20 0 0 1 20 -20 c40 0 0 20 70 30" />
</svg>

<svg width="100" height="100" viewBox="0 0 50 50">
    <path stroke="none" fill="black" d="M35 5 a12 12 0 1 0 9 9 l-9 9 a10 10 0 0 1 -9 -9 l9 -9z m-15 17.5 l-17 17 a2 2 0 0 0 7 7 l17 -17z m-16 18 a2 2 0 0 1 5 5 a2 2 0 0 1 -5 -5z"></path>
</svg>

<img src="../../images/html5.svg" alt="html5-logo" width="100" height="100">
</div>


[Audio]: http://www.w3schools.com/HTML/html5_audio.asp "W3Schools:Audio"
[Video]: http://www.w3schools.com/HTML/html5_video.asp "W3Schools:Video"