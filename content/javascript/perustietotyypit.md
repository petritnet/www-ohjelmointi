+++
Categories = []
Description = ""
Tags = []
Title = "Perustietotyypit"
date = "2016-03-07T22:54:05+02:00"
weight = 10

+++

Javascripti on dynaamisesti tyypitetty kieli, eli muuttujille ei tarvitse
kiinnittää tyyppiä vaan niihin voi sijoittaa minkä tahansa tyyppistä tietoa.

Käydään läpi Javascriptin yleisimmin käytetyt tietotyypit.

Numerot
=======
Monissa muissa kielissä on erilliset tietotyypit kokonaisluvuille ja liukuluvuille (desimaaliluvuille).
Javascriptissä on luvuille vain yksi tyyppi `number`, jolla voidaan esittää positiiviset ja negatiiviset
kokonaisluvut sekä liukuluvut. Tästä on sekä hyötyä että haittaa.
Lukujen käsittely on helppoa, koska niitä ei tarvitse muutella muodosta toiseen, mutta
esimerkiksi desimaalilukujen tarkkuus voi kärsiä.

```javascript
> 0.1 + 0.2
0.30000000000000004
> 9999999999999999
10000000000000000
```

Merkkijonot
===========
Merkkijonojen tyyppi on `string`. Merkkijono on joukko peräkkäisiä merkkejä. Javascriptissä
merkkijonot koostuvat Unicode-merkeistä, eli voivat sisältää käytännössä mitä tahansa merkkejä.
Merkkijonot kirjoitetaan joko kaksoislainausmerkkien `"` tai yksöislainausmerkkien `'` väliin.
Javascriptissä näillä ei ole eroa, kuten joissain muissa kielissä. Kahdet eri lainausmerkit ovat
kuitenkin hyödylliset, jos halutaan määritellä merkkijono, jossa on lainausmerkkejä.

Merkkijonolla on aina pituus, eli merkkien määrä. Merkkijono voi olla myös tyhjä, eli merkkijono,
jonka pituus on nolla.

```javascript
"www-ohjelmointi-kurssi"
'Lorem ipsum dolor sit amet...'
'Pekka sanoi: "Lorem ipsum"'
'Jack O\'Neil sanoi: "Moi!"'
"42"
'' // Tyhjä merkkijono
```

"Takakeno", eli `\` on erikoismerkki, jolla voidaan toisaalta merkitä erikoismerkkejä ja toisaalta
riisua joiltain erikoismerkeiltä niiden erityismerkitys. Esimerkiksi `'\''` tarkoittaa samaa
merkkijonoa kuin `"'"`. Yksöishipsukalta on siis riisuttu sen erityismerkitys (merkkijonon lopetus).


Totuusarvot
===========
Loogisilla väittämillä ja vertailuilla on totuusarvo, jonka tyyppi on `boolean`. Totuusarvo on
joko tosi, eli `true` tai epätosi, eli `false`.

```javascript
1 + 2 < 4
true

2 === 3
false
```


Erikoisarvot
============
Javascriptissä on lisäksi kaksi erityistä arvoa, jotka molemmat tarkoittavat yleensä
tilannetta, jossa muuttujalla ei ole arvoa. Näistä `undefined` tulee yleensä tilanteessa,
jossa tarkastellaan muuttujaa, jolle ei ole annettu arvoa. Toinen, eli `null` on
yleensä "tyhjä" arvo, jonka ohjelmoija itse on antanut muuttujalle.


Objektit
=========
Javascriptissä lähes kaikki käsiteltävät asiat ovat jonkinlaisia objekteja (`object`). Objekteja on helppo
tehdä itse aaltosuljemerkinnällä `{}`. Javascriptissä objektit ovat avain–arvo -pareja, joissa
avaimet ovat merkkijonoja ja arvot mitä tahansa Javascriptin tietotyyppejä. Vaikka objekteja.

Javascriptin dynaamisuus näkyy myös siinä, että objektiin voi laittaa mitä tahansa arvoja ja
niitä voi luoda aina tarpeen mukaan välittämättä tiedon tyypistä.

```javascript
{
    'avain': 'arvo',
    'luku': 42,
    'totuus': true,
    'objekti': {'joo': 'jee'}
}
```


Arrayt
=======
Javascriptissä, kuten monissa muissakin kielissä voi tietoa tallettaa myös järjestetyiksi
jonoiksi, joiden tyyppi on `array`. Array esitetään hakasulkeiden avulla ja jonon
alkiot erotetaan toisistaan pilkulla. Array-rakenteeseen voi tallettaa mitä tahansa
tietoa. Toisin kuin vahvasti tyypitetyissä kielissä, kuten Javassa tai C++:ssa, Javascriptissä
arrayn alkioiden tyypillä ei ole väliä.

Arraylla on aina pituus. Pituus voi olla myös nolla, jolloin array on tyhjä.

```javascript
[1,2,3,4]
['Pekka', 'Jussi', 'Maija']
[1, 'Timo', true, null, {'joo': 'ei'}]
[]  // Tyhjä array
```


