+++
Categories = []
Description = ""
Tags = []
Title = "jQuery"
date = "2016-03-14T22:35:44+02:00"
weight = 130

+++

Javascript-ohjelmien yhteydessä käytetään usein joitain valmiita kirjastoja,
joita käyttämällä saa käyttöön "puhtaasta" Javascriptistä puuttuvia toiminnallisuuksia,
joita ei tarvitse itse toteuttaa. Tyypillisesti ne paketoivat puhtaassa Javascriptissä
olevia ominaisuuksia helpommin käytettävään muotoon.

Ehkä suosituin tällainen kirjasto on [jQuery][jQuery], jota käytetään nykyisin lähes
sivustolla kuin sivustolla. Joitain jQuerysta tuttuja ominaisuuksia, kuten HTML-elementtien
etsiminen CSS:stä tutuilla valitsimilla, on tuotu sittemmin myös puhtaaseen Javascriptiin.

jQueryn ominaisuuksia:

- HTML-dokumentin elementtien etsiminen
- HTML-dokumentin sisällön muokkaaminen
- Tapahtumien hallinta helposti, tehokkaasti ja turvallisesti
- Animointia
- Ajax-kutsuja palvelimelle helposti
- Toimii samoin eri selaimissa
- Laajennettavissa plugin-lisäosilla
- Avoimen lähdekoodin [MIT-lisenssi][MIT].

jQuery-objekti
==============

jQueryssa keskeisessä asemassa ovat jQuery-objektit. Ne ovat taulukon (Array) kaltaisia
objekteja, jotka sisältävät HTML-elementtejä listana ja jolla voidaan esimerkiksi
manipuloida näitä HTML-elementtejä. jQuery-objektit talletetaan usein muuttujiin,
joiden nimi aloitetaan `$`-merkillä. Tämä ei ole pakollista, mutta tämä on yleensä
hyvä käytäntö. Tällöin ohjelmakoodista on helppo nähdä, että kyseisessä muuttujassa
on tarkoitus olla jQuery-objekti.

jQuery-objekteja luodaan `jQuery()`-funktiolla tai sen lyhennysmerkinnällä `$()`.

HTML-elementtien valinta
========================

HTML-elementtejä voidaan valita DOM-puusta käsiteltäväksi jQuerylla käyttämällä
CSS-valitsimia ja `jQuery()`-funktiota. Tämä etsii koko dokumentista kaikki
valitsimeen täsmäävät HTML-elementit ja palauttaa ne jQuery-objektina.

Esimerkiksi:
```html
<!DOCTYPE html>
<html>
    <head>
        <script src="https://code.jquery.com/jquery-2.1.4.js"></script>
    </head>
    <body>
        <article>
            <h1>Pääotsikko</h1>
            <p class="ekakappale">Lorem ipsum <span>dolor sit</span> amet...</p>
            <p>Toinen kappale</p>
            <h2 id="alaotsikko">Alaotsikko 1</h2>
            <p class="ekakappale">Lorem ipsum dolor sit <span>amet...</span></p>
        </article>
    </body>
</html>
```
```javascript
var $otsikko = $('h1'),
    $kappaleet = $('p'),
    $juttu = $('article'),
    $ala = $('#alaotsikko'),
    $ekat = $('.ekakappale');
```
<div class="html-example">
    <article>
        <h1>Pääotsikko</h1>
        <p class="ekakappale">Lorem ipsum <span>dolor sit</span> amet...</p>
        <p>Toinen kappale</p>
        <h2 id="alaotsikko">Alaotsikko 1</h2>
        <p class="ekakappale">Lorem ipsum dolor sit <span>amet...</span></p>
    </article>
</div>

jQuery-objektit ovat saman kaltaisia kuin taulukot, joten niiltä voi kysyä pituuden
ominaisuudella `length`. Tämä kertoo siis, montako HTML-elementtiä kyseisessä jQuery-objektissa
on.

