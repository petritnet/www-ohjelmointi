+++
Categories = []
Description = ""
Tags = []
Title = "Objektit ja taulukot"
date = "2016-03-10T00:08:00+02:00"
weight = 60

+++

Objekti
=======

Javascriptin tietotyypeistä objektit, eli `object`, on varsinainen "sveitsinlinkkari", joka soveltuu joustavuutensa
vuoksi lähes mihin tahansa. Kuten aiemmin todettiin, objektit ovat käytännössä avain–arvo-pareja, joissa avain
on merkkijono ja arvo mitä tahansa tyyppiä oleva muuttujaan sijoitettavissa oleva arvo. Esimerkiksi numero,
merkkijono, totuusarvo, objekti, array tai funktio.

Uuden tyhjän objektin voi luoda aaltosulkeilla `{}` tai pyytämällä uusi objekti kirjoittamalla `new Object()`.
Objektiin voi laittaa ominaisuuksia suoraan luontivaiheessa aaltosulkeiden välissä.

```javascript
var autoni = {
    merkki: 'Ford',
    malli: 'Mustang',
    vuosi: 1969
};
```

Objektin ominaisuuksien arvoja voi sijoittaa tai muuttaa pistenotaatiolla muodossa: `objektinNimi.ominaisuus = uusiArvo`.

```javascript
var autoni = {};
autoni.merkki = 'Ford';
autoni.malli = 'Mustang';
autoni.vuosi = 1969;
```

Vaihtoehtoisesti objektin ominaisuuteen voi viitata pistenotaation sijasta myös hakasuljenotaatiolla:
`objektinNimi['ominaisuus']`.

```javascript
autoni['merkki'] = 'Ford';
autoni['malli'] = 'Mustang';
autoni['vuosi'] = 1969;
```

Hakasuljemerkinnässä hakasulkeiden väliin tulee ominaisuuden nimi **merkkijonona**. Tästä on ainakin kahdenlaista
hyötyä. Ensinnäkin, jos ominaisuuden nimi sisältää erikoismerkkejä, kuten `-`, `.` tai välilyönti, ei niitä voida
käyttää pistenotaatiolla. Toiseksi, hakasuljemerkintä tekee mahdolliseksi viitata ominaisuuteen, jonka nimi on
tallennettu muuttujaan. Tämä tuo objektien käyttöön dynaamisuutta. Tämäkään ei ole mahdollista pistenotaatiolla.

```javascript
var uusiObj = new Object(),
    str = 'Merkkijono',
    rand = Math.random(),
    olio = new Object();
    
uusiObj.type             = 'Pistenotaatio';
uusiObj['oma avain']     = 'Avaimessa välilyönti';
uusiObj[str]             = 'Avain merkkijonomuuttujassa';
uusiObj[rand]            = 'Avaimena satunnaisluku';      // Avaimeksi tulee rand muunnettuna merkkijonoksi!
uusiObj[obj]             = 'Objekti';         // Avaimeksi tulee objektin sijasta merkkijono '[object Object]' !!!
uusiObj['']              = 'Tyhjä merkkijono!';

console.log(uusiObj);
```

Taulukko eli Array
===================

Taulukko, eli `array`, on objekti, joka on tarkoitettu erityisesti järjestetyn alkiojoukon luomiseen ja käsittelyyn.
Taulukko eroaa tavallisesta objektista siinä, että sen avaimina käytetään kokonaislukuja ja sillä on `length`-ominaisuus,
joka kertoo aina sen pituuden. (Pituus on yhtä pienempi kuin suurin käytössä oleva indeksi.) Kuten tavallisilla objekteilla,
Taulukkoon tallennetut arvot voivat olla mitä tahansa tyyppiä, myös funktioita.

Indeksit
--------

Taulukon avaimina olevia numeroita kutsutaan indekseiksi ja tietyllä indeksillä olevaan paikkaa viitataan
hakasuljemerkinnällä aivan samoin kuin objekteillakin.

