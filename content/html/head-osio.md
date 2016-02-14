+++
Categories = []
Description = ""
Tags = []
Title = "Head-osio"
date = "2016-01-06T23:26:08+02:00"
weight = 3

+++

{{% jessyink src="html-johdanto.svg#9" %}}
{{% /jessyink %}}

Head-osioon merkitään tietoa dokumentista sen näyttämistä varten. Ei siis varsinaista sisältöä.
Määrittelyjä ovat esimerkiksi:

* dokumentin kieli
* käytetty merkistö
* dokumentin otsikko
* ulkopuoliset tiedostot (css, javascript, ikoni, rss,...)
* tyyli- ja skriptiosat
* jne.

Title
=====
Dokumentin otsikko lisätään *head*-osioon `<title>`-tagilla. Otsikko näytetään esimerkiksi
selaimen yläpalkissa sekä selaimeen talletetuissa kirjanmerkeissä. Otsikko on myös se teksti,
jonka hakukoneet näyttävät hakutuloksissa. Hakukoneet myöskin painottavat tuloksissaan
otsikossa käytettyjä sanoja.
```
<title>Sivun otsikko</title>
```

Base
====
Dokumentin linkkien osoitteiden ja `target`-attribuutin oletukset voidaan halutessa asettaa
`<base>`-tagilla.
```
<base href="http://petrit.net/www-ohjelmointi" />
<base target="_blank" />
```

Link
====
Ulkoisten tiedostojen liittäminen dokumenttiin tapahtuu `<link>`-tagilla. Sillä on pakollisena
attribuuttina `rel`, jolla kerrotaan tiedoston suhde alkuperäiseen dokumenttiin. Muita attribuutteja
ovat `href`, joka kertoo linkitetyn tiedoston osoitteen, sekä `type`, joka kertoon tiedoston
[MIME-tyypin][MIME].

```
<link rel="stylesheet" type="text/css" href="tyyli.css" />
<link rel="copyright" href="http://creativecommons.org/licenses/by-sa/4.0/" />
<link rel="shortcut icon" href="/static/favicon.ico" />
<link rel="alternate" href="/index.xml" type="application/rss+xml" title="www-ohjelmointi" />
```

Meta
====
Dokumentille voidaan antaa erilaista metatietoa `<meta>`-tagilla. Tagille kirjoitetaan kaksi
attribuuttia:

* `name` kertoo, minkä tyyppinen tieto on kyseessä (esim. `name="autor"`).
* `content` kertoo tiedon sisällön (esim. `content="Petri"`).

```
<meta name="author" content="Petri">
<meta name="description" content="www-ohjelmoinnin opetussivusto">
<meta name="generator" content="Hugo 0.15">
```

Dokumentissa käytetty [merkistökoodauksen][Merkistö] ilmoittaminen on erityisen tärkeää, kun sen sisältö
on jotain muuta kuin englantia. Esimerkiksi suomenkielisissä dokumenteissa se on tärkeää, jotta
å, ä ja ö näkyvät selaimissa oikein. Merkistökoodaus voidaan kertoa HTML5-dokumentissa käyttäen
`<meta>`-tagin `charset`-attribuuttia.
```
<meta charset="utf-8">
```

Muissa dokumenttityypeissä määrittely on hiukan monimutkaisempaa ja tehdään seuraavasti:
```
<meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
```

Style
=====
Dokumentin ulkoasua muokkaavia tyylimäärittelyjä voidaan lisätä suoraan HTML-dokumentin head-osioon `<style>`-tagilla.
Lisää dokumentin ulkoasun muokkaamisesta kurssin [CSS-osuudessa](../../css/).
```
<style>
    ... css-sääntöjä ...
</style>
```

Script
======
Sivulla suoritettavaa Javascript-ohjelmakoodia voidaan joko linkittää ulkopuolisesta tiedostosta tai
suorittaa suoraan HTML-tiedostosta `<script>`-tagilla. Lisää kurssin [Javascript-osiossa](../../javascript/).

```
<script type="text/javascript" src="js/myscript.js"></script>
<script type="text/javascript">
    ... javascript-koodia ...
</script>
```


[MIME]: https://fi.wikipedia.org/wiki/Internet_media_type "Wikipedia:Internet media type"
[Merkistö]: https://fi.wikipedia.org/wiki/Merkist%C3%B6 "Wikipedia:Merkistö"