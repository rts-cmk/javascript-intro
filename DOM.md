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


### Øvlese 3: fetch
Efter introduktion til fetch med eksemplet herunder er din opgave
1. Hent en række forskellige informationer fra api'en og generer et dynamisk html-dokument 

```javascript
document.addEventListener('DOMContentLoaded', function (event) {

    fetch('https://swapi.co/api/people/')
        .then((response) => {
            return response.json();
        })
        .then((json) => {
            console.log(json);
            var content = document.getElementById('content');
            content.innerHTML = '<h1>' + json.results[0].name + '</h1>';
        })

});
```

`løsningsforlag (på opfordring :-)`
```javascript
document.addEventListener('DOMContentLoaded', function (event) {

    const content = document.querySelector('#content');
    fetch('https://swapi.co/api/people/')
        .then(function (response) {
            return response.json();
        })
        .then(function (json) {
            json.results.forEach(function (figure) {

                // opret et h3 med figure-name og tilføj til content
                let h3 = document.createElement('h3');
                h3.appendChild(document.createTextNode(`${figure.name}`))
                content.appendChild(h3);

                // opret liste med filmtitler
                let ul = document.createElement('ul');
                figure.films.forEach(function (film) {
                    fetch(film)
                        .then(function (responseFilms) {
                            return responseFilms.json();
                        }).then(function (films) {
                            li = document.createElement('li');
                            li.appendChild(document.createTextNode(`${films.title}`))
                            ul.appendChild(li);
                        })
                });

                // tilføj listen til h3 når forEach'en er afsluttet
                h3.after(ul);
            });
        })
});
```

### Øvlese 4: Generer kodeblokke
1. Opret flg. eller tilsvarende html-dokument

Kilde: https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Document_and_website_structure 
```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">

    <title>My page title</title>
    <link href="https://fonts.googleapis.com/css?family=Open+Sans+Condensed:300|Sonsie+One" rel="stylesheet" type="text/css">
    <link rel="stylesheet" href="style.css">

    <!-- the below three lines are a fix to get HTML5 semantic elements working in old versions of Internet Explorer-->
    <!--[if lt IE 9]>
      <script src="http://html5shiv.googlecode.com/svn/trunk/html5.js"></script>
    <![endif]-->
  </head>

  <body>
<!-- indhold -->
  </body>
</html>

```


Opret herefter js-fil, som generer flg. kodeblokke

Alt data oprettes i et json, for øvelsens skyld, og hentes ud vha. fetch

En Header 
```html
    <header>
        <h1>Header</h1>
    </header>
```
2. En menu
```html
    <nav>
      <ul>
        <li><a href="#">Home</a></li>
        <li><a href="#">Our team</a></li>
        <li><a href="#">Projects</a></li>
        <li><a href="#">Contact</a></li>
      </ul>
     </nav>
```
3. Et søgefelt i nav-elementet ovenfor
```html
    <form>
        <input type="search" name="q" placeholder="Search query">
        <input type="submit" value="Go!">
    </form>

```
4. Et `<main>` element med et article-element
```html
      <article>
        <h2>Article heading</h2>

        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Donec a diam lectus. Set sit amet ipsum mauris. Maecenas congue ligula as quam viverra nec consectetur ant hendrerit. Donec et mollis dolor. Praesent et diam eget libero egestas mattis sit amet vitae augue. Nam tincidunt congue enim, ut porta lorem lacinia consectetur.</p>

        <h3>subsection</h3>

        <p>Donec ut librero sed accu vehicula ultricies a non tortor. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Aenean ut gravida lorem. Ut turpis felis, pulvinar a semper sed, adipiscing id dolor.</p>

        <p>Pelientesque auctor nisi id magna consequat sagittis. Curabitur dapibus, enim sit amet elit pharetra tincidunt feugiat nist imperdiet. Ut convallis libero in urna ultrices accumsan. Donec sed odio eros.</p>

        <h3>Another subsection</h3>

        <p>Donec viverra mi quis quam pulvinar at malesuada arcu rhoncus. Cum soclis natoque penatibus et manis dis parturient montes, nascetur ridiculus mus. In rutrum accumsan ultricies. Mauris vitae nisi at sem facilisis semper ac in est.</p>

        <p>Vivamus fermentum semper porta. Nunc diam velit, adipscing ut tristique vitae sagittis vel odio. Maecenas convallis ullamcorper ultricied. Curabitur ornare, ligula semper consectetur sagittis, nisi diam iaculis velit, is fringille sem nunc vet mi.</p>
      </article>
```

5. Og et aside-element i samme `<main>` element

```html
      <aside>
        <h2>Related</h2>

        <ul>
          <li><a href="#">Oh I do like to be beside the seaside</a></li>
          <li><a href="#">Oh I do like to be beside the sea</a></li>
          <li><a href="#">Although in the North of England</a></li>
          <li><a href="#">It never stops raining</a></li>
          <li><a href="#">Oh well...</a></li>
        </ul>
      </aside>
```
6. og til sidst en footer
```html
    <footer>
      <p>©Copyright 2050 by nobody. All rights reversed.</p>
    </footer>
```
