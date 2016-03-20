+++
Categories = []
Description = ""
Tags = []
Title = "Oliopohjainen Javascript"
date = "2016-03-20T23:11:51+02:00"
weight = 150

+++

Vaikka Javascriptissä ei ole varsinaisia luokkia, sillä voi ohjelmoida
hyvin samaan tapaan käyttäen prototyyppejä. Prototyyppiobjekti toimii
mallina saman tyyppisille objekteille.

Käytetään jatkossa nimitystä *luokka*, vaikka käytännössä käytetään prototyyppejä.

Luokka ja konstruktori
============

Javascriptissä luokka määritellään konstruktorifunktion avulla. Luodaan siis
uusi funktio, jolla kaikki luokan uudet alkiot alustetaan.

```javascript
var Person = function() {};
```

Luokan uusia alkioita luodaan komennolla `new Person()`.

```javascript
var person1 = new Person();
var person2 = new Person();
```

Luokan ominaisuudet
===================

Usein luokan alkion luonnin yhteydessä sille halutaan jotain parametreja.
Luokan alkion sisälle voidaan tallentaa tietoa alkion ominaisuuksiksi.
Alkioon itseensä viitataan konstruktorin sisällä avainsanalla `this`.

```javascript
var Person = function(firstName, lastName) {
    this.firstname = firstName;
    this.lastName = lastName;
}

var person1 = new Person('Homer', 'Simpson');
var person2 = new Person('Mickey', 'Mouse');
```

Koska Javascriptin objekteilla ei ole mitään suojausta, kuten esimerkiksi
Javan *public*/*private* -jaottelu, voi objektin ominaisuuksiin päästä käsiksi
ulkoa käsin.

```javascript
console.log(person1.firstName);      // 'Homer'
console.log(person2.lastName);       // 'Mouse'
```

Luokan metodit
===============
Luokalle voi luoda metodeja lisäämälle konstruktorin prototyypille ominaisuuksiksi
funktioita. Kun luodaan uusia luokan alkioita, tämä prototyyppi periytyy niille ja
nämä funktiot ovat niiden käytettävissä metodeina. Näissäkin metodeissa
luokan alkioon itseensä voi viitata `this`-avainsanalla.

```javascript
Person.prototype.getFullName = function() {
    return this.firstName + ' ' + this.lastName;
};

Person.prototype.sayHello = function() {
    console.log('Hello, ' + this.getFullName() + '!');
};

console.log(person1.getFullName());       // 'Homer Simpson'
person2.sayHello();                       // 'Hello, Mickey Mouse!'
```

[Lisää oliopohjaisesta ohjelmoinnista Javascriptillä][OOP-javascript]

[OOP-javascript]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Introduction_to_Object-Oriented_JavaScript "Mozilla:OOP-Javascript"

