+++
Categories = []
Description = ""
Tags = []
Title = "Tehtävät 4"
date = "2016-02-29T21:27:38+02:00"
weight = 4
deadline = "18.3.2016"

+++

Lataa itsellesi [html-tiedosto][html-pohja] (hiiren oikea nappi, "tallenna linkki").
Lisää `head`-osioon uusi `style`-tagi ja sen sisälle seuraavat muotoilut css-sääntöinä:

1. Kasvata sivun ylimmän otsikon ("Esimerkkisivu") kokoa noin kaksinkertaiseksi
2. Muuta sisällön `h1`-otsikoiden väriksi tummansininen (`darkblue`).
3. Muuta sisällön `h2`-otsikoiden väriksi tummanpunainen (`darkred`) sekä asettele ne keskitetysti.
4. Poista linkeiltä alleviivaus (`text-decoration`) ja muuta niiden tyyli (`text-style`) kursivoiduiksi (`italic`).
5. Aseta body-elementin taustakuvaksi kuva: http://upload.wikimedia.org/wikipedia/commons/f/f1/Tournesol.png .
    Asettele kuva pystysuunnassa ylös, sivusuunnassa vasemmalle, toista kuvaa pysty- ja vaakasuunnassa. Aseta kuvalisäksi paikalleen
    kiinteästi css-säännöllä: `background-attachment: fixed;`
6. Muuta `strong`-tagilla merkityt tekstit punaisiksi ja alleviivatuiksi (`text-decoration`).
7. Aseta `em`-tagilla merkityille teksteille vaaleankeltainen taustaväri.
1. Lisää `em`-tagilla merkityille teksteille yhden pikselin paksuinen harmaa (`gray`)
    katkoviivoitettu (`dashed`) reunus.
2. Lisää otsakkeelle (`header`):
    - korkeus `200` pikseliä (`px`),
    - leveys `50` m-kirjaimen leveyttä (`em`),
    - marginaali ylös ja alas `0`, oikealle ja vasemmalle `auto`,
    - teksti keskitetyksi,
    - taustaväriksi valkoinen (`white`),
    - "täytettä (`padding`) `1` m-kirjain (`em`),
    - kulmien pyöristyssäteeksi `1` m-kirjain (`em`),
    - kaksi sisäpuolista (`inset`) varjoa, joista toinen `5` pikseliä oikealle ja alas mustana (`black`)
      ja toinen `5` pikseliä ylös ja vasemmalle harmaana (`gray`). Molemmat `5` pikselin sumennuksella.
3. Lisää otsakkeen (`header`) otsikolle (`h1`) harmaa (`gray`) varjo oikealle alas.
4. Lisää otsakkeen (`header`) kuvalle (`img`) tyyli: `float: left;`.
5. Aseta sivun tekstisisällölle (`article`):
    - leveydeksi `40` m-kirjaimen leveyttä (`em`),
    - marginaaleiksi ylös ja alas `2em` ja sivuille `auto`,
    - "täytteeksi" (`padding`) yksi m-kirjaimen leveys (`em`),
    - taustaväriksi valkoinen (`white`),
    - vasempaan ja oikeaan reunaan `1` pikselin (`px`) harmaa (`gray`) pisteviiva (`dotted`),
    - ylös ja alas musta kiinteä (`solid`) viiva, ylös `2` pikselin paksuinen, alas `4` pikseliä,
    - laatikolle varjo `20` pikseliä alas ja oikealle `60` pikselin sumennuksella ja harmaalla värillä.
6. Lisää tekstisisällössä (`article`-tagin sisällä) oleville kuville (`img`):
    - musta (`black`) taustaväri,
    - "täytettä" 10 pikseliä,
    - 15 pikselin reunus, joka on ylä- ja alapuolella harmaa ja sivuilla vaalean harmaa (`lightgray`),
    - marginaalia 2 m-kirjaimen verran muille sivuille, mutta oikealle 0,
    - mustaa pudotusvarjoa oikealle alas harkintasi mukaisen määrän,
    - aseta kuvat tekstin oikeaan reunaan niin, että teksti kiertää kuvan (css-sääntönä `float: right;`)
