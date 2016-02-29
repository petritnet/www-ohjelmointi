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
  (<span style="color: rgba(20,20,170,0.2);">rgba(20,20,170,0.2)</span>,
  <span style="color: rgba(20,20,170,0.5);">rgba(20,20,170,0.5)</span>,
  <span style="color: rgba(20,20,170,0.9);">rgba(20,20,170,0.9)</span>)

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
kuitenkaan käytännössä ole eroa.

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
    <em style="font-style: normal;">dolor</em>
    <span style="font-style: oblique;">amet</span>...
</p>
</div>


Tekstin koko
============
Tekstin kokoon voi vaikuttaa muuttamalla `font-size`-ominaisuuden arvoa. Arvon antaa absoluttisena
tai suhteellisena ja useammassa eri [mittayksikössä][Units]. Yksikön valinta riippuu myös mediasta,
jolle tyylisääntö on tarkoitettu:

- Pikseleinä: `12px` (absoluuttinen, näyttö)
- Prosentteina: `150%` (suhteellinen, näyttö/tuloste)
- M-kirjaimen leveys: `1.5em` (suhteellinen, näyttö)
- x-kirjaimen korkeus: `1.5ex` (suhteellinen, näyttö)
- Points, pica: `12pt`, `12pc` (absoluuttinen, tuloste)
- Sentit, millit, tuumat: `2cm`, `15mm`, `0.5in` (absoluuttinen, tuloste)
- Nimillä: `medium`, `xx-small`, `x-small`, `small`, `large`, `x-large`, `xx-large`, `smaller`, `larger`

Absoluuttiset mittayksiköt ovat samat kautta koko dokumentin. Suhteelliset mittayksiköt puolestaan
määrittelevät kyseisen elementin tekstin koon suhteessa ympäröivään elementtiin. Esimerkiksi, jos
`<article>`-elementin tekstikokona on `12px` ja sen sisällä olevan `<h1>`-elementin kooksi on
määritelty `250%`, tulee otsikon todelliseksi kooksi 30 pikseliä. Koska sivun tekijä ei voi tietää,
minkälaisella ja minkä kokoisella laitteella käyttäjä tulee sivua katselemaan, on yleensä syytä
määritellä tekstin koko suhteellisilla yksiköillä.

```
<p style="font-size: 12px;">
    <span>Lorem</span>
    <span style="font-size: 25px;">ipsum</span> sit
    <em style="font-size: 1.5em;">dolor</em>
    <span style="font-size: 70%;">amet</span>...
</p>
```
<div class="html-example">
<p style="font-size: 12px;">
    <span>Lorem</span>
    <span style="font-size: 25px;">ipsum</span> sit
    <em style="font-size: 1.5em;">dolor</em>
    <span style="font-size: 70%;">amet</span>...
</p>
</div>

Kirjasinperhe
=============
Tekstin *kirjasintyypin*, eli *fontin*, valinta tehdään käyttämällä `font-family`-ominaisuutta.
Fonttiperheen valinta kannattaa tehdä harkitusti, sillä jos kirjasintyypiksi valitaan sellainen,
jota sivun käyttäjällä ei ole käytettävissä, selain käyttää sen sijaan jotain oletuskirjasinta.
Usein `font-family`-ominaisuuden arvoksi kannattaakin antaa pilkulla lueteltu joukko vaihtoehtoisia
kirjasintyyppejä, joista käytetään ensimmäistä löytyvää.

Tarkkojen fonttinimien, kuten `Arial`, `Helvetica`, `"Times New Roman"` ja `"MS Comic Sans"`, lisäksi
käytettävissä on myös yleisempiä kirjasinperheiden nimiä, kuten `serif` (*päätteellinen kirjasin*, kuten
"Times New Roman"), `sans-serif` (*päätteetön kirjasin*, kuten Arial tai Helvetica) sekä
`monospace` (*tasalevyinen kirjasin*, joka sopii esimerkiksi koodille). Yleisiä kirjasinperheitä
käytettäessä käytettävä fontti valitaan selaimen asetusten mukaan.

Kirjasintyyppejä on mahdollista ottaa käyttöön myös niin sanottuina *webfontteina*, jolloin CSS:llä
kerrotaan verkon yli käyttöön ladattava fonttitiedosto jolloin kyseistä kirjasintyyppiä voidaan käyttää
sivulla riippumatta siitä, mitä kirjatyyppejä on asennettuna käyttäjän koneelle. Webfontteja voi ladata
käyttöön joko jostain julkisesta palvelusta, kuten [Google Fonts][Google Fonts] tai
[Open Font Library][OFL], taikka tarjoilemalla ne käyttöön suoraan omalta palvelimelta.

