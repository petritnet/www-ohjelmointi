+++
Categories = []
Description = ""
Tags = []
Title = "Pseudoluokat ja -elementit"
date = "2016-02-10T21:33:29+02:00"
weight = 120

+++

HTML-sivulla voi olla myös tilanteita ja rakenteita, joita ei näy dokumentin varsinaisessa
HTML-kielisessä tekstissä, mutta joita voidaan silti tyylitellä CSS:llä.

Pseudoluokat
============
Luokat ovat HTML-elementteihin `class`-attribuutilla lisättäviä määritteitä, joita voidaan
käyttää tietyssä asemassa olevien elementtien tyylittelyyn.

**[Pseudoluokat][Pseudoluokat]** ovat puolestaan elementin tiloja, jotka eivät näy itse HTML-tekstissä,
mutta joihin voidaan silti viitata CSS-säännöissä. Ne ovat siis olemassaolevan elementin poikkeuksellisia
tiloja, kuten hiiren päällä oleminen, kohdistus tai ensimmäisenä oleminen. Valitsimissa pseudoluokka merkitään
kaksoispisteellä `:` muodossa:

```css
valitsin:pseudo-luokka {
    ominaisuus: arvo;
}
```

Linkit
------
Linkeille, eli `<a>`-tageille on HTML-sivulla neljä erityistä tilaa. Tilat ja niitä vastaavat
pseudoluokat ovat:

- *Normaalitila* (`:link`) – linkki sivulle, jolla ei ole vielä vierailtu
- *Valinta* (`:hover`) – hiiren kursori on viety linkin päälle
- *Vierailtu* (`:visited`) – linkin osoittamalla sivulla on jo käyty (ts. sivu löytyy selaimen historiasta)
- *Kohdistettu* (`:focus`) – linkillä on kohdistus joko hiiren klikkauksen tai tabulaattori-näppäimen painalluksen vuoksi
- *Aktiivinen* (`:active`) – linkin valinta parhaillaan meneillään hiiren klikkauksella (tai näppäimistöltä)

Käytettävyyden kannalta on usein tärkeää määritellä kaikkien neljän tilan ulkoasu erilaisiksi.

Linkkien ulkoasua CSS-säännöillä määriteltäessä on tärkeää huomata näiden pseudoluokkia käyttävien valitsimien keskinäinen
järjestys. Huomattavaa on, että `a:hover`-sääntö on syytä tulla `a:link`- ja `a:visited`-sääntöjen jälkeen, sillä muuten
se ei voi tulla voimaan, koska toisen saman arvoiset säännöt yliajavat sen. Samoin valitsinta `a:active` käyttävän
säännön on syytä olla `a:hover`-säännön jälkeen, sillä hiirellä klikatessa hiiri on myös samalla linkin päällä.
Myös `:focus` on syytä  olla ennen `:active`-pseudoluokkaa, sillä aktiivisella linkillä on aina kohdistus.

```css
a:link {
    color: blue;
}
a:visited {
    color: red;
}
a:hover {
    color: green;
}
a:focus {
    color: brown;
}
a:active {
    color: gold;
}
```
<div class="html-example">
<style type="text/css" scoped>
a:link {
    color: blue;
}
a:visited {
    color: red;
}
a:hover {
    color: green;
}
a:focus {
    color: brown;
}
a:active {
    color: gold;
}
</style>
<a href="abcde">Linkki 1</a> <a href="http://petrit.net/www-ohjelmointi">Linkki 2</a>
</div>

**Huomio:** Yksityisyyssyistä `:visited`-pseudoluokalla käytettävien CSS-sääntöjen määrää
on selaimissa rajoitettu erittäin voimakkaasti. Vain seuraavia ominaisuuksia voidaan säätää
`:visited`-pseudoluokkaa valitsimessa käyttävissä säännöissä: `color`, `background-color`,
`border-color`, `border-bottom-color`, `border-left-color`, `border-right-color`, `border-top-color`,
`outline-color`, `'column-rule-color`, `fill` ja `stroke`.

Mieti, miksi!

