# JavaScript: Intro
Introduktionsopgaver til valgfaget JavaScript

## Events
JavaScript er et event-baseret sprog. Det vil sige, at funktioner kan blive kørt i forbindelse med en `event`.

En `event` kan være mange ting, fx
- DOMContentLoaded
- click
- scroll
- submit
- mouseenter
- mouseout

Du finder en komplet liste over JavaScript events her https://developer.mozilla.org/en-US/docs/Web/Events.

Et JavaScript kan lytte efter events med det, vi kalder en `event listener`. Det ser således ud:

```JavaScript
document.addEventlistener('EVENT_NAVN', function (event) {
	// kode, der skal udføres når eventet træder i kraft
});
```

Eller:
```JavaScript
const myFunction = function (event) {
	// udfør en handling
};

document.addEventListener('EVENT_NAVN', myFunction());
```

> ### Opgave 1
> Brug filerne i mappen `opg1` til at lave en eventListener, der lytter efter `click`-events.  
> Brug `console.log()` til at udskrive, hvad der bliver klikket på.

Ved at skrive `event` objektet ud i konsollen, kan du finde en lang række oplysninger om hvad der blev klikket på. Herunder er cursorens placering på skærmen med X,Y koordinater, timestamps i forskellige formater og måske vigtigst af alt; hvilket element, der blev klikket på.

Du kan se selve elementet som blev klikket på ved at tilføje attributten `target` til `event`. Således: `event.target`.

> ### Opgave 1.1
> Brug konsollen til at tjekke hvilke elementer, der bliver klikket på, ligesom i opgave 1.

Ved at tilføje flere attributter til event-objektet, kan du for eksempel se, hvilket ID et element har, hvis det altså har et: `event.target.id`.

> ### Opgave 1.2
> Lav en betinget sætning, som kun skriver noget i konsollen, hvis der bliver klikket på et element med ID-et "yo".

## querySelector() / querySelectorAll()

`querySelector()`og `querySelectorAll()` fungerer meget på samme måde som `getElementById()`. Den store forskel er, at `querySelector()` kan bruges til at vælge elementer ud fra de samme kriterier, som du bruger, når du skal ramme et element med CSS.

```JavaScript
document.querySelector('.wrapper');
document.querySelector('#formSubmitButton');
document.querySelector('section article h1');
document.querySelector('input[type=checkbox]');
```

> ### Opgave 1.3
> I opgaven ovenfor lavede du en eventListener på elementet `document`. Nu skal du bruge `querySelector()` til at lave en click-eventListener på et enkelt element som du selv vælger.

## URLSearchParams

En stor del af dit arbejde som web-udvikler handler om at vide hvilke sider, der skal hentes. En af de mest brugte metoder til dette er at kigge på hvad der står i URL'en.

Ofte skal vi have ID'et på et produkt eller en bruger, eller måske en side, så vi kan vise det korrekte indhold.

URL'en i JavaScript har hjemme i objektet `window.location`.

> ### Opgave 2
> Udskriv objektet `window.location` i konsollen ved hjælp af filerne i opg2-mappen.  
> Hvad sker der med objektet, når du klikker på de forskellige links i toppen af siden?

Den del af URL'en som indeholder `?klik=1` hedder en "query string". En query string kan indeholder flere parametre, adskilt af `&`: `?klik=1&brugerID=42`.

> ### Opgave 2.1
> Hvilken del af `window.location` objektet indeholder en URL's query string?

Nå du skal hente en værdi fra et enkelt parameter i en URL query string, kan du bruge klassen `URLSearchParams`.

```JavaScript
// http://localhost/index.html?klik=1&brugerID=42
const = searchParams = new URLSearchParams(window.location.search);
console.log(searchParams.get('klik')); // output: 1
console.log(searchParams.get('brugerID')); // output: 42
console.log(searchParams.get('ostemad')); // output: null (fordi parametret ikke findes)
```

> ### Opgave 2.2
> Lav en betinget sætning i opg2-mappen, som kun udskriver noget, hvis der er en URL query string.  
> I konsollen skal der stå: Du har klikket på _n_.