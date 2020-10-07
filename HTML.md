



###Ordnen: 

- On Windows Shift + Alt + F

- On Linux Ctrl + Shift + I
- On Mac Shift + Option + F
- Mac: cmd+option+u = html ansicht im browser

<startTag>

</endTag>

<!--KomentatTag-->

### Head:

- //<!DOCTYPE html> gibt an, dass wir die aktuelle html version benutzen
- //<title> hier können wir den Tiel Unsere Seite angeben, er ist nicht sichtbar
- //<meta charset="utf-8"> angabe des verwendeten Zeichensatzes 

###Body:

- //<header>(nicht zu verwechseln mit head)
- //<Main> (Der Hauptteil)
- //<Footer> (der untere Teil)

### Listen:

- Geordnete Liste: <ol>
  - Einträge dazu: <li>
- ungeordnete Liste: <ul>
  - Einträge dazu: <li>

Es kann auch Liste in Listen geben:

### Tabellen

- // <table>

ist ebenfalls aufgeteilt in Kopf //<thead> und Körper //<tbody>

- // <tr> = Tabelrow
- // <th> = Tabelspalte (im header zu schreiben ist Fett-geschrieben )
- // <tb> = Tabeldata (im body zum schreiben)

### Container

Machen es einfachen klassen mit css zu versehen. Nimmmt die volle Breite der Seite ein

- //<div>
- //<span> = kann dann auch noch einmal einzeln bearbeitet werden

### Links

- <!-- <a href="https://linkzueinerseite.de" targer="blank">Link zu Google</a> -->
- Target="blank" in nach href sagt das der Link in einem neun Tag geöffnet werden soll

### Links zu abschnitten der Webside einfügen

-  <li><!--<a href="">Hallo</a>--></li> 
- Im Element einfach <!-- >a> --> vergeben
-  // <section id="Hallo"> = zum Unterteilen in gewissen section auf der Seite
- Im Elelment, das auf die Section verweisne soll steht dann im href="#hallo"

### Bilder 

- // <img src="pfadzumBild" alt="Wird angezeigt, falls Bild nicht existiert" height="12px"

### Formulare

- // <form action="/login/" methode=""> 
  - action: kann der Pfad angegeben werden, wohin die Form weißt
  - Methode: kann get oder post zum schicken oder bekommen beinhalten

### Input

- <input type="text" name="name des Feldes"
  - input wird verwenden für eingäbe (Eingabeferlder) 
  - placeholder=""
  - type="submit" zum absebden
  - Type = "email "
  - Required sagt das es eingegegn werden muss

### Verknüpfung mit CSS:

<link rel="Stylesheet" href="dortwosccliegt"

         ### Diverses

- // <br setzt einen break in der Zeile

- // <hr> setzt einen Unterstrich zwischne 2 Zeilen

  

  ## Bsp:

  ### Navigationsmenü:

    .navbar {

  ​       background-color: #ffab00;

  ​       margin: 10%;

  ​    }

  ​    .navbar ul{

  ​       list-style-type: none;

  ​    }

  ​    .navbar li{

  ​        display: inline;

  ​        padding: 1%;

  ​    }

  ​    .navbar a{

  ​        text-decoration: none;

  ​        color: black;

  ​       

  ​    }

  