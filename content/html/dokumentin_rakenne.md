+++
Categories = []
Description = ""
Tags = []
Title = "Dokumentin rakenne"
date = "2016-01-06T13:00:00+02:00"
weight = 2

+++

HTML-tagit
==========
{{% jessyink src="html-johdanto.svg#4" %}}
{{% /jessyink %}}

HTML-dokumentti on tekstiä, jolle on annettu rakenne merkitsemällä sen
osia erilaisilla HTML-kielen *tageilla*. Tekstin osan alku merkitään
aloitustagilla ja loppu lopetustagilla.

* Aloitustagi on tagin nimi ympäröitynä `<`- ja `>`-merkeillä.
Esimerkiksi: `<strong>`
* Lopetustagi on tagin nimi ympäröitynä `</`- ja `>`-merkinnöillä.
Esimerkiksi: `</strong>`
* Joillain tageilla ei ole (HTML5:ssä) pakollista lopetustagia. Esimerkiksi
rivinvaihto `<br>` ja kuvatagi `<img>`.
(Jos dokumentin tyypiksi on valittu XHTML niin lopputagi on aina pakollinen. Se voidaan
kuitenkin kirjoittaa aloitustagin sisälle `<br />`)

Esimerkki:
```
<h1>Otsikko</h1>
<p>Pieni kappale ja vähän <strong>korostettua tekstiä</strong>.<p>
<p>Toinen kappale ja <em>toisenlainen korostus</em> tekstissä.</p>
```

Vaikka useimmille tageille on määritelty oletusulkoasu, jolla ne
näytetään www-selaimessa, tagien tarkoitus ei kuitenkaan ole
määritellä sivun osien ulkoasua vaan niiden merkitys dokumentissa.
Tagit ovat siis semanttisia. Tageja ovat esimerkiksi eri tasoiset
otsikot (h1, h2, h3, h4, h5, h6), linkit (a), kappaleet (p) ja listat
sekä listan alkiot (ul, ol, li).

HTML-dokumentin tageista muodostuu sisäkkäinen rakennelma, jota voidaan kuvata
puurakenteena tai sisäkkäisinä laatikoina.

