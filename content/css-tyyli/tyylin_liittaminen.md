+++
Categories = []
Description = ""
Tags = []
Title = "Tyylin liittäminen dokumenttiin"
date = "2016-01-06T23:56:10+02:00"
weight = 3

+++

CSS-tyylisääntöjä voi liittää dokumenttiin kolmella tavalla:

* Suoraan HTML-elementtin tagiin `style`-attribuutilla.
* Sivun `head`-osioon `<style>`- ja `</style>`-tagien väliin.
* Erillisenä tyylitiedostona, esimerkiksi `tyylit.css`.

Suoraan elementissä
===================

Tyylitieto voidaan merkitä suoraan elementin tagiin `style`-attribuutin avulla:

```
<h1 style="color: red;">Otsikko</h1>
```
<div class="html-example">
<h1 style="color: red;">Otsikko</h1>
</div>

Tämä tapa on käyttökelpoinen, kun halutaan määrätä ainoastaan _yhden_ komponentin ulkoasu ja ainoastaan _yhdessä_ tapauksessa.

Yleensä `style`-attribuutin suora käyttö on kuitenkin huono vaihtoehto.

Merkitseminen `head`-osioon
============================
Tyylitieto voidaan antaa myös dokumentin `head`-osiossa:

```
<html>
    <head>
        <style type="text/css">
            h1 {color: red;}
        </style>
        ...
    </head>
    <body>
        ...
        <h1>Otsikko</h1>
        ...
    </body>
</html>
```

* Käyttökelpoinen, kun halutaan tyylitellä yleisemmin komponentteja, esimerkiksi _kaikki_ palstat tai _jokainen_ kuva.
* Säännöt koskevat vain yhtä sivua, eivät koko sivustoa.

Ulkoinen tyylitiedosto
======================
Ulkoisen tyylitiedoston linkittäminen tehdään sivun `head`-osiossa `link`-tagilla:
```
<html>
    <head>
        <link rel="stylesheet" type="text/css" href="tyylit.css">
        ...
    </head>
    <body>
        ...
        <h1>Otsikko</h1>
        ...
    </body>
</html>
```

Tiedostossa `tyylit.css`:
```
h1 {
    color: red;
}
```

* Ulkoinen tyylitiedosto on paras valinta silloin, kun sivusto koostuu useammasta kuin yhdestä sivusta. Sama tyylitiedosto voidaan linkittää moneen sivuun.
* Dokumenttiin voidaan linkittää useampia tyylitiedostoja, esim. `tyylit.css`, `valikot.css`, `mobiili.css` jne.
