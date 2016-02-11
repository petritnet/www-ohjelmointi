+++
date = "2016-01-06T15:44:45+02:00"
title = "Valitsimet"
weight = 2

+++

Tyylisäännössä on yleisesti kaksi osaa:

* __Valitsin__ (selector), joka määrää, mitä elementtejä sääntö koskee.
* __Määrittelyosa__ (declaration block), joukko määrittelyitä (declaration), joilla kerrotaan eri ominaisuuksille arvoja.

Valitsin on yhdistelmä seuraavia:

* Tagin nimi: `h1`, `p`, `span`, `div`,...
* Elementin id: `#header`, `#menu`, `#panel`
* Elementin luokka (class): `.navi`, `.address`
* Pseudo-luokka: `:hover`, `:visited`, `:first-child`,...
* Pseudo-elementti: `::begin`, `::after`, `::first-letter`,...
* Attribuutit: `[title]`, `[target="_blank"]`, `[data-order="4"]`,...

Valitsin on ikäänkuin polku halutulle elementille. Valitsin valitsee kaikki ne HTML-dokumentin
elementit, jotka täyttävät valitsimen asettamat ehdot.

```css
div.asia p.peruskappale span a {
    ... Määrittelyt ...
}
```
Yllä oleva valitsin <code><span style="color: blue;">div.asia</span> <span style="color: red;">p.peruskappale</span> <span style="color: green;">span</span> <span style="color: brown;">a</span></code>
määrittelee tyylisääntöjä kaikille linkeille (`<a>`), jotka ovat `<span>`-tagin sisällä, joka on puolestaan kappaleessa `<p>`, jolla on luokkana (`class`-attribuutti) `peruskappale`, ja joka on
sellaisen `<div>`-tagin sisällä, jolla on luokkana `asia`.

<figure>
<svg xmlns="http://www.w3.org/2000/svg" version="1.1" width="500" height="170" viewBox="0 0 500 170" class="chart">
    <rect stroke="blue" stroke-width="2" fill="none" x="2" y="2" width="400" height="150"></rect>
    <rect stroke="red" stroke-width="2" fill="none" x="10" y="40" width="380" height="100"></rect>
    <rect stroke="green" stroke-width="2" fill="none" x="40" y="80" width="300" height="40"></rect>
    <rect stroke="brown" stroke-width="2" fill="none" x="100" y="85" width="100" height="30"></rect>
    <text x="5" y="20" style="font-family: monospace; font-size: 16px; font-weight: bold; fill: blue;">&lt;div class=&quot;asia&quot;&gt;</text>
    <text x="15" y="65" style="font-family: monospace; font-size: 16px; font-weight: bold; fill: red;">&lt;p class=&quot;peruskappale&quot;&gt;</text>
    <text x="43" y="100" style="font-family: monospace; font-size: 16px; font-weight: bold; fill: green;">&lt;a&gt;</text>
    <text x="110" y="100" style="font-family: monospace; font-size: 16px; font-weight: bold; fill: brown;">&lt;span&gt;</text>
</svg>
</figure>

Esimerkki-HTML:
```
<section>
    <div class="asia">
        <p>Kappale, jossa tekstiä.</p>
        <p>Kappale, jossa myös <a href="#">linkki, jossa <span>tekstiä</span></a>.</p>
        <p class="peruskappale">Kappale, jossa myös <a href="#">linkki, jossa <span>tekstiä</span></a>.</p>
        <p>Kappale, jossa myös <a href="#">linkki ja <span>span</span></a>, mutta ei oikeaa luokkaa.</p>
        <p>Lisää tekstiä.</p>
        <p class="peruskappale">Toinen <a href="#">linkki <span>osuvalla tekstillä</span></a>.</p>
    </div>
</section>
```
Esimerkki-CSS:
```css
div.asia p.peruskappale a span {
    color: red;
}
```

Lopputulos:
<div class="html-example">
<section>
    <div class="asia">
        <p>Kappale, jossa tekstiä.</p>
        <p>Kappale, jossa myös <a href="#">linkki, jossa <span>tekstiä</span></a>.</p>
        <p class="peruskappale">Kappale, jossa myös <a href="#">linkki, jossa <span style="color: red;">tekstiä</span></a>.</p>
        <p>Kappale, jossa myös <a href="#">linkki ja <span>span</span></a>, mutta ei oikeaa luokkaa.</p>
        <p>Lisää tekstiä.</p>
        <p class="peruskappale">Toinen <a href="#">linkki <span style="color: red;">osuvalla tekstillä</span></a>.</p>
    </div>
</section>
</div>

Valitsimia voi yhdistellä (saman HTML-tagin useita ominaisuuksia) sekä luetella (useammalla valitsimella yhteiset säännöt).

```css
h1 {
    /* tagi */
    color: red;
}

h1#otsikko {
    /* tagi ja id */
    color: blue;
}

.address {
    /* luokka (class) */
    font-style: italic;
}

li:first-child, li:last-child {
    /* kaksi valitsinta pilkulla lueteltuna */
    text-decoration: underline;
}

a::before {
    /* tagi ja sen pseudoelementti */
    content: "Linkki: ";
}

a.nav[title="etusivu"]:hover {
    /* tagi, sen luokka, attribuutti sekä sen arvo ja hiiri tagin päällä */
    color: red;
}
```

Tyylisääntöjen tärkeysjärjestys
===============================
CSS:n nimi, Cascading Style Sheets, tulee siitä, että samalle HTML-elementille voi olla
määrätty ominaisuuksia useilla tyylisäännöillä, jotka "limittyvät" keskenään.

Jos säännöt ovat ristiriidassa, jää tarkin sääntö voimaan:

* Inline-sääntö, eli suoraan HTML-tagiin `style`-attribuutilla kirjoitettu
    sääntö yliajaa `<style>`-tagilla annetut tai ulkoisessa tiedostossa
    määritellyt säännöt.
* Tarkemmalla valitsimella määrätty sääntö on tärkeämpi
    * `id` on vahvempi kuin luokka, pseudoluokka tai attribuutti, jotka taas ovat
        vahvempia kuin tagi tai pseudoelementti.
* Myöhempi sääntö "peittää" aiemman saman arvoisen säännön.