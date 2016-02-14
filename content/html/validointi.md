+++
Categories = []
Description = ""
Tags = []
Title = "Validointi"
date = "2016-01-31T20:00:53+02:00"
weight = 90

+++

{{% jessyink src="html-johdanto.svg#33" %}}
{{% /jessyink %}}

Sivun validoinnilla varmistetaan, että sivu on annetun dokumenttityypin mukainen.
Validi sivu toimii todennäköisemmin halutusti eri laite- ja selainympäristöissä.
Validaattori on sivun tekijän apuväline, ei itsetarkoitus. Esimerkiksi
sivun *[http://www.yle.fi](http://www.yle.fi)* validointi antaa
noin 50 virhettä tai varoitusta.

Sivun validointiin voidaan käyttää [W3C:n][W3C] validaattoria:
[validator.w3.org][Validaattori]

Validoinnin voi suorittaa kolmella eri tavalla:

* "by URL" -välilehti – Tarkistetaan netissä olevan sivun validius antamalla sen osoite.
* "by File upload" -välilehti – Tarkistetaan oma HTML-tiedosto lähettämällä se tarkistettavaksi lomakkella.
* "by Direct input" -välilehti – Tarkistetaan omaa HTML-koodia syöttämällä se suoraan tekstilaatikkoon.

Validin sivun tunnusmerkkejä:

* Documenttityyppi merkitty oikein tiedoston alkuun.
* Tageilla on vastaava lopetustagi, jos vaadittu. (Huom. poikkeukset)
* Dokumentti on rakenteellisesti oikein muodostettu.
* HTML-entiteetit on merkitty oikein.
* Elementeillä on kaikki tarvittavat attribuutit.




[W3C]: https://www.w3.org "W3C"
[Validaattori]: https://validator.w3.org "W3C:Validaattori"