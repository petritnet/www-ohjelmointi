+++
Categories = []
Description = ""
Tags = []
Title = "Elementtityypit"
date = "2016-02-10T21:26:26+02:00"
weight = 40

+++

HTML-elementeillä on näyttämisensä puolesta erilaisia elementtityyppejä. Jokaista elementtiä käsitellään
selaimessa jollain oletustyypillä, mutta elementin tyyppiä voi vaihtaa muuttamalla
sen `display`-ominaisuuden arvoa css-määrittelyllä. Tämä ominaisuus määrittelee sen, millä säännöillä
elementin näyttäminen selaimessa tapahtuu.

Elementtityyppejä ovat esimerkiksi:

* Tekstin tasalla olevat **inline**-elementit (a, strong, em, span,...)
* Erikseen "laatikoidut" lohkoelementit, eli **block**-elementit (h1–h6, p, div, article, section,...)
* Tekstin tasalle laatikoidut **inline-block**-elementit (img)
* **Table-cell**-elementit (td, th)

Inline (rivin sisäinen)
======
`inline`-elementit ovat nimensä mukaisesti rivin sisällä näytettäviä elementtejä. Nämä elementit
merkitsevät tekstistä jonkin osuuden, joka alkaa ja päättyy jostain kohtaa rivin sisällä.
(Ei siis automaattista rivinvaihtoa ennen ja jälkeen elementin.)

Elementin leveys, korkeus ja pystymarginaali ovat automaattisia. Leveys määräytyy sisällön mukaan
rivittyen muun tekstin mukaan. Korkeus ja pystymarginaali määräytyvät rivin korkeuden mukaan.
Vain vaakamarginaaleja voi muuttaa.

Inline-elementtejä ovat oletuksena muun muassa: `<a>`, `<strong>`, `<em>` ja `<span>`.

```
<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.
<span style="background-color: #ffa;">Donec quis risus non velit imperdiet laoreet. Nulla molestie a ante id pharetra.
Morbi finibus sed elit tincidunt laoreet. Etiam elementum malesuada nisl ut sodales.
Vestibulum tristique pharetra fringilla. Integer vel ligula mollis, iaculis purus sit
amet, mattis augue.</span> Maecenas ultrices purus id dui mattis gravida. Cras sem lorem, accumsan
eget placerat ac, hendrerit sit amet erat. Nam consequat vehicula nibh. Vivamus nec
egestas est. Aliquam erat volutpat. Suspendisse potenti. </p>
```
<div class="html-example">
<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.
<span style="background-color: #ffa;">Donec quis risus non velit imperdiet laoreet. Nulla molestie a ante id pharetra.
Morbi finibus sed elit tincidunt laoreet. Etiam elementum malesuada nisl ut sodales.
Vestibulum tristique pharetra fringilla. Integer vel ligula mollis, iaculis purus sit
amet, mattis augue.</span> Maecenas ultrices purus id dui mattis gravida. Cras sem lorem, accumsan
eget placerat ac, hendrerit sit amet erat. Nam consequat vehicula nibh. Vivamus nec
egestas est. Aliquam erat volutpat. Suspendisse potenti. </p>
</div>

Block (lohko)
=====
`block`-tyyppinen elementti täyttää vanhempanaan olevan elementin vasemmasta reunasta oikeaan reunaan.
Se alkaa uudelta riviltä ja sitä seuraava elementti alkaa seuraavalta riviltä.
Sille voidaan määritellä **leveys**, **korkeus** ja **marginaalit**.

Oletuksena block-tyyppisiä elementtejä ovat esimerkiksi: `<h1>`, `<h2>`, `<h3>`, `<h4>`, `<h5>`, `<h6>`,
`<p>`, `<ul>`, `<ol>`, `<li>`, `<div>`, `<article>`, `<section>`, `<aside>`, `<nav>` ja monet muut.

```
<div>
    <h1>Otsikko</h1>
    <p>Hiukan jotain tekstiä</p>
    <ul>
        <li>yksi</li>
        <li>kaksi</li>
    </ul>
</div>
```
<div class="html-example">
<div style="border: 1px solid red; margin: 1px;">
    <h1 style="border: 1px solid red; margin: 1px;">Otsikko</h1>
    <p style="border: 1px solid red; margin: 1px;">Hiukan jotain tekstiä</p>
    <ul style="border: 1px solid red; margin: 1px;">
        <li style="border: 1px solid red; margin: 1px;">yksi</li>
        <li style="border: 1px solid red; margin: 1px;">kaksi</li>
    </ul>
</div>
</div>

Inline-block
============
`inline-block`-tyyppiset elementit ovat sekoitus `inline`- ja `block`-tyyppisten elementtien
ominaisuuksia. Ne ovat laatikoita, joille voi määrätä koon ja marginaalit, mutta joka sijoittuu
tekstiriville kuin kirjain.

