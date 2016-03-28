+++
Categories = []
Description = ""
Tags = []
Title = "PHP"
date = "2016-03-28T22:36:40+03:00"
weight = 50

+++

Yksi varsin usein käytetty palvelinpään ohjelmointikieli on PHP.

- PHP: Hypertext preprocessor
- Ensimmäinen versio vuonna 1995
- Nykyiset versiot 5.6.19 – 7.0.4 (maaliskuu 2016)
- Käytetään yleensä palvelinpään skriptikielenä
- Lisätietoja, tutoriaaleja ja ohjeita: http://www.php.net

PHP on usein asennettu toimimaan yhdessä Apache-web-palvelimen ja
MySQL-tietokannan (tai MariaDB-kannan) kanssa. Kokonaisuuteen viitataan
alla olevasta käyttöjärjestelmä riippuen usein kirjainyhdistelmillä
[LAMP][LAMP], WAMP, MAMP, XAMP tai [XAMPP][XAMPP].

Integrointi web-palvelimen yhteyteen antaa PHP:lle selkeän edun muihin palvelinpään
kieliin verrattuna. PHP-ohjelma on helppoa luoda vain muuttamalla HTML-tiedoston päätteeksi
`.php`, jolloin web-palvelin osaa käyttää PHP-kieltä sen suorittamiseen.

PHP on pohjimmiltaan kieli HTML-sivupohjille, eli sillä voidaan luoda HTML-sivuja,
joissa on seassa muuttujien, ehtolausekkeiden, silmukoiden sekä muiden kontrollirakenteiden
avulla tehtyä dynaamisuutta.
PHP-koodia voidaan kirjoittaa mihin tahansa kohtaan HTML-tiedostossa, merkkien
`<?php` ja `?>` väliin. Näiden välissä oleva PHP-koodi suoritetaan ja korvataan
ohjelmakoodin tulostuksella. Esimerkiksi koodi

```php
<h1><?php echo 'Terve kaikki!'; ?></h1>
```
Tuottaa HTML-koodin
```html
<h1>Terve kaikki!</h1>
```

Tiedosto voi olla myös alusta loppuun saakka pelkkää PHP:tä, jolloin kaikki HTML-koodi
sen tulostetta.

Materiaalia
===========

Materiaalia PHP:n tarkempaan opiskeluun löytyy esimerkiksi seuraavista:

- [Kalvot](../../slideshows/palvelin.pdf)
- [PHP W3Schoolsissa][PHP W3Schoolsissa]
- [PHP kotisivu][PHPnet]
- [Codecademyn harjoittelusivuston PHP-osio][CodecademyPHP]
- [WriteCodeOnlinen][WriteCodeOnline] PHP-harjoitteluympäristö

XAMPP
======

Halutessasi voit asentaa omalle koneellesi PHP-ympäristön sekä muita tarvittavia välineitä
asentamalla [XAMPP][XAMPP]-paketin. XAMPP (=Cross-platform, Apache, MySQL, PHP, Perl) sisältää
seuraavat osat:

- **Apache**: Www-palvelinohjelmisto, joka vastaa verkosta tuleviin pyyntöihin ja tarjoilee pyytävälle ohjelmalle (selaimelle) tiedostoja.
- **MySQL**: Tietokantajärjestelmä, jota voidaan palvelimella käyttää tietojen tallentamiseen.
- **PHP**: Laajasti www-sivustojen ohjelmointiin käytetty ohjelmointikieli.
- **Perl**: Toinen, vanhempi, ohjelmointikieli, jota käytettiin aiemmin paljon www-sivustojen ohjelmointiin.

Asentaminen
-----------

XAMPP Lite -palvelimen voi ladata koneelle osoitteesta http://portableapps.com/apps/development/xampp
valitsemalla "Download XAMPP Lite". Paketti pitää purkaa johonkin sopivaan kansioon. Paketista puretussa kansiossa
"xampplite" on tiedosto "setup_xampp.bat", jota kaksoisklikkaamalla XAMPP:ille tehdään sopivat asetukset.

Palvelin käynnistyy kaksoisklikkaamalla tiedostoa "xampp_start.exe" ja sen voi sammuttaa suorittamalla tiedoston
"xampp_stop.exe". Käynnissä olevan palvelimen toimivuutta voi kokeilla siirtymällä selaimella
osoitteeseen: http://127.0.0.1 tai osoitteeseen http://localhost/ .

**Muista aina sammuttaa palvelin lopetettuasi kokeilut!**

PHP-ohjelmien suoritus
----------------------

Kaikki palvelimen tarjoilemat tiedostot ovat "xampplite"-kansion alla olevan kansion "htdocs" sisällä.
Osoite "http://127.0.0.1" viittaa tähän kansioon ja esimerkiksi kansiossa olevaan tiedostoon "testi.php"
voi viitata osoitteella "http://127.0.0.1/testi.php". PHP-tiedoston voi suorittaa laittamalla sen tähän
kansioon ja menemällä sitä vastaavaan osoitteeseen www-selaimella.


[LAMP]: https://en.wikipedia.org/wiki/LAMP_%28software_bundle%29 "Wikipedia:LAMP"
[XAMPP]: https://fi.wikipedia.org/wiki/XAMPP "Wikipedia:XAMPP"
[PHP W3Schoolsissa]: http://www.w3schools.com/php/default.asp
[PHPnet]: http://www.php.net "PHP.net"
[CodecademyPHP]: http://www.codecademy.com/tracks/php "Codecademy:PHP"
[WriteCodeOnline]: http://writecodeonline.com/php/ "WriteCodeOnline:PHP"