```javascript
var lista = [1, 'merkkijono', true, {key: 'value'}, [1,2,3,4], function(a){return a+1;}];
lista.length;        // 6                 arrayn pituus
lista[0];            // 1                 paikalla 0 oleva arvo
lista[3].key;        // 'value'           paikalla 3 olevan objektin ominaisuus 'key'
lista[4];            // [1, 2, 3, 4]      paikalla 4 on array
lista[4][1];         // 2                 paikalla 4 olevan arrayn paikalla 1 oleva arvo
lista[5](4);         // 5                 paikalla 5 on funktio, joka suoritetaan parametrilla 4
```

Taulukkoon voidaan myös sijoittaa uusia arvoja indeksin avulla. Jos taulukkoon lisätään uusia arvoja
yli taulukon nykyisen pituuden, taulukon pituus kasvaa ja väliin jäävillä indekseillä olevat paikat
jäävät tyhjiksi, arvoina määrittelemätön, eli `undefined`.

```javascript
var lista = ['a', 'b', 'c'];
console.log(lista.length);        // 3
lista[9] = 'j';
console.log(lista.length);        // 10
console.log(lista);               // ['a', 'b', 'c',,,,,,,'j']
```

Samoin kuin merkkijonolta, myös taulukolta voi kysyä, monentenako kysytty alkio on taulukossa, `indexOf()`-metodilla.
Jos alkio on taulukossa, vastaus on ensimmäinen indeksi, josta se löytyy. Jos alkiota ei ole taulukossa, on vastaus `-1`.
Jos alkio on taulukossa useasti, vastauksena on ensimmäinen indeksi, josta se löytyy. Löydettävän alkion tulee olla
operaattorin `===` kannalta sama kuin haettavan. Ei siis riitä, että se on vain samanlainen, vaan sen on oltava sama.

```javascript
var lista = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'a', 'b', 'c',];
lista.indexOf('c');          // 2
lista.indexOf('h');          // -1

var arvoja = [1, 2, 3, 0, 5, false, true];
arvoja.indexOf(false);       // 5
```

Jono- ja pino-operaatiot
---------------

Taulukoille ovat käytettävissä metodit, jotka käsittelevät niitä jonon tai pinon tapaan.
Tämä tarkoittaa alkioiden lisäämistä ja poistamista taulukon päihin tai päistä. Nämä
operaatiot muuttavat taulukon pituutta.

Metodit ovat:

| Metodi        | Toiminto                          | Palauttaa                   | Esimerkki               |
|---------------|-----------------------------------|-----------------------------|-------------------------|
| `push()`      | Lisää alkioita taulukon loppuun   | Taulukon uusi pituus        | `lista.push('Aku')`     |
| `pop()`       | Poistaa alkion taulukon lopusta   | Taulukon viimeisen alkion   | `lista.pop()`           |
| `unshift()`   | Lisää alkion taulukon alkuun      | Taulukon uusi pituus        | `lista.unshift('Mikki') |
| `shift()`     | Poistaa alkioita taulukon alusta  | Taulukon ensimmäinen alkion | `lista.shift()          |

Esimerkiksi:

```javascript
var lista = ['Aku', 'Mikki', 'Hessu'];
lista.push('Iines');                      // lista === ['Aku', 'Mikki', 'Hessu', 'Iines']
lista.push('Tupu', 'Hupu', 'Lupu');       // lista === ['Aku', 'Mikki', 'Hessu', 'Iines', 'Tupu', 'Hupu', 'Lupu']
lista.length                              // 7
var pojat = [];
pojat.push(lista.pop());                  // pojat === ['Lupu'], lista === ['Aku', 'Mikki', 'Hessu', 'Iines', 'Tupu', 'Hupu']
pojat.push(lista.pop());                  // pojat === ['Lupu', 'Hupu'], lista === ['Aku', 'Mikki', 'Hessu', 'Iines', 'Tupu']
pojat.push(lista.pop());                  // pojat === ['Lupu', 'Hupu', 'Tupu'], lista === ['Aku', 'Mikki', 'Hessu', 'Iines']
lista.unshift('Pluto');                   // lista === ['Pluto', 'Aku', 'Mikki', 'Hessu', 'Iines']
var koira = lista.unshift();              // koira === 'Pluto', lista === ['Aku', 'Mikki', 'Hessu', 'Iines']
```

