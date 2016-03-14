+++
Categories = []
Description = ""
Tags = []
Title = "Dokumentti"
date = "2016-03-10T00:13:06+02:00"
weight = 100

+++

Javascriptin käyttö www-sivuilla pyrkii yleensä saamaan aikaiseksi
myös jotain sivun käyttäjälle näkyvää. Toisin sanoen Javascript-ohjelmalla
pitää pystyä muokkaamaan selaimessa näytettävää dokumenttia jollain tavalla.

Tätä varten selainikkuna (tai välilehti) sekä ikkunassa näytettävä
dokumentti ovat edustettuina ohjelmaa suorittavassa Javascript-ympäristössä
omina objekteinaan: `window` ja `document`. 

`window`-objekti
================

Ikkunaa edustava `window`-objekti on selaimessa suoritettavan Javascriptin
*globaali objekti*, eli objekti, jonka ominaisuutena kaikki globaalit muuttujat
ovat. Siis, mikä tahansa kaikkien funktioiden ulkopuolella luotu muuttuja,
eli globaali muuttuja, ilmestyy `window`-objektin ominaisuudeksi. Tai päin vastoin,
jos `window`-objektiin luodaan uusi ominaisuus, siitä tulee globaali muuttuja, joka
on käytettävissä kaikkialla, missä sitä ei ole "peitetty" saman nimisellä lokaalilla
muuttujalla.


`document`-objekti
===================

Objekti nimeltä `document` edustaa koko selaimeen ladattua dokumenttia ja sen kautta
Javascriptillä pääsee tutkimaan ja muokkaamaan mitä tahansa kohtaa dokumentista.
[HTML DOM (Document Object Model)][DOM] tarkoittaa puurakennetta, joka mallintaa
HTML-dokumentin Javascript-objektiksi. Tätä objektia muokkaamalla Javascript-ohjelma
voi:

- muokata sivun HTML-elementtejä,
- muokata sivun HTML-elementtien attribuutteja,
- muokata sivun CSS-tyyliä,
- poistaa HTML-elementtejä ja attribuutteja,
- lisätä HTML-elementtejä ja attribuutteja
- reagoida sivulla tapahtuviin tapahtumiin,
- luoda uusia tapahtumia sivulle.

Itse `document`-objekti on DOM-puun juuri, jonka ominaisuutena ovat dokumentin
`head`- ja `body`-elementtejä edustavat objektit sekä niiden lapsina ja lastenlapsina
edelleen kaikki sivulla olevat HTML-elementit. Lisäksi `document` ja sekä jälkeläiset
sisältävät joukon metodeja, joilla voi etsiä, muokata, luoda ja poistaa HTML-elementtejä
DOM-puussa.

Esimerkiksi:
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
document.documentElement;              // <html lang="fi-fi">     (<html>-elementti objektina)
document.head;                         // <head>                  (<head>-elementti objektina)
document.body;                         // <body>                  (<body>-elementti objektina)
document.head.children;                // HTMLCollection [<title>, <meta>, <style>]
                                       // Arrayn kaltainen objekti, jossa <head>-elementin lapset
document.head.children.length;         // 3
document.body.children.length;         // 5
document.body.attributes;              // NamedNodeMap [ id="etusivu", class="sivu maanantai" ]
                                       // Arrayn kaltainen objekti, jossa objekteja, joilla 'name'- ja 'value'-ominaisuudet
document.body.className;               // "sivu maanantai"        (class-attribuutin arvo merkkijonona)
document.body.classList;               // ["sivu", "maananatai"]  (class-attribuutissa luetellut luokat taulukkona)
```


[DOM]: http://www.w3schools.com/js/js_htmldom.asp "W3Schools:DOM"