```
<p style="font-family: Helvetica, Ariel, sans-serif; font-size: 150%;">
    <span>Lorem ipsum dolor sit amet,</span>
    <span style="font-family: 'Times New Roman', serif;">consectetur adipiscing elit.</span>
    Sed semper eleifend mauris eu gravida.
    <span style="font-family: 'Comic Sans MS';">Nulla volutpat ante eget consequat malesuada.</span>
    <span style="font-family: 'Josefin Sans';">Nunc iaculis mauris eros, ac pharetra libero dapibus et.</span>...
</p>
```
<div class="html-example">
<p style="font-family: Helvetica, Ariel, sans-serif; font-size: 150%;">
    <span>Lorem ipsum dolor sit amet,</span>
    <span style="font-family: 'Times New Roman', serif;">consectetur adipiscing elit.</span>
    Sed semper eleifend mauris eu gravida.
    <span style="font-family: 'Comic Sans MS';">Nulla volutpat ante eget consequat malesuada.</span>
    <span style="font-family: 'Josefin Sans';">Nunc iaculis mauris eros, ac pharetra libero dapibus et.</span>...
</p>
</div>

Tekstin "koristelu"
==================
Tekstiä voidaan myös [koristella][Textdecoration] käyttämällä `text-decoration`-ominaisuutta. Esimerkiksi `<u>`-tagin oletusulkoasu
on alleviivattu, eli sen `text-decoration`-ominaisuuden arvo on `underline`.

Ominaisuuden mahdollisia arvoja ovat:

- `underline`: <span style="text-decoration: underline;">alleviivaus</span>
- `overline`: <span style="text-decoration: overline;">ylleviivaus</span>
- `line-through`: <span style="text-decoration: line-through;">yliviivaus</span>

Arvoja voi antaa `text-decoration`-ominaisuudelle useita yhtä aikaa välilyönnillä eroteltuina.

```
<p>
    <span style="text-decoration: underline overline;">Lorem</span>
    <span style="text-decoration: line-through;">ipsum</span> sit
    <span style="text-decoration: line-through underline overline;">dolor</span>
    <span style="text-decoration: underline;">amet</span>...
</p>
```
<div class="html-example">
<p>
    <span style="text-decoration: underline overline;">Lorem</span>
    <span style="text-decoration: line-through;">ipsum</span> sit
    <span style="text-decoration: line-through underline overline;">dolor</span>
    <span style="text-decoration: underline;">amet</span>...
</p>
</div>


Tekstin tasaus elementissä
==========================
Tekstilohkon sivureunojen tasaukseen käytetään `text-align`-ominaisuutta, jonka mahdollisia
arvoja ovat:

- `left`: vasen tasaus
- `center`: keskitys
- `right`: oikea tasaus
- `justify`: molempien reunojen tasaus

```
    <p style="text-align: left;">
        Nulla facilisi. Mauris sapien massa,...
    </p>
    <p style="text-align: center;">
        Nulla facilisi. Mauris sapien massa,...
    </p>
    <p style="text-align: right;">
        Nulla facilisi. Mauris sapien massa,...
    </p>
    <p style="text-align: justify;">
        Nulla facilisi. Mauris sapien massa,...
    </p>
```
<div class="html-example">
    <div style="font-size: 80%; width: 50%; margin: 0 auto;">
    <p style="text-align: left;">Nulla facilisi. Mauris sapien massa, viverra quis massa posuere, tempor eleifend lacus.
    Proin at iaculis metus. Curabitur a dolor est. Praesent vitae ipsum ligula. Pellentesque in
    tellus congue, euismod orci sit amet, scelerisque lorem. Maecenas et quam felis. Phasellus
    accumsan auctor sapien sed facilisis. Pellentesque metus felis, euismod in sapien vitae,
    ultricies convallis lacus. Cras non ultricies nibh.</p>
    <p style="text-align: center;">Nulla facilisi. Mauris sapien massa, viverra quis massa posuere, tempor eleifend lacus.
    Proin at iaculis metus. Curabitur a dolor est. Praesent vitae ipsum ligula. Pellentesque in
    tellus congue, euismod orci sit amet, scelerisque lorem. Maecenas et quam felis. Phasellus
    accumsan auctor sapien sed facilisis. Pellentesque metus felis, euismod in sapien vitae,
    ultricies convallis lacus. Cras non ultricies nibh.</p>
    <p style="text-align: right;">Nulla facilisi. Mauris sapien massa, viverra quis massa posuere, tempor eleifend lacus.
    Proin at iaculis metus. Curabitur a dolor est. Praesent vitae ipsum ligula. Pellentesque in
    tellus congue, euismod orci sit amet, scelerisque lorem. Maecenas et quam felis. Phasellus
    accumsan auctor sapien sed facilisis. Pellentesque metus felis, euismod in sapien vitae,
    ultricies convallis lacus. Cras non ultricies nibh.</p>
    <p style="text-align: justify;">Nulla facilisi. Mauris sapien massa, viverra quis massa posuere, tempor eleifend lacus.
    Proin at iaculis metus. Curabitur a dolor est. Praesent vitae ipsum ligula. Pellentesque in
    tellus congue, euismod orci sit amet, scelerisque lorem. Maecenas et quam felis. Phasellus
    accumsan auctor sapien sed facilisis. Pellentesque metus felis, euismod in sapien vitae,
    ultricies convallis lacus. Cras non ultricies nibh.</p>
    </div>
