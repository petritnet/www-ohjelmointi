+++
Categories = []
Description = ""
Tags = []
Title = "Elementtien koko"
date = "2016-02-10T21:32:19+02:00"
weight = 110

+++

Normaalisti lohkoelementtien koko määräytyy sen sisällä olevan
materiaalin määrän mukaan. Toisinaan kuitenkin on tarvetta määritellä
elementille koko, jolloin sen sisältö ei välttämättä enää mahdu kokonaisuudessaan
elementin sisään.

Koon määrittely
===============
Lohkotyyppisen elementin leveys ja korkeus voidaan määrätä jo aiemmin tutuksi
tulleilla `width`- ja `height`-ominaisuuksilla. Näiden lisäksi elementtien leveyteen ja
korkeuteen voidaan vaikuttaa määräämällä niille vähimmäis- ja enimmäisleveyksiä ja
-korkeuksia. Näitä varten käytetään ominaisuuksia:

- `min-width`
- `min-height`
- `max-widht`
- `max-height`

Nämä määräävät arvot, joiden yli tai ali leveys ja korkeus eivät voi mennä.

Sisällön ylivuoto
=================

Jos elementin koko on määritelty pienemmäksi kuin sen sisällön koko, silloin
sisältö *vuotaa yli*. Se, miten ylivuototilanteessa toimitaan määräytyy
`overflow`-ominaisuuden avulla. Tämä ominaisuus voi saada arvokseen
jonkin seuraavista avainsanoista:

- `visible` – Selain piirtää sisällön elementin reunojen yli, jos sisältö ei mahdu sen sisälle.
- `hidden` – Selain piilottaa sisällön ylivuotavan osuuden.
- `scroll` – Selain esittää elementin reunoilla vierityspalkit riippumatta sisällön koosta.
- `auto` – Selain esittää elementin reunoilla vierityspalkit, *jos* sisältö ei mahdu elementin sisään.

Ylivuotoa voidaan hallita myös erikseen 'x'- ja 'y'-suunnassa käyttämällä erikseen ominaisuuksia
`overflow-x` ja `overflow-y`.

Käytännössä on usein järkevintä joko jättää elementin korkeus määrittämättä, jolloin se venyy
automaattisesti sisällön mukaan, tai käyttää arvoa `auto`, jolloin vierityspalkit näytetään
tarvittaessa.

