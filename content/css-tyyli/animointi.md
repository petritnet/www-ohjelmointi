+++
Categories = []
Description = ""
Tags = []
Title = "Animointi"
date = "2016-03-04T01:59:49+02:00"
weight = 140

+++

Joskus sivulla olevien HTML-elementtien ominaisuuksien muutoksia, kuten
elementtien sijaintia ja kokoa tai näkyvyyttä, halutaan
näyttävyyden tai käytettävyyden vuoksi animoida.
Aiemmin elementtien ominaisuuksien animointiin tarvittiin
Javascriptiä, jolla elementteihin tai niiden CSS-ominaisuuksiin
tehtiin muutoksia jollain aikavälillä tiettyjen askelten välein.
Tämä oli helposti virhealtista ja saattoi aiheuttaa tekijän
kyvyistä riippuen ylimääräistä kuormaa sivuston käyttöön.

CSS3:n myötä CSS:ään tuli sisäänrakennettuna ominaisuuksia,
joilla animoinnin voi suorittaa. Tämän etuna on erityisesti
se, että toiminnallisuus on toteutettu selaimeen sisäänrakennetusti,
jolloin vältetään Javascript-toteutuksen mahdollinen raskaus ja
sivun ohjelmoijan mahdolliset virheet.

Transition
==========
Tyypillisin ja yksinkertaisin tapa animoida sisältöä on käyttää
[muutoksia][Transitions], eli
`transition`-ominaisuutta. Sillä voidaan määritellä numeerisessa
muodossa olevien CSS-ominaisuuksien arvojen muutoksia tapahtumaan
pehmeästi. Muutos tapahtuu yleensä tilanteessa, jossa jokin
elementti siirtyy yhden CSS-säännön määräämästä tilasta toisen
säännön määräämään tilaan esimerkiksi silloin, kun hiiri tulee
elementin (tai sen vanhemman) päälle tai elementille lisätään taikka
siltä poistetaan ohjelmallisesti jokin luokka.

`transition`-ominaisuudelle annetaan vähintään kaksi arvoa, jotka ovat
muunnettavan CSS-ominaisuuden nimi sekä muunnoksen kesto. Näitä arvopareja
voidaan sääntöön luetella pilkulla eroteltuina useampiakin.

Seuraavassa esimerkissä hiiren tuominen `pohja`-luokalla merkityn
`<div>`-elementin päälle vaihtaa elementin taustavärin sekä muuttaa
sen sisällä olevan `<img>`-elementin sijaintia ja kiertoa.

```css
.pohja {
    background-color: white;
    transition: background-color 3s;
}
.pohja:hover {
    background-color: #ffa;
}
.pohja img {
    transition: transform 2s;
}
.pohja:hover img {
    transform: translate(500px) rotate(720deg);
}
```
```html
<div class="pohja">
    <img src="../../images/html5.svg" width="50" height="50">
</div>
```
<div class="html-example">
<style type="text/css" scoped>
.pohja {
    background-color: white;
    transition: background-color 3s;
}
.pohja:hover {
    background-color: #ffa;
}
.pohja img {
    width: 50px;
    transition: transform 2s, width 2s;
}
.pohja:hover img {
    width: 100px;
    transform: translate(500px) rotate(720deg);
}
</style>
<div class="pohja">
    <img src="../../images/html5.svg">
</div>
</div>

Muutos alkutilasta lopputilaan tapahtuu oletuksena `ease`-nimisen funktion
mukaisesti, mikä tarkoittaa, että muutos alkaa ensin hitaasti, kiihtyy nopeammaksi
ja lopuksi hidastuu jälleen hitaammaksi. Tämä vaikuttaa ihmissilmälle varsin
luonnolliselta tavalta. Tätä *ajoitusfunktiota* voidaan muuttaa ominaisuudella
`transition-timing-function` taikka lisäämällä `transition`-ominaisuuteen
kolmas arvo, joka on jokin seuraavista:

- `ease` – hidas, nopea, hidas
- `linear` – vakionopeus alusta loppuun
- `ease-in` – hidas alku, nopeampi loppu
- `ease-out` – nopeampi alku, hidas loppu
- `ease-in-out` – hidas alku ja hidas loppu
- `cubic-bezier(n,n,n,n)` –  itse määritelty "cubic-bezier"-funktio annetuilla parametreilla

Lisäksi muutoksen alkamiselle voidaan antaa viive ominaisuudella `transition-delay` tai
lisäämällä aika `transition`-ominaisuuteen neljänneksi arvoksi.