Muut elementit
--------------
Edellä mainittuja linkeille hyödyllisiä pseudoluokkia voidaan soveltuvin osin käyttää myös muilla
elementeillä. Näistä `:hover` ja `:active` toimivat kaikille elementeille ja `:focus` niille elementeille,
joille voidaan antaa kohdistus, kuten `<input>`-elementeille.

CSS3 määrittelee lisäksi melko suuren joukon muitakin pseudoluokkia:

| Valitsin              | Esimerkki              | Esimerkin kuvaus                                                                                            |
|-----------------------|------------------------|-------------------------------------------------------------------------------------------------------------|
|`:active`              | `a:active`             | Valitsee aktiivisen (parhaillaan klikattavan) linkin.                                                       |
|`:checked`             | `input:checked`        | Valitsee ruksitut `<input>`-elementit (checkbox tai radio)                                                  |
|`:disabled`            | `input:disabled`       | Valitsee `<input>`-elementit, joilla `disabled`-attribuutti                                                 |
|`:empty`               | `p:empty`              | Valitsee `<p>`-elementit, joiden sisältö on tyhjä.                                                          |
|`:enabled`             | `input:enabled`        | Valitsee `<input>`-elementit, joilla **ei** ole `disabled`-attribuuttia.                                    |
|`:first-child`         | `p:first-child`        | Valitsee `<p>`-elementit, jotka ovat vanhempiensa ensimmäisiä lapsia.                                       |
|`:first-of-type`       |`p:first-of-type`       | Valitsee `<p>`-elementit, jotka ovat vanhempansa ensimmäisiä `<p>`-elementtejä.                             |
|`:focus`               | `input:focus`          | Valitsee `<input>`-elementin, jolla on kohdistus                                                            |
|`:hover`               | `a:hover`              | Valitsee linkin, jonka päällä hiiri on.                                                                     |
|`:in-range`            | `input:in-range`       | Valitsee `<input>`-elementit, joiden arvo on määrätyllä välillä.                                            |
|`:invalid`             | `input:invalid`        | Valitsee `<input>`-elementit, joiden arvo on virheellinen.                                                  |
|`:lang(kieli)`         | `p:lang(fi)`           | Valitsee `<p>`-elementit, joiden `lang`-attribuutti alkaa "fi".                                             |
|`:last-child`          | `p:last-child`         | Valitsee `<p>`-elementit, jotka ovat vanhempiensa viimeisiä lapsia.                                         |
|`:last-of-type`        | `p:last-of-type`       | Valitsee `<p>`-elementit, jotka ovat vanhempiensa viimeisiä `<p>`-elementtejä.                              |
|`:link`                | `a:link`               | Valitsee käymättömät linkit.                                                                                |
|`:not(valitsin)`       | `:not(p)`              | Valitsee kaikki elementit, jotka eivät ole `<p>`-elementtejä.                                               |
|`:nth-child(n)`        | `p:nth-child(2)`       | Valitsee kaikki `<p>`-elementit, jotka ovat vanhempansa toisia lapsia.                                      |
|                       | `li:nth-child(3n)`     | Valitsee kaikki `<li>`-elementit, jotka ovat vanhempansa *3n*:nsiä lapsia. (Joka kolmas)                    |
|                       | `tr:nth-child(3n+2)`   | Valitsee kaikki `<tr>`-elementit, jotka ovat vanhempansa *3n+1*:nsiä lapsia. (Joka kolmas alkaen toisesta)  |
|`:nth-last-child(n)`   | `p:nth-last-child(2)`  | Valitsee `<p>`-elementit, jotka ovat vanhempansa toiseksi viimeisiä lapsia.                                 |
|`:nth-last-of-type(n)` | `p:nth-last-of-type(2)`| Valitsee `<p>`-elementit, jotka ovat vanhempansa toiseksi viimeisiä `<p>`-elementtejä.                      |
|`:nth-of-type(n)`      | `p:nth-of-type(2)`     | Valitsee `<p>`-elementit, jotka ovat vanhempansa toisia `<p>`-elementtejä.                                  |
|`:only-child`          | `p:only-child`         | Valitsee `<p>`-elementit, jotka ovat vanhempansa ainoita lapsia.                                            |
|`:only-of-type`        | `p:only-of-type`       | Valitsee `<p>`-elementit, jotka ovat vanhempansa ainoita `<p>`-elementtejä.                                 |
|`:optional`            | `input:optional`       | Valitsee `<input>`-elementit, joilla ei ole `required`-attribuuttia.                                        |
|`:out-of-range`        | `input:out-of-range`   | Valitsee `<input>`-elementit, joiden arvo on määrätyn välin ulkopuolella.                                   |
|`:read-only`           | `input:read-only`      | Valitsee `<input>`-elementit, joilla on `readonly`-attribuutti.                                             |
|`:read-write`          | `input:read-write`     | Valitsee `<input>`-elementit, joilla ei ole `readonly`-attribuuttia.                                        |
|`:required`            | `input:required`       | Valitsee `<input>`-elementit, joilla on `required`-attribuutti.                                             |
|`:root`                | `:root`                | Valitsee dokumentin juurielementin.                                                                         |
|`:target`              | `#news:target`         | Valitsee nykyisen aktiivisen `#news`-elementin (klikattu linkkiä, jossa `#news` osoitteen lopussa)          |
|`:visited`             | `a:visited`            | Valitsee vieraillut linkit.                                                                                 |
|`:valid`               | `input:valid`          | Valitsee `<input>`-elementit, joiden arvot ovat luvallisia.                                                 |

