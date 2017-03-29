+++
Categories = []
Description = ""
Tags = []
Title = "Sisällön ryhmittely"
date = "2016-02-06T16:21:14+02:00"
weight = 45

+++

{{% jessyink src="html-johdanto.svg#12" %}}
{{% /jessyink %}}

Www-sivun sisältöä voidaan ja se kannattaa tarvittaessa ryhmitellä osiin. Sisällön jaotteluun on
aiemmissa HTML:n versioissa käytetty `<div>`- ja `<span>`-tageja ja HTML5:n myötä käytettäväksi
on saatu useita muita tageja. Alkuperäisillä `<div>`- ja `<span>`-tageilla ei ole sellaisenaan
mitään varsinaista merkitystä, jonka ne antaisivat sisältämälleen dokumentin osalle eikä selaimilla
ole niiden esittämiseen mitään erityisiä tyylisääntöjä. Uusilla HTML5-tageilla sen sijaan on
kullakin jokin semanttinen merkitys, jossa niitä on tarkoitus käyttää.

Semanttisten tagien käyttäminen sivun rakentamisessa on tärkeää, sillä silloin sivun sisältö on
helpommin luettavissa ja tulkittavissa koneellisesti. Tämä helpottaa esimerkiksi hakukoneiden sekä
näkövammaisille suunnattujen ruudunlukijaohjelmien toimintaa.

Div
===
[Dokumentin osio][Div] (*division*) merkitään `<div>`-tagilla. Tällä tagilla merkityllä osiolla ei
tarvitse olla erityisempää semanttista merkitystä tai sitä voidaan käyttää sellaisten sisältöjen
rajaamiseen, joille ei ole omaa tagia. Sitä voidaan käyttää esimerkiksi blogikirjoituksen
metatietojen (kirjoittaja ja päiväys) rajaamiseen.

Tällä tagilla ei ole valmiiksi määriteltyä merkitystä, mutta sivun tekijä voi itse lisätä sille
`class`-attribuutilla luokan, joka kuvaa elementin sisältöä ja jonka avulla sille voidaan määritellä ulkoasua.
`<div>`-tagi luo dokumenttiin niin sanottu *lohkotyyppisen* elementin, eli mahdollisesti suurempiakin
sisältöjä sisältävän "laatikon".

```
<div class="esimerkki">
    <p>Vähän tekstiä</p>
    <p>Hiukan lisää pidempää tekstiä.</p>
</div>
```
<div class="html-example">
<div class="esimerkki">
    <p>Vähän tekstiä</p>
    <p>Hiukan lisää pidempää tekstiä.</p>
</div>
</div>

Span
====
Kun tekstistä halutaan jostain syystä merkitä jokin osuus, jonka merkitykselle ei ole omaa tagia,
voidaan käyttää [`<span>`-tagia][Span]. Samoin kuin `<div>`-tagilla, myöskään `<span>`-tagilla ei ole
valmiiksi määriteltyä merkitystä tai ulkoasua vaan ne ovat käyttäjän itse määriteltävissä esimerkiksi
`class`-attribuuttia käyttämällä.

`<span>`-tagi on tyypiltään rivin sisäinen elementti, eli sen sisään ei ole tarkoitus koota suurempia
lohkotyyppisiä dokumentin osia, kuten kappaleita, vaan rivin sisällä olevaa juoksevaa tekstiä.

```
<div class="esimerkki">
    <p>Vähän tekstiä</p>
    <p>Hiukan <span class="huomio">lisää pidempää</span> tekstiä.</p>
</div>
```
<div class="html-example">
<div class="esimerkki">
    <p>Vähän tekstiä</p>
    <p>Hiukan <span class="huomio">lisää pidempää</span> tekstiä.</p>
</div>
</div>

Article
=======
[`<article>`-tagilla][Article] luodaan lohkotyyppinen elementti, joka on jollain tavalla itsenäinen ja
itseriittoinen yksinään luettavissa oleva kokonaisuus. Tällainen on esimerkiksi foorumille
tai blogiin lähetetty postaus tai yksittäinen uutinen sivuilla, joilla on luettavissa
yhtä aikaa useita artikkeleita.

