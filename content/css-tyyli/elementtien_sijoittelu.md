+++
Categories = []
Description = ""
Tags = []
Title = "Elementtien sijoittelu"
date = "2016-02-10T21:31:12+02:00"
weight = 90

+++

Normaalisti HTML-elementit piirretään sivulla ylhäältä alas siinä
järjestyksessä, jossa ne esiintyvät, ja ympäröivien elementtien sisään.
Piirtokohtaan vaikuttaa elementin etäisyys muista elementeistä, eli marginaali,
sekä elementtejä ympäröivä täyte, eli padding.

Elementtejä voidaan kuitenkin irroittaa normaalista elementtijärjestyksestä
tietyillä css-ominaisuuksilla. Näistä ensimmäinen on `position`-ominaisuus.

Mahdollisia arvoja `position`-ominaisuudelle ovat:

- `static`,
- `relative`,
- `absolute` ja
- `fixed`

Seuraavassa kuvattujen asetteluiden lisäksi elementtien sijoittelua voidaan
vielä hienosäätää marginaalien tai negatiivisten marginaalien avulla.

Static
======
Elementtien normaali oletusasettelu on `static`, jolloin kukin elementti
sijaitsee omalla paikallaan toinen toisensa jälkeen. Sijaintiin voi vaikuttaa
lähinnä `margin`- ja `padding`-ominaisuuksilla.

Relative
========
Seuraava asettelutyyppi on suhteellinen, eli `relative`. Tällä asettelulla
elementti sijoittuu muuten samaan paikkaan kuin normaalilla `static`-asettelulla,
mutta sen sijaintia siirretään `top`-, `right`-, `bottom`- ja `left`-ominaisuuksien
määräämillä arvoilla. Arvot voivat olla positiivisia, negatiivisia tai nolla ja
ne kuvaavat elementin sijainnin etäisyyttä oletusarvostaan.

Suhteellisesti aseteltu elementti varaa kokoisensa paikan sieltä, mihin normaali
asettelu sen sijoittaisi, mutta tämän jälkeen elementtiä siirretään käsketyn etäisyyden
verran käsekttyyn suuntaan. Esimerkiksi asetus `top: 20px;` siirtää elementtiä niin,
että sen yläreuna on 20 pikseliä normaalia alempana ja `top: -20px;` siirtää elementtiä
vastaavasti 20 pikseliä ylemmäs.

```html
<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis pretium gravida
massa id tristique. Quisque at nulla congue, imperdiet odio at, accumsan nulla.
<span style="border: 1px solid red; position: relative; left: 2em; bottom: 1em;">
Maecenas luctus pretium massa, at feugiat sapien ultrices non. Suspendisse iaculis
</span>
ac massa dapibus sollicitudin. Ut euismod ipsum et odio rutrum sagittis. Donec
tincidunt augue eu tristique convallis. Class aptent taciti sociosqu ad litora
torquent per conubia nostra, per inceptos himenaeos. Phasellus id justo non metus
<img src="ghost-penguin.png" style="border: 1px solid blue; position: relative; top: -10px; left: -1em;">
tempus sagittis in nec tortor. Suspendisse sed accumsan est, non tincidunt lorem.
Sed at metus vitae ipsum aliquet malesuada ut eget tortor. In vitae fringilla urna.
</p>
```
<div class="html-example">
<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis pretium gravida
massa id tristique. Quisque at nulla congue, imperdiet odio at, accumsan nulla.
<span style="border: 1px solid red; position: relative; left: 2em; bottom: 1em;">
Maecenas luctus pretium massa, at feugiat sapien ultrices non. Suspendisse iaculis
</span>
ac massa dapibus sollicitudin. Ut euismod ipsum et odio rutrum sagittis. Donec
tincidunt augue eu tristique convallis. Class aptent taciti sociosqu ad litora
torquent per conubia nostra, per inceptos himenaeos. Phasellus id justo non metus
<img src="../../images/ghost-penguin.png" style="border: 1px solid blue; position: relative; top: -10px; left: -1em;">
tempus sagittis in nec tortor. Suspendisse sed accumsan est, non tincidunt lorem.
Sed at metus vitae ipsum aliquet malesuada ut eget tortor. In vitae fringilla urna.
</p>
</div>

Absolute
========
Absoluuttinen sijoittelu, eli css-sääntö `position: absolute;` irroittaa elementin
normaalista asettelusta. Se ei siis vie enää tilaa normaalilta paikaltaan, kuten
staattisessa tai suhteellisessa sijoittelussa. Absoluuttisesti sijoiteltu
elementti sijoitetaan sen sijaan absoluuttisesti sen lähimmän ympäröivän elementin
suhteen, joka on *sijoiteltu*, eli jonka `position`-ominaisuus on jotain muuta kuin `static`.
Jos tällaista elementtiä ei ole, se sijoitellaan itse sivun, eli `<html>`-elementin suhteen.

