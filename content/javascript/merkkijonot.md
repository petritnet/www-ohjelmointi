+++
Categories = []
Description = ""
Tags = []
Title = "Merkkijonot"
date = "2016-03-10T00:04:39+02:00"
weight = 50

+++

Merkkijonot ovat toinen hyvin useasti käsiteltävät tyyppi. Merkkijono on
tyypiltään `string`.

```
typeof 'www-kurssi'     // 'string
```

Pituus
======
Merkkojonolla on aina pituus, joka löytyy aina sen `length`-ominaisuudesta.

```
"Maijal oli karitsa".length            // 18

var kurssi = 'www-ohjelmointi';
kurssi.length                          // 15
```

Indeksointi
===========
Merkkijonot ovat nimensä mukaisesti jono merkkejä. Merkit ovat siis
tietyssä järjestyksessä ja niiden sijainnit ovat numeroidut *indekseillä*.
Javascriptissä, kuten suurimmassa osassa ohjelmointikielistä,
merkkien paikkojen numerointi alkaa nollasta.

Merkkijonon paikassa `n` olevaan kirjaimeen voi viitata hakasuljemerkinnällä
`muuttujanNimi[n]`.

```
"Kissa"[0]                 // 'K'

var elain = 'Koira';
elain[2]                   // 'i'
elain[elain.length - 1]    // 'a'    (viimeinen kirjain)
```

Merkkijonolta voi kysyä yksittäisen merkin ensimmäisen esiintymän indeksiä
metodilla `indexOf()`. Jos merkki esiinty useammin, kuin kerran, palautetaan
ensimmäisen esiintymän indeksi. Jos merkkiä ei löydy merkkijonosta, on
paluaarvona `-1`.

```
var elain = "Koira";
elain.indexOf('i');          // 2
elain = "Kissa";
elain.indexOf('s')           // 2   (ensimmäinen 's'-kirjain)
elain.indexOf('r')           // -1  (ei löytynyt)
```

Merkkijonojen yhdistäminen
==========================
Merkkijonoja voidaan katenoida, eli kirjoittaa yhteen `+`-operaattorilla.

```javascript
"www-" + "kurssi"          // "www-kurssi"
```

Osamerkkijono
=============
Merkkijonoista voi kopioida alimerkkijonon kahdella eri metodilla. Näistä `substring(alku, loppu)`
saa kaksi parametria, joista ensimmäinen kertoo indeksin, josta haluttu merkkijono alkaa
ja toinen kertoo ensimmäisen pois jäävän merkin indeksin. Jos toinen parametri jätetään
pois, saadaan paluuarvona alimerkkijono aloituskohdasta merkkijonon loppuun saakka.
Aloitus- ja lopetusindeksit voidaan kertoa myös "takaperin".

```javascript
"Linnanmäki".substring(2, 8)      // "nnanmä"
"Linnanmäki".substring(8, 2)      // "nnanmä"
"Linnanmäki".substring(5)         // "nmäki"
```

Toinen metodi, jolla merkkijonosta saadaan leikattua pätkiä, on `substr(alku, pituus).
Tämä metodi toimii muuten samoin kuin `substring()`, mutta jälkimmäinen parametri ei
olekaan indeksi vaan merkkijonosta leikattavan osuuden pituus.

Lisäksi `substr()` huolii indeksiksi myös negatiivisen luvun, jolloin sijainnin
laskeminen aloitetaankin lopusta. Indeksi `-1` on viimeinen kirjain, `-2` toiseksi
viimeinen ja niin edelleen.

```javascript
"Aurajoki".substr(2, 2)      // "ra"
"Aurajoki".substr(2)         // "rajoki"
"Aurajoki".substr(-3)        // "oki"
```

Erikoismerkit
=============

On joitain erikoismerkkejä, joita on hankala kirjoittaa merkkijonoon suoraan.
Esimerkiksi rivinvaihtoja ei voida kirjoittaa merkkijonoihin suoraa sellaisenaan.
Näiden merkkien kirjoittamiseen käytetään takakenomerkin `\` avulla kirjoitettavia
"escape-komentoja". Näistä tärkeimpiä ovat esimerkiksi:

| Escape     | Merkitys                        |
|------------|---------------------------------|
| `\n`       | Rivinvaihto                     |
| `\t`       | Tabulaattorimerkki              |
| `\'`       | Yksöislainausmerkki             |
| `\"`       | Kaksoislainausmerkki            |
| `\\`       | Takakeno                        |
| `\udddd`   | Unicode-merkki neljällä heksadesimaalinumerolla. Esimerkiksi <code>&#x00a9;</code> on `\u00A9`  |

Esimerkiksi:

```javascript
var merkkijono = "Pekka sanoi: \t \"Olipa hyvä elokuva.\"\nOlli vastasi: \t \"Niin oli.\"\n\\o/\n\u262D \u2602";
console.log(merkkijono);
```
<div class="html-example">
<style type="text/css" scoped>
.koodia {font-family: monospace; font-size: 150%; white-space: pre;}
</style>
<div class="koodia">
Pekka sanoi: 	 "Olipa hyvä elokuva."
Olli vastasi: 	 "Niin oli."
\o/
&#x262d; &#x2602;
</div>
</div>
