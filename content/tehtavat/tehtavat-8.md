+++
Categories = []
Description = ""
Tags = []
Title = "Tehtävät 8"
date = "2016-03-28T18:28:20+03:00"
weight = 10
deadline = "4.4.2016"
+++

Kertaustehtäviä
-----------------

Lataa oheinen [zip-paketti](../../files/tehtava8.zip), josta löytyy HTML-, CSS- ja Javascript-tiedosto.
Täydennä ne alla olevien ohjeiden mukaisesti. Lisää HTML-elementit HTML-tiedostoon,
CSS-säännöt CSS-tiedostoon ja Javascript-toiminnallisuus JS-tiedostoon.

Tee oma ratkaisusi ennen kuin katsot [malliratkaisun](../../files/tehtava8-malliratkaisu.zip).

1. Lisää `<article>`-osioon merkittyyn kohtaan (Paikka 1) neljä 2-tason otsikkoa luokilla `haitariotsikko` ja teksteillä:
    - HTML
    - CSS
    - Javascript
    - Palvelin
2. Lisää edellisen kohdan kunkin otsikon alle `<div>`-elementti, jonka luokkana
   on `haitarisisalto`.
3. Lisää edellisen kohdan elementtien sisään numeroidut listat, joiden alkioina ovat
   kurssin kotisivuilla vastaavan osion etusivulla olevat viisi ensimmäistä väliotsikkoa. (1. Johdanto, 2. Dokumentin rakenne, 3. Head-osio,...)
4. Tee lista-alkioista linkkejä vastaaville sivuille.
5. Lisää luokalla `haitari` ja id:llä `haitari1` varustettu `<div>`-elementti kaikkien `haitariotsikko`- ja `haitarisisalto`-elementtien ympärille. (Yksi elementti)
6. Kopioi `#haitari1` kahteen muuhun merkittyyn kohtaan (Paikka 2 ja Paikka 3) ja vaihda näiden uusien elementtien id:ksi vastaavasti `haitari2` ja `haitari3`.
6. Lisää CSS-sääntö, jolla `haitari`-luokalla varustetuille elementeille tulee
    - maksimileveydeksi 45 em
    - vasemmaksi ja oikeaksi marginaaliksi arvot `auto`
7. Lisää CSS-säännöt, joka laittavat `haitariotsikko`-luokalla varustetuille `<h2>`-otsikoille seuraavat tyylit:
    - sopiva taustaväri
    - sopivan värinen ja paksuinen reunaviiva
    - reunaviivalle pyöristystä
    - sopivasti täytettä, että teksti ei ole ihan raunassa kiinni
    - marginaaliksi 0
    - hiiren kursoriksi sama kuin yleensä linkeillä
    - korosta otsikkoa jotenkin, kun hiiri on sen päällä (esimerkiksi vaaleampi taustaväri, varjostuksella luoto hehku tai erivärinen teksti)
8. Lisää CSS-sääntö, jolla `haitariotsikko`-elementeille `before`-pseudoelementin sisällöksi tulee Unicode-merkki numero 25B6.
9. Lisää CSS-sääntöjä `haitarisisalto`-elementille
    - taustaväri/-kuva
    - marginaali: ylös ja alas 0, sivuille "sopivasti"
    - täytettä ylös ja alas 1em ja sivuille sopivasti
    - ohut reunaviiva
10. Lisää CSS-sääntö, joka piilottaa `haitarisisalto`-elementit näkyvistä. (Niin, etteivät ne vie tilaa)
11. Lisää CSS-sääntö, joka korostaa `haitariotsikko`-elementit, jos niillä on myös luokka `auki`.
12. Lisää CSS-sääntö, jolla `haitariotsikko`-elementin `before`-pseudoelementin sisällöksi tulee Unidoce-merkki numero 25BC, jos sillä on luokka `auki`.
13. Lisää CSS-sääntö, joka asettaa `haitarisisalto`-elementin näkyviin, jos se on `haitari1`:n sisällä ja sen edellä on `haitariotsikko`, jolla on luokka `auki`.
14. Lataa jQuery-kirjaston versio 1.12.x osoitteesta https://jquery.com/ ja lataa se HTML-tiedoston `<head>`-osiossa.
15. Lisää JS-tiedostoon rakenne, jolla toimintoja suoritetaan, kun sivu on ladattu:<br>
    `$(document).ready(function(){ /* Tähän koodia */ });`<br>
    Lisää rakenteen sisään seuraavat toiminnallisuudet.
17. Etsitään sivulta kaikki `haitari1`-id:llä varustetun elementin sisällä olevat `haitariotsikko`-elementit
    - Lisätään niille tapahtumakäsittelijä tapahtumalle `click`. Käsittelijä tekee seuraavaa:
    - jos klikatulla otsikolla (`$(this)`) on luokka `auki`, se poistetaan, jos ei, niin se lisätään
18. Etsitään sivulta kaikki `haitari2`-id:llä varustetun elementin sisällä olevat `haitariotsikko`-elementit
    - Lisätään niille tapahtumakäsittelijä tapahtumalle `click`. Käsittelijä tekee seuraava:
    - Tarkistetaan, onko otsikolla (`$(this)`) luokka `auki`. (Laita muuttujaan)
    - Jos luokka on, otetaan se pois ja liu'utetaan sen jälkeen oleva `haitarisisalto` (`.next('.haitarisisalto')`) animoiden kiinni (`.slideUp()`).
    - Jos luokkaa ei ole, lisätään se ja liu'utetaan sen jälkeen oleva `haitarisisalto` (`.next('.haitarisisalto')`) animoiden auki (`.slideDown()`).
19. Etsitään sivulta kaikki `haitari3`-id:llä varustetun elementin sisällä olevat `haitariotsikko`-elementit
    - Lisätään niille tapahtumakäsittelijä tapahtumalle `click`. Käsittelijä tekee seuraavaa:
    - Tarkistetaan, onko otsikolla (`$(this)`) luokka `auki`. (Laita muuttujaan)
    - Etsitään otsikon lähimmän vanhempana olevan `haitari`-luokallisen elementin (`.closest('.haitari')`) lapset, joilla on luokka `haitariotsikko` ja otetaan niiltä pois luokka `auki`.
    - Etsitään otsikon lähimmän vanhempana olevan `haitari`-luokallisen elementin (`.closest('.haitari')`) lapset, joilla on luokka `haitarisisalto` ja liu'utetaan ne kiinni.
    - Jos klikattu otsikko ei ollut auki, lisätään sille luokka `auki` ja liu'utetaan sen jälkeen oleva `haitarisisalto` auki.