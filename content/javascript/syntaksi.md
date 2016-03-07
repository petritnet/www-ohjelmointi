+++
Categories = []
Description = ""
Tags = []
Title = "Ohjelman kirjoittaminen"
date = "2016-03-08T01:05:22+02:00"
weight = 7

+++

Muutamia perusohjeita Javascriptin syntaksista alkuun pääsemiseksi.

Kommentit
=========

Kommentteja voidaan ohjelmakoodissa käyttää dokumentoimaan ja selittämään
hankalasti ymmärrettäviä ohjelmakohtia. Niillä voidaan myös kytkeä
väliaikaisesti pois käytöstä osia ohjelmasta.

Javasriptissä kommentteja voi kirjoittaa kahdella tavalla:

- rivikommentteina
- lohkokommentteina

Rivikommentissa merkintä `//` aloittaa kommentin missä tahansa kohtaa ohjelmakoodia ja
samalla rivillä kaikki tämän merkinnän jälkeen on kommenttia, jota ei suoriteta.

```javascript
// Lasketaan yhteen x ja y
z = x + y;
a = b - c;  // Vähennyslasku
```

Lohkokommentti puolestaan alkaa merkinnällä `/*` ja kestää lopettavaan merkintään `*/`
saakka. Tämä kommenttimerkintä voi ulottua useamman rivin yli.

```javascript
/*****************************
 * Copyright: Petri Salmela
 *****************************/
z = x + y;
a = b + /* Kommentti voi olla keskelläkin */ c;
/*
luku = 3;
*/
```

Puolipisteet
============

Javascript-lauseet kirjoitetaan yleensä omalle riville ja ne päätetään puolipisteellä.
Puolipiste ei ole yleensä pakollinen, kuten joissain muissa ohjelmointikielissä, sillä
Javascript osaa täydentää rivinvaihdon tarvittaessa lauseen päättymiseksi.
Lauseet kannattaa kuitenkin yleensä päättää puolipisteellä, sillä toisinaan sen puuttuminen
voi aiheuttaa ohjelmakoodin tulkitsemisen toisin kuin ohjelmoija on sen tarkoittanut.


