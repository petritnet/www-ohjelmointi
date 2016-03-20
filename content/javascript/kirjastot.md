+++
Categories = []
Description = ""
Tags = []
Title = "Javascript-kirjastot"
date = "2016-03-20T22:01:12+02:00"
weight = 140

+++

Javascript-ohjelmien tekoon on tarjolla lukuisia avointa lähdekoodia olevia
ja vapaasti käytettäviä kirjastoja, joita käyttämällä ohjelmoijan ei tarvitse
tehdä aivan kaikkia toiminnallisuuksia itse. Esimerkiksi käyttöliittymän
yhtenäisen ulkoasun luomiseen on useita vaihtoehtoisia kirjastoja.

Esimerkiksi [JS Bin](http://jsbin.com)-sivustolla on valikon "Add library"-kohdassa
lisättävissä laaja kirjo erilaisiin kirjastoihin viittaavia `<script>`-tagia.

jQuery-ui
=========

[jQuery-ui][jQuery-ui] on jQueryn pohjalle laajennuksena rakennettu käyttöliittymäkirjasto.
Kirjasto sisältää laajan kokoelman erilaisia "widgettejä", eli käyttöliittymäkomponentteja,
efektejä sekä interaktiivisia toiminnallisuuksia. Widgettien kokoelmaan kuuluu muun muassa
nappulat, dialogi-ikkunat, valikot, liukusäätimet, välilehtisysteemit, "sisältöhaitarit" sekä
automaattisesti täydennettävät syöttökentät. Nämä kaikki ovat teemoitettavissa yhdenmukaisella
ulkoasulla.

jQuery-ui tarjoaa myös työkalut omien interaktiivisten käyttöliittymien rakentamiseen
raahattavilla ja pudotettavilla elementeillä.

Tarjolla oleviin toimintoihin voi tutustua [jQuery-ui:n demosivulla][jQui-demot]


jQuery Mobile
=============

[jQuery Mobile][jQuery Mobile] on erityisesti mobiililaitteiden käyttöön tarkoitettu
jQueryyn pohjautuva käyttöliittymäkirjasto. Sitä käyttäen voi tehdä helposti
hyvän näköisiä ja teemoitettavia responsiivisia, eli mobiililaitteen pienelle näytölle
automaattisesti skaalautuvia, käyttöliitymiä.

Käyttöliittymäkomponentteja esittelevä [jQuery Mobilen demosivusto][jQueryM-demo].

Bootstrap
=========

[Bootstrap][Get Bootstrap] on alun perin Twitterin omaan sisäiseen käyttöön kehitetty
käyttöliittymäkirjasto. Bootstrap koostuu ennen kaikkea käyttöliittymälle yhtenäisen tyylin
antavista CSS-säännöistä sekä HTML-pohjista, joilla näitä CSS-määrittelyitä voidaan käyttää.

Lisäksi Bootstrapin mukana tulee joukko jQuery-lisäosina toteutettuja Javascript-komponentteja,
joilla voidaan toteuttaa interaktiivisempia käyttöliittymän osia, kuten popup-ikkunoita ja
kuvakaruselleja.

[Bootstrap-komponenttien esittelyä][Bootstrap components]

AngularJS
=========

[AngularJS][AngularJS] on erityisesti web-sovellusten tekemiseen suunnattu kirjasto.
Se soveltuu erityisesti tilanteisiin, joissa käyttöliittymäkomponenttien pitää
dynaamisesti päivittyä niihin tehtyjen muutosten seurauksina. Esimerksi tilanteisiin,
joissa yhden näytöllä olevan liukusäätimen arvon muuttaminen vaikuttaa yhteen tai
useampaan muuhun näytöllä olevaan komponenttiin.

AngularJS keskittyy ennemminkin käyttöliittymäkomponenttien ja Javascript-objektien
väliseen toiminnallisuuteen kuin käyttöliittymän ulkoasuun. Ulkoasun voi puolestaan
muodostaa esimerkiksi Bootstrapilla.

[AngularJS:n opiskelusivusto][AngularJS-learn]



[jQuery-ui]: http://jqueryui.com "jQuery-ui"
[jQui-demot]: http://jqueryui.com/demos/ "jQuery-ui demot"
[jQuery Mobile]: http://jquerymobile.com/ "jQuery Mobile"
[jQueryM-demo]: http://jquerymobile.com/demos "jQuery Mobile demos"
[Get Bootstrap]: http://getbootstrap.com/ "Bootstrap"
[Bootstrap components]: http://getbootstrap.com/components/ "Bootstrap komponentteja"
[AngularJS]: https://angularjs.org/ "AngularJS"
[AngularJS-learn]: http://campus.codeschool.com/courses/shaping-up-with-angular-js/intro "AngularJS opiskelu"