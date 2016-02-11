+++
Categories = []
Description = ""
Tags = []
Title = "Taulukot"
date = "2016-01-06T23:29:43+02:00"
weight = 60

+++

[Taulukkoa][Taulukko] käytetään riveistä ja sarakkeista koostuvan datan esittämiseen.
Esimerkiksi alkuainetaulukko tai lukujärjestys ovat lunnostaan tällaisia.

Taulukko esitetään `<table>`-tagin avulla. Ennen [tyylien](../../css/) mukaan
ottamista taulukkoon saa piirrettyä reunaviivat lisäämällä `<table>`-tagille
attribuutti `border`, jonka arvoksi annetaan reunan paksuuden kertova luku.
`<table border="1">`
(Jatkossa reunaviivat kannattaa kuitenkin luoda css-tyyleillä.)

Rivejä ja soluja
================
Taulukko sisältää rivejä, jotka merkitään `<tr>`-tagilla (*tablerow*).
Rivit taas koostuvat soluista, jotka merkitään `<td>`-tagilla (*tabledata*).
Selain luo annetuista riveistä ja niiden sisältämistä soluista oikean kokoisen
taulukon automaattisesti ja kohdistaa solut sarakkeiksi.

Taulukoiden kaikki varsinainen sisältö on kirjoitettava soluihin. Eli rakenteellisesti
taulukossa on vain rivejä ja riveissä soluja.
Eri rivit voivat sisältää eri määrän soluja. Taulukon koko päätetään eniten soluja
sisältävän rivin mukaan.

```
<table border="1">
    <tr>
        <td>Eka rivi, eka solu</td>
        <td>Eka rivi, toinen solu</td>
    </tr>
    <tr>
        <td>Toka rivi, eka solu</td>
        <td>Toka rivi, toinen solu</td>
    </tr>
</table>
```

<div class="html-example">
<table class="rawtable" border="1">
    <tr>
        <td>Eka rivi, eka solu</td>
        <td>Eka rivi, toinen solu</td>
    </tr>
    <tr>
        <td>Toka rivi, eka solu</td>
        <td>Toka rivi, toinen solu</td>
    </tr>
</table>
</div>

Otsikkosolut
============
Varsinaisten sisältösolujen lisäksi taulukoissa tarvitaan usein myös "otsikkosoluja",
joita merkitään `<th>`-tagilla (*table header*). Otsikkosolut toimivat käytännössä
täysin samoin kuin varsinaiset solutkin.

Oletuksena selaimet näyttävät otsikkosolut lihavoituina.

```
<table border="1">
    <tr>
        <th>Matti</th>
        <th>Jorma</th>
        <th>Antti</th>
    </tr>
    <tr>
        <td>6</td>
        <td>7</td>
        <td>8</td>
    </tr>
</table>
```

<div class="html-example">
<table class="rawtable" border="1">
    <tr>
        <th>Matti</th>
        <th>Jorma</th>
        <th>Antti</th>
    </tr>
    <tr>
        <td>6</td>
        <td>7</td>
        <td>8</td>
    </tr>
</table>
</div>

Solujen yhdistäminen
====================
Epäsäännöllisiä taulukoita voi tehdä yhdistelemällä soluja keskenään. Taulukon
soluja voi yhdistellä `<td>`-tagin attribuuteilla:

* `colspan` – Yhdistää solun sitä seuraavien solujen kanssa. <br>
    Saa arvokseen luvun, joka kertoo yhdistettävien solujen määrän.
* `rowspan` – Yhdistää solun alaspäin seuraavien solujen kanssa. <br>
    Saa arvokseen luvun, joka kertoo yhdistettävien solujen määrän.

```
<table border="1">
    <tr>
        <td colspan="2">_1_</td>
        <td>_3_</td>
    </tr>
    <tr>
        <td>_a_</td>
        <td>_b_</td>
        <td rowspan="2">_c_</td>
    </tr>
    <tr>
        <td>_1_</td>
        <td>_2_</td>
    </tr>
</table>
```

<div class="html-example">
<table class="rawtable" border="1">
    <tr>
        <td colspan="2" style="background-color: #fd0;">_1_</td>
        <td>_3_</td>
    </tr>
    <tr>
        <td>_a_</td>
        <td>_b_</td>
        <td rowspan="2" style="background-color: #fd0;">_c_</td>
    </tr>
    <tr>
        <td>_1_</td>
        <td>_2_</td>
    </tr>
</table>
</div>



Taulukon otsikko
================
Koko taulukolle voi antaa otsikon tai "kuvatekstin" tagilla `<caption>`.
Tagi tulee heti ensimmäiseksi `<table>`-tagin sisään.

