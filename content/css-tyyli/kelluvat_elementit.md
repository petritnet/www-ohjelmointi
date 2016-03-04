+++
Categories = []
Description = ""
Tags = []
Title = "Kelluvat elementit"
date = "2016-02-10T21:31:45+02:00"
weight = 100

+++

Toinen keino irrottaa elementtejä normaalista elementtijärjestyksestä
on niiden *kelluttaminen*, eli `float`-ominaisuuden käyttö. Elementtien
sijoittelu `position`-ominaisuudella on toisinaan tarpeellista, mutta
usein kätevämpi tapa elementin paikan määräämiseen on sen määrääminen
kelluvaksi.

Kellutus on toimiva tapa esimerkiksi pitkän juoksevan tekstin seassa
olevien kuvien sijoitteluun. Normaalistihan `<img>`-elementit ovat
`inline-block`-tyyppisiä, eli asettuvat tekstiriville yksittäisen
kirjaimen tavoin.

Kellutettaessa elementti sijoitetaan normaalin elementtivirran jompaankumpaan
reunaan, vasemmalle tai oikealle, ja muut sen jälkeen tulevat elementit tai
tekstit kiertävät sen ympäri.

Float
=====
`float`-ominaisuus voi saada arvokseen jonkin kolmesta avainsanasta
`left`, `right` tai `none` sen mukaan halutaanko kelluttaa vasemmalle,
oikealle vai purkaa kellutus.

- Tekstitason sisältö (`inline`- ja `inline-block`-elementit) kiertää
  automaattisesti kellutettuja elementtejä.
- Lokotason elementit piirretään ikään kuin kellutettuja elementtejä
  ei olisi olemassa. Ne voivat siis jäädä (`z-index`-arvosta riippuen)
  kellutettujen elementtien alle tai päälle.

```css
p {
    width: 70%;
    margin: 0 auto;
    text-align: justify;
}

.kelluva {
    float: right;
    margin: 0.5em 0 0.5em 0.5em;
}

```
```html
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus maximus
gravida pulvinar. Donec ut metus fermentum, elementum ipsum nec, aliquam
lacus. <img src="ghost-penguin.png"> Sed eu tortor ex. Curabitur ligula tellus, scelerisque non dapibus
venenatis, tempus porttitor diam. In hac habitasse platea dictumst. Praesent
eu lacinia ex. Etiam scelerisque viverra lorem, ut fringilla enim gravida et.
Praesent venenatis nisi id sagittis laoreet. Nullam vitae risus efficitur, facilisis
justo vitae, mollis felis. <img src="ghost-penguin.png" class="kelluva">
Pellentesque ac efficitur urna. Nam ultricies diam
ut efficitur tincidunt. Ut vulputate pretium justo, sit amet maximus tortor
aliquet sed. Morbi ut lectus euismod, tempor tellus vel, finibus erat. Praesent
rhoncus, velit sit amet varius fringilla, lorem est commodo odio, eu ullamcorper
nisl nulla nec nunc. Vivamus facilisis, justo nec vestibulum gravida, mauris diam
consectetur felis, accumsan gravida eros risus nec massa. Quisque lobortis ut est
vitae porttitor. 
</p>
```
<div class="html-example">
<p style="width: 70%; margin: 0 auto; text-align: justify;">
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus maximus
gravida pulvinar. Donec ut metus fermentum, elementum ipsum nec, aliquam
lacus. <img src="../../images/ghost-penguin.png"> Sed eu tortor ex. Curabitur ligula tellus, scelerisque non dapibus
venenatis, tempus porttitor diam. In hac habitasse platea dictumst. Praesent
eu lacinia ex. Etiam scelerisque viverra lorem, ut fringilla enim gravida et.
Praesent venenatis nisi id sagittis laoreet. Nullam vitae risus efficitur, facilisis
justo vitae, mollis felis.
<img src="../../images/ghost-penguin.png" style="float: right; margin: 0.5em 0 0.5em 0.5em;">
Pellentesque ac efficitur urna. Nam ultricies diam
ut efficitur tincidunt. Ut vulputate pretium justo, sit amet maximus tortor
aliquet sed. Morbi ut lectus euismod, tempor tellus vel, finibus erat. Praesent
rhoncus, velit sit amet varius fringilla, lorem est commodo odio, eu ullamcorper
nisl nulla nec nunc. Vivamus facilisis, justo nec vestibulum gravida, mauris diam
consectetur felis, accumsan gravida eros risus nec massa. Quisque lobortis ut est
vitae porttitor. 
</p>
</div>

