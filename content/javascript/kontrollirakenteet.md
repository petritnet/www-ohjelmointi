+++
Categories = []
Description = ""
Tags = []
Title = "Kontrollirakenteet"
date = "2016-03-09T22:36:33+02:00"
weight = 30

+++

Ohjelmoinnin peruselementtejä missä tahansa kielessä ovat kontrollirakenteet,
eli suorituksen haarauttamisesta huolehtivat ehtolauseet ja toistot hoitavat
silmukat.

Loogiset lausekkeet
===================
Ehtojen ja silmukoiden käyttämiseen tarvitaan loogisia väittämiä, lausekkeita,
joiden perusteella valitaan ehtolaueen suoritettava haara ja silmukoiden
suorituskertojen määrät.

Looginen lauseke muodostuu jostain totuusarvoisesta väittämästä tai niiden yhdistelmästä.
Yleisimmin tällainen väite muodostetaan jollain [vertailuoperaattorilla][Vertailu].

| Operaattori    | Esimerkki     | Merkitys                                 | Huom!                                               |
|----------------|---------------|------------------------------------------|-----------------------------------------------------|
| `==`           | `a == b`      | yhtäsuuruus, `a` on yhtä suuri kuin `b`  | Ei täsmällinen yhtäsuuruus vaan "samankaltaisuus"   |
| `===`          | `a === b`     | samuus, `a` on sama kuin `b`             | Muuttujat `a` ja `b` ovat täsmälleen sama olio.     |
| `!=`           | `a != b`      | erisuuruus, `a` on erisuuri kuin `b`     | Ei täsmällinen                                      |
| `!==`          | `a !== b`     | erit, `a` on eri kuin `b`                | Täsmällinen                                         |
| `<`            | `a < b`       | `a` on pienempi kuin `b`                 |                                                     |
| `>`            | `a > b`       | `a` on suurempi kuin `b`                 |                                                     |
| `<=`           | `a <= b`      | `a` on pienempi tai yhtä suuri kuin `b`  |                                                     |
| `>=`           | `a >= b`      | `a` on suurempi tai yhtä suuri kuin `b`  |                                                     |

Vertailuoperaattoreita voidaan käyttää erityyppisten muuttujien ja arvojen vertailuun. Yhtäsuuruuden vertaamiseen on
käytettävissä kaksi operaattoria, kahden yhtäsuuruusmerkin `==` (*yhtäläisyys*, *equality*) sekä kolmen yhtäsuurusmerkin
`===` (*samuus*, *identtisyys*, *identity*). Näiden  erona on se, että operaattorilla `===` verrattavien arvojen tulee
olla täsmälleen samat oliot (objekti, luku, merkkijono jne.). Operaattorilla `==` riittää, että vertailtavat arvot ovat
tulkittavissa samoiksi. Esimerkiksi:

```javascript
1 == 1            // true
'1' == 1          // true
1 == true         // true
0 == false        // true
0 == null         // false
0 == undefined    // false
null == undefined // true
```

Kahden yhtäsuuruusmerkin vertailuoperaattorin yhtäläisyyssäännöt ovat melko monimutkaiset ja virhealttiit.
Siksi on yleensä syytä käyttää `===`-operaattoria, kun mahdollista. Vastaavat erisuuruusoperaattorit
ovat `!=` ja `!==`.

Vertailuoperaattoreilla muodostettuja väittämiä voidaan yhdistellä loogisilla operaattoreilla **ja**, **tai** sekä **ei**.
Seuraavassa taulukossa oletetaan, että `x === 6` ja `y === 3`.

| Operaattori                 | Esimerkki            | Arvo     | Merkitys                                    |
|-----------------------------|----------------------|----------|---------------------------------------------|
| `&&`                        | `x < 10 && y > 1`    | `true`   | **JA**: Molemmat väitteet ovat tosia.       |
| <code>&#124;&#124;</code>   | <code>x === 5 &#124;&#124; y === 5</code> | `false`  | **TAI**: Ainakin toinen väitteistä on tosi. |
| `!`                         | `!(x === 5)`         | `true`   | **EI**: Väite ei ole tosi                   |

Eri tyyppiä olevien varvojen vertailu voi tuottaa yllättäviä tuloksia ja niiden kanssa kannattaa siksi olla varovainen.

Ehtolauseet
===========

Ehtolauseella on mahdollista jakaa ohjelman suoritus eri haaroihin sen mukaan, onko ehtona käytetty väite tosi
vai epätosi. Ehtolauseen rakenne on:

```
if (ehto) {
    ... lohko, joka suoritetaan, jos ehto on tosi ...
}
```

Ehtolauseelle voidaan lisätä `else`-avainsanalla toinen haara, joka suoritetaan, kun ehto ei ole voimassa.

```
if (ehto) {
    ... lohko, joka suoritetaan, jos ehto on tosi ...
} else {
    ... lohko, joka suoritetaan, jos ehto on epätosi ...
}
```

