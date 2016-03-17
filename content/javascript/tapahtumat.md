+++
Categories = []
Description = ""
Tags = []
Title = "Tapahtumat"
date = "2016-03-10T00:14:21+02:00"
weight = 120

+++

Ikkunoiduissa, hiirellä ja näppäimistöllä ohjatuissa käyttöliittymissä
tyypillistä on, että suurimman osan ajasta ohjelma vain odottaa
käyttäjän reaktioita. Käyttäjän toiminnot voivat olla esimerkiksi
napin painallus hiirellä, tekstin kirjoittamista näppäimistöllä tai
jonkin objektin raahaamista hiirellä.

Käyttöliittymä on yleensä toteutettu niin, että erilaisiin näytöllä
oleville komponenteille tapahtuviin tapahtumiin on liitetty funktioita,
jotka suoritetaan tapahtuman sattuessa. Esimerkiksi viestin lähetyksestä
vastaava funktio suoritetaan, kun käyttäjä klikkaa hiirellä "Lähetä"-nappia.

Javascriptissä [tapahtumat][Events] (*events*) ovat varsin keskeisessä osassa.
Dokumentin HTML-elementteihin voidaan sitoa tapahtumankäsittelijöitä (*handler*),
eli funktioita, jotka suoritetaan halutun tyyppisen tapahtuma, esimerkiksi
hiiren klikkauksen, sattuessa.

Tapahtumankäsittelijän lisääminen
===============================

Javascriptissä tapahtumankäsittelijöitä voi liittää elementille sattuvaan
tapahtumaan useammalla tavalla.

Ehkä suoraviivaisin tapa on kirjoittaa se suoraan HTML-elementin attribuutiksi.
Attribuutin nimi on muotoa: `ontapahtuma`, eli `on` ja sen perässä tapahtuman nimi.
Esimerkiksi `onclick` tai `onload`.

```html
<h1 onclick="alert(this.getAttribute('data-viesti'));" data-viesti="Moikka">Klikkaa tätä</h1>
```
<div class="html-example">
<h1 onclick="alert(this.getAttribute('data-viesti'));" data-viesti="Moikka">Klikkaa tätä</h1>
</div>

Suoritettavat komennot voidaan tietenkin kerätä funktioksi, jolloin attribuuttiin riittää
lisätä vain tuon funktion kutsu.

```html
<h1 onclick="suoritus(this);" data-viesti="Moikka">Klikkaa tätä</h1>
<script>
function suoritus(element) {
    alert(element.getAttribute('data-viesti'));
}
</script>
```
<div class="html-example">
<h1 onclick="suoritus(this);" data-viesti="Moikka">Klikkaa tätä</h1>
<script>
function suoritus(element) {
    alert(element.getAttribute('data-viesti'));
}
</script>
</div>

Elementin tapahtumalle voidaan lisätä käsittelijä myös puhtaasti Javascriptillä.
Esimerkiksi:

```html
<h1 id="otsikko">Klikkaa tästä</h1>
<input type="text" id="tekstikentta">
```
```javascript
document.getElementById('otsikko').onclick = function(){
    var text = this.getAttribute('data-viesti');
    alert(text);
}
document.getElementById('tekstikentta').onchange = function(){
    alert('Kirjoitit: ' + this.value);
}
```
<div class="html-example">
<h1 id="otsikko" data-viesti="Hello, World!">Klikkaa tästä</h1>
<input type="text" id="tekstikentta">
<script>
document.getElementById('otsikko').onclick = function(){
    var text = this.getAttribute('data-viesti');
    alert(text);
}
document.getElementById('tekstikentta').onchange = function(){
    alert('Kirjoitit: ' + this.value);
}
</script>
</div>

Toinen tapa [lisätä elementille tapahtumankäsittelijä][MozListener], on käyttää `addEventListener()`-metodia.

```javascript
document.getElementById('otsikko').addEventListener('click', function(){
    var text = this.getAttribute('data-viesti');
    alert(text);
});
document.getElementById('tekstikentta').addEventListener('change', function(){
    alert('Kirjoitit: ' + this.value);
});
```
<div class="html-example">
<h1 id="otsikko2" data-viesti="Hello, World!">Klikkaa tästä</h1>
<input type="text" id="tekstikentta2">
<script>
document.getElementById('otsikko2').addEventListener('click', function(){
    var text = this.getAttribute('data-viesti');
    alert(text);
});
document.getElementById('tekstikentta2').addEventListener('change', function(){
    alert('Kirjoitit: ' + this.value);
});
</script>
</div>