Useampia elementtejä voidaan kelluttaa samaan reunaan (tai eri reunoihin). Jos
peräkkäin kellutetut elementit mahtuvat rinnakkain, ne asettuvat rinnakkain.
Tämä mahdollistaa siis esimerkiksi useamman elementin asettelun rinnakkain.

```css
.ulompi {background-color: #ffa; padding: 1em; margin: 1em; min-height: 2em;}
.laatikko {width: 3em; height: 1em; padding: 0.5em; border: 1px solid black;}
.toka .laatikko {float: left;}
.kolmas .laatikko {float: right;}
```
```html
<div class="ulompi eka">
    <div class="laatikko">div1</div>
    <div class="laatikko">div2</div>
    <div class="laatikko">div3</div>
    <div class="laatikko">div4</div>
    <div class="laatikko">div5</div>
</div>
<div class="ulompi toka">
    <div class="laatikko">div1</div>
    <div class="laatikko">div2</div>
    <div class="laatikko">div3</div>
    <div class="laatikko">div4</div>
    <div class="laatikko">div5</div>
</div>
<div class="ulompi kolmas">
    <div class="laatikko">div1</div>
    <div class="laatikko">div2</div>
    <div class="laatikko">div3</div>
    <div class="laatikko">div4</div>
    <div class="laatikko">div5</div>
</div>
```
<div class="html-example">
<div style="padding: 1em; margin: 1em; clear: both; min-height: 2em;">
    <div style="width: 3em; height: 1em; border: 1px solid black; padding: 0.5em;">div1</div>
    <div style="width: 3em; height: 1em; border: 1px solid black; padding: 0.5em;">div2</div>
    <div style="width: 3em; height: 1em; border: 1px solid black; padding: 0.5em;">div3</div>
    <div style="width: 3em; height: 1em; border: 1px solid black; padding: 0.5em;">div4</div>
    <div style="width: 3em; height: 1em; border: 1px solid black; padding: 0.5em;">div5</div>
</div>
<div style="padding: 1em; margin: 1em; clear: both; min-height: 2em;">
    <div style="width: 3em; height: 1em; border: 1px solid black; padding: 0.5em; float: left;">div1</div>
    <div style="width: 3em; height: 1em; border: 1px solid black; padding: 0.5em; float: left;">div2</div>
    <div style="width: 3em; height: 1em; border: 1px solid black; padding: 0.5em; float: left;">div3</div>
    <div style="width: 3em; height: 1em; border: 1px solid black; padding: 0.5em; float: left;">div4</div>
    <div style="width: 3em; height: 1em; border: 1px solid black; padding: 0.5em; float: left;">div5</div>
</div>
<div style="padding: 1em; margin: 1em; clear: both; min-height: 2em;">
    <div style="width: 3em; height: 1em; border: 1px solid black; padding: 0.5em; float: right;">div1</div>
    <div style="width: 3em; height: 1em; border: 1px solid black; padding: 0.5em; float: right;">div2</div>
    <div style="width: 3em; height: 1em; border: 1px solid black; padding: 0.5em; float: right;">div3</div>
    <div style="width: 3em; height: 1em; border: 1px solid black; padding: 0.5em; float: right;">div4</div>
    <div style="width: 3em; height: 1em; border: 1px solid black; padding: 0.5em; float: right;">div5</div>
</div>
</div>

Clear
=====

Mikäli jokin elementti halutaan piirtää kelluvien elementtien perään, eli "unohtavan" elementtien kellumisen,
sille voidaan käyttää css:n `clear`-ominaisuutta. Ominaisuus voi saada arvokseen jonkin avainsanoista
`left`, `right` tai `both` riippuen siitä, halutaanko sen "unohtavan" vasemman, oikean vai molempien puolten
elementtien kellutukset. Elementti, jolle on asetettu `clear`-ominaisuus, siis "putsaa" tai "tyhjentää" kaikki
meneillään olevat halutun puolen kellutukset.

Kellutuksen käyttökohteita
==========================
Elementtien kellutus on kätevää erityisesti, kun:

- Halutaan saada kuvan, taulukon tai muu elementti tekstipalstan yhteyteen niin, että teksti kiertää sitä.
- Halutaan saada useampi kuin yksi elementti rinnakkain. (esimerkiksi valikko vasemmalle ja sisältö oikealle)
- Halutaan saada useampi kuin yksi lohkotason elementti rinnakkain.
