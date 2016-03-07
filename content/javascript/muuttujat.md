+++
Categories = []
Description = ""
Tags = []
Title = "Muuttujat"
date = "2016-03-08T00:47:58+02:00"
weight = 20

+++

Ohjelmointikielissä tietoa tallennetaan suorituksen aikana [muuttujiin][Variables].

Muuttujan esittely
==================

Javascriptissä muuttujat esitellään sanalla `var`. Esittelyn yhteydessä
muuttujalle voidaan haluttaessa antaa myös arvo. Muussa tapauksessa
arvoksi tulee tässä vaiheessa `undefined`, eli määrittelemätön.

Säännöt laillisille muuttujien nimille ovat seuraavat:

- Nimessä voi olla kirjaimia, numeroita, alaviivoja ja dollari-merkkejä.
- Nimi ei saa alkaa numerolla.
- Nimissä isoilla ja pienillä kirjaimilla on merkitysero.
- Javascriptin varattuja sanoja ei saa käyttää.

Muuttujaan sijoitetaan arvo sijoitusoperaattorilla, joka on `=`.

```javascript
var luku = 42;
var nimi = 'Petri';
var jokinPitkaMuuttujanNimi;
var toinen_muuttujan_nimi = true;
var abc, foo = 'bar', baz;
```

Muuttujan esitteleminen `var`-sanalla ei ole aivan pakollista, mutta **erittäin suositeltavaa**,
sillä `var`-sanan unohtaminen voi joskus johtaa erittäin vaikeasti löydättäviin virheisiin.

Muuttujan näkyvyysalue
======================

Muuttujan näkyvyysalue, eli se, missä kohdissa koodia jokin muuttuja on käytettävissä, voi olla
**globaali** tai **lokaali**. Globaalit muuttujat ovat käytettävissä kaikkialla ohjelmakoodissa
ja lokaalit muuttujat vain sen funktion sisällä, jossa se on määritelty.

Käytännössä kannattaa pyrkiä minimoimaan globaalien muuttujien määrä ja käyttää vain lokaaleja
muuttujia, jos se on mahdollista.


[Variables]: http://www.w3schools.com/js/js_variables.asp "W3Schools:Variables"