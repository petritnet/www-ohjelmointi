+++
Categories = []
Description = ""
Tags = []
Title = "HTML-dokumentin käsittely"
date = "2016-03-10T00:13:06+02:00"
weight = 110

+++

Javascriptin `document`-elementiltä löytyvät kaikki tarvittavat metodit
DOM-puun manipulointiin.

Elementtien etsiminen
=====================

Dokumenttipuusta voi etsiä haluamaansa HTML-elementtiä useammalla tavalla.
Jos puun rakenne on tiedossa, sitä pitkin voi edeta elementistä toiseen
`children`- ja `parentElement`-ominaisuuksia käyttämällä. HTML-elementin
`children` on aina taulukon kaltaisena objekti, jossa ovat kyseisen
elementin lapsielementit. Halutun lapsen voi valita hakasulkumerkintää
ja indeksinumeroa käyttämällä.
Elementin `parentElement` puolestaan on aina kyseisen HTML-elementin vanhempana
oleva elementti.

```javascript
var element = document.body.children[2];        // <body>-elementin kolmas lapsielementti
element.parentElement;                          // <body>-elementti
```

Usein ei kuitenkaan ole järkevää yrittää edetä puuta juuresta lähtien askel kerrallaan
vaan on kannattavampaa yrittää etsiä haluttu elementti suoraan esimerkiksi `id`-attribuutin,
tagin nimen taikka luokan perusteella. Näitä varten `document`-objektissa, ja kaikissa
muissa HTML-elementtiobjekteissa, on joukko metodeja, jotka palauttavat tyypillisesti
joko yhden HTML-elementin tai useamman elementin taulukkoa muistuttavina `HTMLCollection`-
ja `NodeList`-objekteina.

Nämä metodit etsivät halutun kaltaisia elementtejä metodin kutsumiseen käytetyn elementin lapsista.

| Metodi                    | Tehtävä                                                         | Esimerkki                                         | Palauttaa       |
|---------------------------|-----------------------------------------------------------------|---------------------------------------------------|-----------------|
|`getElementById()`         | Etsi sellainen, jonka `id` on pyydetty.                         |`var menu = document.getElementById('menu')`       | HTML-elementti  |
|`getElementsByTagName()`   | Etsi kaikki pyydetyt tagit.                                     |`var form = document.getElementsByTagName('form')` | HTMLCollection  |
|`getElementsByClassName()` | Etsi kaikki kysyttyä luokkaa olevat.                            |`menu.getElementsByClassName('current')`           | HTMLCollection  |
|`getElementsByName()`      | Etsi `name`-attribuutilla.                                      |`document.getElementsByName('osoite')`             | NodeList        |
|`querySelector()`          | Etsi ensimmäinen, joka vastaa annettua CSS-valitsinta.          |`menu.querySelector('.current')`                   | HTML-elementti / null  |
|`querySelectorAll()`       | Etsi kaikki, jotka vastaavat annettua CSS-valitsinta.           |`content.querySelectorAll('p a[target="_blank"]')` | NodeList        |

Elementtien attribuutit
=======================

Kun HTML-elementti on saatu etsittyä objektina, sen attribuutteja voidaan tutkia ja muokata
käyttämällä sen `getAttribute()`- ja `setAttribute()`-metodeja.

```html
<!DOCTYPE html>
<html>
    <head lang="fi-fi">
        <title>Otsikko</title>
        <meta charset="utf-8">
        <style>
            h1 {color: red;}
        </style>
    </head>
    <body id="etusivu" class="sivu maanantai">
        <header> ... </header>
        <nav> ... </nav>
        <aside class="sivujuttu"> ... </aside>
        <article> ... </article>
        <footer> ... </footer>
    </body>
</html>
```
```javascript
var body = document.body;
var id = body.getAttribute('id');                // "etusivu"
var luokat = body.getAttribute('class');         // "sivu maanantai"
body.setAttribute('id', 'takasivu');
var kieli = document.head.getAttribute('lang');  // 'fi-fi'
```