Muita taulukko-operaatioita
---------------------

Taulukosta voidaan kopioida keskeltä osia `slice()`-metodilla. Tämä toimii samaan tapaan kuin merkkijonojen
`substring()`-metodi. Sen syntaksi on: `taulukko.slice(alku, loppu)`. Se palauttaa uuden taulukon, jossa ovat
alkuperäisen taulukon alkioita indeksistä `alku` alkaen indeksiin `loppu - 1` saakka. (`loppu` on siis ensimmäinen
indeksi, joka ei tule mukaan!) Jos `loppu`-indeksiä ei anneta, kopiointi tapahtuu alkuperäisen taulukon loppuun saakka.
Indeksit voivat olla myös negatiivisia, jolloin niiden sijainti lasketaan taulukon lopusta.

Alkuperäinen taulukko pysyy muuttumattomana.

Esimerkiksi:

```javascript
var lista = ['Aku', 'Mikki', 'Hessu', 'Iines', 'Tupu', 'Hupu', 'Lupu'];
var uusi = lista.slice(2, 5);             // uusi === ['Hessu', 'Iines', 'Tupu']
lista.slice(3);                           // ['Iines', 'Tupu', 'Hupu', 'Lupu']
lista.slice(-3);                          // ['Tupu', 'Hupu', 'Lupu']
lista.slice(1, -1);                       // ['Mikki', 'Hessu', 'Iines', 'Tupu', 'Hupu']
```

Taulukosta voidaan poistaa tai siihen voidaan lisätä alkoita keskelle `splice()`-metodilla. Sen syntaksi on muotoa:
`taulukko.splice(indeksi, montako, alkio1, ..., alkioX)`.

Näistä `indeksi` kertoo, mitä kohtaa taulukosta operoidaan. Parametri `montako` kertoo, kuinka monta alkiota
taulukosta poistetaan, alkaen kohdasta `indeksi`. Loput parametrit ovat alkioita, jotka laitetaan tämän jälkeen taulukkoon
kyseiseen kohtaan. Metodi palauttaa listan poistetuista alkioista.

Esimerkki 1: Lisätään taulukkoon indeksin `2` kohdalle kaksi hedelmää poistamatta yhtään hedelmää.


```javascript
var hedelmat = ['Banaani', 'Appelsiini', 'Omena', 'Mango'];
var paluu = hedelmat.splice(2, 0, 'Sitruuna', 'Kiivi');
console.log(hedelmat);                    // ['Banaani', 'Appelsiini', 'Sitruuna', 'Kiivi', 'Omena', 'Mango']
console.log(paluu);                       // []
```

Esimerkki 2: Poistetaan taulukosta kolme hedelmää indeksistä `2` alkaen.
```javascript
var hedelmat = ['Banaani', 'Appelsiini', 'Sitruuna', 'Kiivi', 'Omena', 'Mango'];
var paluu = hedelmat.splice(2, 3);
console.log(hedelmat);                    // ['Banaani', 'Appelsiini', 'Mango']
console.log(paluu);                       // ['Sitruuna', 'Kiivi', 'Omena']
```

Esimerkki 3: Korvataan `Appelsiini` ja `Sitruuna` hedelmillä `Kirsikka` ja `Luumu`.
```javascript
var hedelmat = ['Banaani', 'Appelsiini', 'Sitruuna', 'Kiivi', 'Omena', 'Mango'];
var paluu = hedelmat.splice(1, 2), `Kirsikka`, 'Luumu');
console.log(hedelmat);                    // ['Banaani', 'Kirsikka', 'Luumu', 'Kiivi', 'Omena', 'Mango']
console.log(paluu);                       // ['Appelsiini', 'Sitruuna']
```