```javascript
$otsikko.length;            // 1
$kappaleet.length;          // 3
$juttu.length;              // 1
$ala.length;                // 1
$ekat.length;               // 2
```

Jo olemassa olevan jQuery-objektin sisältä voidaan hakea edelleen muita elementtejä.
jQuery-objektilla ovat käytettävissä muun muassa metodit `.find()` ja `.children()`.
Näille molemmille voidaan antaa parametriksi CSS-valitsin. Metodi `.find()` etsii
jQuery-objektin sisältä valitsimen mukaisia HTML-elementtejä. `.children()` puolestaan
rajoittaa haun koskemaan vain jQuery-objektin lapsia.

```javascript
var $sp1 = $juttu.find('span');                  // $sp1.length === 2
var $sp2 = $juttu.find('.ekakappale span');      // $sp2.length === 1
var $hh1 = $juttu.children('h1');                // $hh1.length === 1
var $hh2 = $juttu.find('> h1');                  // $hh2.length === 1
```

Vastaavasti jQuery-objektissa olevalle HTML-elementille voidaan etsiä vanhempia
metodeilla `.parent()` (elementin välitön vanhempi), `.parents()` (elementin vanhemmat välittömästä vanhemmasta
`<html>`-elementtiin) ja `.closest()` (lähin ehdon täyttävä vanhempi). Myös näitä hakuja voidaan
rajoittaa käyttämällä CSS-valitsimia.

```javascript
$otsikko.parent();                // <article>
$otsikko.parents();               // <article>, <body>, <html>
$sp2.parents('article');          // <article>
$sp2.closest('article, p, div');  // <p>
```

Sisällön muokkaaminen
=====================

jQuery-objektiin talletettuihin HTML-elementteihin pääsee käsiksi `[]`-merkinnällä, kuten
tavallisissa taulukoissa.

```javascript
$kappaleet[1].innerHTML;       // "Toinen kappale"
$juttu[0].innerHTML;
//"
//            <h1>Pääotsikko</h1>
//            <p class=\"ekakappale\">Lorem ipsum dolor sit amet...</p>
//            <p>Toinen kappale</p>
//            <h2 id=\"alaotsikko\">Alaotsikko 1</h2>
//            <p class=\"ekakappale\">Lorem ipsum dolor sit amet...</p>
//        "
```

Toisaalta, jos halutaan käsitellä vain yhtä löydetyistä elementeistä, on usein
hyödyllisempää käsitellä sitä jQuery-objektina, jossa on vain yksi elementti.
jQuery-objektin `n`:nnen alkion voi valita `.eq()`-metodilla. jQuery-objektiin
talletetuista HTML-elementeistä ensimmäisen HTML-koodiin pääsee puolestaan käsiksi
metodilla `.html()`. Ilman parametreja se palauttaa elementin sisällön samoin kuin
`innerHTML` puhtaan Javascriptin HTML-elementillä.

```javascript
$kappaleet.eq(1).html();       // "Toinen kappale"
$juttu.html();
//"
//            <h1>Pääotsikko</h1>
//            <p class=\"ekakappale\">Lorem ipsum dolor sit amet...</p>
//            <p>Toinen kappale</p>
//            <h2 id=\"alaotsikko\">Alaotsikko 1</h2>
//            <p class=\"ekakappale\">Lorem ipsum dolor sit amet...</p>
//        "
```

Jos `.html()`-metodille annetaan parametrina merkkijono, tämä sijoitetaan
HTML-tekstinä kyseisen elementin sisään. Siis samaan tapaan kuin sijoittamalla
merkkijono puhtaan Javascriptin HTML-elementin `innerHTML`-ominaisuuteen.
Elementin sisällön voi puolestaan tyhjentää `.empty()`-metodilla.

```javascript
$ala.html('Uusi alaotsikko');
$otsikko.empty();
$kappaleet.html('Kappaleiden uusi sisältö');
```
<div class="html-example">
    <article>
        <h1></h1>
        <p class="ekakappale">Kappaleiden uusi sisältö</p>
        <p>Kappaleiden uusi sisältö</p>
        <h2 id="alaotsikko">Uusi alaotsikko</h2>
        <p class="ekakappale">Kappaleiden uusi sisältö</p>
    </article>
