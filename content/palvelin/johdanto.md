+++
Categories = []
Description = ""
Tags = []
date = "2016-01-06T12:37:27+02:00"
title = "Johdanto"
weight = 10

+++

Palvelin tarjoilee www-sivut ja muun materiaalin asiakkaalle, eli yleensä www-selaimelle,
sen pyyntöjen mukaan. Kun asiakas tulee sivulle, se pyytää ensin itse html-sivun tiedoston.
Sen www-selain alkaa näyttää sivua sekä etsii html-sivun sisällöstä kaikkien muiden tarvittavien
tiedostojen URL-osoitteet. Näitä ovat muun muassa:

- CSS-tiedostot
- Javascript-tiedostot
- Sivun ikoni (favicon)
- Sivulla olevat kuvat

Esimerkiksi CSS-tiedostoissa voi olla lisäksi viittauksia muihin tiedostoihin, kuten:

- Fonttitiedostot
- Taustakuvat
- Muita CSS-tiedostoja

Asiakas pyytää myös nämä tiedostot palvelimelta tarpeensa mukaan. Yksinkertaisimmillaan
www-sivut ja niiden muu materiaali ovat tavallisia tiedostoja ja palvelimen tehtävänä on
vain antaa asiakkaalle pyydetty tiedosto.



Staattiset vs. dynaamiset sivut
===============================

Www-selaimen tai muun asiakaan kannalta toiminta näyttää aina samanlaiselta, pyydetään
tiedostoja ja näytetään sivu tai sovellus saatujen tiedostojen mukaan. Palvelimen puolella
toteutus voi kuitenkin vaihdella hyvinkin paljon. Tärkein jaottelu on sivustojen jakautuminen
staattisiin ja dynaamisiin.

Staattiset sivut ovat valmiissa muodossa HTML-tiedostoina palvelimella (tai omalla koneella)
ja palvelimen tehtävänä on vain antaa ne asiakkaalle pyydettäessä. Mahdolliset dynaamiset
toiminnallisuudet on toteutettu Javascriptillä ja ne suoritetaan asiakkaan puolella.

<figure>
    <img src="../../images/palvelin-staattinen.svg" style="max-width: 90%;" alt="staattinen sivu palvelimelta">
</figure>

Palvelinpuolen dynaamiset www-sivut **muodostetaan palvelinpäässä** selaimen pyytäessä
kyseistä sivua. Sivun sisältö haetaan esimerkiksi tietokannasta ja lisätään haluttuun
kohtaan sivupohjaa. Palvelimella ei siis ole olemassa kyseistä kokonaista HTML-tiedostoa
vaan se luodaan joka kerta uudelleen, kun sitä pyydetään.

<figure>
    <img src="../../images/palvelin-dynaaminen.svg" style="max-width: 90%;" alt="dynaaminen sivu palvelimelta">
</figure>

Selaimen ja selailijan kannalta näillä kahdella ei ole eroa.
