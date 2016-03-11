+++
Categories = []
Description = ""
Tags = []
Title = "Funktiot"
date = "2016-03-09T22:45:34+02:00"
weight = 40

+++

Ohjelmointikielissä oleellista on koodin uudelleenkäytettävyys.
Jotta vältyttäisiin saman toiminnallisuuden toteuttamiselta
useaan kertaan, koodilohkoja kootaan [funktioiksi][Funktiot], joita voidaan kutsua nimellä.

Funktion määrittely
===================
Javascriptissä funktio voidaan määritellä kahdella tavalla. Ensimmäinen on
niinsanottu *funktiomäärittely* (*function declaration*) ja on muotoa:

```
function funktionNimi(parametrit) {
    ... suoritettava lohko ...
}
```

Toisesta tavasta käytetään nimitystä *funktiolauseke* (*function expression*) ja siinä käytännössä
määritellään nimetön funktio, joka sijoitetaan muuttujaan. Tämä havainnollistaa
hyvin sitä, miten javascriptissä myös funktio on muuttujaan sijoitettavissa oleva
arvo siinä, missä luku, merkkijono tai mikä tahansa muukin objekti.  

```
var funktionNimi = function(parametrit) {
    ... suoritettava lohko ...
}
```

Sijoitusmerkin vasemmalla puolella on aivan normaali muuttujan esittely ja oikealla
puolella samanlainen funktiomäärittely kuin edellä, mutta ilman funktion nimeä.
Käytännössä molemmilla tavoilla määritellyt funktiot toimivat kutsuttaessa aivan samoin.

Esimerkiksi:
```
function pintaAla(leveys, korkeus) {
    console.log('Pinta-ala on: ' + (leveys * korkeus));
}
```


Funktion kutsuminen
===================
Funktion suorittaminen tapahtuu kutsumalla sitä muodossa `funktionNimi()`,
`funktionNimi(parametri)`, `funktionNimi(parametri1, parametri2)` ja niin edelleen
riippuen funktion vastaan ottamien parametrien määrästä.

```
pintaAla(12, 32);
```

Funktion palautusarvo
=====================
Toisinaan funktion halutaan vain suorittavan jonkin tehtävät, muuttujien sijoittamisia,
olioiden muokkailuja, tulostusta tai muuta vastaavaa. Usein kuitenkin funktion halutaan
etsivän vastauksen johonkin kysymykseen ja palauttavan sen. Tällöin funktion palauttaman
arvon voi sijoittaa haluamaansa muuttujaan myöhempää käyttöä varten.

```
function pintaAla(leveys, korkeus) {
    return leveys * korkeus;
}

var pala = pintaAla(12, 14);
```


[Funktiot]: http://www.w3schools.com/js/js_functions.asp "W3Schools:Funktiot"