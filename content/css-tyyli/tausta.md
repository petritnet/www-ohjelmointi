+++
Categories = []
Description = ""
Tags = []
Title = "Tausta"
date = "2016-02-10T21:25:46+02:00"
weight = 30

+++

Mille tahansa HTML-elementille voidaan määrittää sen tausta joko väreillä tai taustakuvilla.
Oletuksena kunkin elementin tausta on läpinäkyvä (`transparent`), eli niiden alla oleva elementti
taustoineen näkyy niistä läpi.

Taustan voi määrittää CSS:n `background`-ominaisuudella ja sen aliominaisuuksilla.

Taustaväri
==========
Jos elementille halutaan antaa vain taustaväri, se voidaan määrätä `background-color`-ominaisuudella,
jonka arvoksi annetaan haluttu väri. Väri voidaan kertoa samoin kuin tekstin `color`-ominaisuudelle
värin nimellä tai erimuotoisina RGB-arvoina.

```
<h1 style="background-color: gold;">Otsikolla "kultainen" tausta</h1>
```
<div class="html-example">
<h1 style="background-color: gold;">Otsikolla "kultainen" tausta</h1>
</div>

```
<h1 style="background-color: #ffaaaa;">Punaisella tsikolla <span style="background-color: rgba(0,0,255,0.5);>korostettu</span> osuus</h1>
```
<div class="html-example">
<h1 style="background-color: #ffaaaa;">Punaisella otsikolla <span style="background-color: rgba(0,0,255,0.5);">korostettu</span> osuus</h1>
</div>


Taustakuva
==========
Taustaksi voidaan asettaa jokin kuva antamalla `background-image`-ominaisuudelle arvoksi kuvatiedoston
url-osoite muodossa: `url('osoitekuvaan.jpg')`.

Oletusarvoisesti taustakuva alkaa vasemmasta yläkulmasta ja sitä toistetaan taustalla vaaka- ja pystysuunnassa koko
elementin alueella.

```
<h1 style="background-image: url('leafy.png');">Vihertävällä taustalla</h1>
```
<div class="html-example">
<h1 style="background-image: url('../../images/leafy.png');">Vihertävällä taustalla</h1>
</div>

Taustakuvan toistoa voi hallita `background-repeat`-ominaisuudella, jolle voi antaa arvot:

- `repeat` (toistetaan vaaka- ja pystysuunnassa)
- `repeat-x` (toistetaan vain vaakasuunnassa)
- `repeat-y` (toistetaan vain pysytysuunnassa)
- `no-repeat` (ei toisteta lainkaan)

```
<div style="background-image: url('ghost-penguin.png'); background-repeat: no-repeat;">
    <h1>Aavepingviini</h1>
    <p>Hiukan lisää tekstiä.</p>
</div>
```
<div class="html-example">
<div style="background-image: url('../../images/ghost-penguin.png'); background-repeat: no-repeat;">
    <h1>Aavepingviini</h1>
    <p>Hiukan lisää tekstiä.</p>
</div>
</div>

Kuvan sijoittelua taas voi hallita `background-position`-ominaisuudella. Arvoiksi ominaisuus saa vaaka- ja
pystysuuntaisen sijainnin. Arvot voi antaa joko sanallisesti, `left`/`center`/`right` ja `top`/`center`/`bottom`,
tai suhteellisina prosentteina taikka absoluuttisina arvoina (px, em, ...) vasemmasta yläkulmasta laskien.

```
<div style="background-image: url('ghost-penguin.png'); background-repeat: no-repeat;
            background-position: 30% bottom;">
    <h1>Aavepingviini</h1>
    <p>Hiukan lisää tekstiä.</p>
</div>
```
<div class="html-example">
<div style="background-image: url('../../images/ghost-penguin.png'); background-repeat: no-repeat;
            background-position: 30% bottom;">
    <h1>Aavepingviini</h1>
    <p>Hiukan lisää tekstiä.</p>
</div>
</div>


Ominaisuuksien yhdistäminen
===========================
Taustaa säätelevät `background-*`-ominaisuudet voidaan määritellä myös yhdellä säännöllä käyttämällä
`background`-ominaisuutta, jonka muoto on:
```
background: <taustaväri> url('<taustakuvan osoite>') <vaaka-asettelu> <pystyasettelu> <toisto>;
```

Eli esimerkiksi:

```
<div style="background: #ffa url('ghost-penguin.png') center bottom no-repeat;">
    <h1>Aavepingviini</h1>
    <p>Hiukan lisää tekstiä.</p>
</div>
```
<div class="html-example">
<div style="background: #ffa url('../../images/ghost-penguin.png') center bottom no-repeat;">
    <h1>Aavepingviini</h1>
    <p>Hiukan lisää tekstiä.</p>
</div>
</div>

Jos tässä muodossa jokin arvoista jätetään pois, sen sijalla käytetään oletusarvoja.