Elementeille on mahdollista tapahtua useita erilaisia tapahtumia. Näitä ovat muun muassa:

|Tapahtuma             | Merkitys                          |
|----------------------|-----------------------------------|
|`onclick`             | Elementin klikkaaminen hiirellä.  |
|`onmousedown`         | Hiiren nappi painetaan pohjaan elementin päällä. |
|`onmouseup`           | Hiiren nappi vapautetan elementin päällä. |
|`onmouseover`         | Hiiri siirtyy elementin päälle.   |
|`onmouseout`          | Hiiri siirtyy pois elementin päältä. |
|`onfocus`             | Elementti saa fokuksen. (`<a>`, `<input>`,...  |)
|`onchange`            | Laukeaa, kun `<input>` menettää fokuksen ja se on muuttunut. |


Tapahtuman eteneminen
=====================

Kun elementille sattuu jokin tapahtuma, esimerkiksi sitä klikataan hiirellä,
tämä tapahtuma etenee DOM-puussa. Kun hiirellä klikataan, klikkaus tapahtuu
tyypillisesti useamman toistensa kanssa sisäkkäisen HTML-elementin päällä.
Mikä näistä käsittelee tapahtuman? Historiallisesti Netscape- ja Internet Explorer-selaimet
hoitivat tapahtumien käsittelyn toisistaan poikkeavalla tavalla.
Netscapessa tapahtuma lähti etenemään uloimmasta elementistä ja päätyi sisimpään elementtiin
(*capturing*), jonka päällä tapahtuma tapahtui. Internet Explorerissa puolestaan
tapahtuma oli ensin tarkolla käsiteltäväksi sisimmälle lenetille ja sen jälkeen
käsittelyvuoro siirtyi askel kerrallaan ulos päin (*bubbling*).

Nykyään *bubbling* on tapahtumien oletustapa toimia ja *capturing* on käytössä
vain, jos sitä erikseen pyydetään.

Esimerkiksi hiiren klikkauksella kukin hiiren alla oleva elementti saa vuorollaan
mahdollisuuden käsitellä tapahtuman, alkaen sisimmästä elementistä ja päätyen uloimpaan.

```html
<h1 id="otsikko3">Klikkaa <span id="sana">tätä</span></h1>
<script>
document.getElementById('otsikko3').addEventListener('click', function(event) {
    alert('h1');
});
document.getElementById('sana').addEventListener('click', function(event) {
    alert('span');
});
</script>
```
<div class="html-example">
<h1 id="otsikko3">Klikkaa <span id="sana">tätä</span></h1>
<script>
document.getElementById('otsikko3').addEventListener('click', function(event) {
    alert('h1');
});
document.getElementById('sana').addEventListener('click', function(event) {
    alert('span');
});
</script>
</div>


Kukin tapahtumankäsittelijä voi vuorollaan halutessaan pysäyttää "kuplimisen"
kutsumalla epahtuman `stopPropagation()`-metodia.

```html
<h1 id="otsikko3">Klikkaa <span id="sana">tätä</span></h1>
<script>
document.getElementById('otsikko4').addEventListener('click', function(event) {
    alert('h1');
});
document.getElementById('sana3').addEventListener('click', function(event) {
    event.stopPropagation();  // Estetään tapahtuman "bubbliminen" ulompiin elementteihin.
    alert('span');
});
</script>
```
<div class="html-example">
<h1 id="otsikko4">Klikkaa <span id="sana3">tätä</span></h1>
<script>
document.getElementById('otsikko4').addEventListener('click', function(event) {
    alert('h1');
});
document.getElementById('sana3').addEventListener('click', function(event) {
    event.stopPropagation();  // Estetään tapahtuman "bubbliminen" ulompiin elementteihin.
    alert('span');
});
</script>
</div>



[Events]: http://www.w3schools.com/js/js_htmldom_events.asp "W3Schools:Events"
[MozListener]: https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener?redirectlocale=en-US&redirectslug=DOM%2FEventTarget.addEventListener "Mozilla:addEventListener()"