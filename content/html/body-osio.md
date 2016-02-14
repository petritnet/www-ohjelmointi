+++
Categories = []
Description = ""
Tags = []
Title = "Body-osio"
date = "2016-01-06T23:26:08+02:00"
weight = 4

+++

{{% jessyink src="html-johdanto.svg#11" %}}
{{% /jessyink %}}

Dokumentin varsinainen sisältö kirjoitetaan *body*-osioon `<body>`-tagin sisään.
Sisältö jaotellaan tageilla loogisiin osiin ja merkitään niillä osien merkityksen
mukaisesti.

Otsikot
=======
[Otsikot][Otsikot] merkitään `<h#>`- ja `</h#>`-tageilla, joissa # on jokin numero yhdestä kuuteen.
Näistä `<h1>` tarkoittaa sivun pääotsikkoa ja `<h2>` ... `<h6>` alaotsikoita
suurimmasta pienimpään.

```
<!DOCTYPE html>
<html>
    <head>
        <title>Esimerkki otsikoista</title>
    </head>
    <body>
        <h1>Sivun pääotsikko</h1>
        <h2>Alaotsikko 1</h2>
        <h3>Toinen alaotsikko</h3>
        <h4>Ei ihan niin tärkeä otsikko...</h4>
    </body>
</html>
```

<div class="html-example">
        <h1>Sivun pääotsikko</h1>
        <h2>Alaotsikko 1</h2>
        <h3>Toinen alaotsikko</h3>
        <h4>Ei ihan niin tärkeä otsikko...</h4>
</div>


Leipäteksti
===========
Sisällön tavallinen teksti, eli leipäteksti, kirjoitetaan [tekstikappaleina][Kappale], jotka merkitään
`<p>`-tagilla. Selaimet erottelevat tekstipalstat oletuksena toisistaan hieman normaalia
rivinväliä suuremmalla pystysuuntaisella tyhjällä tilalla. Kappaleenvaihdot erottuvat siis
selvästi.

HTML-raakatekstissä olevia rivinvaihtoja ei sivua näytettäessä normaalisti huomioida.
Rivinvaihto voidaan pakottaa `<br>`-tagilla. Sillä ei ole vastaavaa sulkutagia.

```
<p>
    Tässä on kokonainen palsta tekstiä. Huomaa,
    että selain tulostaa kaiken sisällön peräkkäin, eli
    html-tiedostossa olevat rivinvaihdot eivät vaikuta
    Tulostukseen.

    Tämä lause tulostuu siis edellisen lauseen perään.
</p>
<p>
    Tässä on puolestaan uusi kappale.
</p>
```

<div class="html-example">
<p>
    Tässä on kokonainen palsta tekstiä. Huomaa,
    että selain tulostaa kaiken sisällön peräkkäin, eli
    html-tiedostossa olevat rivinvaihdot eivät vaikuta
    Tulostukseen.

    Tämä lause tulostuu siis edellisen lauseen perään.
</p>
<p>
    Tässä on puolestaan uusi kappale.
</p>
</div>

Kuvat
=====
[Kuvat][Kuva] lisätään HTML-dokumenttiin `<img>`-tagilla. Sillä ei ole
vastaavaa lopetustagia, mutta lopetus voidaan kirjoittaa suoraan
aloitustagiin muodossa `<img />`. Oletuksena kuva sijoitetaan sivulle HTML-tekstissä
määrättyyn kohtaan tekstiriville samaan tapaan kuin se olisi yksi erikoisen kokoinen kirjain.

Kuvatagilla on useita attribuutteja, joista tärkeimmät ovat:

* `src` – kuvatiedoston osoite
* `alt` – Vaihtoehtoinen teksti, jos kuvaa ei pystytä näyttämään. Jos kuvan sisältö on tärkeää, tämä oleellinen esimerkiksi näkövammaisten ruudunlukijoita varten.
* `width` – kuvan leveys
* `height` – kuvan korkeus
* `title` – kuvan otsikko (Selaimet näyttävät tämän yleensä, kun hiiri jätetään hetkeksi kuvan päälle.)

```
Tekstiä <img src="images/html5.png" alt="HTML5-logo"> kuvan ympärillä.
<img src="images/html5.png" alt="HTML5-logo" width="50" height="30" title="HTML5-logo skaalattuna ja litistettynä.">
```

<div class="html-example">
Tekstiä <img src="../../images/html5.png" alt="HTML5-logo"> kuvan ympärillä.
<img src="../../images/html5.png" alt="HTML5-logo" width="50" height="30" title="HTML5-logo skaalattuna ja litistettynä.">
</div>

Linkit
======
[Hyperlinkit][Linkki] dokumentin sisällä, dokumentin ulkopuolelle, toisiin dokumentteihin, kuviin ja
tiedostoihin merkitään `<a>`-tagilla. Tagin tärkein attribuutti on `href`, jolla kerrotaan linkityksen
kohteen osoite. Alku- ja lopputagin väliin jäävästä sisällöstä tulee klikattava linkki, joka johtaa
kohteeseen. Linkkinä käytettävä sisältö voi olla esimerkiksi tekstiä tai kuvia.

```
<a href="http://petrit.net/www-ohjelmointi">WWW-ohjelmointi</a>
<a href="images/html5-pieni.png"><img src="images/html5-pieni.png"></a>
```

<div class="html-example">
<a href="http://petrit.net/www-ohjelmointi">WWW-ohjelmointi</a>
<a href="../../images/html5-pieni.png"><img src="../../images/html5-pieni.png"></a>
</div>

Absoluuttinen ja suhteellinen polku
-----------------------------------
Linkkien, kuvien tai muiden sivuun liittyvien tiedostojen tai sivujen osoitteet voivat olla
**absoluuttisia** tai **suhteellisia**.

Osoite on absoluuttinen, kun se on annettu kokonaisuudessaan, mukaan lukien `http://`-aluke.
Absoluuttinen polku riittää yksinään löytämään halutun kohteen.

```
<a href="http://www.google.com/">Google</a>
<img src="http://petrit.net/www-ohjelmointi/images/html5.png">
```

Osoite on suhteellinen, jos se on viittaus nykyisen dokumentin sijainnin suhteen. Suhteellisella
viittauksella voidaan viitata nykyisessä kansiossa olevien kohteiden lisäksi vaikka alikansioissa tai
yläkansioissa oleviin kohteisiin.
```
<a href="johdanto">Google</a>
<a href="ali/kansio/kuva.jpg">Google</a>
<img src="../../images/html5.png">
```


Harjoituksia
============
Tutustu [JSBin][JSBin]-palveluun, jossa voi kirjoittaa ja muokata HTML-sivuja selaimeen upotetulla
editorilla ja nähdä lopputuloksen suoraan livenä.

Kullekin sivulle luodaan yksilöllinen osoite jota käyttämällä sille pääsee palaamaan tai jolla sen
voi jakaa toisille. Toisten tekemistä sivuista on helppo tehdä oma kopio, joka saa oman yksilöllisen
osoitteen. Sivustolle kirjautumalla pääsee selaamaan omia aiempia tuotoksia.
 


[Otsikot]: http://www.w3schools.com/tags/tag_hn.asp "W3Schools:Otsikot"
[Kappale]: http://www.w3schools.com/tags/tag_p.asp "W3Schools:Kappale"
[Kuva]: http://www.w3schools.com/tags/tag_img.asp "W3Schools:Kuva"
[Linkki]: http://www.w3schools.com/tags/tag_a.asp "W3Schools:Linkki"
[JSBin]: https://jsbin.com/ "JSBin"