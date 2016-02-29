+++
date = "2016-01-06T12:37:40+02:00"
title = "Tehtävät 3"
weight = 3
+++

Luo HTML-dokumentti nimellä `lomakeharjoitus.html`.

Toteuta dokumenttiin lomake, jolla kysytään käyttäjältä oheiset tiedot.
Pohdi, mikä elementti sopii parhaiten kunkin tiedon kysymiseen käytettävyyden
ja haettavan informaation kannalta.

Lisää dokumenttiin muut tarpeelliset elementit (mm. ryhmät, otsikot ja selitystekstit).
Mieti myös mitkä kentät ovat vastauksessa pakollisia. Tarkista lopuksi, että sivu
validoituu ja korjaa mahdolliset virheet.

Lomakkeen `action`-attribuutiksi voit antaa osoitteen *http://www.w3schools.com/tags/demo_form.asp*, jolloin
lomake lähetetään käsiteltäväksi w3schoolsin palvelimelle, joka tulostaa lomakkeeseen syötetyt tiedot.
Tarkastele kumpaa lähetysmetodia palvelin käsittelee.

Tyylittele lomaketta makusi mukaan esimerkiksi seuraavaan tapaan:

- Merkitse pakolliset kentät punaisella värillä
- Alleviivaa otsikko.
- Lihavoi tärkeimmät kenttien nimet (nimi, ikä, osoite).
- Laita sivulle taustaväri tai kuva.

<div class="tehtavaluettelo">
    <div class="esimlomake">
        <h3>Ohjelmointikokemukset</h3>
        <p>Nimi: <br>
        Ikä: </p>
        <p>Osoite:<br>
        Sähköpostiosoite:<br>
        Puhelinnumero:</p>
        <p>Sukupuoli: </p>
        <p>Koulutus (ilmoita myös valmistumisvuodet):</p>
        <p>Olen kuullut seuraavista ohjelmointikielistä aikaisemmin:</p>
        <ul>
            <li>Java / C#</li>
            <li>Python</li>
            <li>C / C++</li>
            <li>Perl</li>
            <li>Pascal / Delphi</li>
        </ul>
        <p>Mieluisin ohjelmointikielistä minulle on:</p>
        <ul>
            <li>Java / C#</li>
            <li>Python</li>
            <li>C / C++</li>
            <li>Perl</li>
            <li>Pascal / Delphi</li>
        </ul>
        <p>Ohjelmointikokemukseni seuraavilla kielillä <br>
        (asteikolla 1...5: 1 – ei yhtään, 3 – jonkin verran, 5 – paljon):</p>
        <ul>
            <li>Java / C#</li>
            <li>Python</li>
            <li>C / C++</li>
            <li>Perl</li>
            <li>Pascal / Delphi</li>
        </ul>
        <p>Muuta kerrottavaa aikaisemmasta ohjelmointikokemuksestani:</p>
    </div>
</div>
