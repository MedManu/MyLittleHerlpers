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
- ohne var u const ist es Globale Variable, Function mit varible muss aber zuerst aufgerufen werden.
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
  ```
  
  ```

### Arrow-Functions:

hat eine kürzere Syntax als ein Funktionsausdruck und hat kein eigenes `this`, [arguments](https://developer.mozilla.org/de/docs/Web/JavaScript/Reference/Functions/arguments), [super](https://developer.mozilla.org/de/docs/Web/JavaScript/Reference/Operators/super), oder [new.target](https://developer.mozilla.org/de/docs/Web/JavaScript/Reference/Operators/new.target). Solche Funktionsausdrücke sind am besten für Funktionen, die nicht als Methode genutzt werden, geeignet und können nicht als Konstruktoren verwendet werden.

### Asynchrones Programmieren:

FUnktions wird nicht sofotz und auch nocht in der scheinbar richtigen Reihnefolge ausgeführt.

## DiesDas:

- .search() -> lässt im text nach etwas suchen
- .toLowerCase() -> convertieren in groß oder Kleinbuchstaben