</div>

Tekstin muunnokset
==================
`text-transform`-ominaisuudella voidaan muuntaa tekstin ilmiasua suurten ja pienten kirjainten suhteen. Arvoja ovat:

- `uppercase`: kaikki kirjaimet isolla
- `lowercase`: kaikki kirjaimet pienellä
- `capitalize`: sanojen ensimmäiset kirjaimet isolla
- `none`: muotoilut pois (nollaa ulommassa elementissä määrätyn arvon)

```
    <p style="text-transform: uppercase;">
        Nulla facilisi. Mauris sapien massa,...
    </p>
    <p style="text-transform: lowercase;">
        Nulla facilisi. Mauris sapien massa,...
    </p>
    <p style="text-transform: capitalize;">
        Nulla facilisi. Mauris sapien massa,...
    </p>
    <p style="text-transform: uppercase;">
        Nulla facilisi. <span style="text-transform: none;">Mauris sapien</span> massa,...
    </p>
```
<div class="html-example">
    <p style="text-transform: uppercase;">
        Nulla facilisi. Mauris sapien massa,...
    </p>
    <p style="text-transform: lowercase;">
        Nulla facilisi. Mauris sapien massa,...
    </p>
    <p style="text-transform: capitalize;">
        Nulla facilisi. Mauris sapien massa,...
    </p>
    <p style="text-transform: uppercase;">
        Nulla facilisi. <span style="text-transform: none;">Mauris sapien</span> massa,...
    </p>
</div>

Tekstin varjostus
=================
CSS3:n myötä on tullut mahdolliseksi lisätä teksteihin myös varjostusta `text-shadow`-ominaisuudella.
Ominaisuuden arvoksi annetaan välilyönneillä eroteltuina varjostuksen vaakapoikkeama, pystypoikkeama,
sumennuksen määrä sekä väri. Kolme ensimmäistä arvoa annetaan mittayksikköinä, kuten pikseleinä ja
väri annetaan jossain RGB- tai RGBA-muodossa, kuten `color`-ominaisuudelle.

Varjostuksia voidaan antaa myös useampia yhtä aikaa luettelemalla ne pilkulla erotettuina.

Tyypillisesti varjostusta käytetään esimerkiksi otsikoissa. Sen käytön kanssa kannattaa olla varovainen,
sillä huolimattomasti käytettynä lopputulos on suttuisen näköinen ja hankalasti luettava teksti.

```
    <h1 style="text-shadow: 2px 2px 3px red;">Nulla facilisi. Mauris sapien massa</h1>
    <p style="text-shadow: 1px 1px 2px rgba(0,0,0,0.5);">
        Nulla facilisi. Mauris sapien massa,...
    </p>
    <p style="text-shadow: 1px 1px 2px black;">
        Nulla facilisi. Mauris sapien massa,...
    </p>
    <h1 style="color: white; text-shadow: 1px 1px 0 black, 1px -1px 0 black, -1px 1px 0 black, -1px -1px 0 black;">
        Nulla facilisi. Mauris sapien massa
    </h1>
    <h1 style="text-shadow: 10px 10px 2px blue, -10px -10px 2px red;">
        Nulla facilisi. Mauris sapien massa
    </h1>
```
<div class="html-example">
    <h1 style="text-shadow: 2px 2px 3px red;">Nulla facilisi. Mauris sapien massa</h1>
    <p style="text-shadow: 1px 1px 2px rgba(0,0,0,0.5);">
        Nulla facilisi. Mauris sapien massa,...
    </p>
    <p style="text-shadow: 1px 1px 2px black;">
        Nulla facilisi. Mauris sapien massa,...
    </p>
    <h1 style="color: white; text-shadow: 1px 1px 0 black, 1px -1px 0 black, -1px 1px 0 black, -1px -1px 0 black;">
        Nulla facilisi. Mauris sapien massa
    </h1>
    <h1 style="text-shadow: 10px 10px 2px blue, -10px -10px 2px red;">
        Nulla facilisi. Mauris sapien massa
    </h1>
</div>


[Units]: https://www.w3.org/Style/Examples/007/units.en.html "W3org:Yksiköt"
[Google Fonts]: https://www.google.com/fonts "Google Fonts"
[OFL]: https://fontlibrary.org/ "Open Font Library"
[Textdecoration]: http://www.w3schools.com/cssref/pr_text_text-decoration.asp "W3C:Textdecoration"