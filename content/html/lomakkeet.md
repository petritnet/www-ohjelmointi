+++
Categories = []
Description = ""
Tags = []
Title = "Lomakkeet"
date = "2016-01-06T23:32:46+02:00"
weight = 80

+++

Lomakkeiden tarkoituksena on yleensä kerätä käyttäjältä tietoja, esimerkiksi
palveluun rekisteröinnin tai sisäänkirjautumisen yhteydessä. Lomake voidaan toteuttaa
HTML-komponenttien avulla, mutta tiedon käsittelyyn tarvitaan yleensä kuitenkin
palvelinpäässä toimiva ohjelma.

Form-elementti
==============
Lomake merkitään `<form>`-tagilla. Se saa `method`-attribuutiksi menetelmän, jolla
tiedot lähetetään palvelimelle ja `action`-attribuutiksi osoitteen, johon tiedot
lähetetään käsiteltäväksi. Usein on lisäksi hyvä antaa lomakkeelle jokin nimi joko
`id`- tai `name`-attribuutilla, jotta siihen on tarvittaessa helpompi viitata.


Lähetysmetodi
--------------
Lähetysmetodi on valittavissa kahdesta vaihtoehdosta: `get` ja `post`. Lähetysmetodi
määrittelee sen, missä muodossa lomakkeella kerätty tieto lähetetään palvelimelle.

`GET`
:    Tarkoitettu nimensä mukaisesti tiedon pyytämiseen palvelimelta. (lähetettävää tietoa vähän)
:    Lisää lomakkeen tiedot URL-osoitteeseen `"nimi"="arvo"` -pareina.
:    Tietojen lähetysmäärällä on yläraja
:    Älä koskaan käytä arkaluonteisen datan lähettämiseen `get`-metodia!
:    Käyttökelpoinen, jos datan haluaa selaimen kirjanmerkkeihin.

`POST`
:    Tarkoitettu nimensä mukaisesti tiedon lähettämiseen palvelimelle. (lähetettävää ehkä paljon)
:    Tietojen lähetysmäärällä ei ole ylärajaa
:    Sopivampi arkaluonteisen datan lähettämiseen

Metodin valinnasta enemmän [palvelinosuudessa](../../palvelin/).

Action-attribuutti
------------------
Attribuutti määrittelee osoitteen, johon lomakkeen tiedot lähetetään. Se on ollut pakollinen kaikille
`form`-elementeille, mutta HTML5:n mukaan se ei enää ole sitä. Osoite voi olla suhteellinen tai absoluuttinen.

Lomakkeen nimi
--------------
Lomakkeelle annetaan tunniste joko `name`- tai `id`-attribuutilla. `name` on yhteensopiva vanhempienkin
selainten kanssa, mutta nykyisin `id`-attribuutin käyttö on kuitenkin suositeltavampaa.

Tunniste on tärkeä *erityisesti silloin*, kun sivulla on enemmän kuin yksi `form`-elementti.

```
<form method="post" action="login.php" name="kirjautuminen">
   ... Tähän tulee lomakkeen kenttiä ...
</form>

<form method="get" action="http://www.example.com/cgi-bin/handler.cgi" id="rekisterointilomake">
    ... Tähän tulee lomakkeen kenttiä ...
</form>

<form method="get" name="asetukset" id="form_1">
    ... Tähän tulee lomakkeen kenttiä ...
</form>
```

Lomakkeen sisältö
-----------------
Lomake sisältää syöttökenttiä (*input*) ja otsikoita eli nimilappuja (*label*). Syöttökenttä
luodaan `<input>`-tagilla, jolla ei ole lopetustagia. Yhdessä lomakkeessa voi olla useita erityyppisiä
syöttökenttiä. Input-tekstikenttään ei saa kuin yhden rivin tekstiä ja mikäli halutaan useampirivinen
syöttökenttä, voidaan käyttää `<textarea>`-tagia.

Input
======
Input-tagilla on useita attribuutteja ja attribuutit riippuvat usein syöte-elementin tyypistä.

`name` ja `id`
:    Kentän nimi – käytetään kentän tunnistamiseen

`size`
:    Oletuskoko – huomaa, että selain voi tästä huolimatta näyttää kentän minkä kokoisena tahansa.

`type`
:    Kentän tyyppi – esimerkiksi `text`, `password`,... tarkastellaan tarkemmin myöhemmin.

`maxlength`
:    Maksimipituus – huomaa, että tämäkin attribuutti on ohjeellinen ja käyttäjä tai selain voi ohittaa sen.

