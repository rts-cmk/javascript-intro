# JavaScript: Intro
Introduktionsopgaver til valgfaget JavaScript

## Events
JavaScript er et event-baseret sprog. Det vil sige, at funktioner kan blive kørt i forbindelse med en `event`.

En `event` kan være mange ting, fx
- DOMContentLoaded
- Click
- Scroll

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

## Opgave 1
Brug filerne i mappen `opg1` til at lave en eventListener, der lytter efter `click`-events.

Brug `console.log()` til at udskrive, hvad der bliver klikket på.