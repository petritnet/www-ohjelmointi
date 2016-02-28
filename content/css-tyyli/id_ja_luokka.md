+++
Categories = []
Description = ""
Tags = []
Title = "Id ja luokka"
date = "2016-02-10T21:30:24+02:00"
weight = 80

+++

Koska HTML-elementeille voidaan antaa **ainutkertaisia nimiä** `id`-attribuutilla
ja useammin käytettäviä **luokkamääreitä** `class`-attribuutilla, niihin voidaan
viitata CSS-säännöissä.

Säännöissä voi viitata elementtiin joko suoraan HTML-tagin nimellä, sen `id`-attribuutilla
tai `class`-attribuutin arvolla taikka näiden yhdistelmillä.

Id-määre
========
`id`-attribuutilla nimettyihin elementteihin voi viitata valitsimella, jossa on
"risuaitamerkki" `#` sekä `id`-attribuutin nimi:

```
#paaotsikko {color: red; border-bottom: 2px solid black;}
#kappale a {background-color: #faa;}
```
```
<h1 id="paaotsikko">Pääotsikko</h1>
<p id="kappale">Teksti, jossa <a href="http://petrit.net/www-ohjelmointi">linkki</a>.</p>
<p>Teksti, jossa <a href="http://petrit.net/www-ohjelmointi">linkki</a>.</p>
```
<div class="html-example">
<h1 style="color: red; border-bottom: 2px solid black;">Pääotsikko</h1>
<p id="kappale">Teksti, jossa <a style="background-color: #faa;" href="http://petrit.net/www-ohjelmointi">linkki</a>.</p>
<p>Teksti, jossa <a href="http://petrit.net/www-ohjelmointi">linkki</a>.</p>
</div>


Luokkamääre
===========

`class`-attribuutissa mainittuun luokkaan voi CSS-säännöissä viitata pisteellä `.` ja luokan nimellä.

```
.huomio {background-color: #ff0;}
p.kappale a {background-color: #faa;}
```
```
<p class="huomio">Lorem ipsum dolor sit amet, consectetur adipiscing elit.
Donec quis risus non velit imperdiet laoreet. Nulla molestie a ante id pharetra.
Morbi finibus sed elit tincidunt laoreet. Etiam elementum malesuada nisl ut sodales.</p>
<p class="jokumuu kappale">Teksti, jossa <a href="http://petrit.net/www-ohjelmointi">linkki</a>.</p>
<p>Teksti, jossa <a href="http://petrit.net/www-ohjelmointi">linkki</a>.</p>
```
<div class="html-example">
<p style="background-color: #ff0;">Lorem ipsum dolor sit amet, consectetur adipiscing elit.
Donec quis risus non velit imperdiet laoreet. Nulla molestie a ante id pharetra.
Morbi finibus sed elit tincidunt laoreet. Etiam elementum malesuada nisl ut sodales.</p>
<p>Teksti, jossa <a style="background-color: #faa;" href="http://petrit.net/www-ohjelmointi">linkki</a>.</p>
<p>Teksti, jossa <a href="http://petrit.net/www-ohjelmointi">linkki</a>.</p>
</div>