`value`
:    Kentän oletussisältö

`required`
:    Määrittää kentän pakolliseksi täyttää ennen lähetystä.

`disabled`
:    Asettaa kentän "pois päältä".


Input-tagin tyypit
------------------
Input-tagille voi `type`-attribuutilla määrätä erilaisia syöttötyyppejä. Tyyppi vaikuttaa kentän ulkoasuun ja
siihen, minkälaista tietoa sillä voi syöttää. Osa tyypeistä on uusia HTML5:n mukana tulevia ja niiden selaintuki
saattaa olla rajallinen. Jos selain ei tue valittua tyyppiä, kyseinen input-tagi näytetään tekstikenttänä.

| | Tyyppi        | Kuvaus                             | HTML                                     | Esimerkki     |
|---|---------------|------------------------------------|------------------------------------------|---------------|
||`button`       | Painonappi                         | `<input type="button" value="Lähetä">`   | <input type="button" value="Lähetä"> |
||`checkbox`     | Rastiruutu                         | `<input type="checkbox">`                | <input type="checkbox"> |
|![HTML5](../../images/html5-pieni.png)|`color`        | Värivalitsin                       | `<input type="color" value="#ffdd00">`   | <input type="color" value="#ffdd00"> |
|![HTML5](../../images/html5-pieni.png)|`date`         | Päivämäärä                         | `<input type="date" value="2016-02-01>`  | <input type="date" value="2016-02-01"> |
|![HTML5](../../images/html5-pieni.png)|`datetime`     | Päivämäärä ja aika                 | `<input type="datetime" value="2016-02-01 12:05">` | <input type="datetime" value="2016-02-01 12:05"> |
|![HTML5](../../images/html5-pieni.png)|`datetime-local`| Päivämäärä ja aika                | `<input type="datetime-local" value="2016-02-01 12:05">` | <input type="datetime-local" value="2016-02-01 12:05"> |
|![HTML5](../../images/html5-pieni.png)|`email`        | Sähköposti                         | `<input type="email" value="testi@example.com">` | <input type="email" value="testi@example.com"> |
||`file`         | Tiedosto                           | `<input type="file">`                    | <input type="file"> |
||`hidden`       | Piilotettu                         | `<input type="hidden" value="jotain">`   | <input type="hidden" value="jotain"> |
||`image`        | "Lähetä"-nappi kuvana              | `<input type="image" src="html5-pieni.png">` | <input type="image"  src="../../images/html5-pieni.png"> |
|![HTML5](../../images/html5-pieni.png)|`month`        | Kuukausi                           | `<input type="month" value="2016-02>`          | <input type="month" value="2016-02"> |
|![HTML5](../../images/html5-pieni.png)|`number`       | Kokonaisluku                       | `<input type="number" min="-5" max="5" value="2">` | <input type="number" min="-5" max="5" value="2"> |
||`password`     | Salasana                           | `<input type="password">`| <input type="password" value="joopajoo"> |
||`radio`        | Radio-valinta                      | `<input type="radio" value="a" name="yksi">a<br>`<br>`<input type="radio" checked="checked" value="b" name="yksi">b` | <input type="radio" value="a" name="yksi">a<br><input type="radio" checked="checked" value="b" name="yksi">b |
|![HTML5](../../images/html5-pieni.png)|`range`        | Liukusäädin (luku)                 | `<input type="range" min="-5" max="5" step="0.5" value="2">` | <input type="range" min="-5" max="5" step="0.5" value="2"> |
||`reset`        | Lomakkeen tyhjennys                | `<input type="reset">` | <input type="reset"> |
|![HTML5](../../images/html5-pieni.png)|`search`       | Hakukenttä                         | `<input type="search">` | <input type="search"> |
||`submit`       | Lähetys-nappi                      | `<input type="submit">` | <input type="submit"> |
|![HTML5](../../images/html5-pieni.png)|`tel`          | Puhelinnumero                      | `<input type="tel">`    | <input type="tel">   |
||`text`         | Teksti                             | `<input type="text" value="testi">` | <input type="text" value="testi"> |
|![HTML5](../../images/html5-pieni.png)|`time`         | Aika                               | `<input type="time" value="12:05">` | <input type="time" value="12:05"> |
|![HTML5](../../images/html5-pieni.png)|`url`          | URL-osoite                         | `<input type="url" value="http://petrit.net">` | <input type="url" value="http://petrit.net"> |
|![HTML5](../../images/html5-pieni.png)|`week`         | Viikko                             | `<input type="week" value="2016-W10">` | <input type="week" value="2016-W10"> |