Kaksi taulukkoa voidaan liittää peräkkäin `concat()`-metodilla. Metodi ei muuta alkuperäistä taulukkoa vaan palauttaa
uuden taulukon, jossa molempien taulukoiden alkiot ovat peräkkäin.

Esimerkki

```javascript
var lista = [1, 2, 3, 4];
var taulukko = ['a', 'b', 'c'];
var uusi = lista.concat(taulukko);     // [1, 2, 3, 4, 'a', 'b', 'c']
```

Järjestäminen
--------------

Taulukoita voidaan järjestää sen `sort()`-metodilla. Tämä metodi sekä järjestää alkuperäisen
taulukon uudelleen että palauttaa järjestetyn taulukon. Oletuksena `sort()` järjestää alkiot
merkkijonoina akkosjärjestykseen. Tämä kannattaa huomioida, jos haluaa esimerkiksi järjestää
lukuja.

```javascript
var nimet = ['Eemeli', 'Celcius', 'Aarne', 'Daavid','Bertta',  'Frans'];
nimet.sort();    // ["Aarne","Bertta","Celcius","Daavid","Eemeli","Frans"]

var numerot = [6, 3, 1, 7, 10, 21];
numerot.sort();  // [1,10,21,3,6,7]
```

Jos taulukon alkioita halutaan järjestää jollain muulla tavalla kuin merkkijonojen aakkosjärjestyksellä,
pitää `sort()`-metodille antaa parametrina funktio, jota se käyttää kahden alkion oikean järjestyksen
päättelemiseen. Funktion täytyy olla sellainen, että se saa kaksi parametria ja palauttaa jonkin luvuista
`1`, `0` tai `-1` (tai tarkemmin sanottuna positiivisen, nollan tai negatiivisen) sen mukaan, kumpi
alkioista on "suurempi" tai "pienempi" tai ovatko alkiot yhtä suuret.

Esimerkki 1: Lukujen järjestäminen
```javascript
var numerot = [6, 3, 1, 7, 10, 21];
numerot.sort(function(a, b){
    return a-b;      // Positiivinen, kun a > b
});                  // Nolla, kun a === b
                     // Negatiivinen, kun a < b
                     // [1, 3, 6, 7, 10, 21]
```

Esimerkki 2: Objektien järjestäminen
```javascript
var piste1 = {x: 2, y: 5};
var piste2 = {x: 3, y: 4};
var piste3 = {x: -3, y: 5};
var pisteet = [piste1, piste2, piste3];

pisteet.sort(function(a, b){
    var etaisyysA = Math.sqrt(a.x * a.x + a.y * a.y);
    var etaisyysB = Math.sqrt(b.x * b.x + b.y * b.y);
    var result;
    if (etaisyysA < etaisyysB) {
        result = 1;
    } else if (etaisyysA > etaisyysB) {
        result = -1;
    } else {
        result = 0;
    };
    return result;
});
// [ { x: -3, y: 5 }, { x: 2, y: 5 }, { x: 3, y: 4 } ]
```
Tässä esimerkissä meillä on taulukossa kolme tason pistettä (objekti, jolla on x-koordinaatti ja y-koordinaatti).
Taulukko järjestetään sen mukaan, mikä on pisteiden etäisyys origosta. **Kauimpana oleva ensin.**
Järjestykseen käytettävä funktio laskee Pythagoraan lauseella pisteiden `a` ja `b` etäisyydet origosta ja
palauttaa luvun `1`, jos `a` on lähempänä, luvun `-1`, jos `b` on lähempänä ja muussa tapauksessa luvun `0`.

Taulukon `sort()`-metodia voidaan käyttää näppärästi myös järjestyksen sekoittamiseen antamalla sille
järjestyksen ilmaisevaksi funktioksi sellaisen funktion, joka palauttaa positiivisia ja negatiivisia arvoja
satunnaisesti.

```javascript
var numerot = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20];
numerot.sort(function(a, b){
    return Math.random() - 0.5;   // Satunnainen luku väliltä -0.5 ... 0.5
});
// [1,19,5,4,15,14,13,12,2,10,20,16,8,6,11,17,3,7,9,18]
```