<figure>
<svg xmlns="http://www.w3.org/2000/svg" version="1.1" width="800" height="400" viewBox="0 0 800 400" class="chart">
    <rect stroke="blue" stroke-width="2" fill="none" x="2" y="2" width="750" height="380"></rect>
    <text x="5" y="20" style="font-family: monospace; font-size: 12px; font-weight: bold; fill: blue;">&lt;html&gt;</text>
    <text x="5" y="375" style="font-family: monospace; font-size: 12px; font-weight: bold; fill: blue;">&lt;/html&gt;</text>

    <g transform="translate(10,30)">
        <rect stroke="red" stroke-width="2" fill="none" x="0" y="0" width="735" height="100"></rect>
        <text x="5" y="15" style="font-family: monospace; font-size: 12px; font-weight: bold; fill: red;">&lt;head&gt;</text>
        <text x="5" y="94" style="font-family: monospace; font-size: 12px; font-weight: bold; fill: red;">&lt;/head&gt;</text>

        <g transform="translate(10,20)">
            <rect stroke="brown" stroke-width="2" fill="none" x="0" y="0" width="715" height="20"></rect>
            <text x="5" y="15" style="font-family: monospace; font-size: 12px; font-weight: bold; fill: brown;">&lt;title&gt;</text>
            <text x="150" y="15" style="font-family: monospace; font-size: 12px; font-weight: bold; fill: black;">Www-ohjelmointi</text>
            <text x="645" y="15" style="font-family: monospace; font-size: 12px; font-weight: bold; fill: brown;">&lt;/title&gt;</text>
        </g>

        <g transform="translate(10,40)">
            <rect stroke="brown" stroke-width="2" fill="none" x="0" y="0" width="715" height="20"></rect>
            <text x="5" y="15" style="font-family: monospace; font-size: 12px; font-weight: bold; fill: brown;">&lt;link&gt;</text>
            <text x="645" y="15" style="font-family: monospace; font-size: 12px; font-weight: bold; fill: brown;">&lt;/link&gt;</text>
        </g>

        <g transform="translate(10,60)">
            <rect stroke="brown" stroke-width="2" fill="none" x="0" y="0" width="715" height="20"></rect>
            <text x="5" y="15" style="font-family: monospace; font-size: 12px; font-weight: bold; fill: brown;">&lt;script&gt;</text>
            <text x="645" y="15" style="font-family: monospace; font-size: 12px; font-weight: bold; fill: brown;">&lt;/script&gt;</text>
        </g>

    </g>

    <g transform="translate(10,150)">
        <rect stroke="red" stroke-width="2" fill="none" x="0" y="0" width="735" height="210"></rect>
        <text x="5" y="15" style="font-family: monospace; font-size: 12px; font-weight: bold; fill: red;">&lt;body&gt;</text>
        <text x="5" y="200" style="font-family: monospace; font-size: 12px; font-weight: bold; fill: red;">&lt;/body&gt;</text>

        <g transform="translate(120,10)">
            <rect stroke="green" stroke-width="2" fill="none" x="0" y="0" width="600" height="40"></rect>
            <text x="5" y="15" style="font-family: monospace; font-size: 12px; font-weight: bold; fill: green;">&lt;header&gt;</text>
            <text x="5" y="34" style="font-family: monospace; font-size: 12px; font-weight: bold; fill: green;">&lt;/header&gt;</text>
        </g>

        <g transform="translate(120,58)">
            <rect stroke="green" stroke-width="2" fill="none" x="0" y="0" width="600" height="100"></rect>
            <text x="5" y="15" style="font-family: monospace; font-size: 12px; font-weight: bold; fill: green;">&lt;article&gt;</text>
            <text x="5" y="94" style="font-family: monospace; font-size: 12px; font-weight: bold; fill: green;">&lt;/article&gt;</text>

            <g transform="translate(10,20)">
                <rect stroke="brown" stroke-width="2" fill="none" x="0" y="0" width="570" height="20"></rect>
                <text x="5" y="15" style="font-family: monospace; font-size: 12px; font-weight: bold; fill: brown;">&lt;h1&gt;</text>
                <text x="150" y="15" style="font-family: monospace; font-size: 12px; font-weight: bold; fill: black;">Otsikko</text>
                <text x="500" y="15" style="font-family: monospace; font-size: 12px; font-weight: bold; fill: brown;">&lt;/h1&gt;</text>
            </g>

            <g transform="translate(10,40)">
                <rect stroke="brown" stroke-width="2" fill="none" x="0" y="0" width="570" height="20"></rect>
                <rect stroke="#777" stroke-width="1" fill="#ffa" x="213" y="2" width="170" height="16"></rect>
                <text x="5" y="15" style="font-family: monospace; font-size: 12px; font-weight: bold; fill: brown;">&lt;p&gt;</text>
                <text x="150" y="15" style="font-family: monospace; font-size: 12px; font-weight: bold; fill: black;">Sisältöä &lt;strong&gt;tekstiä&lt;/strong&gt; sisältöä...</text>
                <text x="500" y="15" style="font-family: monospace; font-size: 12px; font-weight: bold; fill: brown;">&lt;/p&gt;</text>
            </g>

            <g transform="translate(10,60)">
                <rect stroke="brown" stroke-width="2" fill="none" x="0" y="0" width="570" height="20"></rect>
                <rect stroke="#777" stroke-width="1" fill="#ffa" x="213" y="2" width="90" height="16"></rect>
                <text x="5" y="15" style="font-family: monospace; font-size: 12px; font-weight: bold; fill: brown;">&lt;p&gt;</text>
                <text x="150" y="15" style="font-family: monospace; font-size: 12px; font-weight: bold; fill: black;">Sisältöä &lt;a&gt;linkki&lt;/a&gt; sisältöä...</text>
                <text x="500" y="15" style="font-family: monospace; font-size: 12px; font-weight: bold; fill: brown;">&lt;/p&gt;</text>
            </g>

        </g>

        <g transform="translate(120,167)">
            <rect stroke="green" stroke-width="2" fill="none" x="0" y="0" width="600" height="40"></rect>
            <text x="5" y="15" style="font-family: monospace; font-size: 12px; font-weight: bold; fill: green;">&lt;footer&gt;</text>
            <text x="5" y="34" style="font-family: monospace; font-size: 12px; font-weight: bold; fill: green;">&lt;/footer&gt;</text>
        </g>

        <g transform="translate(8, 20)">
            <rect stroke="green" stroke-width="2" fill="none" x="0" y="0" width="100" height="160"></rect>
            <text x="5" y="15" style="font-family: monospace; font-size: 12px; font-weight: bold; fill: green;">&lt;nav&gt;</text>
            <text x="5" y="154" style="font-family: monospace; font-size: 12px; font-weight: bold; fill: green;">&lt;/nav&gt;</text>

            <g transform="translate(5,20)">
                <rect stroke="brown" stroke-width="2" fill="none" x="0" y="0" width="90" height="20"></rect>
                <text x="5" y="15" style="font-family: monospace; font-size: 12px; font-weight: bold; fill: brown;">&lt;h1&gt;</text>
                <text x="50" y="15" style="font-family: monospace; font-size: 12px; font-weight: bold; fill: brown;">&lt;/h1&gt;</text>
            </g>

            <g transform="translate(5,40)">
                <rect stroke="brown" stroke-width="2" fill="none" x="0" y="0" width="90" height="100"></rect>
                <text x="5" y="15" style="font-family: monospace; font-size: 12px; font-weight: bold; fill: brown;">&lt;ul&gt;</text>
                <text x="5" y="95" style="font-family: monospace; font-size: 12px; font-weight: bold; fill: brown;">&lt;/ul&gt;</text>

                <g transform="translate(5,20)">
                    <rect stroke="#777" stroke-width="1" fill="#ffa" x="0" y="0" width="80" height="20"></rect>
                    <text x="5" y="15" style="font-family: monospace; font-size: 12px; font-weight: bold; fill: brown;">&lt;li&gt;</text>
                    <text x="40" y="15" style="font-family: monospace; font-size: 12px; font-weight: bold; fill: brown;">&lt;/li&gt;</text>
                </g>
                <g transform="translate(5,40)">
                    <rect stroke="#777" stroke-width="1" fill="#ffa" x="0" y="0" width="80" height="20"></rect>
                    <text x="5" y="15" style="font-family: monospace; font-size: 12px; font-weight: bold; fill: brown;">&lt;li&gt;</text>
                    <text x="40" y="15" style="font-family: monospace; font-size: 12px; font-weight: bold; fill: brown;">&lt;/li&gt;</text>
                </g>
                <g transform="translate(5,60)">
                    <rect stroke="#777" stroke-width="1" fill="#ffa" x="0" y="0" width="80" height="20"></rect>
                    <text x="5" y="15" style="font-family: monospace; font-size: 12px; font-weight: bold; fill: brown;">&lt;li&gt;</text>
                    <text x="40" y="15" style="font-family: monospace; font-size: 12px; font-weight: bold; fill: brown;">&lt;/li&gt;</text>
                </g>

            </g>

        </g>

    </g>