Esimerkkejä:

* Tekstikenttä,jossa kysytään käyttäjän nimeä
* Pakollinen tekstikenttä, jossa kysytään salasanaa
* Tekstikenttä, jossa kysytään verkko-osoitetta

```
<input name="nimi" type="text" size="30" value="" maxlength="40">
<input name="salasana" type="password" size="20" maxlength="20">
<input name="verkkosivu" type="url">
```
<div class="html-example">
<input name="nimi" type="text" size="30" value="" maxlength="40">
<input name="salasana" type="password" size="20" maxlength="20">
<input name="verkkosivu" type="url">
</div>


Kenttien otsikot
----------------
Syöttökentille voi kirjoittaa otsikon pelkällä tekstillä, mutta kenttien otsikot kannattaa
antaa `<label>`-tagilla. `<label>`-elementti yhdistetään johonkin syöttökenttään `for`-attribuutin
avulla. Attribuutin arvon pitää olla täsmälleen sama kuin kentän `id`-attribuutin arvon. Tällöin
kentän otsikosta tulee osa syöttökenttää.

```
Etunimi: <input name="etunimi" id="nimi1" type="text" value="" size="20" maxlength="20">
<br>
<label for="nimi2">Etunimi:</label> <input name="etunimi" id="nimi2" type="text" value="" size="20" maxlength="20">
```
<div class="html-example">
Etunimi: <input name="etunimi" id="nimi1" type="text" value="" size="20" maxlength="20">
<br>
<label for="nimi2">Etunimi:</label> <input name="etunimi" id="nimi2" type="text" value="" size="20" maxlength="20">
</div>


Perus input-tyypit
------------------

`text`
:    Tavallinen tekstisyöttö

`password`
:    "Salattu" salasanan syöttökenttä

`checkbox`
:    Päällä / pois -tyyppinen "rastiruutu". Oletuksena "rastiruutu" voidaan laittaa valmiiksi päälle antamalla sille
     attribuutti `checked="checked"`.

`radio`
:    Optionapit eroavat "rastiruuduista" siinä, että ainoastaan yksi samaan rymään kuuluvista napeista voi olla kerrallaan
     valittuna. Esivalinnan voi tehdä asettamalla attribuutin `checked="checked"`.
:    Samaan ryhmään kuuluvat napit yhdistetään antamalla niille sama nimi `name`-attribuutilla.
:    Samaan ryhmään kuuluvat napit erotetaan toisistaan `value`-attribuutilla.

`hidden`
:    Joskus on tarpeellista lähettää lomakkeen mukana sellaisia tietoja, joita ei haluta muuttaa tai näyttää käyttäjälle.
     Nämä voidaan antaa `hidden`-tyyppisellä input-tagilla.
:    Tunnisteeksi sille annetaan `name`-attribuutti ja sisällöksi `value`-attribuutti.

`submit`
:    Lomakkeen lähetystä varten siihen lisätään tyyppiä `submit`-oleva painonappi. Napin looginen paikka on yleensä lomakkeen lopussa.
     Napin teksti tulee sen `value`-attribuutista.

`reset`
:    Lomake voidaan tyhjentää tyyppiä `reset` olevalla napilla. Napin teksti tulee sen `value`-attribuutista.


Lomakkeen muotoilu
==================
Koska lomakkeet ovat usein luonnostaan taulukkomuotoista sisältöä, voidaan niiden muotoilussa hyödyntää [taulukkoja](../taulukot).
Label-elementit asetetaan yleensä taulukon vasempaan sarakkeeseen ja kentät oikeaan.

```
<form name="kirjautumislomake" method="post" action="http://www.example.com/">
    <h1>Esimerkki kirjautumislomakkeesta</h1>
    <p>Kirjoita seuraaviin kenttiin nimesi ja salasanasi ja valitse lähetä!</p>
    <table>
        <tr>
            <td><label for="k_nimi">Nimi:</label></td>
            <td><input type="text" name="nimi" id="k_nimi" size="20"/> </td>
        </tr>
        <tr>
            <td><label for="s_sana">Salasana:</label></td>
            <td><input type="password" name="salasana" id="s_sana" size="20"/></td>
        </tr>
    </table>
    <p>
    <input type="submit" name="laheta" value="Lähetä!"\>
    </p>
</form>
```
<div class="html-example">
<form name="kirjautumislomake" method="post" action="">
    <h1>Esimerkki kirjautumislomakkeesta</h1>
    <p>Kirjoita seuraaviin kenttiin nimesi ja salasanasi ja valitse lähetä!</p>
    <table class="rawtable">
        <tr>
            <td><label for="k_nimi">Nimi:</label></td>
            <td><input type="text" name="nimi" id="k_nimi" size="20"/> </td>
        </tr>
        <tr>
            <td><label for="s_sana">Salasana:</label></td>
            <td><input type="password" name="salasana" id="s_sana" size="20"/></td>
        </tr>
    </table>
    <p>
    <input type="submit" name="laheta" value="Lähetä!"\>
    </p>