Elementin `class`-attribuutti löytyy lisäksi merkkijonona elementin ominaisuudesta `className`.
Elementin `class`-attribuutissa määritellyt luokat ovat lisäksi käsiteltävissä elementin
ominaisuudessa `classList`, johon voi lisätä luokkia `add()`-metodilla, poistaa niitä `remove()`-metodilla
sekä nykyisen tilanteen mukan lisätä tai poistaa `toggle()`-metodilla. `toggle()` palauttaa samalla
totuusarvon sen mukaan, lisättiinkö (`true`) vai poistettiinko (`false`) luokka.

Lisäksi `classList`-ominaisuudella on metodi `contains()`, jolla voi tarkistaa, onko elementillä
kysytty luokka. Metodi palauttaa totuusarvon.

```javascript
var body = document.body;
body.className;                   // "sivu maanantai"
body.classList;                   // DOMToken [ "sivu", "maanantai" ]
body.classList.add('testi');      // body.className = "sivu maanantai testi"
body.classList.remove('sivu');    // body.className = "maanantai testi"
body.classList.toggle('sivu');    // true, body.className = "sivu maanantai testi"
body.classList.contains('testi'); // true
```


Elementin sisältö
=================

Käsillä olevan HTML-elementin HTML-muotoisen tekstisisältöä voi tutkia ja muokata
sen ominaisuudella `innerHTML`. Tämä ominaisuus sisältää elementin sisällä olevan
HTML-teksti merkkijonona. `innerHTML`-merkkijonon muuttaminen muuttaa kyseisen
elementin sisällön.

```html
...
<div id="sisalto">
    <p>Lorem ipsum <span>sit dolor</span> amet</p>
</div>
...
```
```javascript
var sisus = document.getElementById('sisalto');
sisus.innerHTML;                            // "    <p>Lorem ipsum <span>sit dolor</span> amet</p>"
var sisempi = sisus.querySelector('span');
sisempi.innerHTML;                          // "sit dolor"
sisempi.innerHTML = "SIT DOLOR";
sisus.innerHTML;                            // "    <p>Lorem ipsum <span>SIT DOLOR</span> amet</p>"
```

Samaan tapaan toimii eleemntin `outerHTML`-ominaisuus, mutta se on merkkijono, joka sisältää
myös elementin oman tagin.

```javascript
sisus.outerHTML;
// "<div id="sisalto">
//     <p>Lorem ipsum <span>sit dolor</span> amet</p>
//  </div>"
```

Luonti, lisääminen ja poisto
========================================

HTML-dokumentin sisältöä voi muokata syöttämällä merkkijonona HTML-kieltä suoraan
jonkin HTML-elementin sisällöksi `innerHTML`-ominaisuuden kautta. Usein on kuitenkin
hyödyllistä hieman hienovaraisemmin vain lisätä tai poistaa yksittäisiä elementtejä.

Uuden elementin voi luoda `document`-objektin `createElement()`-metodilla. Luonnin
jälkeen uudelle elementille voidaan antaa halutut attribuutit ja sisältö.

```javascript
var skripti = document.createElement('script');
skripti.setAttribute('type', 'text/javascript');
skripti.setAttribute('src', 'http://petrit.net/www-kurssi/skriptit/omaskripti.js');

var otsikko = document.createElement('h1);
otsikko.setAttribute('class', 'paaotsikko important');
otsikko.innerHTML = 'Otsikon teksti';
```

Lopuksi uusi elementti lisätään DOM-puuhun haluttuun kohtaan. Lisätään edellä
luotu `skripti`-muuttujaan tallennettu `<script>`-elementti dokumentin `<head>`-osion
viimeiseksi ja lisätään `otsikko`-muuttujaan tallennettu `<h1>`-elementti `<body>`-osioon
ensimmäiseksi (ennen nykyistä ensimmäistä elementtiä).

```javascript
document.head.appendChild(skripti);

var body = document.body;
var eka = body.children[0];
body.insertBefore(otsikko, eka);
```

HTML-elementin voi poistaa DOM-puusta `remove()`-metodilla.

```javascript
var sisalto = document.querySelector('#sisalto');
sisalto.remove();
```