```
<table border="1">
    <caption>Poikien tulokset</caption>
    <tr>
        <th>Matti</th>
        <th>Jorma</th>
        <th>Antti</th>
    </tr>
    <tr>
        <td>6</td>
        <td>7</td>
        <td>8</td>
    </tr>
</table>
```

<div class="html-example">
<table class="rawtable" border="1">
    <caption>Poikien tulokset</caption>
    <tr>
        <th>Matti</th>
        <th>Jorma</th>
        <th>Antti</th>
    </tr>
    <tr>
        <td>6</td>
        <td>7</td>
        <td>8</td>
    </tr>
</table>
</div>



Taulukon sisäinen ryhmittely
============================
Taulukon rivejä voidaan ryhmitellä `<thead>`-, `<tbody>`- ja `<tfoot>`-tageilla
taulukon ylätunnisteeksi, varsinaiseksi sisällöksi sekä alatunnisteeksi. Nämä tagit
tulevat suoraan `<table>`-tagin sisään ja niiden sisään tulee taulukon rivejä `<tr>`-tageilla.
`<thead>`- ja `<tfoot>`-tageja voi taulukossa olla yksi kumpaakin, mutta `<tbody>`-tageja voi olla useampi.

Ryhmittely mahdollistaa muun muassa taulukon tyylittelyn css-säännöillä normaalia tehokkaammin.
Erityisen hyödyllistä voi olla mahdollisuus skrollata `<tbody>`-tagin sisällä olevia
datarivejä `<thead>`- ja `<tfoot>`-tageihin laitetuista otsikkoriveistä riippumattomasti.
Näin saadaan taulukon otsikkorivit pysymään koko ajan näkyvissä, vaikka dataa on paljon.

Toinen vastaava tilanne voi olla tulostettaessa, jos taulukko jatkuu useammalle sivulle.
Erottelemalla taulukon ylä- ja alatunnisteen, on mahdollista saada ne tulostumaan taulukon
jokaiselle sivulle.

```
<table border="1">
    <caption>Poikien tulokset</caption>
    <thead>
        <tr>
            <th>Matti</th>
            <th>Jorma</th>
            <th>Antti</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>6</td>
            <td>7</td>
            <td>8</td>
        </tr>
        <tr>
            <td>9</td>
            <td>10</td>
            <td>11</td>
        </tr>
    </tbody>
    <tfoot>
        <tr>
            <th>Matti</th>
            <th>Jorma</th>
            <th>Antti</th>
        </tr>
    </tfoot>
</table>
```

<div class="html-example">
<table class="rawtable" border="1">
    <caption>Poikien tulokset</caption>
    <thead>
        <tr>
            <th>Matti</th>
            <th>Jorma</th>
            <th>Antti</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>6</td>
            <td>7</td>
            <td>8</td>
        </tr>
        <tr>
            <td>9</td>
            <td>10</td>
            <td>11</td>
        </tr>
    </tbody>
    <tfoot>
        <tr>
            <th>Matti</th>
            <th>Jorma</th>
            <th>Antti</th>
        </tr>
    </tfoot>
</table>
</div>


Taulukon sisällä
================
Taulukon sisällä voi olla lähes mitä tahansa HTML-sisältöä.

```
<table border="1">
    <tr>
        <td>Vain tekstiä</td>
        <td>
            <h1>Tässä on otsikko</h1>
            <p>Tässä taas tekstikappale</p>
        </td>
    </tr>
    <tr>
        <td>
            Solussa voi olla lista
            <ul>
                <li>Lista-eka</li>
                <li>Lista-toka</li>
            </ul>
        </td>
        <td>
            Tai, kuten listoissa, taulukossa voi olla taulukko
            <table border="1">
                <tr>
                    <td>A</td>
                    <td>B</td>
                </tr>
                <tr>
                    <td>C</td>
                    <td>D</td>
                </tr>
            </table>
        </td>
    </tr>
</table>
```

<div class="html-example">
<table class="rawtable" border="1">
    <tr>
        <td>Vain tekstiä</td>
        <td>
            <h1>Tässä on otsikko</h1>
            <p>Tässä taas tekstikappale</p>
        </td>
    </tr>
    <tr>
        <td>
            Solussa voi olla lista
            <ul>
                <li>Lista-eka</li>
                <li>Lista-toka</li>
            </ul>
        </td>
        <td>
            Tai, kuten listoissa, taulukossa voi olla taulukko
            <table class="rawtable" border="1">
                <tr>
                    <td>A</td>
                    <td>B</td>
                </tr>
                <tr>
                    <td>C</td>
                    <td>D</td>
                </tr>
            </table>
        </td>
    </tr>
</table>
</div>

[Taulukko]: http://www.w3schools.com/html/html_tables.asp "W3Schools:Taulukko"