</svg>
</figure>


Tagien-attribuutit
------------------
Tagin merkitystä voidaan tarkentaa lisäämällä aloitustagiin tagin
tyypistä riippuen erilaisia attribuutteja ja niiden arvoja.
Attribuutit kirjoitetaan tagin nimen jälkeen ennen `>`-merkkiä.
Ne ovat muotoa `attribuutti="arvo"`.
Esimerkki:

* Linkkitagissa attribuutti `href` kertoo linkin osoitteen:<br>
  `<a href="http://petrit.net/www-ohjelmointi">Linkki kurssisivulle</a>`
* Kuvatagissa attribuutti `src` kertoo osoitteen, josta näytettävä kuva haetaan:<br>
  `<img src="http://petrit.net/www-ohjelmointi/images/kuva.png">`

Id:t ja luokat
--------------
Kaksi erityistä attribuuttia, joilla HTML-elementtejä voidaan merkitä, ovat `id` ja `class`.
Näistä `id` on tarkoitettu attribuutiksi, jolla elementille annetaan dokumentin sisällä
yksilöllinen nimi, jolla siihen voidaan viitata esimerkiksi CSS-tyylityksissä, Javascript-toiminnallisuudessa
tai sivun linkityksessä.  Esimerkiksi dokumentin sisällä voidaan toteuttaa linkityksiä
viittaamalla näihin nimettyihin elementteihin `id`-attribuutin arvolla.

