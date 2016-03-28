+++
Categories = []
Description = ""
Tags = []
Title = "Staattisten sivujen generointi"
date = "2016-03-28T12:23:04+03:00"
weight = 40

+++

Staattisten ja dynaamisten sivustojen hyviä puolia on myös
koetettu tuoda yhteen staattisten sivustojen koostamiseen
tarkoitetuilla työkaluilla, sivugeneraattoreilla.

Näissä on ideana, että sivut koostetaan raakamateriaaleista ja sivupohjista,
kuten dynaamisilla sivustoilla, mutta tämä koostaminen tehdään vain kerran,
minkä jälkeen palvelin tarjoilee nämä valmiiksi koostetut sivut asiakkaille
staattisina sivuina.

Tämä menetelmä sopii hyvin tasaisesti, muttei aivan jatkuvasti, päivittyvien
sivustojen ylläpitoon. Näillä voidaan luoda esimerkiksi tietosivustoja tai
blogeja. Menetelmä ei kuitenkaan yleensä sovi sivustoihin, joiden sisältöä
täytyy käyttäjien päästä päivittämään reaaliaikaisesti ja joiden toiminta
nojaa vahvasti tietokantojen käyttöön, kuten sosiaalisen median sivustot.

Tyypillisesti sivuston sisältö kirjoitetaan jollain HTML-tekstiä yksinkertaisemmalla
merkintäkielellä, kuten [Markdownilla][Markdown].
Sivuston sisältösivujen rakenne määritellään jonkinlaisilla sivupohjilla ja
ulkoasua varten luodaan CSS-tiedostoja. Järjestelmät tukevat usein teemoitusta,
jolloin teemat koostuvat sivupohjista ja CSS-tiedostoista.

Usein käytettyjä staattisia sivustoja koostavia generaattoreita ovat:

- [Jekyll][Jekyll]
- [Octopress][Octopress]
- [DocPad][DocPad]
- [Hugo][Hugo]

Tämän sivuston rakentamiseen on käytetty [Hugoa][Hugo].

[Markdown]: https://en.wikipedia.org/wiki/Markdown "Wikipedia:Markdown"
[Jekyll]: http://jekyllrb.com/ "Jekyll"
[Octopress]: http://octopress.org/ "Octopress"
[DocPad]: http://docpad.org/ "DocPad"
[Hugo]: http://gohugo.io/ "Hugo"