Lisäksi voidaan lisätä haluttu määrä tarkentavia ehtoja ja lohkoja ketjuttamalla `if`-`else`-rakenteita.

```
if (ehto1) {
    ... lohko, joka suoritetaan, jos ehto1 on tosi ...
} else if (ehto2) {
    ... lohko, joka suoritetaan, jos ehto1 on epätosi, mutta ehto2 on tosi ...
} else {
    ... lohko, joka suoritetaan, jos ehto1 ja ehto2 ovat on epätosia ...
}
```

Esimerkiksi:

```
if (lasku > 100) {
    console.log("Onpa kallista!");
} else if (lasku <= 10) {
    console.log("Olipa halpaa!");
} else {
    console.log("Ihan käypä hinta.");
}
```


Toistorakenteet
===============
Javascriptissä toistorakenteet ovat hyvin samanlaisia kuin muissakin ohjelmointikielissä.

`for`-silmukka
--------------
For-silmukalle on tyypillistä, että toistoa hallitaan ennen suoritusta alustetuilla muuttujilla,
suoritusehdolla sekä jokaisen silmukan suorituksen jälkeen suoritettavalla muutoksella.
Silmukkaa suoritetaan niin kauan kuin ehto on voimassa. Muutoksen tulee olla sellainen, että
silmukka väistämättä saavuttaa tilanteen, jossa ehto lakkaa olemasta voimassa ja silmukan suoritus
katkeaa.

Javascriptissä for-silmukan rakenne on:

```
for (alustus; ehto; muutos) {
    ... suoritettava lohko ...
}
```

Esimerkiksi:

```
for (var i = 0; i < 10; i++) {
    console.log(i);
}
```

Huomaa, että laskurin ei tarvitse lähteä luvusta 0 ja kasvaa joka kierros yhdellä. Silmukkamuuttujan ei tarvitse välttämättä olla edes luku.
Olennaista on vain, että silmukkamuuttuja lähenee kierros toisensa jälkeen tilannetta, jossa silmukan suoritus pysähtyy.

Hyvin usein `for`-silmukalla halutaan käydä läpi jonkin `Arrayn` sisältö.

```
var lista = ['Jussi', 'Maija', 'Pekka', 'Jaana'];
for (var i = 0; i < lista.length; i++) {
    console.log(lista[i]);
}
```

`for`-`in`-silmukka
--------------------
Javascriptissä on tavallisen `for`-silmukan lisäksi `for`-`in`-silmukka, jolla voidaan käydä läpi
jonkin objektin ominaisuudet. Tämä silmukka ei takaa, missä järjestyksessä ominaisuudet käydään läpi.
Sen kanssa on lisäksi syytä olla varma, että läpi käytävällä objektilla ovat vain halutut ominaisuudet.

Seuraavassa esimerkissä silmukkamuuttuja `nimi` käy läpi kaikki objektin `ika` ominaisuudet, eli avaimet.
Silmukan sisällä tulostetaan teksti, jossa käytetään sekä henkilön nimi muuttujasta `nimi` että
hänen ikänsä `ika[nimi]`.

```
var ika = {'Jussi': 17, 'Maija': 8, 'Pekka': 9, 'Jaana': 21};
for (var nimi in ika) {
    console.log(nimi + ' on iältään ' + ika[nimi]);
}
```

`while`-silmukka
----------------
`while`-silmukka muistuttaa myös hyvin paljon muiden ohjelmointikielten vastaavaa. Silmukkaa
suoritetaan niin kauan, kuin sen määrittelevä ehto on voimassa. `while`-silmukkaa käytettäessä
kiinnittää erityistä huomiota siihen, että silmukan suoritus todella päättyy ennen pitkää.
On erittäin yleinen virhe joko unohtaa päivittää silmukan sisällä jotain sen päättymiseen vaikuttavaa
muuttujaa tai vain päivittää sitä väärin.

```
while (ehto) {
    ... lohko, jota suoritetaan niin kauan kuin ehto on voimassa ...
}
```

Esimerkiksi:

```
while (jonossa > 0) {
    console.log('Jonossa on ' + jonossa + ' ihmistä.');
    jonossa = jonossa - Math.floor(3 * Math.random() + 1);
}
```

`do`-`while`-silmukka
---------------------
Tämä on `while`-silmukan versio, jossa ehto tulee vasta suoritettavan lohkon jälkeen, jolloin
silmukan lohko suoritetaan aina vähintään yhden kerran ennen ehdon tarkistamista.

```
do {
    ... lohko ...
} while (ehto);
```

Esimerkiksi:

```
var i = 20;
do {
    console.log('luko = ' + i);
    i--;
} while (i > 0);
```


[Vertailu]: http://www.w3schools.com/js/js_comparisons.asp "W3Schools:Vertailu"