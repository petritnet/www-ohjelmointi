+++
Categories = []
Description = ""
Tags = []
Title = "Javascriptin suoritus"
date = "2016-03-07T23:54:29+02:00"
weight = 5

+++

Koska Javascript on tulkittu kieli, se tarvitsee aina jonkin tulkin,
eli ohjelman, joka suorittaa Javascript-kielisiä komentoja.
Useimmiten tulkki on www-selaimeen sisäänrakennettu koneisto, mutta
nykyään on myös komentoriviltä toimivia Javascript-tulkkeja, kuten
[Node.js]. Node.js:stä on tullut suosittu alusta myös palvelinohjelmistojen
rakentamiseen.

WWW-sivulla
===========
HTML-sivulle Javascript-kielisen ohjelman voi lisätä `<script>`-tagilla.
Kun sivua ladataan, `<script>`-tagilla merkitty ohjelma suoritetaan
siinä kohdassa kuin se on sivulle merkitty. Tagi voi olla joko sivun `<head>`-
tai `<body>`-osiossa. Usein `<script>`-tagi on sijoitettu `<body>`:n loppuun, jolloin
se suoritetaan muun sivun lataamisen jälkeen, taikka sen suoritus määrätään
muuten käynnistettäväksi vasta sivun latauduttua.

`<script>`-tagia voidaan käyttää kahdella tavalla. Ensimmäisessä Javascript-ohjelma on
erillisessä tiedostossa, johon viitataan tagin `src`-attribuutilla:

```html
<script type="text/javascript" src="munoma.js"></script>
```

Toinen vaihtoehto on kirjoittaa Javascript-ohjelma suoraan HTML-tiedostoon
`<script>`-tagin sisään.

```html
<script type="text/javascript">
    var luku = 42;
    alert('Moi ' + 42 + '!');
</script>
```

Selaimen konsolissa
===================
Useimmissa selaimissa on mahdollista ottaa esiin jonkinlainen Javascript-konsoli, eli komentorivi,
johon voi kirjoittaa Javascript-komentoja suoraan. Tämä löytyy usein joko valikosta tai
hiiren oikean napin takaa ja on usein nimetty tyyliin "Inspect Element" tai "Kehittäjän työkalut".

Selaimen osoiterivillä
=======================
Javascriptiä voi suorittaa vaikka suoraan selaimen osoiterivillä. Kokeile kirjoittaa osoiteriville:

```javascript
javascript:for (var i = 0; i < 10; i++){document.write(i + ': hihhei!<br>');}; alert('Moi!');
```

Selaimen kirjanmerkistä
=======================
Vastaavasti osoitteen voi tietenkin tallettaa myös kirjanmerkiksi, eli **bookmarkletiksi**.
<a href="javascript:var%20t=((window.getSelection&&window.getSelection())||(document.getSelection&&document.getSelection())||(document.selection%20&&document.selection.createRange&&document.selection.createRange().text));var%20e=(document.charset||document.characterSet);if(t!=''){var translw=open('http://translate.google.com/translate_t?text='+t+'&hl=en&langpair=auto|en&tbb=1&ie='+e);}else{var translw=open('http://translate.google.com/translate?u='+escape(location.href)+'&hl=en&langpair=auto|en&tbb=1&ie='+e);}; translw.focus();">Google-käännös</a>

Firefoxin Scratchpad
====================
Firefox sisältää Scratchpad-toiminnallisuuden, eli kevyen syntaksikorostetun Javascript-editorin,
johon kirjoitetun koodin voi suorittaa selainikkunassa.

Scratchpad avataan näppäinyhdistelmällä `shift-F4`, valittu koodi suoritetaan näppäilemällä `ctrl-r`.



Komentorivillä
==============
Javascriptiä voi tietenkin käyttää myös komentoriviltä, esimerkiksi [Node.js]:llä.


[Node.js]: https://nodejs.org/en/ "Node.js"