</div>

jQuerylla voi myös luoda uusia elementtejä ilman, että niitä sijoitetaan
mihinkään kohtaan DOM-puuta.

```javascript
var $elementti = $('<div class="punainen">Lorem ipsum <span>dolor sit</span> amet</div>');
$elementti.find('span');           // <span>
$elementti.parent();               // Tyhjä jQuery-objekti (.length === 0)
```

Muuttujassa olevan jQuery-objektin tai merkkijonona annetun HTML-tekstin
voi sijoittaa haluamaansa kohtaan DOM-puuta.
Sijoituspaikka voidaan määrätä suhteessa toiseen jQuery-objektiin seuraavilla
metodeilla:

- `.before()` – Sijoitetaan DOM-puuhun tämän elementin edelle
- `.after()` – Sijoitetaan DOM-puuhun tämän elementin jälkeen
- `.append()` – Sijoitetaan DOM-puuhun tämän elementin sisään viimeisen lapsen jälkeen
- `.prepend()` – Sijoitetaan DOM-puuhun tämän elementin sisään ensimmäiseksi lapseksi
- `.html()` – Sijoitetaan DOM-puuhun tämän elementin ainoaksi sisällöksi

```javascript
var $headeri = $('<header><h1>Yläotsikko</h1></header>');   // Luodaan uusi <header>-elementti
$juttu.after('<article>Toinen juttu</article>');            // Lisätään <article>:n jälkeen toinen
$juttu.before($headeri);                                    // Lisätään luotu <header> ennen ensimmäistä <article>:a
$juttu.append($elementti);                                  // Lisätään $elementti <article>:n sisään loppuun
$juttu.prepend('<p>Yläteksti</p>');                         // Lisätään uusi kappale <article>:n sisään alkuun
$sp2.html('<strong>Tärkeää</strong>');                      // Korvataan $sp2:n sisältö lihavoidulla tekstillä
```

```html
<!DOCTYPE html>
<html>
    <head>
        <script src="https://code.jquery.com/jquery-2.1.4.js"></script>
    </head>
    <body>
        <header><h1>Yläotsikko</h1></header>
        <article>
            <p>Yläteksti</p>
            <h1>Pääotsikko</h1>
            <p class="ekakappale">Lorem ipsum <span>dolor sit</span> amet...</p>
            <p>Toinen kappale</p>
            <h2 id="alaotsikko">Alaotsikko 1</h2>
            <p class="ekakappale">Lorem ipsum dolor sit <span><strong>Tärkeää</strong></span></p>
            <div class="punainen">Lorem ipsum <span>dolor sit</span> amet</div>
        </article>
        <article>Toinen juttu</article>
    </body>
</html>
```

<div class="html-example">
    <header><h1>Yläotsikko</h1></header>
    <article>
        <p>Yläteksti</p>
        <h1>Pääotsikko</h1>
        <p class="ekakappale">Lorem ipsum <span>dolor sit</span> amet...</p>
        <p>Toinen kappale</p>
        <h2 id="alaotsikko">Alaotsikko 1</h2>
        <p class="ekakappale">Lorem ipsum dolor sit <span><strong>Tärkeää</strong></span></p>
        <div class="punainen">Lorem ipsum <span>dolor sit</span> amet</div>
    </article>
    <article>Toinen juttu</article>
</div>

Attribuuttien muokkaaminen
==========================

jQuerylla voi muokata myös HTML-elementtien attribuutteja. Luokkien ja muiden attribuuttien käsittelyyn
käytettäviä metodeita ovat:

