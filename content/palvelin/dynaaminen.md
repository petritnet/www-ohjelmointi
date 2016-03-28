+++
Categories = []
Description = ""
Tags = []
Title = "Dynaamiset www-sivut"
date = "2016-03-28T10:38:40+03:00"
weight = 30

+++

Sivuston dynaamisuudella tarkoitetaan sitä, että sivun HTML-koodi "tulostetaan"
jollain ohjelmointikielellä (PHP, Python, Java,...) sitä pyydettäessä ja palvelin
syöttää valmiin HTML-sivun takaisin asiakkaalle. Palvelimella ei siis säilytetä
valmiita sivuja vaan vain materiaali niiden koostamiseen.

Koska koostaminen suoritetaan palvelinpäässä, näkee sivulla kävijä ainoastaan
valmiin sivun (tai sen lähdekoodin), mutta ei sen generoivaa ohjelmakoodia.

Dynaamisten www-sivujen tuottamiseen on tarjolla useita valmiita **sisällönhallintajärjestelmiä**,
joiden käyttäjä voi keskittyä sisällön tuottamiseen, kunhan sivusto on ensin asennettu käyttövalmiiksi.
Monet näistä järjestelmistä on vapaasti käytettävissä [avoimen lähdekoodin][Avoin lähdekoodi] lisensseillä.

- [WordPress][WordPress]
- [Drupal][Drupal]
- [Joomla][Joomla]
- [MediaWiki][MediaWiki]

Dynaamisuuden hyödyt
====================

Sivun voi muodostaa erillisistä komponenteista. Tällöin sivuston sivujen yhteiset osat, kuten
yläosa, navigointi ja alaosa voidaan laittaa omiin tiedostoihinsa. Tällöin kaikille sivuille
yhteisten osuuksien päivittäminen tapahtuu vain yhdestä paikasta.

<figure>
    <img src="../../images/palvelin-komponentit.svg" style="max-width: 90%;" alt="dynaaminen sivu komponenteista">
</figure>


Sivu voidaan muodostaa myös täysin käyttäjän antaman syötteen avulla.

Sisältö voidaan hakea tiedostosta, tietokannasta tai generoida kokonaisuudessaan
alusta alkaen. Yleensä haettavaan (tai muodostettavaan) tietoon vaikuttaa jokin
käyttäjän valinta. Esimerkiksi elokuvateatterin esitysten ja esitysaikojen luettelo.

Mahdollistaa myös "Web 2.0 -palvelut", joissa sisältö on jatkuvasti muuttuvaa ja ajantasaista.


Dynaamisuuden haitat
====================

Koska sivut koostetaan aina uudelleen jokaisella sivupyynnöllä, on dynaamisten sivujen käyttäminen
**raskaampaa palvelimelle** ja voi ääritapauksessa tehdä sivuston toiminnasta hitaampaa.
Hitautta voidaan koettaa ehkäistä käyttämällä palvelimella välimuistitoimintoja, jolloin
sivua ei joka kerta luodakaan tyhjästä vaan muistetaan vasta koostetut sivut jonkin aikaa.
Tämä ei kuitenkaan toimi erityisesti sivustoilla, joiden sisältö koostuu joka kerta
erilaiseksi. Tällaisia ovat esimerkiksi Facebookin ja Twitterin kaltaiset sivustot, joiden
sisältö elää jatkuvasti.



[Avoin lähdekoodi]: https://fi.wikipedia.org/wiki/Avoin_l%C3%A4hdekoodi "Wikipedia:Avoin lähdekoodi"
[WordPress]: https://wordpress.org/ "WordPress"
[Drupal]: https://www.drupal.org/ "Drupal"
[Joomla]: https://www.joomla.org/ "Joomla"
[MediaWiki]: https://www.mediawiki.org "MediaWiki"
