+++
Categories = []
Description = ""
Tags = []
Title = "CSS-määrittelyt"
date = "2016-02-10T20:27:49+02:00"
weight = 10

+++

CSS-määrittelyt muodostuvat avain–arvo -pareista siten, että määrittelyssä ensin tulee
määriteltävä **ominaisuus**, sen jälkeen kaksoispiste **`:`**, ominaisuuden **arvo** sekä lopuksi
puolipiste **`;`**. CSS-määrittelyt ovat samaa muotoa riippumatta siitä, onko ne kirjoitettu
suoraan HTML-elementin `style`-attribuuttiin vai erillisiksi valitsimilla kohdennetuiksi
tyylisäännöiksi.

<figure>
<svg xmlns="http://www.w3.org/2000/svg" version="1.1" width="500" height="200" viewBox="0 0 500 200" class="chart">
    <text x="10" y="100" style="font-weight: bold;">
        &lt;h1 style="<tspan style="fill: blue;">color</tspan><tspan style="fill: red;">:</tspan> <tspan style="fill: green;">red</tspan><tspan style="fill: red;">;</tspan> <tspan style="fill: blue;">font-size</tspan><tspan style="fill: red;">:</tspan> <tspan style="fill: green;">10px</tspan><tspan style="fill: red;">;</tspan>"&gt;Otsikko&lt;/h1&gt;
    </text>
    <text x="100" y="20" style="font-weight: bold; fill: blue;">ominaisuus</text>
    <text x="250" y="20" style="font-weight: bold; fill: green;">arvo</text>
    <path style="stroke: blue; stroke-width: 2px; fill: none;" d="M120 80 l20 -50 l70 50" />
    <path style="stroke: green; stroke-width: 2px; fill: none;" d="M160 80 l100 -50 l10 50" />
    <text x="140" y="180" style="font-weight: bold; fill: black;">välimerkit <tspan fill="red">:</tspan> ja <tspan fill="red">;</tspan></text>
    <path style="stroke: red; stroke-width: 2px; fill: none;" d="M140 110 l50 50 l100 -50" />
    <path style="stroke: red; stroke-width: 2px; fill: none;" d="M170 110 l20 50 l50 -50" />
</svg>
</figure>

CSS-määrittelyitä `style`-attribuutissa:
```
<h1 style="color: red; font-size: 10px;">Otsikko</h1>
```

Valitsimella kohdennettuja CSS-määrittelyitä `<style>`-tagin sisällä tai erillisessä css-tiedostossa:
```
h1 {
    color: red;
    font-size: 10px;
}
```