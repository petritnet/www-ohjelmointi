+++
Categories = []
Description = ""
Tags = []
Title = "Entiteetit"
date = "2016-01-06T23:32:27+02:00"
weight = 70

+++

Eräitä erikoismerkkejä (esimerkiksi `<` ja `>`) ei voi kirjoittaa tekstin sekaan
suoraan, vaan ne on kirjoitettava erikoismerkinnällä, eli [*entiteetteinä*][Entiteetit].

HTML-entiteetti alkaa `&`-merkillä ja päättyy puolipisteeseen `;`. Entiteetin
tunniste on teksti tai järjestysnumero muodossa `#numero`.

Esimerkiksi:

| Merkki       | Entiteetti    | Merkki      | Entiteetti    |
|--------------|---------------|-------------|---------------|
| "välilyönti" | `&nbsp;`      | &           | `&amp;`       |
| <            | `&lt;`        | "           | `&quot;`      |
| >            | `&gt;`        | €           | `&euro;`      |
| ä            | `&auml;`      | &copy;      | `&copy;`      |
| Ä            | `&Auml;`      | &rarr;      | `&rarr;`      |
| ö            | `&ouml;`      | &clubs;     | `&clubs;`     |
| Ö            | `&Ouml;`      | &permil;    | `&permil;`    |


[Entiteetit]: http://www.w3schools.com/html/html_entities.asp "W3Schools:Entiteetit"