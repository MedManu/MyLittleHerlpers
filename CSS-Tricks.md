# CSS-Tricks and helper

### Position:

- control K --> shortcut liste
- Shift option f --> formatieren



### Layout-Beispiele:

```css

html{
  font-size: 14px;
}

body {
  margin: 0;
  font-size: 12px;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Roboto', 'Oxygen',
    'Ubuntu', 'Cantarell', 'Fira Sans', 'Droid Sans', 'Helvetica Neue',
    sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.episode-layout {
  display: flex;
  flex-wrap: wrap;
  min-width: 100vh;
}

.episode-box {
  padding: .5rem
}

.header {
  display: flex;
  justify-content: space-betrween;
  background: white;
  border-bottom: 1px solid black;
  padding: .5rem;
  position: sticky;
  top: 0;
}

```



# CSS

### Verweiß im Html Text:

- Ganzes file: <link rel"Stylesheet" href"Pfad"
- Styles: < irgendEinTag class="namederKlassedesStyles"

### Klassen stylen

- fangen mit einem Punkt an
- .text {}

### id's stylen (nicht unbedingt verwenden, lieber Klassen)

- Raute und name der Id //#Name{}

### Rahmen:

- border: 2px solid green; 
  - brauch immer eine From: solid
  - Und kann auch direkt eine fabe zugewiesen bekommen.

### Einzelne Attribute im Element ansprechen

- zb alle p's mit dem attribute class darin

- p[class] {}

-  nav ul{}  ungeordnete Liste in einer Navigation

  

###Boxinhalt eines Elements:

![Bildschirmfoto 2020-06-13 um 14.52.34](/Users/manu/Library/Application Support/typora-user-images/Bildschirmfoto 2020-06-13 um 14.52.34.png)

- Content = Inhalte
- padding = Innenabstand 
  - pedding: 4px; (eine Zahlenangabe nimmt Eintrag für alle Ränder)
  - pedding: 4px 8px 8 px 4 px; (im Uhrzeigersinn)
  - pedding: 4px 8px; (1. Wert is oben u unten 2. Wert is rechts u links)
- border = Ausenrahmen
  - border: 4px;
- Margin = ausenabstand
  - margin: 4px 8px 8 px 4 px (gleichen möglichkieten wie bei pedding)

### Externe Schriften einbeziehen:

- link muss im Header in das html eingefügt werden
  - <link href="https://fonts.googleapis.com/css2?family=**Metal+Mania**&display=swap" rel="stylesheet">
- Dazu gehöriger verweis ins css 
  - font-family: 'Metal Mania', cursive;

### Mehrere Elemente ansprechen

- He,h3,input (elemente mit beistricjh trennen)

### EInzelne Wörter Bearbeiten

- <!--<span class="">WörterWörterWörter</span>-->

## Bsp's:

### Navigationslesite beim Scrollen mitnehmen:

position: fixed;

  width: 100%;

### Navigationsleiste erstellen:

- nav muss im HTML vergeben sein

.navbar{

​    background-color: #8888;

​    height: 45px;

}

 .navList{

float: right;

 }

 .navList li{

​     display: inline-block;

 }

 .navList li a{

​    color: greenyellow;

​    margin: 0 10px;

​    text-decoration: none;

} 

.navList li a:hover{

​    color: red;

​    text-decoration: underline;

} 

### Butto designen:

- .btn{

  ​    color: black;

  ​    font-weight: 700;

  ​    border: 2px solid greenyellow;

  }

###Hintergrungbild:

.welcome{

​    background-image: url(./img/background.jpg);

​    background-position: center;

​    background-size: cover;

​    padding: 150px;

​    font-size: 24px;

}

### Bilder nebeneinander:

- HTML:

  <!--<div class="row">  

   <!-- <div class="column">    
    <img src="img_snow.jpg" alt="Snow" style="width:100%">  
    </div>  

    <!--<div class="column">   
      <img src="img_forest.jpg" alt="Forest" style="width:100%">  
    </div>   

    <!--<div class="column">    
      <img src="img_mountains.jpg" alt="Mountains" style="width:100%">   
    </div> 

  </div> 

  - Css:

    /* Three image containers (use 25% for four, and 50% for two, etc) */
    .column {
     float: left;
     width: 33.33%;
     padding: 5px;
    }

    /* Clear floats after image containers */
    .row::after {
     content: "";
     clear: both;
     display: table;
    }

## Buttons anzeigen

## Diverses

- alles auswählen: *{ }
- **float: right**; (bringt das ELement auf die rechte Seite des Bildschirms)
- **display: inline-Block** (Element in einer reihe darstellen) 
  - Alternativ auch **float: right;**
- .navList li a :hover{} 
  - hover = was soll passieren, wenn ma nmit dermaus drüber fährt
- **text-decoration: none;** Unterstrich bei links verschwunden
- **text-align: center;** macht den text mittig in der Seite
- **letter-spacing: 5px** ; Abstand zwischen den einzelnen Buchstaben
- **.basic-section:nth-child(odd){}** jede ungerade section soll das bekommen
- **border-radius: 25px;** Element rund machen
- **border: 1px solid red** gibt den Rahmen an
- <b>alles was zwischen Bsteht wird Fett geschrieben <!--</b>-->
- <i> für Kursive