```css
.eka {
    background-color: #faa;
    height: 5em;
    overflow: hidden;
}
.toka {
    background-color: #ffa;
    max-height: 5em;
    overflow: auto;
}
.kolmas {
    background-color: #afa;
    height: 5em;
    overflow: visible;
}
```
```html
<div class="eka">
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus maximus gravida pulvinar. Donec ut metus fermentum, elementum ipsum nec, aliquam
lacus. Sed eu tortor ex. Curabitur ligula tellus, scelerisque non dapibus venenatis, tempus porttitor diam. In hac habitasse platea dictumst. Praesent
eu lacinia ex. Etiam scelerisque viverra lorem, ut fringilla enim gravida et. Praesent venenatis nisi id sagittis laoreet. Nullam vitae risus efficitur, facilisis
justo vitae, mollis felis. Pellentesque ac efficitur urna. Nam ultricies diam ut efficitur tincidunt. Ut vulputate pretium justo, sit amet maximus tortor
aliquet sed. Morbi ut lectus euismod, tempor tellus vel, finibus erat. Praesent rhoncus, velit sit amet varius fringilla, lorem est commodo odio, eu ullamcorper
nisl nulla nec nunc. Vivamus facilisis, justo nec vestibulum gravida, mauris diam consectetur felis, accumsan gravida eros risus nec massa. Quisque lobortis ut est vitae porttitor. 
</div>
<div class="toka">
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus maximus gravida pulvinar. Donec ut metus fermentum, elementum ipsum nec, aliquam
lacus. Sed eu tortor ex. Curabitur ligula tellus, scelerisque non dapibus venenatis, tempus porttitor diam. In hac habitasse platea dictumst. Praesent
eu lacinia ex. Etiam scelerisque viverra lorem, ut fringilla enim gravida et. Praesent venenatis nisi id sagittis laoreet. Nullam vitae risus efficitur, facilisis
justo vitae, mollis felis. Pellentesque ac efficitur urna. Nam ultricies diam ut efficitur tincidunt. Ut vulputate pretium justo, sit amet maximus tortor
aliquet sed. Morbi ut lectus euismod, tempor tellus vel, finibus erat. Praesent rhoncus, velit sit amet varius fringilla, lorem est commodo odio, eu ullamcorper
nisl nulla nec nunc. Vivamus facilisis, justo nec vestibulum gravida, mauris diam consectetur felis, accumsan gravida eros risus nec massa. Quisque lobortis ut est vitae porttitor. 
</div>
<div class="kolmas">
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus maximus gravida pulvinar. Donec ut metus fermentum, elementum ipsum nec, aliquam
lacus. Sed eu tortor ex. Curabitur ligula tellus, scelerisque non dapibus venenatis, tempus porttitor diam. In hac habitasse platea dictumst. Praesent
eu lacinia ex. Etiam scelerisque viverra lorem, ut fringilla enim gravida et. Praesent venenatis nisi id sagittis laoreet. Nullam vitae risus efficitur, facilisis
justo vitae, mollis felis. Pellentesque ac efficitur urna. Nam ultricies diam ut efficitur tincidunt. Ut vulputate pretium justo, sit amet maximus tortor
aliquet sed. Morbi ut lectus euismod, tempor tellus vel, finibus erat. Praesent rhoncus, velit sit amet varius fringilla, lorem est commodo odio, eu ullamcorper
nisl nulla nec nunc. Vivamus facilisis, justo nec vestibulum gravida, mauris diam consectetur felis, accumsan gravida eros risus nec massa. Quisque lobortis ut est vitae porttitor. 
</div>
```
<div class="html-example">
<div style="background-color: #faa; height: 5em; overflow: hidden;">
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus maximus
gravida pulvinar. Donec ut metus fermentum, elementum ipsum nec, aliquam
lacus. Sed eu tortor ex. Curabitur ligula tellus, scelerisque non dapibus
venenatis, tempus porttitor diam. In hac habitasse platea dictumst. Praesent
eu lacinia ex. Etiam scelerisque viverra lorem, ut fringilla enim gravida et.
Praesent venenatis nisi id sagittis laoreet. Nullam vitae risus efficitur, facilisis
justo vitae, mollis felis. Pellentesque ac efficitur urna. Nam ultricies diam
ut efficitur tincidunt. Ut vulputate pretium justo, sit amet maximus tortor
aliquet sed. Morbi ut lectus euismod, tempor tellus vel, finibus erat. Praesent
rhoncus, velit sit amet varius fringilla, lorem est commodo odio, eu ullamcorper
nisl nulla nec nunc. Vivamus facilisis, justo nec vestibulum gravida, mauris diam
consectetur felis, accumsan gravida eros risus nec massa. Quisque lobortis ut est
vitae porttitor. 
</div>
<div style="background-color: #ffa; height: 5em; overflow: scroll;">
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus maximus
gravida pulvinar. Donec ut metus fermentum, elementum ipsum nec, aliquam
lacus. Sed eu tortor ex. Curabitur ligula tellus, scelerisque non dapibus
venenatis, tempus porttitor diam. In hac habitasse platea dictumst. Praesent
eu lacinia ex. Etiam scelerisque viverra lorem, ut fringilla enim gravida et.
Praesent venenatis nisi id sagittis laoreet. Nullam vitae risus efficitur, facilisis
justo vitae, mollis felis. Pellentesque ac efficitur urna. Nam ultricies diam
ut efficitur tincidunt. Ut vulputate pretium justo, sit amet maximus tortor
aliquet sed. Morbi ut lectus euismod, tempor tellus vel, finibus erat. Praesent
rhoncus, velit sit amet varius fringilla, lorem est commodo odio, eu ullamcorper
nisl nulla nec nunc. Vivamus facilisis, justo nec vestibulum gravida, mauris diam
consectetur felis, accumsan gravida eros risus nec massa. Quisque lobortis ut est
vitae porttitor. 
</div>
<div style="background-color: #afa; height: 5em; overflow: visible;">
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus maximus
gravida pulvinar. Donec ut metus fermentum, elementum ipsum nec, aliquam
lacus. Sed eu tortor ex. Curabitur ligula tellus, scelerisque non dapibus
venenatis, tempus porttitor diam. In hac habitasse platea dictumst. Praesent
eu lacinia ex. Etiam scelerisque viverra lorem, ut fringilla enim gravida et.
Praesent venenatis nisi id sagittis laoreet. Nullam vitae risus efficitur, facilisis
justo vitae, mollis felis. Pellentesque ac efficitur urna. Nam ultricies diam
ut efficitur tincidunt. Ut vulputate pretium justo, sit amet maximus tortor
aliquet sed. Morbi ut lectus euismod, tempor tellus vel, finibus erat. Praesent
rhoncus, velit sit amet varius fringilla, lorem est commodo odio, eu ullamcorper
nisl nulla nec nunc. Vivamus facilisis, justo nec vestibulum gravida, mauris diam
consectetur felis, accumsan gravida eros risus nec massa. Quisque lobortis ut est
vitae porttitor. 
</div>
</div>