```
<article>
    <h2>Avaruusalus laskeutui kuuhun</h2>
    <p>Tänään keskipäivällä kuuhun laskeutui ...</p>
    <p>Kuussa käveltiin...</p>
</article>
<article>
    <h2>Kuuauto törmäsi kiveen</h2>
    <p>Kuussa ajelulla ollut auto törmäsi kuukiveen.</p>
</article>
```
<div class="html-example">
<article>
    <h2>Avaruusalus laskeutui kuuhun</h2>
    <p>Tänään keskipäivällä kuuhun laskeutui ...</p>
    <p>Kuussa käveltiin...</p>
</article>
<article>
    <h2>Kuuauto törmäsi kiveen</h2>
    <p>Kuussa ajelulla ollut auto törmäsi kuukiveen.</p>
</article>
</div>


Section
=======
[`<section>`-tagilla][Section] luodut elementit ovat lohkotyyppisiä ja sillä merkitään pidemmästä dokumentista
sen osuuksia, kuten lukuja/kappaleita, ylä- tai ala-tunnisteita tai muun tyyppisiä sisällön osia.

```
<article>
    <h1>Raportti tärkeästä asiasta</h1>
    <section>
        <h2>Alaotsikko</h2>
        <p>Raportin tärkeää asiaa...</p>
    </section>
    <section>
        <h2>Toinen alaotsikko</h2>
        <p>Lisää tärkeää asiaa...</p>
    </section>
</article>
```
<div class="html-example">
<article>
    <h1>Raportti tärkeästä asiasta</h1>
    <section>
        <h2>Alaotsikko</h2>
        <p>Raportin tärkeää asiaa...</p>
    </section>
    <section>
        <h2>Toinen alaotsikko</h2>
        <p>Lisää tärkeää asiaa...</p>
    </section>
</article>
</div>


Aside
=====
[`<aside>` on lohkotyyppinen tagi][Aside], jolla merkitään varsinaisen dokumentin tai artikkelin ohessa olevia
"sivusisältöjä", kuten uutisten yhteydessä olevia inforuutuja tai artikkelin ohessa olevia asiaan läheisesti
liittyviä muita asioita.

```
<article>
    <h2>Avaruusalus laskeutui kuuhun</h2>
    <p>Tänään keskipäivällä kuuhun laskeutui ...</p>
    <aside>
        <h4>Kuu</h4>
        <p>Kuu kiertää maapallon kerran kuukaudessa</p>
    </aside>
    <p>Kuussa käveltiin...</p>
</article>
```
<div class="html-example">
<article>
    <h2>Avaruusalus laskeutui kuuhun</h2>
    <p>Tänään keskipäivällä kuuhun laskeutui ...</p>
    <aside style="float: right; margin: 0 0.5em; border: 1px solid #666; max-width: 15em;">
        <h4 style="padding: 0 0.5em; margin: 0; background-color: #aaf;">Kuu</h4>
        <p style="padding: 0.5em;">Kuu kiertää maapallon kerran kuukaudessa</p>
    </aside>
    <p>Kuussa käveltiin...</p>
    <div style="clear: both;"></div>
</article>
</div>


Header
======
[`<header>`-tagi on lohkotyyppinen][Header] ja sillä merkitään yleensä sivun tai artikkelin alussa olevat
otsikkotiedot tai ylätunnisteen. Tyypillisesti `<header>`-elementti sisältää yhden tai
useampia otsikkotageja (`<h1>` - `<h6>`), logon tai ikonin ja ehkä sivun tai artikkelin tekijän
tietoja.


Footer
======
[`<footer>`-tagi][Footer] on myös lohkotyyppinen ja sillä merkitään sivun tai artikkelin alatunniste, jossa
on tyypillisesti yhteystietoja, tekijänoikeustietoja, artikkelin tekijän tietoja ja niin edelleen.