```css
input:invalid {background-color: #faa; border: 1px solid red;}
input:valid {background-color: #afa; border: 1px solid green;}
input:checked + label {color: green;}
input:required {border: 1px solid black; border-left: 10px solid black;}
input:disabled {box-shadow: 0 0 2px blue;}
li:nth-child(3n+2) {background-color: #ffa;}
li:not(.valittu) {color: gray;}
li:nth-child(3n+2) {background-color: #ffa;}
```
```html
<input type="number" min="0" max="5" value="8">
<input type="checkbox" checked><label>rastiruutu</label>
<input type="text" placeholder="osoite" required>
<input type="text" placeholder="lempijuoma" disabled>
<ul>
    <li>yksi</li>
    <li>kaksi</li>
    <li>kolme</li>
    <li class="valittu">neljä</li>
    <li>viisi</li>
    <li class="valittu">kuusi</li>
    <li>seitsemän</li>
    <li>kahdeksan</li>
</ul>
</ul>
```
<div class="html-example">
<style type="text/css" scoped>
input:invalid {background-color: #faa; border: 1px solid red;}
input:valid {background-color: #afa; border: 1px solid green;}
input:checked + label {color: green;}
input:required {border: 1px solid black; border-left: 10px solid black;}
input:disabled {box-shadow: 0 0 2px blue;}
li:nth-child(3n+2) {background-color: #ffa;}
li:not(.valittu) {color: gray;}
</style>
<input type="number" min="0" max="5" value="8">
<input type="checkbox" checked><label>rastiruutu</label>
<input type="text" placeholder="osoite" required>
<input type="text" placeholder="lempijuoma" disabled>
<ul>
    <li>yksi</li>
    <li>kaksi</li>
    <li>kolme</li>
    <li class="valittu">neljä</li>
    <li>viisi</li>
    <li class="valittu">kuusi</li>
    <li>seitsemän</li>
    <li>kahdeksan</li>
</ul>
</div>


Pseudoelementit
===============
Pseudoluokat olivat jo olemassa olevan elementin erityisessä tilanteessa esiintyviä ominaisuuksia,
joiden avulla elementin voi CSS-sääntöjä varten valita.
[Pseudoelementit][Pseudoelementit] puolestaan ovat elementtejä, joita ei todellisessa HTML-tekstissä ole,
mutta joita selain osaa käsitellä itsenäisen elementin tavoin. Tällaisia ovat esimerkiksi jonkin elementin sisällä sen
ensimmäinen kirjain.

Valitsimissa pseudoelementtiä merkitään kahdella kaksoispisteellä `::` muodossa:

```css
valitsin::pseudo-elementti {
    ominaisuus: arvo;
}
```

Pseudoelementit:

| Valitsin              | Esimerkki              | Esimerkin kuvaus                                                                                            |
|-----------------------|------------------------|-------------------------------------------------------------------------------------------------------------|
|`::after`              | `p::after`             | Lisää ja valitsee sisältöelementin `<p>`-elementtien loppuun.                                               |
|`::before`             | `p::before`            | Lisää ja valitsee sisältöelementin `<p>`-elementtien alkuun.                                                |
|`::first-letter`       | `p::first-letter`      | Valitsee `<p>`-elementtien ensimmäisen kirjaimen.                                                           |
|`::first-line`         | `p::first-line`        | Valitsee `<p>`-elementtien ensimmäisen rivin.                                                               |
|`::selection`          | `p::selection`         | Valitsee `<p>`-elementtien osan, jonka käyttäjä on valinnut.                                                |

Pseudoelementit `::before` ja `::after` ovat kyseisen todellisen elementin sisälle alkuun ja loppuun tulevat
elementit, joiden sisällöksi tulee CSS-säännöissä `content`-ominaisuuden arvona oleva teksti tai
merkinnällä `url('kuvan_osoite.png')` ilmoitettu kuva.

Pseudoelementti `::first-letter` käsittelee kyseisen lohkoelementin ensimmäistä kirjainta kuin
todellista HTML-elementtiä ja `::first-line` tekee saman lohkoelementin ensimmäiselle riville.

`::selection` puolestaan tarkoittaa elementin sisältä käyttäjän valitsemaa ("maalaamaa") osuutta.
Firefox ei tue suoraan `::selection`-pseudoelementtiä vaan se täytyy huomioida erikseen
*prefixillä* "-moz-" merkityllä vastineella `::-moz-selection`.

```css
    .laatikko {
        border: 1px dotted black;
    }
    .laatikko::before {
        content: "Laatikon alku";
        background-color: #faa;
    }
    .laatikko::after {
        content: "Laatikon loppu " url('ghost-penguin.png') " ja kummitus";
        display: block;
        background-color: #aaf;
        text-align: right;
    }
    p::first-line {
        font-weight: bold;
    }
    p::first-letter {
        font-size: 265%;
        color: red;
        margin: 0 0.2em 0.2em 0;
        padding: 0;
        display: block;
        float: left;
    }
    p::selection {
        background-color: #ffa;
    }
    p::-moz-selection {
        background-color: #ffa;
    }
```
```html
<div class="laatikko">
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Cras auctor consequat lorem eget vestibulum. Aenean sodales magna et mauris elementum, quis facilisis lacus scelerisque. Etiam egestas lectus non tellus facilisis malesuada. Pellentesque faucibus maximus aliquet. Etiam sed nunc nec ante cursus accumsan.
</div>
<p>
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Cras auctor consequat lorem eget vestibulum. Aenean sodales magna et mauris elementum, quis facilisis lacus scelerisque. Etiam egestas lectus non tellus facilisis malesuada. Pellentesque faucibus maximus aliquet. Etiam sed nunc nec ante cursus accumsan.
</p>
<p>
    Vestibulum consectetur eros ac porttitor viverra. Mauris id pulvinar nunc. Quisque non consectetur nisi. Nullam a rutrum libero, quis fermentum diam. Praesent eu mauris a ligula consequat faucibus vel sit amet erat. In maximus sapien eget est mollis, nec sagittis orci placerat. Vestibulum lorem sem, rutrum quis enim ac, commodo eleifend libero. Interdum et malesuada fames ac ante ipsum primis in faucibus. Aenean non lacinia justo.
</p>
```
<div class="html-example">
<style type="text/css" scoped>
    .laatikko {
        border: 1px dotted black;
    }
    .laatikko::before {
        content: "Laatikon alku";
        background-color: #faa;
    }
    .laatikko::after {
        content: "Laatikon loppu " url('../../images/ghost-penguin.png') " ja kummitus";
        display: block;
        background-color: #aaf;
        text-align: right;
    }
    p::first-line {
        font-weight: bold;
    }
    p::first-letter {
        font-size: 265%;
        color: red;
        margin: 0 0.2em 0.2em 0;
        padding: 0;
        display: block;
        float: left;
    }
    p::selection {
        background-color: #ffa;
    }
    p::-moz-selection {
        background-color: #ffa;
    }
</style>
<div class="laatikko">
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Cras auctor consequat lorem eget vestibulum. Aenean sodales magna et mauris elementum, quis facilisis lacus scelerisque. Etiam egestas lectus non tellus facilisis malesuada. Pellentesque faucibus maximus aliquet. Etiam sed nunc nec ante cursus accumsan.
</div>
<p>
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Cras auctor consequat lorem eget vestibulum. Aenean sodales magna et mauris elementum, quis facilisis lacus scelerisque. Etiam egestas lectus non tellus facilisis malesuada. Pellentesque faucibus maximus aliquet. Etiam sed nunc nec ante cursus accumsan.
</p>
<p>
    Vestibulum consectetur eros ac porttitor viverra. Mauris id pulvinar nunc. Quisque non consectetur nisi. Nullam a rutrum libero, quis fermentum diam. Praesent eu mauris a ligula consequat faucibus vel sit amet erat. In maximus sapien eget est mollis, nec sagittis orci placerat. Vestibulum lorem sem, rutrum quis enim ac, commodo eleifend libero. Interdum et malesuada fames ac ante ipsum primis in faucibus. Aenean non lacinia justo.
</p>
</div>

Hiiren osoitin
==============

Myös hiiren osoittimen ulkoasua, sen ollessa valitun elementin päällä, voidaan
vaihtaa CSS-ominaisuudella `cursor`. Tyyppejä on useita ja lisäksi kursoriksi voi määrätä myös
oman kuvan `url(kuva.png)`-muotoisella arvolla. Käytettävissä olevia tyyppejä voi
kokeilla esimerkiksi [W3Schoolsin kokeilusivulla][Cursor].

Valmiilla arvoilla osoittimen lopullinen tyyli määräytyy käyttöjärjestelmän käytössä
olevista osoittimista.

```css
.laatikko {min-height: 50px; min-width: 100px; display: inline-block; text-align: center; padding: 10px 0;}
.eka {background-color: #faa; cursor: pointer;}
.toka {background-color: #ffa; cursor: wait;}
.kolmas {background-color: #afa; cursor: help;}
.neljas {background-color: #aaf; cursor: move;}
.viides {background-color: #aff; cursor: copy;}
.kuudes {background-color: #faf; cursor: grab;}
.kuudes:active {background-color: #faf; cursor: grabbing;}
.seitsemas {background-color: #aaa; cursor: url(html5-pieni.png), auto;}
```
```html
<div class="laatikko eka">Pointer</div>
<div class="laatikko toka">Wait</div>
<div class="laatikko kolmas">Help</div>
<div class="laatikko neljas">Move</div>
<div class="laatikko viides">Copy</div>
<div class="laatikko kuudes">Grab</div>
<div class="laatikko seitsemas">Html5</div>
```
<div class="html-example">
    <style type="text/css" scoped>
        .laatikko {min-height: 50px; min-width: 100px; display: inline-block; text-align: center; padding: 10px 0;}
        .eka {background-color: #faa; cursor: pointer;}
        .toka {background-color: #ffa; cursor: wait;}
        .kolmas {background-color: #afa; cursor: help;}
        .neljas {background-color: #aaf; cursor: move;}
        .viides {background-color: #aff; cursor: copy;}
        .kuudes {background-color: #faf; cursor: grab;}
        .kuudes:active {background-color: #faf; cursor: grabbing;}
        .seitsemas {background-color: #aaa; cursor: url(../../images/html5-pieni.png), auto;}
    </style>
    <div class="laatikko eka">Pointer</div>
    <div class="laatikko toka">Wait</div>
    <div class="laatikko kolmas">Help</div>
    <div class="laatikko neljas">Move</div>
    <div class="laatikko viides">Copy</div>
    <div class="laatikko kuudes">Grab</div>
    <div class="laatikko seitsemas">Html5</div>
</div>


[Pseudoluokat]: http://www.w3schools.com/css/css_pseudo_classes.asp "W3Schools:Pseudoluokat"
[Pseudoelementit]: http://www.w3schools.com/css/css_pseudo_elements.asp "W3Schools:Pseudoelementit"
[Cursor]: http://www.w3schools.com/cssref/playit.asp?filename=playcss_cursor "W3Schools:Cursor"