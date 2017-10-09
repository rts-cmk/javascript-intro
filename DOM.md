# Javascript DOM

### Mål
* DOM Navigation - kan navigere i DOM vha. javascript
* DOM Manipulation - kan oprette og manipulere objekter i DOM vha. javascript

Primær referencer: javascript.info
### Nodes i DOM
![DOM](http://javascript.info/article/dom-navigation/dom-links@2x.png)

### Øvelse 1: DOM Navigation
http://javascript.info/dom-navigation 
1. Opret en html-side med 3 div-elementer og tilhørende js-fil med en eventlistener til `DOMContentLoaded`
```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
</head>

<body>
    <div>div 1</div>
    <div>div 2</div>
    <div>div 3</div>
</body>
<script src="dom.js"></script>

</html>
```
2. Udskriv følgende med `console.log`
    - document
    - document.documentElement
    - document.body;
> break

3. Find og udskriv det første div-element med "child"
4. og herefter de øvrige div-elementer med "sibling"
> break

5. Hent alle div-elementer og udskriv de enkelte nodeValues vha. en for-løkke
> break


### Øvelse 2: DOM Manipulation
[http://javascript.info/modifying-document](http://javascript.info/modifying-document)
1. Slet alle div-elementer vha. javascript
> break

2. Opret et div-element med createElement
3. Opret en text-node med createTextNode
4. Tilføj text-node til div-element, for til sidst body - alle tre med appenChild
> break

5. Tilføj en class og et id til div-elementet
> break

6. Opret et h2-element med teksten "DOM Javascript" og placer det før div-elementet
> break

7. Operet et ol-element samt to tilhørende li-elementer
> break

8. Opret et array med tre elementer
9. Opret en forEach-løkke som tilføjer et list-element for hvert argument i array'et
> break

10. Opret et div-element med tekst, lav en klon og tilføj en ny tekst til klonen. Vis begge div-elementer på siden.