</form>
</div>

Lomakkeiden syöttökenttiä voi myös ryhmitellä `<fieldset>`-tagin avulla. Tällöin selain "laatikoi"
samaan ryhmään kuuluvat syöttökentät. Ryhmälle voi antaa otsikon `<legend>`-tagilla.
Ryhmää ja sen otsikkoa voidaan käyttää myös suoraan kentän otsikkona.

```
<fieldset>
    Nimi: <input type="text" name="nimi"/><br>
    Osoite: <input type="text" name="osoite"/>
</fieldset>

<fieldset>
    <legend>Perustiedot</legend>
    Nimi: <input type="text" name="nimi"><br>
    Osoite: <input type="text" name="osoite">
</fieldset>

<fieldset>
    <legend>Lisätiedot</legend>
    Ikä: <input type="text" name="ika"\><br>
    Puhelin: <input type="text" name="puhelin">
</fieldset>

<fieldset>
    <legend>Nimi:</legend>
    <input type="text" name="nimi"/>
</fieldset>
```
<div class="html-example">
<fieldset>
    Nimi: <input type="text" name="nimi"/><br>
    Osoite: <input type="text" name="osoite"/>
</fieldset>

<fieldset>
    <legend>Perustiedot</legend>
    Nimi: <input type="text" name="nimi"><br>
    Osoite: <input type="text" name="osoite">
</fieldset>

<fieldset>
    <legend>Lisätiedot</legend>
    Ikä: <input type="text" name="ika"\><br>
    Puhelin: <input type="text" name="puhelin">
</fieldset>

<fieldset>
    <legend>Nimi:</legend>
    <input type="text" name="nimi"/>
</fieldset>
</div>


Muita lomake-elementtejä
========================
Input-tagien lisäksi lomakkeissa voi käyttää myös muutamaa muuta elementtityyppiä.

Textarea
--------
Lomakkeeseen voidaan syöttää useamman kuin yhden rivin verran tekstiä `<textarea>`-tagin avulla.
Tagi saa attribuutikseen nimen (ja mahdollisen `id`-arvon) lisäksi rivien ja sarakkeiden määrät
`rows`- ja `cols`-attribuuteilla. Huomaa, että toisin kuin `<input>`-tagilla, `<textarea>`:lla on myös lopputagi.

```
<label for="teksti_area">Kirjoita kuvaus itsestäsi:</label><br>
<textarea name="kuvaus" id="teksti_area" rows="5" cols="80">Oletussisältö tähän</textarea>
```
<div class="html-example">
<label for="teksti_area">Kirjoita kuvaus itsestäsi:</label><br>
<textarea name="kuvaus" id="teksti_area" rows="5" cols="80">Oletussisältö tähän</textarea>
</div>

Alasvetovalikko `<select>`
---------------
Lomakkeeseen voidaan liittää alasvetovalikoita `<select>`-tagin avulla. Tagin sisään kirjoitetaan
valittavien vaihtoehtojen näkyvät tekstit `<option>`-tagin sisään ja vaihtoehdon arvo tagin
`value`-attribuutin arvoksi. Oletuksena valitun vaihtoehdon voi valita lisäämällä tagiin
attribuutin `selected="selected"`.

Alasvetovalikon toiminnallisuus on käytännössä sama kuin `radio`-tyyppisen `<input>`-tagin, mutta
sen visuaalinen ulkoasu on kompaktimpi.

```
<select name="juomat">
    <option value="milk">Maito</option>
    <option value="water" selected="selected">Vesi</option>
    <option value="coffee">Kahvi</option>
    <option value="tea">Tee</option>
    <option value="cola">Kola-kola</option>
</select>
```
<div class="html-example">
<select name="juomat">
    <option value="milk">Maito</option>
    <option value="water" selected="selected">Vesi</option>
    <option value="coffee">Kahvi</option>
    <option value="tea">Tee</option>
    <option value="cola">Kola-kola</option>
</select>
</div>