Oletuksena tätä tyyppiä ovat kuvat, eli `<img>`-elementit.

```
<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.
Donec quis risus non velit imperdiet laoreet. Nulla molestie a ante id pharetra.
Morbi finibus sed elit tincidunt laoreet. Etiam elementum malesuada nisl ut sodales.
Vestibulum tristique pharetra fringilla. <img src="ghost-penguin.png"> Integer vel ligula mollis, iaculis purus sit
amet, mattis augue. Maecenas ultrices purus id dui mattis gravida.
<span style="display: inline-block; width: 150px; height: 80px; font-size: 50%; background-color: #ffa;">
    Lorem ipsum dolor sit amet, consectetur adipiscing elit.
    Donec quis risus non velit imperdiet laoreet. Nulla molestie a ante id pharetra.
    Morbi finibus sed elit tincidunt laoreet. Etiam elementum malesuada nisl ut sodales.
    Vestibulum tristique pharetra fringilla.
</span>
Cras sem lorem, accumsan
eget placerat ac, hendrerit sit amet erat. Nam consequat vehicula nibh. Vivamus nec
egestas est. Aliquam erat volutpat. Suspendisse potenti. </p>
```
<div class="html-example">
<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.
Donec quis risus non velit imperdiet laoreet. Nulla molestie a ante id pharetra.
Morbi finibus sed elit tincidunt laoreet. Etiam elementum malesuada nisl ut sodales.
Vestibulum tristique pharetra fringilla. <img src="../../images/ghost-penguin.png"> Integer vel ligula mollis, iaculis purus sit
amet, mattis augue. Maecenas ultrices purus id dui mattis gravida.
<span style="display: inline-block; width: 150px; height: 80px; font-size: 50%; background-color: #ffa;">
    Lorem ipsum dolor sit amet, consectetur adipiscing elit.
    Donec quis risus non velit imperdiet laoreet. Nulla molestie a ante id pharetra.
    Morbi finibus sed elit tincidunt laoreet. Etiam elementum malesuada nisl ut sodales.
    Vestibulum tristique pharetra fringilla.
</span>
Cras sem lorem, accumsan
eget placerat ac, hendrerit sit amet erat. Nam consequat vehicula nibh. Vivamus nec
egestas est. Aliquam erat volutpat. Suspendisse potenti. </p>
</div>


Table-cell
==========
`table-cell`-on elementtityyppi, joka on tarkoitettu taulukon soluille (`<td>` ja `<th>`).
Se käyttäytyy hieman muista poikkeavalla tavalla, "taulukkomaisemmin".

None
====
Elementin `display`-ominaisuudelle voi lisäksi antaa arvon `none`, joka tarkoittaa, että kyseistä
elementtiä ei näytetä sivulla lainkaan. Tätä käyttämällä voidaan dynaamisesti muotoiltavalla sivustolla
osa sisällöstä piilottaa tai näyttää tarpeen mukaan.

Muut arvot
==========
Lisäksi `display`-ominaisuudelle on myös muita arvoja, joihin voi tutustua
vaikka [W3Schoolsin sivulla][Display]. Näistä CSS3:n mukana tullut mielenkiintoinen uusi
vaihtoehto on `flex`, johon voi tutustua esimerkiksi [CSS-Tricks][Complete Flex]-sivustolla.
Sitä voi käyttää esimerkiksi sivun palstoitukseen tai navigointipalkkien rakentamiseen.

Display ja visibility
==========
Elementin voi piilottaa asettamalla sen `display`-ominaisuuden arvoksi `none`, mutta tällöin
elementti poistetaan kokonaan pois näkyvistä ja sen koko on käytännössä nolla joka suuntaan.
Toisinaan kuitenkin halutaan piilottaa vain elementin sisältö, mutta halutaan, että se silti
vie sivulta oman kokonsa verran "tyhjää" tilaa. Tällöin kannattaa käyttää ominaisuutta
`visibility` ja antaa sille arvoksi `hidden`. Elementin saa takaisin näkyviin arvolla
`visible`.

```
<div style="background-color: #ffa;">
    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.<p>
    <p style="visibility: hidden;">Donec quis risus non velit imperdiet laoreet. Nulla molestie a ante id pharetra.<p>
    <p>Morbi finibus sed elit tincidunt laoreet. Etiam elementum malesuada nisl ut sodales.</p>
</div>
```
<div class="html-example">
<div style="background-color: #ffa;">
    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.<p>
    <p style="visibility: hidden;">Donec quis risus non velit imperdiet laoreet. Nulla molestie a ante id pharetra.<p>
    <p>Morbi finibus sed elit tincidunt laoreet. Etiam elementum malesuada nisl ut sodales.</p>
</div>
</div>


[Display]: http://www.w3schools.com/cssref/pr_class_display.asp "W3Schools:Display"
[Complete Flex]: https://css-tricks.com/snippets/css/a-guide-to-flexbox/ "A Complete Guide to Flexbox"