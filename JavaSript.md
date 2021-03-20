# JavaScript

F12 im Browser und Console wählen, können ausgaben die im js file gemacht werden angeschaut werden

- kann in extra js file geschrieben werden oder in den html Text

   <script src="../javaScript/JS(MeineErsteKleienWebsite).js" type="text/javascript"> </script>

- Im HTML file einen script tag (<script>)

 <script type="text/javascript">
   alrt("Hello World");
</script>

- **Ausgäbe**:  alert("Hello World");

### Variablen:

- var a = "Hallo Welt";
- const b = "Hallo Welt";
- console.log(a);
- **ohne var u const ist es Globale Variable, Function mit varible muss aber zuerst aufgerufen werden.**
- Strenger Modus:
  -  undeklarierte Variablen oder Anweisungen ohne abschließendes Semikolon verboten
  - "use strict"

## Vergleichsoperatoren

- Boolean(a==b) -> Prüft auch gleichen Inhalt
- Boolean(a===B) -> Prüft auch noch auf den gleichen Typen
- var x = (42 == 42) ? 42:2121;
  - Wenn bedingung wahr wollen wir in die Variable 42 schreiben, wenn nicht dann 2121



### Funktionen:

- ersteleln einer Funktion

  ```javascript
  function test() {
      var b = "Hallo Werlt - b";
      console.log(a);
      console.log(b);
  }
  
  ```

  - aufrufen der Funktion: 

    ```javascript
    test();
    
    ```
  - mit Parametern  

    ```js
    function addieren(a, b) {
    console.log(a + b);
    }
    
    addieren(2, 5);
    ```

  - Return = verwenden wenn wir mit dem Ergebnis unterschiedliche sachen machen wollen u des halb nur rein z-b die Zahl haben wollen

  ```js
  unction meinAlert(a, b) {
      console.log(a * b);
  }
  
  meinAlert(3,4757856);
  
  function addieren(a, b) {
      return a+b;
  }
  
      meinAlert(7,addieren(2,3))
  ```

## rekursive Funktionen:

- um z.b die Fakultät zu berechnen

```js
function fakul(n) {
if (n <= 2) {
return n
}
return n*fakul(n-1);
}
```



### Arrow-Functions:

hat eine kürzere Syntax als ein Funktionsausdruck und hat kein eigenes `this`, [arguments](https://developer.mozilla.org/de/docs/Web/JavaScript/Reference/Functions/arguments), [super](https://developer.mozilla.org/de/docs/Web/JavaScript/Reference/Operators/super), oder [new.target](https://developer.mozilla.org/de/docs/Web/JavaScript/Reference/Operators/new.target). Solche Funktionsausdrücke sind am besten für Funktionen, die nicht als Methode genutzt werden, geeignet und können nicht als Konstruktoren verwendet werden.

### Asynchrones Programmieren:

FUnktions wird nicht sofotz und auch nocht in der scheinbar richtigen Reihnefolge ausgeführt.



## Arrays

- Mit . **push** fügen wir einen neuen Eintrag an nächste freie Stelle ins Array hinzugefügt

- geht auch über direkte zuteilung

  - Array[4] = " "

- Bei JS kann auch eine Stelle vergeben werden, wo die Pltze davor noch nicht belegt sind unsers[10] = ""

- Mit **.pop** wird der letzte Eintrag aus dem Array entefernt 

- ```js
  console.log(array.join("Hallo"))
  ```

  Hier wird nach jedem EIntrag im Array ein Hallo angehängt

- **Shift** und **unshift** entfernen/fügen an die erste Stelle des array etwas

- **.sort** sorteirt aufsteigend unser Array

- **.reverse** sortiert unser Array absteigend



## For-Schleife:

```js
for(i = 0; i < array; i++) {

Console.log(array[i] ) }
```

- Array.lenght -1 gint immmer die letzte stelle des Arrays zurück



## For-in-Schleife

 ```
for(i in array) {
console.log(array[i])
}
 ```

- kürzere Schreibweise der for-Schleife geht aber nur so oft, wie es auch einträge gibt

## While/do-While-Schleife

```js
do{tuWas}
while(bedingung)
```

- Do-while führt mindestens einmal die Bedingung aus

```js
while(Bedingung) {
tuwas
}
```

- Tu nur etwas wenn die Bedingung erfüllt ist



### Rduce-Function

- Itariert über jeds Element eines arrays
  - Para2: das über das iterriret werden soll
  - Para1: Das was wir zurück bekommen als nächste itration
- Die Methode **reduce** ruft die angegebene Rückruffunktion (Callback) für alle Elemente in einem Array auf, mit dem Ziel, den Array-Inhalt auf einen einzigen Wert zu reduzieren. Einsatzzweck kann zum Beispiel eine Summen- oder Durchschnittsbildung sein.

```
export const sumRecpies = function (recepies) {
  recepies.reduce((para1, para2) => {
      
  }, []);
  return [];
};
```



## MAthematische Funktionen:

- Math.ramdom() liefert zahlen zwischen 0(selten) und 1(nie)
  - Math.ramdo,()*100 liefert zahlen zwischen 0 und 99
  - Math.random()*100+100 liefert zahlen zwischen 100 und 200
- Math.round(Math.random()*100+100) liefert Ganze Zahlen zwiscgen 100 und 200

## DOM - Document Object Model

- Brauch ich um auf elemente zugreifen zukönnen u sie zu bearbeiten
  - Document.getElementById("ID").innerHTML = "NeuerName" -> Ändert den Namen wenn darauf geklickt wird
  - innerHTML gibt mir immer den Inhalt aus: gerade Zhalen sind der Text zwischen zwei Elementen, ungereade der text innerhalb eines Elements
- Document.getElementsByTagName("NamedesTags")
  - var tag = Document.getElementsByTagName("NamedesTags"):
  - Zugriff mit tag[1]
- Document.getElementsByClassName("NamederKlasse")
- Document.getElementsById("Name").id = "neueId"

## this:

- this im Funltionsaufruf sagt, das genau das element gemeint ist, in dem das Event stattfinden

  - ```html
    <h1>onclick="nameDerFubktion(this)"</h1>
    ```

    


## Cookies:

- Gedacht um Informationen vom user zu speichern

## DiesDas:

- .search() -> lässt im text nach etwas suchen

- .toLowerCase() -> convertieren in groß oder Kleinbuchstaben

- Break = Springt immer direkt ans ende der Schleife

  ```js
  for(i in array) {
  if(i == 2) {
  break;
  }
  }
  ```

  

- Continue = beendet nur der aktuellen Schleifendurchlauf u macht dannach weitert 
- Elementee bewegen

```js
function moveDiv() {
  var div = document.getElementById("div1");
  var margin = 0;
  var id = setInterval(function () {
    if (margin >= 500) {
      clearInterval(id);
    }
    else{
        div.style.marginLeft = margin + "px";
         div.style.marginTop = margin + "px";
        margin++;
    }
  }, 5);
}
```

- Event innerhalb einer funktion hinzufügen
  
  - Document.getElementById("id").addEveentListener("mouseover", funktion die ausfegührt werden soll)
  
- Element dynamisch per klick hinzufügen

  - ```javascript
    //paragraph erzeugen
       var newPara = document.createElement("p");
       //paragraph befüllen
       newPara.innerHTML = "dynamisch erzeugter Praragraph";
       //paragrapg an body heften
       var div = document.getElementById("div1");
       div.appendChild(newPara)
    
    
    ```

- Auf neue Seite schicken

  - ```javascript
    window.location.href = "https.//www.google.com"
    ```

    

  - 