- `.addClass('luokka')` – Lisää elementille luokan `luokka`
- `.removeClass('luokka')` – Poistaa elementiltä luokan `luokka`
- `.toggleClass('luokka')` – Jos elementillä on luokka `luokka`, se poistetaan, muuten se lisätään
- `.hasClass('luokka')` – Palauttaa `true`, jos elementillä on luokka `luokka`, muuten `false`
- `.attr('avain')` – Palauttaa elementin attribuutin `avain` arvon
- `.attr('avain', 'arvo')` – Asettaa elementin attribuutin `avain` arvoksi tekstin `arvo`

Esimerkiksi luokan lisäämisellä, poistamisella tai vaihtamisella voidaan helposti vaihtaa elementin
ulkoasu seuraamaan eri CSS-sääntöjä. Tätä voidaan käyttää esimerkiksi elementin piilottamiseen ja näyttämiseen.
Jos CSS-säännöissä on määritelty `transition`-ominaisuuksia tai muita animointeja, näillä saadaan
muutoksiin lisää näyttävyyttä.

```javascript
$juttu.addClass('tarina');                  // Lisää luokan 'tarina'
$ekat.eq(1).removeClass('ekakappale');      // Poistaa toiselta alkiolta luokan 'ekakappale'
$('div').toggle('punainen');                // Vaihtaa kaikilta <div>-elementeiltä luokan 'punainen' päälle tai pois
$('#alaotsikko').attr('id');                // 'alaotsikko'
$juttu.attr('title', 'Juttu');              // Asettaa <article>:n title-attribuutiksi tekstin 'Juttu'
```

Efektit
=======
Elementeille voidaan myös tehdä joitakin efektejä, joita ovat esimerkiksi:

- `.show()` – Näytetään piilossa ollut elementti
- `.hide()` – Piilotetaan näkyvissä ollut elementti
- `.toggle()` – Vaihdetaan näyttö-/piilotustilaa
- `.slideDown()` – Näytetään piilossa ollut elementti animoimalla se "auki"
- `.slideUp()` – Piilotetaan elementti animoimalla se "kiinni"
- `.slideToggle()` – Näytetään tai piilotetaan elementti animoimalla

Monet efektit on nykyään kuitenkin selkeämpää ja monipuolisempaa toteuttaa sopivilla
CSS-säännöillä (`transition`-ominaisuuksilla) ja lisäämällä tai poistamalla luokkia.

Lisää efekteistä [jQueryn dokumentaatiosta][jQuery-effects].

Tapahtumat jQuerylla
====================

Tapahtumakäsittelijöiden lisääminen jQuerylla on helppoa. Lisäksi siitä on pyritty tekemään
muistivuotojen kannalta turvallisempi kuin puhtaalla Javascriptillä luoduista käsittelijöistä.

jQuery-objektiin valituille HTML-elementeille lisätään tapahtumakäsittelijä metodilla `.on()`.
Metodille annetaan parametreina tapahtuman nimi sekä sen käsittelevä funktio.

```javascript
$otsikko.on('click', function(event){
    alert('Moikka');
});
```

jQueryn vahvoja puolia on mahdollisuus tapahtumakäsittelyn "delegointiin". Tämä tarkoittaa sitä,
että jokin ulompi elementti käsittelee tapahtuman sen sisällä olevan, CSS-säännöllä valitun, elementin
puolesta. Tapahtumat käsitellään kuitenkin aivan kuin ne tapahtuisivat valitulle elementille.
Tämä eroaa edellisestä esimerkistä sillä, että `.on()`-metodille annetaan lisäksi parametrina
CSS-valitsin. Käsittelijässä tapahtuman laukaisseen elementtiin voi viitata jQuery-objektilla
`$(this)`.

```javascript
$juttu.on('mouseenter', 'strong', function(event){
    $(this).css('color', 'red');
});
$juttu.on('mouseleave', 'strong', function(event){
    $(this).css('color', '');
});
```

