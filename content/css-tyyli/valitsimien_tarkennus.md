+++
Categories = []
Description = ""
Tags = []
Title = "Valitsimien tarkennus"
date = "2016-03-05T23:21:04+02:00"
weight = 130

+++

Aiemmin todettiin, että valitsimissa voidaan käyttää tagien nimiä,
elementin id:tä, elementin luokkaa, pseudo-luokkaa, pseudo-elementtiä
tai elementtien attribuutteja ja niiden arvoja. Valitsin koostuu
näiden yhdistelmistä, joissa samaan elementtiin viittaavat osat
on kirjoitettu yhteen, sisäkkäin olevat elementit välilyönnillä
eroteltuina peräkkäin ja rinnakkaiset vaihtoehtoiset valitsimet
samalle säännölle on eroteltu pilkulla.

Nyt lisätään valitsinten käsittelyyn vielä muutama keino, joilla
valitsimen kohdistamista haluttuun elementtiin voidaan tarkentaa.

Välitön jälkeläinen
===================

Välilyönnillä eroteltuna peräkkäin kirjoitetut valitsimet tarkoittavat
siis elementtien sisäkkäisyyttä. Eli `article .important` tarkoittaa
siis `<article>`-tagin sisällä olevaa elementtiä, jolla on luokka `important`.
Sillä ei ole väliä, onko `.important`-elementti heti `<article>`-elementin
lapsi vai onko välissä yksi tai useampikin taso.

```css
article .important {background-color: #faa;}
```
```
<article>
    <p class="important">Lorem ipsum dolor sit amet, consectetur...</p>
    <p>Lorem ipsum <span class="important">dolor sit</span> amet, consectetur...</p>
</article>
```
<div class="html-example">
<style type="text/css" scoped>
article .important {background-color: #faa;}
</style>
<article>
    <p class="important">Lorem ipsum dolor sit amet, consectetur...</p>
    <p>Lorem ipsum <span class="important">dolor sit</span> amet, consectetur...</p>
</article>
</div>

Jos kuitenkin halutaan valitsimessa määrätä, että jokin elementti on toisen
välitön jälkeläinen, merkitään tämä jälkeläisyysrelaatio `>`-merkillä.
Siis välittömästi `<article>`-elementin lapsena oleva `.important`-elementti
valitaan valitsimella `article > .important`.

```css
article > .important {background-color: #faa;}
```
```
<article>
    <p class="important">Lorem ipsum dolor sit amet, consectetur...</p>
    <p>Lorem ipsum <span class="important">dolor sit</span> amet, consectetur...</p>
</article>
```
<div class="html-example">
<style type="text/css" scoped>
article > .important {background-color: #faa;}
</style>
<article>
    <p class="important">Lorem ipsum dolor sit amet, consectetur...</p>
    <p>Lorem ipsum <span class="important">dolor sit</span> amet, consectetur...</p>
</article>
</div>


Seuraava elementti
==================

Toinen hyödyllinen merkintä on *seuraajarelaatio*, jota merkitään `+`-merkillä.
Tämä tarkoittaa, että esimerkiksi `important`-luokalla merkityn elementin jälkeen tulevaan
`<p>`-elementtiin voidaan viitata valitsimella `.important + p`.

```css
.important + p {background-color: #ffa;}
```
```
<article>
    <p class="important">Lorem ipsum dolor sit amet, consectetur...</p>
    <p>Lorem ipsum dolor sit amet, consectetur...</p>
</article>
```
<div class="html-example">
<style type="text/css" scoped>
.important + p {background-color: #ffa;}
</style>
<article>
    <p class="important">Lorem ipsum dolor sit amet, consectetur...</p>
    <p>Lorem ipsum dolor sit amet, consectetur...</p>
</article>
</div>
