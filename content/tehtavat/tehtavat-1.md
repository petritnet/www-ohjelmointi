+++
date = "2016-01-06T12:37:40+02:00"
title = "Tehtävät 1"
weight = 1
deadline = "11.3.2016"

+++

Tee seuraavat tehtävät. Tarkista tiedostojen toimivuus lataamalla sivu selaimeen.

Toteutetaan www-sivu, jolla esitellään joku kuvitteellinen tai todellinen henkilö.

1. Luo uusi tekstitiedosto kyseisen henkilön nimellä, esimerkiksi `aku_ankka.txt`.
   Kirjoita tekstitiedostoon seuraavat tiedot järjestyksessä:
    <dl class="reunuksilla">
        <dt>Henkilön nimi</dt>
        <dd>Kirjoita kuvaus henkilöstä. Pituutta muutama lause.</dd>
        <dt>Harrastukset</dt>
        <dd>Kirjoita kuvaus henkilön harrastuksista. Pituutta muutama lause.</dd>
        <dt>Mielenkiintoisia asioita verkossa</dt>
        <dd>Kirjoita selvitys muutamista henkilöön liittyvistä verkkosivuista ja niiden sisällöstä. Pituutta muutama lause.</dd>
    </dl>
2. Luo uusi HTML-tiedosto henkilön nimellä, esimerkiksi `aku_ankka.html`. Kopioi tekstitiedoston sisältö
    siihen kokonaisuudessaan.
3. Lisää HTML-tiedostoon `<html>`-, `<head>`- ja `<body>`-tagit oikeille paikoilleen. Lisää
    head-osioon dokumentin otsikko `<title>`-tagilla. Varmista, että tiedosto tallennetaan
    `utf-8`-muotoisena ja lisää merkistökoodauksen kertova `<meta>`-tagi.
4. Merkitse otsikot `<h?>`-tageilla. Pohdi, mikä on dokumentin pääotsikko ja mitkä alaotsikoita.
5. Merkitse leipäteksti (tekstikappaleet) `<p>`-tageilla.
6. Etsi vaikka Googlen kuvahaun tai vastaavan avulla verkosta henkilöllesi jokin kasvokuva.
    (jpg, png, n. 400x600 pikseliä) Tallenna se www-sivun kanssa samaan hakemistoon henkilön nimellä,
    esimerkiksi `aku_ankka.jpg`. Muista ottaa talteen kuvan alkuperäinen osoite.
7. Avaa lataamasi kuva johonkin kuvankäsittelyohjelmaan ja tee kuvasta noin 100x100 pikselin
    kokoinen kopio. Tallenna kopio samaan hakemistoon. Esimerkiksi nimellä `aku_ankka_pieni.jpg`.
8. Lisää pikkukuva www-sivulle henkilön kuvauksen perään `<img>`-tagin avulla. Anna tagille attribuuteiksi
    kuvan osoitteen lisäksi koko ja vaihtoehtoinen teksti.
9. Lisää "Mielenkiintoisia asioita verkossa" -kohtaan leipätekstin sekaan linkit tekstissä
    mainituille sivuille `<a>`-tagilla. Pohdi erityisesti, mitä sanoja tai lauseita kannattaa
    käyttää linkkinä. Käytä absoluuttisia viittauksia!
10. Tee hakemistoon uusi HTML-tiedosto nimellä `harrastukset.html`. Kopio "Harrastukset"-osio
    (otsikko ja leipäteksti) aiemmasta HTML-tiedostosta tähän tiedostoon. Lisää tarvittavat
    `<html>`-, `<head>`- ja `<body>`-tagit.
11. Poista "Harrastukset"-osio alkuperäisestä dokumentista ja korvaa se linkillä tiedostoon
    `harrastukset.html`. Käytä suhteellista viittausta!
12. Tee etusivulle lisäämästäsi pikkukuvasta linkki alkuperäiseen kuvaan verkossa.
    (Kuvasta saa linkin lisäämällä `<a>`-tagin kuvan ympärille.)

[JSBin]: https://jsbin.com "JSBin"