Tässä esimerkissä hiiren vieminen `.pohja`-elementin päälle animoi sen sisällä
olevan `.laatikko`-elementin korkeuden lineaarisesti arvosta `0` arvoon `100%`, eli
`.pohja`-elementin korkeuteen. Samalla yhden sekunnin viiveen jälkeen oikeaan reunaan
alkaa vähitellen tulla näkyviin kummitus, jonka peittävyys, `opacity`, muuttuu
kahden sekunnin aikana täysin läpinäkyvästä arvosta `0` täysin peittävään arvoon `1`.
Kummituksen `transition`-ominaisuuden arvot ovat erit, kun hiiri on `.pohja`-elementin
päällä tai ei ole. Muutoksen animointiin käytetään niitä arvoja, jotka astuvat voimaan
animoinnin alkaessa, eli esimerkiksi, kun hiiri menee `.pohja`-elementin päälle,
voimassa ovat valitsimen `.pohja:hover img`-mukaiset säännöt.

```css
.pohja {
    height: 150px;
    background-color: white;
    transition: background-color 3s;
}
.pohja:hover {
    background-color: #ffa;
}
.pohja img {
    float: right;
    opacity: 0;
    transition: opacity 2s ease-in-out 0s;
}
.pohja:hover img {
    opacity: 1;
    transition: opacity 2s ease-in-out 1s;
}
.pohja .laatikko {
    overflow: auto;
    width: 400px;
    height: 0;
    background-color: #aaf;
    transition: height 1s linear;
}
.pohja:hover .laatikko {
    height: 100%;
}
```
```html
<div class="pohja">
    <img src="../../images/ghost-penguin.png">
    <div class="laatikko">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc elementum, tortor id interdum venenatis, turpis est malesuada nulla, in mattis ante tellus in turpis. Sed scelerisque facilisis odio, eu maximus urna lobortis a. Suspendisse id tortor a augue commodo tempor eu vitae ipsum. Vestibulum hendrerit purus nec risus gravida iaculis. Quisque in eros vel velit ornare semper at eget ipsum. Nulla vulputate orci a arcu tempor, eu tincidunt est egestas. Sed lacus odio, blandit et massa at, convallis ullamcorper arcu. Fusce finibus augue eget semper imperdiet. Ut metus ipsum, porta sed ipsum id, sagittis mattis ante. Nulla varius, dui vel consequat iaculis, tellus ex tristique ante, molestie euismod arcu felis vel dolor. Duis purus massa, porta sollicitudin hendrerit a, sagittis at arcu. Etiam leo odio, bibendum eu sapien in, ullamcorper congue sapien. Aliquam enim nibh, faucibus sit amet posuere vitae, aliquam vitae massa. Sed id urna ac sem finibus sollicitudin eu a justo. 
    </div>
</div>
```
<div class="html-example">
<style type="text/css" scoped>
.pohja {
    height: 150px;
    background-color: white;
    transition: background-color 3s;
}
.pohja:hover {
    background-color: #ffa;
}
.pohja img {
    float: right;
    opacity: 0;
    transition: opacity 2s ease-in-out 0s;
}
.pohja:hover img {
    opacity: 1;
    transition: opacity 2s ease-in-out 1s;
}
.pohja .laatikko {
    overflow: auto;
    width: 400px;
    height: 0;
    background-color: #aaf;
    transition: height 1s linear;
}
.pohja:hover .laatikko {
    height: 100%;
}
</style>
<div class="pohja">
    <img src="../../images/ghost-penguin.png">
    <div class="laatikko">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc elementum, tortor id interdum venenatis, turpis est malesuada nulla, in mattis ante tellus in turpis. Sed scelerisque facilisis odio, eu maximus urna lobortis a. Suspendisse id tortor a augue commodo tempor eu vitae ipsum. Vestibulum hendrerit purus nec risus gravida iaculis. Quisque in eros vel velit ornare semper at eget ipsum. Nulla vulputate orci a arcu tempor, eu tincidunt est egestas. Sed lacus odio, blandit et massa at, convallis ullamcorper arcu. Fusce finibus augue eget semper imperdiet. Ut metus ipsum, porta sed ipsum id, sagittis mattis ante. Nulla varius, dui vel consequat iaculis, tellus ex tristique ante, molestie euismod arcu felis vel dolor. Duis purus massa, porta sollicitudin hendrerit a, sagittis at arcu. Etiam leo odio, bibendum eu sapien in, ullamcorper congue sapien. Aliquam enim nibh, faucibus sit amet posuere vitae, aliquam vitae massa. Sed id urna ac sem finibus sollicitudin eu a justo. 
    </div>
</div>
</div>

Animation
=========
Toinen keino tehdä monimutkaisempia animaatiota CSS:ää hyödyntäen on määritellä animaatio
`animation`-ominaisuudella ja `@keyframes`-määrittelyllä, joiden käyttöön voi tutustua
lisää [W3Schoolsin ohjeista][Animations].

[Transitions]: http://www.w3schools.com/css/css3_transitions.asp "W3Schools:Transition"
[Animations]: http://www.w3schools.com/css/css3_animations.asp "W3Schools:Animation"