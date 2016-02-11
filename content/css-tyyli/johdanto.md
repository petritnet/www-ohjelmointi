+++
date = "2016-01-06T12:36:36+02:00"
title = "Johdanto"
weight = 1
+++

HTML-tiedoston teksti määrittelee vain dokumentin varsinaisen asiasisällön sekä sen rakenteen, ei ulkoasua.
WWW-selaimet esittävät dokumentin kunkin rakennetyypin jollain oletusulkoasulla, mutta niiden ulkoasu on täysin
sivuston suunnittelijan muokattavissa. Ulkoasun tyylittelyyn käytetään __CSS__-kielellä esitettyjä tyylisääntöjä.

{{% jessyink src="css-johdanto.svg" %}}
Johdanto HTML-kielen perusteisiin.
{{% /jessyink %}}

Mitä on CSS?
============
* Cascading Style Sheets, eli "porrastetut tyyliarkit".
* Sääntöjä, joilla eri HTML-elementeille määrätään ulkoasuasetuksia.
* Samaa elementtiä voi koskea useampi sääntö, joista osuvin tai viimeisin jää voimaan.
* Nykyisin käytössä versio 3.
* Samalle sivustolle voi olla useita erilaisia css-tyylejä, joilla sivuston ulkoasu voi muuttua hyvinkin paljon.
    * [CSS Zen Garden][CSS Zen Garden]

Miksi CSS?
==========
* Nykyaikaisilla www-sivustoilla erotellaan toisistaan *sisältö*, *ulkoasu* ja *toiminnallisuus*. (HTML, CSS ja Javascript)
* Koko sivustolle saadaan yhtenäinen ulkoasu, joka on muutettavissa yhdestä paikasta.

CSS-tyylisäännöt
================

Tyylisäännössä on yleisesti kaksi osaa:

* __Valitsin__ (selector), joka määrää, mitä elementtejä sääntö koskee.
* __Määrittelyosa__ (declaration block), joukko määrittelyitä (declaration), joilla kerrotaan eri ominaisuuksille arvoja.

HTML-dokumentin tagit voidaan ajatella "laatikoiksi", joiden ominaisuuksia CSS-säännöillä määritellään:

* Tekstin väri, taustan väri, taustakuva
* Reunaviiva ja sen paksuus, väri, kulmien pyöristys yms.
* Marginaalit reunaviivan ulkopuolella, tila reunaviivan ja sisällön välissä (*padding*).
* Monia muita ominaisuuksia
* Myös animaatioita


CSS:n versiot
=============
CSS-kieli on kehittynyt vuosien mittaan tarpeen ja kieleltä vaadittavien ominaisuuksien ymmärryksen myötä.

CSS1
----

* Yleinen muotoilu
* Leveyden ja korkeuden asettaminen
* Reunaviivat ja täytteet
* Listojen muotoilu
* Fontit ja niiden ominaisuudet
    * Värit, alleviivaus, koko, ym.
* Asemointi
    * Vasemmalle, oikealle, keskelle


CSS2
-----
Lisäsi ominaisuuksia edelliseen versioon.

* Parempi asemointi
    * Elementit, kuvat ja teksti voidaan asemoida minne vain.
* Edellisestä johtuen elementtejä voi laittaa päällekkäin niin, että voidaan päättää, mikä on päällä ja mikä alla.
* Ylivuodon käsittely. Mitä tehdä, jos sisältö ei mahdu sille varattuun tilaan?


CSS3
-----
Peilaa nykyisiä tarpeita.

* Ominaisuuksien animointi
* Elementtien kääntely
* "Laatikoiden" muotoilu
    * Pyöristys, varjostus, ym.
* Web-fontit
* 3D-efektit




[CSS Zen Garden]: http://www.csszengarden.com/ "CSS Zen Garden"