<div class="html-example" id="tapahtumaesimerkki">
    <script src="https://code.jquery.com/jquery-1.11.3.js"></script>
    <header><h1>Yläotsikko</h1></header>
    <article>
        <p>Yläteksti</p>
        <h1>Pääotsikko</h1>
        <p class="ekakappale">Lorem ipsum <span>dolor sit</span> amet...</p>
        <p>Toinen kappale</p>
        <h2 id="alaotsikko">Alaotsikko 1</h2>
        <p class="ekakappale">Lorem ipsum dolor sit <span><strong>Tärkeää</strong></span></p>
        <div class="punainen">Lorem ipsum <span>dolor sit</span> amet</div>
    </article>
    <article>Toinen juttu</article>
    <script type="text/javascript">
    $('#tapahtumaesimerkki h1').on('click', function(event){
        alert('Moikka');
    });
    $('#tapahtumaesimerkki article').on('mouseenter', 'strong', function(event){
        $(this).css('color', 'red');
    });
    $('#tapahtumaesimerkki article').on('mouseleave', 'strong', function(event){
        $(this).css('color', '');
    });
    </script>
</div>

Delegoinnin vahvuus on siinä, että koska tapahtumakäsittelijää ei ole sidottu suoraan tapahtuman
laukaisevaan elementtiin, voidaan vastaavia elementtejä poistaa ja lisätä dynaamisesti ilman, että
tapahtumankäsittelijää tarvitsee joka kerta uudelleen lisätä ja poistaa.

jQuerylla lisätyn käsittelijän käsittelemän tapahtuman ei tarvitse olla standardi Javascript-tapahtuma
vaan ohjelmoija voi luoda omia tapahtumatyyppejä keksimällä niille omat nimet. Itsekeksittyjä sekä
standardeja tapahtumia voi laukaista haluttuun elementtiin metodilla `.trigger()`.

```javascript
$juttu.on('aloitus', 'h1', function(event){
    alert('alkoi');
});

$otsikko.trigger('aloitus');
```

Tapahtumille voidaan `.trigger()`-metodilla antaa myös parametreja, jotka välitetään käsittelijäfunktiolle.
Parametrit annetaan taulukkona.

```javascript
$juttu.on('aloitus', 'h1', function(event, nimi, teksti){
    alert('Heippa, ' + nimi + '!\n' + teksti);
});

$otsikko.trigger('aloitus', ['Petri', 'Hyvää päivää.']);
```

jQuerylla lisätyn tapahtumankäsittelijän voi poistaa metodilla `.off()`.

```javascript
$otsikko.off('click');
$juttu.off('mouseenter', 'strong');
$juttu.off('mouseleave', 'strong');
```


Ajax
====
jQuery sisältää myös puhdasta Javascriptiä yksinkertaisemman ja selkeämmän tavan lähettää
taustalla pyyntöjä ja dataa palvelimelle. Näistä voi lukea lisää tarkemmin [jQueryn omilta sivuilta][jQuery-ajax].



Lisäosat
========

jQuery on rakennettu laajennettavaksi. Siihen löytyy lukematon määrä erilaisia lisäosia, joista osa laajentaa itse
jQueryn toimintaa ja osa on niille annetun HTML-elementin sisällä toimivia websovelluksia. Jälkimmäisestä tyypistä
ovat esimerkkejä vaikkapa lukuisat WYSIWYG-editorit, kalenterisovellukset ja kuvagalleriat.

jQuery-lisäosia voi selata vaikka [jQuery-plugins.net][jQuery-plugins]-sivustolla.


[jQuery-harjoituksia Codecademyssa][jQuery-Codecademy]

[jQuery]: http://jquery.com/ "jQuery"
[MIT]: https://tldrlegal.com/license/mit-license "MIT-lisenssi"
[jQuery-Codecademy]: https://www.codecademy.com/learn/jquery
[jQuery-ajax]: http://api.jquery.com/category/ajax/ "jQuery + Ajax"
[jQuery-plugins]: http://jquery-plugins.net/ "jQuery-plugins"
[jQuery-effects]: http://api.jquery.com/category/effects/ "jQuery-effects"
[jQuery_vs_js]: http://jsfiddle.net/QdMc5/ "Esimerkki"
