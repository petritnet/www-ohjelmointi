+++
Categories = []
Description = ""
Tags = []
Title = "Muut kielet"
date = "2016-03-28T23:16:37+03:00"
weight = 60

+++

Muilla ohjelmointikielillä palvelinpään ohjelmia tehdessä tyypillisesti
joudutaan web-palvelimelle kertomaan hieman monimutkaisemmin, että
tiettyyn osoitteeseen tulevat pyynnöt prosessoidaan halutulla
ohjelmalla. Käytössä on joko kielen oma palvelinohjelmisto taikka
jonkinlainen ohjaus yleiskäyttöisestä web-palvelimesta (kuten Apache)
halutun kielen suoritusalustalle.

Esimerkiksi Javalla ohjelmoitaessa on yleensä käytössä oma [Tomcat][Tomcat]-palvelinohjelmisto,
joka siis sisältää web-palvelintoiiminnallisuuden ja kyvyn suorittaa Java-kielellä
tehtyjä ohjelmia.

Palvelinpään ohjelmointia voi tehdä myös Javascriptillä käyttämällä [Node.js][NodeJS]-suoritusympäristöä.
Node.js sisältää Chromesta tutun V8-JavaScript-koneiston sekä joukon palvelintoimintaan tarvittavia osia.
Node.js sisältää myös toiminnallisuuden itsenäiseen web-palvelimena toimimiseen, eli se ei välttämättä
tarvitse erillistä web-palvelinta, kuten Apache, parikseen.

Muita usein käytettyjä palvelinpään kieliä ovat:

- Python
- Ruby
- C#
- Perl




[Tomcat]: https://tomcat.apache.org/ "Apache:Tomcat"
[NodeJS]: https://nodejs.org/ "NodeJS"