```
<a href="#linkitys">Linkitys</a>
...
<h1 id="linkitys">Linkitys</a>
```
<div class="html-example">
<a href="#linkitys">Linkitys</a>
<br>...
<h1 id="linkitys">Linkitys</a>
</div>

`class`-attribuutilla voidaan merkitä elementti kuulumaan yhteen tai useampaan "luokkaan",
eli kertoa elementin olevan jotain tiettyä tyyppiä kyseisessä dokumentissa. Luokkia voidaan
hyödyntää esimerkiksi ulkoasun tyylittelyssä määräämällä tiettyyn luokkaan kuuluville elementeille
keskenään yhtenäinen ulkoasu. Attribuuttiin voidaan laittaa useampi luokka erottelemalla ne välilyönneillä.

```
<article class="blogpost latestpost">
    <div class="author">Petri Salmela</div>
    <div class="postcontent">
        ...
    </div>
</article>
<article class="blogpost">
    <div class="author">Petri Salmela</div>
    <div class="postcontent">
        ...
    </div>
</article>
```
<div class="html-example">
<article class="blogpost latestpost" style="margin: 2em; padding: 0.5em; border: 1px solid #777; border-radius: 0.5em; background-color: #ffa;">
    <div class="author" style="background-color: black; color: white; border-radius: 0.5em 0.5em 0 0; margin: -0.5em -0.5em 0.5em -0.5em; padding: 0.3em 0.5em; font-style: italic;">Petri Salmela</div>
    <div class="postcontent">
        ...
    </div>
</article>
<article class="blogpost" style="margin: 2em; padding: 0.5em; border: 1px solid #777; border-radius: 0.5em;">
    <div class="author" style="background-color: black; color: white; border-radius: 0.5em 0.5em 0 0; margin: -0.5em -0.5em 0.5em -0.5em; padding: 0.3em 0.5em; font-style: italic;">Matti Meikäläinen</div>
    <div class="postcontent">
        ...
    </div>
</article>
</div>

HTML-dokumentti
=========
HTML-dokumentti kirjoitetaan `<html>`- ja `</html>`-tagien väliin heti doctype-määrittelyn
jälkeen. HTML-tagin sisällä dokumentti jakautuu *head*- ja *body* osiin, jotka ympäröidään
vastaavasti `<head>`- ja `</head>`-tagien sekä `<body>`- ja `</body>`-tagien väliin.

```
<!DOCTYPE html>
<html>
    <head>
        ... dokumentin määrittelyjä ...
    </head>
    <body>
        ... dokumentin sisältö ...
    </body>
</html>
```

Head-osio sisältää dokumentin määrittelyitä, kuten selaimen yläpalkissa näkyvän otsikon,
käytetyn merkistökoodauksen sekä ulkoasuun vaikuttavien tiedostojen sijainnin.

Body-osio puolestaan sisältää dokumentin varsinaisen sisällön.
