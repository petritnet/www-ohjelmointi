+++
date = "2016-01-06T12:36:17+02:00"
title = "Johdanto"
weight = "1"

+++

Lyhyt johdanto siitä, mitä HTML on ja mihin sitä käytetään.

{{% jessyink src="html-johdanto.svg" %}}
Johdanto HTML-kielen perusteisiin.
{{% /jessyink %}}

Mitä HTML on?
=============
* HyperText Markup Language, eli hypertekstin merkintäkieli
* Kehitetty alkujaan vuonna 1991, HTML 1 vuonna 1993
* Nykyään käytössä versio 5

HTML-merkinnät antavat tekstidokumentin osille __semanttisen__
merkityksen ja mahdollistaa linkityksen dokumenttien välillä ja dokumentin sisällä.
Toisin sanoen dokumentin osille merkitään niiden merkitys, eritasoiset
otsikot, kappaleet, luettelot, valikot, korostukset jne. HTML-merkintöjä ei
käytetä dokumentin osien ulkoasun määrittämiseen.

HTML-dokumentti on "pelkkää" tekstiä, eli sitä voi kirjoittaa millä
tahansa tekstieditorilla, vaikka Notepadilla, ja tiedosto tallennetaan 
päätteellä `.html`. Monissa tekstieditoreissa on rakenteen
kirjoittamista auttavia toimintoja, kuten dokumentin rakenteen korostaminen väreillä 
sekä merkintöjen automaattitäydennyksiä. Myös monet muut ohjelmat
osaavat tuottaa HTML-koodia, esimerkiksi MS Word, mutta niiden tuottama 
koodi voi olla sekavaa, vaikeasti luettavaa ja vaikeasti käsin korjattavaa tai muokattavaa.

HTML-dokumenttityyppi
=====================

HTML-tiedoston esimmäisellä rivillä määritellään [dokumentin
tyyppi](http://www.w3schools.com/tags/tag_doctype.asp)
`<!DOCTYPE>`-tagilla. Tämä tagi ei itse ole HTML-kieltä vaan merkintä,
jolla www-selaimelle kerrotaan, minkä kielen mukaan kyseinen tiedosto
tulee tulkita. HTML-kielen versiot eroavat toisistaan jonkin verran ja
selaimen käyttäytyminen riippuu siitä, mitä versiota se kuvittelee
tiedoston olevan.

Esimerkiksi HTML5:
```
<!DOCTYPE html>
```

ja HTML 4.01 Strict:
```
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">
```