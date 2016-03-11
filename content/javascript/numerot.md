+++
Categories = []
Description = ""
Tags = []
Title = "Numerot"
date = "2016-03-10T21:09:19+02:00"
weight = 45

+++

Useimmissa ohjelmissa tarvitaan ainakin jonkin verran numeroita puhtaasti
aritmeettisia laskuoperaatiota. Javascriptin numeroille käyttämä tyyppi
on nimeltään `number`.

```
typeof 5;     // 'number'
```

Laskuoperaatioita
=================

Peruslaskuoperaatioina ovat käytettävissä tutut operaatiot:

| Operaatio              | Operaattori   | Esimerkki      |
|------------------------|---------------|----------------|
|Negatiivinen etumerkki  | `-`           | `-3`           |
|Yhteenlasku             | `+`           | `5 + 8 === 13` |
|Vähennyslasku           | `-`           | `4 - 7 === -3` |
|Kertolasku              | `*`           | `4 * 3 === 12` |
|Jakolasku               | `/`           | `16 / 2 === 8` |
|Modulo, eli jakojäännös | `%`           | `15 % 4 === 3` |


Math
====

Muita [matematiikkaan][Math] liittyviä operaatioita ja funktioita löytyy
Javascriptin `Math`-objektista. Esimerkiksi:

```
Math.PI              // 3.141592653589793 (Pii:n likiarvo)
Math.E               // 2.718281828459045 (Neperin luku e)
Math.random()        // Satunnainen desimaaliluku väliltä 0 – 1
Math.floor(1.21)     // 1  Pyöristys alas päin kokonaislukuun.
Math.floor(-1.21)    // -2
Math.ceil(3.4)       // Pyöristys ylös päin kokonaislukuun.
Math.round(2.3)      // Pyöristys lähimpään kokonaislukuun.
Math.abs(-5)         // 5, Itseisarvo
Math.sqrt(3)         // 1.7320508075688772, Neliöjuuri
Math.sin()           // Sini
Math.cos()           // Kosini
Math.tan()           // Tangentti
Math.min(3, 7, 2, 5) // 2, Minimi
Math.max(6, 9, 4, 1) // 9, Maksimi
```

Lukujen kanssa operoitaessa kannattaa olla varovainen, sillä esimerkiksi joissain erikoistilanteissa
saattaa vastaukseksi tulla `NaN` (**N**ot **a** **N**umber), joka nimestään huolimatta on samaa
tyyppiä kuin muut luvut, eli `number`. Muita erikoisarvoja ovat `Infinity` ja `-Infinity`,
jotka edustavat ääretöntä ja negatiivista ääretöntä.

```
7 / 0                // NaN
typeof (7 / 0)       // 'number'
```

[Math]: http://www.w3schools.com/js/js_math.asp "W3Schools:Math"