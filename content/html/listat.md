+++
Categories = []
Description = ""
Tags = []
Title = "Listat"
date = "2016-01-06T23:28:13+02:00"
weight = 50

+++

HTML-kielessä voi määritellä useamman tyyppisiä listoja:

- numeroimattomia listoja (kuten tämä)
- numeroituja listoja
- määritelmälistoja

Listat koostuvat itse listasta ja sen sisällä olevista lista-alkioista.

Numeroimaton lista
==================
[Numeroimaton lista][Lista] esitetään `<ul>`-tagilla (*unordered list*). Listan yksittäiset
alkiot luetellaan `<ul>`- ja `</ul>`-merkintöjen välissä `<li>`-tagilla merkittyinä.

Numeroimaton lista esitetään selaimissa oletuksena tyypillisesti "palluralistana".

```
<h2>Hedelmiä</h2>
<ul>
    <li>Omena</li>
    <li>Banaani</li>
    <li>Appelsiini</li>
</ul>
```

<div class="html-example">
<h2>Hedelmiä</h2>
<ul>
    <li>Omena</li>
    <li>Banaani</li>
    <li>Appelsiini</li>
</ul>
</div>

Numeroitu lista
==================
[Numeroitu lista][Lista] esitetään vastaavasti kuin numeroimaton, mutta käyttämällä `<ol>`-tagia
(*ordered list*). Numeroimattoman listan tavoin lista-alkiot ympäröidään `<li>`-tagilla.

Oletuksena selaimet numeroivat listan alkiot kokonaisluvuilla luvusta yksi alkaen.

```
<h2>Juoksukilpailun tulokset</h2>
<ol>
    <li>Antti</li>
    <li>Jaana</li>
    <li>Liisa</li>
    <li>Pekka</li>
</ol>
```

<div class="html-example">
<h2>Juoksukilpailun tulokset</h2>
<ol>
    <li>Antti</li>
    <li>Jaana</li>
    <li>Liisa</li>
    <li>Pekka</li>
</ol>
</div>

