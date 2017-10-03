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
document.querySelector('section article h1');
document.querySelector('input[type=checkbox]');
```

> ### Opgave 1.3
> I opgaven ovenfor lavede du en eventListener på elementet `document`. Nu skal du bruge `querySelector()` til at lave en click-eventListener på et enkelt element.