+++
Categories = []
Description = ""
Tags = []
Title = "Laatikoiden muotoilut"
date = "2016-02-10T21:29:09+02:00"
weight = 60

+++

Koon, reunojen ja tyhjän tilan lisäksi HTML-elementtilaatikoille voidaan määritellä joitain
muitakin muotoiluja, kuten kulmien pyöristystä ja laatikon varjoa.

Pyöristetyt kulmat
==================
Aiemmin laatikoiden kulmien pyöristys oli monimutkaista ja pyöreäkulmaiset laatikot tehtiin yleensä
asettelemalla sen kulmiin pienet pyöristävät kuvat. CSS3:n myötä käyttöön tuli `border-radius`-ominaisuus,
jolla pyöristäminen on helppoa. Arvoksi tälle ominaisuudelle annetaan pyöristyksen säde jollain yksiköillä
(px, em, cm, in, %). Kulmien pyöristyksen arvot voidaan antaa myös kullekin kulmalle erikseen luettelemalla
neljä arvoa myötäpäivään alkaen vasemmasta yläkulmasta.

```
<h1 style="border: 3px solid green; border-radius: 10px;">Laatikoitu Otsikko</h1>
<h1 style="border: 3px solid green; border-radius: 3em;">Laatikoitu Otsikko</h1>
<h1 style="border: 3px solid green; border-radius: 100%;">Laatikoitu Otsikko</h1>
<h1 style="border: 3px solid green; border-radius: 15px 0 15px 0;">Laatikoitu Otsikko</h1>
```
<div class="html-example">
<h1 style="border: 3px solid green; border-radius: 10px;">Laatikoitu Otsikko</h1>
<h1 style="border: 3px solid green; border-radius: 3em;">Laatikoitu Otsikko</h1>
<h1 style="border: 3px solid green; border-radius: 100%;">Laatikoitu Otsikko</h1>
<h1 style="border: 3px solid green; border-radius: 15px 0 15px 0;">Laatikoitu Otsikko</h1>
</div>

Laatikon varjo
==============
Samoin kuin tekstille, myös HTML-elementtilaatikolle voidaan määrätä varjo `box-shadow`-ominaisuudella.
Ominaisuus saa arvoksi:

- vaakasiirtymän (pakollinen) (px, em, ...)
- pystysiirtymän (pakollinen) (px, em, ...)
- sumennuksen säteen (valinnainen) (px, em, ...)
- levinneisyyden, joka lisää varjon kokoa (valinnainen) (px, em, ...)
- värin (nimi, rgb- tai rgba-arvo)

Lisäksi avainsanalla `inset` varjo voidaan määrätä asetettavaksi laatikon sisäpuolelle.
Tätä voi käyttää esimerkiksi 3-ulotteisen efektin tekemiseen esimerkiksi nappuloihin
tai "upotuksiin".
Tarvittaessa varjostus voidaan myös kytkeä pois päältä arvolla `none`.
Varjoja voidaan myös asettaa samalle elementille useampia erottelemalla ne toisistaan
pilkulla.

Koska varjoa ei "vie tilaa" elementin asettelussa, voi sillä tehdä elementille yhden tai
useamman reunuksen lisäämättä sen kokoa.

```
<h1 style="box-shadow: 5px 5px 5px gray; background-color: green;">Otsikko</h1>
<h1 style="box-shadow: -5px -10px 0 red; background-color: green;">Otsikko</h1>
<h1 style="box-shadow: 0 0 25px lime, 5px 5px 5px gray; background-color: green;">Otsikko</h1>
<h1 style="box-shadow: 0 0 0 4px blue, 0 0 0 8px red, 0 0 0 12px green; background-color: #ffa; ">Otsikko</h1>
<h1 style="box-shadow: inset 3px 3px 3px rgba(0,0,0,0.5), inset -3px -3px 3px rgba(255,255,255,0.5); background-color: #ff0; ">Otsikko</h1>
<button style="box-shadow: inset 4px 4px 4px rgba(255,255,255,0.5), inset -4px -4px 4px rgba(0,0,0,0.5);
               padding: 1em; border: 1px solid #444;
               border-radius: 10px;
               background-color: #999;
               color: black;">Nappula</button>
```
<div class="html-example">
<h1 style="box-shadow: 5px 5px 5px gray; background-color: green;">Otsikko</h1>
<h1 style="box-shadow: -5px -10px 0 red; background-color: green;">Otsikko</h1>
<h1 style="box-shadow: 0 0 25px lime, 5px 5px 5px gray; background-color: green;">Otsikko</h1>
<h1 style="box-shadow: 0 0 0 4px blue, 0 0 0 8px red, 0 0 0 12px green; background-color: #ffa; ">Otsikko</h1>
<h1 style="box-shadow: inset 3px 3px 3px rgba(0,0,0,0.5), inset -3px -3px 3px rgba(255,255,255,0.5); background-color: #ff0; ">Otsikko</h1>
<button style="box-shadow: inset 4px 4px 4px rgba(255,255,255,0.5), inset -4px -4px 4px rgba(0,0,0,0.5);
               padding: 1em; border: 1px solid #444;
               border-radius: 10px;
               background-color: #999;
               color: black;">Nappula</button>
</div>