Määritelmälista
==================
Kolmantena listatyyppinä oleva [määritelmälista][Deflista] poikkeaa kahdesta
aiemmasta. Sen tagina on `<dl>` (*description list*), mutta listan sisällä ei
olekaan yksittäisiä lista-alkioita vaan *termejä* ja *määritelmiä*/*kuvauksia*.
Termit merkitään `<dt>`-tagilla (*term*) ja niiden kuvaukset `<dd>`-tagilla (*description*).

Tällä listatyypillä voidaan luoda erilaisia avain–arvo -muotoisia luetteloita,
kuten sanakirjoja tai tekijäluetteloita. Kunkin termin on tarkoitus esiintyä listassa
vain kerran, mutta samaan termiin voi olla liitettynä useampia kuvauksia tai useammalla
termillä voi olla yhteinen kuvaus.

Selaimet näyttävät yleensä oletuksena kuvaukset sisennettyinä.

```
<h4>Juomia</h4>
<dl>
    <dt>Kahvi</dt>
    <dd>Musta ja kuuma juoma</dd>
    <dt>Maito</dt>
    <dd>Valkoinen ja kylmä juoma</dd>
</dl>

<h4>Tekijät</h4>
<dl>
    <dt>Ohjaajat:</dt>
    <dd>Tapio Piirainen</dd>
    <dt>Näyttelijät:</dt>
    <dd>Kai Lehtinen</dd>
    <dd>Mari Rantasila</dd>
    <dt>Musiikki:</dt>
    <dd>Tapio Piirainen</dd>
    <dd>Mari Rantasila</dd>
</dl>
```

<div class="html-example">
<h4>Juomia</h4>
<dl>
    <dt>Kahvi</dt>
    <dd>Musta ja kuuma juoma</dd>
    <dt>Maito</dt>
    <dd>Valkoinen ja kylmä juoma</dd>
</dl>

<h4>Tekijät</h4>
<dl>
    <dt>Ohjaajat:</dt>
    <dd>Tapio Piirainen</dd>
    <dt>Näyttelijät:</dt>
    <dd>Kai Lehtinen</dd>
    <dd>Mari Rantasila</dd>
    <dt>Musiikki:</dt>
    <dd>Tapio Piirainen</dd>
    <dd>Mari Rantasila</dd>
</dl>
</div>

Sisäkkäiset listat
==================
Listoja voi käyttää myös sisäkkäin, eli muodostaa alilistoja. Tällöin lista-alkion `<li>`- ja `</li>`-merkintöjen
väliin kirjoitetaan uusi `<ul>`- tai `<ol>`-lista.

Selaimet näyttävät sisällä olevan listan automaattisesti sisennettynä. Erilaisia listatyyppejä voi sekoitella vapaasti.

```
<ol>
    <li>Ensimmäisen tason alkioita
        <ul>
            <li>Toisen tason alkioita
                <ol>
                    <li>Kolmannen tason ensimmäinen alkio</li>
                    <li>Kolmannen tason toinen alkio</li>
                </ol>
            </li>
            <li>Toisen tason alkioita</li>
        </ul>
    </li>
    <li>Ensimmäisen tason alkioita</li>
</ol>
```

<div class="html-example">
<ol>
    <li>Ensimmäisen tason alkioita
        <ul>
            <li>Toisen tason alkioita
                <ol>
                    <li>Kolmannen tason ensimmäinen alkio</li>
                    <li>Kolmannen tason toinen alkio</li>
                </ol>
            </li>
            <li>Toisen tason alkioita</li>
        </ul>
    </li>
    <li>Ensimmäisen tason alkioita</li>
</ol>
</div>

Listojen attribuutteja
======================
Järjestettyjen listojen toimitaa voi muokata jonkin verran antamalla niille sopivia attribuutteja.

* `start` – asettaa listalle aloitusarvon
* `type` – asettaa listan laskurin tyypin
    - `1` numero
    - `A` isot kirjaimet
    - `a` pienet kirjaimet
    - `I` isot roomalaiset numerot
    - `i` pienet roomalaiset numerot

Myös lista-alkiolle `<li>` voi antaa tyypin (`type`) sekä numeroarvon attribuutilla `value`.

```
<ol type="a" start="20">
    <li>Kahvia</li>
    <li type="I" value="3">Teetä</li>
    <li>Maitoa</li>
    <li value="42">Vettä</li>
    <li type="1">Kolajuomaa</li>
</ol>
```

<div class="html-example">
<ol type="a" start="20">
    <li>Kahvia</li>
    <li type="I" value="3">Teetä</li>
    <li>Maitoa</li>
    <li value="42">Vettä</li>
    <li type="1">Kolajuomaa</li>
</ol>
</div>

Harjoituksia
============
Harjoittele tähän saakka opittua muotoilemalla [Wikipediasta kopioitu artikkeli][Liftari]
HTML-sivun muotoon. Kannattaa tehdä sivusta oma kopio. (JSBinin valikosta File -> Clone)

1. Lisää tekstiin `<html>`-, `<head>`- ja `<body>`-tagit
2. head-osioon otsikko `<title>`-tagilla ja merkistökoodaus `<meta>`-tagilla.
3. Merkitse body-osioon otsikot ja eritasoiset alaotsikot, tekstikappaleet sekä listat.
4. Merkitse tekstiin muutamia linkkejä muihin Wikipedia-artikkeleihin, erityisesti lopun "Katso myös"-osioon.
5. Korosta kirjojen ja elokuvien nimet.


[Lista]: http://www.w3schools.com/html/html_lists.asp "W3Schools:Listat"
[Deflista]: http://www.w3schools.com/TAGS/tag_dl.asp "W3Schools:Määritelmälista"

[Liftari]: https://jsbin.com/faqugo/latest/edit "Linnunradan käsikirja liftareille"