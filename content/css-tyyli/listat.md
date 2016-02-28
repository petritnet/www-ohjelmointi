+++
Categories = []
Description = ""
Tags = []
Title = "Listat"
date = "2016-02-10T21:29:50+02:00"
weight = 70

+++

Listojen muotoiluja voitiin tehdä jonkin verran suoraan HTML-elementin attribuuteilla,
mutta CSS-sääntöjä käyttämällä tyylitykset saadaan toimimaan sivustolla yleisesti
eikä vain listakohtaisesti.

Listan tyylit
============
Listojen "listamerkkejä" voidaan vaihtaa toisen tyyppisiksi `list-style`-ominaisuudella
ja sen aliominaisuuksilla `list-style-type`, `list-style-position` ja `list-style-image`.

Sääntö on muotoa:
```
list-style: list-style-type list-style-position list-style-image
```

`list-style-type`-ominaisuuden vaihtoehdot ovat:

- `none` – ei listamerkkiä
- `disc` – oletusarvo, täytetty ympyrä
- `circle` – täyttämätön ympyrä
- `decimal` – numeroitu lista (1,2,3,...)
- `upper-roman` – numeroitu lista (I, II, III, IV, ...)
- `upper-latin` – aakkostettu (A, B, C, D, ...)

`list-style-position`-ominaisuuden mahdolliset arvot ovat `outside` (oletus) ja `inside`.
Tämä määrittelee sen, tuleeko listamerkki `<li>`-elementin sisä- vai ulkopuolelle.

Listamerkiksi voi laittaa myös oman kuvatiedoston `list-style-image` ominaisuudella
muodossa `url('omatilpukka.png')`.

Listatyylin voi määrätä joko koko listalle, eli `<ul>`- tai `<ol>`-elementille, taikka
yksittäiselle lista-alkiolle, eli `<li>`-elementille.

```
<ul style="list-style: upper-roman;">
    <li>yksi</li>
    <li style="list-style-position: inside;">kaksi</li>
    <li>kolme</li>
</ul>
```
<div class="html-example">
<ul style="list-style: upper-roman;">
    <li>yksi</li>
    <li style="list-style-position: inside;">kaksi</li>
    <li>kolme</li>
</ul>
</div>