Elementille annetut `top`-, `left`-, `bottom`- ja `right`-arvot määräävät siis elementin
sijainnin kyseisen reunan etäisyyden ympäröivän elementin vastaavasta reunasta.
Huomattavaa on, että jos elementille on annettu leveys tai jos se on esimerkiksi kuva, jolla
on valmiiksi sen oletusleveys, ei `left`- ja `right`-ominaisuuksia voida yleensä käyttää yhtä aikaa.
Samoin `top`- ja `bottom`-ominaisuuksien yhtäaikainen käyttö voi olla mahdotonta, jos elementillä
on määrätty korkeus.


```css
.ulompi {
    position: relative;
    border: 1px solid red;
    height: 200px;
    width: 300px;
}
.sisempi {
    position: absolute;
    top: 30px;
    right: 75px;
    border: 1px solid blue;
    height: 100px;
    width: 100px;
}
img {
    position: absolute;
    left: 0;
    bottom: 0;
    border: 1px solid green;
}
```
```html
<div class="ulompi">
    .ulompi
    <div class="sisempi">
        .sisempi
    </div>
    <img src="ghost-penguin.png">
</div>
```
<div class="html-example">
<div style="position: relative;
            border: 1px solid red;
            height: 200px;
            width: 300px;">
    .ulompi
    <div style="position: absolute;
                top: 30px;
                right: 75px;
                border: 1px solid blue;
                height: 100px;
                width: 100px;">
        .sisempi
    </div>
    <img src="../../images/ghost-penguin.png" style="border: 1px solid green; position: absolute; left: 0; bottom: 0;">
</div>
</div>


Fixed
=====
`position`-ominaisuuden neljäs mahdollinen arvo on `fixed`, joka tarkoittaa, että elementti on kiinnitetty
selainikkunan näkymän suhteen. Tällöin siis `top`-, `right`-, `bottom`- ja `left`-arvot eivät tarkoita
elementin sijaintia minkään muun HTML-selaimen suhteen vaan itse ikkunan suhteen. Tällä asetuksella
on mahdollista asettaa esimerkiksi sivuston valikko pysymään koko ajan näkyvissä samassa kohtaa vaikka
sivua rullattaisiin alas päin.

```
.kiinnitetty {
    position: fixed;
    right: 50px;
    bottom: 100px;
    width: 50px;
    height: 50px;
    border: 1px solid red;
    background-color: rgba(255,170,170,0.5);
}
```
```html
<div class="kiinnitetty">Fixed</div>
```
<div class="html-example">
<br>
<div style="border: 1px solid red; background-color: rgba(255,170,170,0.5); width: 50px; height: 50px; position: fixed; right: 50px; bottom: 100px;">Fixed</div>
</div>

Elementtien päällekkäisyys
==========================
Jos elementtien sijoittelu on staattinen, ne asettuvat aina siististi toinen toisensa jälkeen.
Jos taas elementin asettelu on jotain muuta kuin staattinen ja sen sijaintia on liikuteltu
`top`-, `right`-, `bottom`- tai `left`-ominaisuuksilla, se voi sijoittua osittain tai
kokonaan jonkin toisen elementin alle tai päälle.

Päällekkäin asettuneiden elementtien järjestystä voidaan hallita css-ominaisuudella `z-index`,
joka saa arvokseen jonkin kokonaisluvun. Suuremman `z-index`-arvon saava elementti näkyy pienemmän
arvon saaneen elementin päällä. Oletusarvona on 0. Elementit, joiden arvo on sama, asettuvat
piirtojärjestyksessä, eli dokumentissa myöhemmin oleva piirretään aiemmin olevan päälle.

`z-index`-arvo ei kuitenkaan vaikuta keskenään sisäkkäisiin elementteihin. Sisempi on
aina ulomman päällä.

```
.ulompi {
    position: relative;
    width: 300px;
    height: 200px;
    border: 1px solid gold;
    background-color: #ffa;
}
.sisempi1 {
    position: absolute;
    top: 25px;
    left: 75px;
    width: 100px;
    height: 100px;
    border: 1px solid red;
    background-color: #faa;
    z-index: 3;
}
.sisempi2 {
    position: absolute;
    top: 75px;
    right: 75px;
    width: 100px;
    height: 100px;
    border: 1px solid green;
    background-color: #afa;
    z-index: 2;
}
```
```html
<div class="ulompi">
    <div class="sisempi1"></div>
    <div class="sisempi2"></div>
</div>
```
<div class="html-example">
<div style="border: 1px solid gold; background-color: #ffa; width: 300px; height: 200px; position: relative;">
    <div style="position: absolute;
                top: 25px;
                left: 75px;
                width: 100px;
                height: 100px;
                border: 1px solid red;
                background-color: #faa;
                z-index: 3;"></div>
    <div style="position: absolute;
                top: 75px;
                right: 75px;
                width: 100px;
                height: 100px;
                border: 1px solid green;
                background-color: #afa;
                z-index: 2;"></div>
</div>
</div>