7. Tekstisisällön (`article`) sisällä olevalle listalle (`ul`):
    - ylös ja alas 2 pikselin sininen (`blue`) reunus,
    - "täytettä" pystysuunnassa 0.5 m-kirjaimen ja vaakasuunnassa 2 m-kirjaimen verran,
    - tekstin väriksi tumman sininen (`darkblue`)
8. Tekstisisällön (`article`) sisällä olevan listan (`ul`) sisällä olevalle alilistalle (`ul`):
    - poista reunus,
    - lisää vasen reunus, jonka paksuus on 6 pikseliä, tyyli `groove` ja väri sininen,
    - muuta lista-alkioiden palluran tilalle neliö (`square`)
9. Taulukolle (`table`):
    - 3 pikselin verran kaksinkertaista (`double`) sinistä reunaviivaa
    - marginaaliksi ylös ja alas 0, sivuille `auto`,
    - aseta fonttiperheeksi (`font-family`) tasavälinen fontti (`monospace`),
    - lisää vielä css-sääntö: `border-collapse: collapse;`
10. Taulukon otsakkeen (`tbody`) sisällä oleville otsikkosoluille (`th`):
    - taustaväriksi sininen,
    - väriksi valkoinen,
    - tekstivarjoksi 1 pikselin verran vasemmalle ja ylös sekä 1 pikselin sumennuksella musta varjo,
    - "täytettä" pystysuunnassa 0 ja sivusuunnissa puoli m-kirjainta.
11. Taulukon rungon (`tbody`) sisällä oleville otsikkosoluille (`th`):
    - yläreunaksi 2 pikselin kiinteä sininen viiva,
    - alareunaksi 1 pikselin sininen pisteviiva (`dotted`)
12. Lisää alatunnisteelle (`footer`):
    - taustaväriksi valkoinen,
    - reunukseksi 1 pikselin paksuinen harmaa pisteviiva,
    - puolen m-kirjaimen verran "täytettä"
13. Poista alatunnisteen listan (`ul`) alkioilta listapallero.
14. Muuta alatunnisteen listan alkioita (`li`) seuraavasti:
    - muuta ne `display`-tyypiltään `inline-block`-tyyppisiksi,
    - muuta marginaaliksi pystysuunnassa 0 ja sivusuunnassa 0.5em,
    - "täytteeksi" pystysuunnassa puoli m-kirjainta ja vaakasuuunnassa yksi m-kirjain,
    - reunaksi 1 pikselin kiinteä harmaa reunaviiva,
    - pyöristä kulmat yhden m-kirjaimen säteellä,
    - taustaväriksi `gold`,
    - laatikolle kaksi sisäpuolista (`inset`) varjoa:
        - 5 pikseliä alas oikealle 5 pikselin sumennuksella ja vaaleanharmaalla värillä,
        - 5 pikseliä ylös vasemmalle 5 pikselin sumennuksella ja harmaalla värillä

Kokeillaan seuraavaksi css-sääntöjen käyttämistä ulkoisella tiedostolla.

1. Kopio äskeisestä html-tiedostosta `style`-tagin sisältö uuteen tiedostoon ja tallenna se nimellä `oma.css`.
2. Poista html-tiedostosta `style`-tagin sisältö sekä korvaa se `link`-tagilla, joka viittaa tekemääsi css-tiedostoon.<br>
    `<link rel="stylesheet" type="text/css" href="oma.css" />`
3. Vertaa lopputulosta [kuvakaappaukseen][mallisivu]
4. Palauta tekemäsi tyylitiedosto sähköpostilla.



[html-pohja]: ../../files/tyyliteltavaa.html "Tyyliteltävä html-tiedosto"
[mallisivu]: ../../files/mallisivu.png "Mallisivu"