```
<article>
    <header>
        <img src="images/html5.png" alt="HTML5-logo">
        <h1>Www-ohjelmointi</h1>
        <h2>Lukiolaisille</h2>
    </header>
    <section>
        <p>Artikkelin sisältö.</p>
    </section>
    <footer>
        <ul>
            <li>Tekijä: Petri Salmela</li>
            <li>Osoite: <a href="http://petrit.net/www-ohjelmointi/">http://petrit.net/www-ohjelmointi/</a>
        </ul>
    </footer>
</article>
```
<div class="html-example">
<article>
    <header>
        <img src="../../images/html5.png" alt="HTML5-logo" style="float: left; height: 6em; margin-right: 2em;">
        <h1>Www-ohjelmointi</h1>
        <h2>Lukiolaisille</h2>
        <div style="clear: both;"></div>
    </header>
    <section>
        <p>Artikkelin sisältö.</p>
    </section>
    <footer style="background-color: #ddd; border-top: 2px solid #666;">
        <ul>
            <li>Tekijä: Petri Salmela</li>
            <li>Osoite: <a href="http://petrit.net/www-ohjelmointi/">http://petrit.net/www-ohjelmointi/</a>
        </ul>
    </footer>
</article>
</div>

Nav
====
[`<nav>`-tagi][Nav] on lohkotyyppinen elementti, joka on tarkoitettu sivuston navigoinnin esittämiseen.
Navigoinnin merkitseminen semanttisesti `<nav>`-tagilla on tärkeää siksi, että esimerkiksi osa
näkövammaisille tarkoitetuista ruudunlukijaohjelmista osaa jättää sillä merkityt osat sivusta
oletuksena lukematta ja toisaalta osaavat lukea ne navigointia pyydettäessä.


Strong
======
[`<strong>`-tagi][Strong] on tyypiltään rivin sisällä käytettävä tagi, jolla merkitään tekstistä tärkeitä kohtia.
Selaimet käyttävät `<strong>`-tagin ulkoasuna yleensä **lihavointia**, mutta sivun tekijä voi
tyylimäärityksillä määritellä sille haluamansa ulkoasun. Aiemmissa HTML-versioissa lihavointiin
käytettiin `<b>`-tagia (*bold*), mutta nykyisin suositellaan käyttämään `<strong>`-tagia, joka
kertoo paremmin sillä merkityn tekstiosuuden merkityksen, eli tärkeyden, eikä niinkään sen ulkoasua.

```
<p>Vähän tekstiä <strong>korostuksella</strong>.</p>
```
<div class="html-example">
<p>Vähän tekstiä <strong>korostuksella</strong>.</p>
</div>


Em
=====
[`<em>`-tagi][Em] on toinen rivitason tekstin korostamiseen tarkoitettu tagi. Selaimet käyttävät sillä
merkityn tekstin tyypillisesti *kursivoituna*. Aiemmissa HTML-versioissa kursivointiin käytettiin
usein `<i>`-tagia (*italics*), mutta nykyään `<em>`-tagi on merkitystä (*emphasise* /*korostus*) korostavana suositeltavampi.

```
<p>Vähän tekstiä <em>korostuksella</em>.</p>
```
<div class="html-example">
<p>Vähän tekstiä <em>korostuksella</em>.</p>
</div>




[Div]: http://www.w3schools.com/tags/tag_div.asp "W3Schools:Div"
[Span]: http://www.w3schools.com/tags/tag_span.asp "W3Schools:Span"
[Article]: http://www.w3schools.com/tags/tag_article.asp "W3Schools:Article"
[Section]: http://www.w3schools.com/tags/tag_section.asp "W3Schools:Section"
[Aside]: http://www.w3schools.com/tags/tag_aside.asp "W3Schools:Aside"
[Header]: http://www.w3schools.com/tags/tag_header.asp "W3Schools:Header"
[Footer]: http://www.w3schools.com/tags/tag_footer.asp "W3Schools:Footer"
[Nav]: http://www.w3schools.com/tags/tag_nav.asp "W3Schools:Nav"
[Strong]: http://www.w3schools.com/tags/tag_strong.asp "W3Schools:Strong"
[Em]: http://www.w3schools.com/tags/tag_em.asp "W3Schools:Em"