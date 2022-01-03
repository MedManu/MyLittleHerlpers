# CSS-Tricks and helper

## Maßeinheiten

| px Pixel  | Absolut / Relativ Ein Pixel beschreibt die kleinste Ausgabeeinheit eines Monitors und ist relativ von Ausgabegerät zu Ausgabegerät. Auf den einzelnen Monitor bezogen ist die Angabe von Pixeln ein absolutes Maß. Pixel sind ein geeignetes Maß, um Schriftgrößen und die Abmessungen von Elementen für den Monitor festzulegen. Pixel sind unabhängig von der CSS-Kaskade. |
| --------- | ------------------------------------------------------------ |
| em EMS    | Relativ bezieht sich auf die Schriftgröße eines Elements. Für ein flexibles Layout, dass sich anpasst, wenn der Benutzer die Schriftgröße im Browserfenster ändert, ist em als Maßeinheit für Schriften und Layout-Boxen besser geeignet als Pixel. em reagiert auf die CSS-Kaskade. |
| ex EX     | Relativ wie EMS, aber ex steht für die Größe des Kleinbuchstabens in einem Element – i.d.R. also etwa die Hälfte von em. |
| % Prozent | Relativ Prozentangaben eignen sich besonders gut für die Ausgabe auf dem Monitor, wenn Layoutelemente an verschiedene Monitorgrößen angepaßt werden sollen. |

## Rangliste:

- Tag < class < id

- Tag: 

```html
<p>ich bin ein Paragraph </p>
```

- class

```
<p class/classname ={ptagstyle}>Ich bin auch ein Paragraph</p>
```

- ID

  ```html
  <p id ="pID">Ich bin ebenfalls ein Paragraph</p>
  ```

  

```css
p {
color: black;
}

.pTagStyle {
  color: green;
}

#pID {
  colir: red;
}

```

 ```css
p.p1{ 
color: grey;
} 

 ```

- Alle Ps doe die Klasse p1 haben

  - achtung Stellung!! Wenn p{...} davor, dann wir das was in p{} steht angewandt

  - Besser h1.p{ } verwenden

- Es können auch mehrer Klassen auf ein Element zuweisen

  ```html
  <p class " p1 para1" = ></p>
  ```

- ```css
  .p1{
  color: red
  }
  .para1{
  background: black;
  }
  ```

  - Ansprechen mehrer Elemente (Gruppierung)

  - ````css
    p,h1{
    color: red;
    }
    ````

  - 

  

### Farben:

- rgb( rot Grün Blau) zwischne 0 u 255

```css
p{color: rgb( 100 54 243); }
```

- name

- ```css
  p{color: red; }
  ```

- ""#"rotrotgrüngrünblaublau zwischen 0 bis  9 - a bis F

- ```css
  p{color: #04AF5B; }
  ```

### Background

```css
body{
background-image url("");
background-repeat: no-repeat;
background-position: cent/ bottom-left/ top-right;
background-attachment: fixed/scroll;
}
```



### Box-Modell:

```html
<div id="div1"></div>
```



```css
#div1{
background-color: red
}
```



## Tipps:

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

## Flexbox

```css
const centralFlexBox: CSSProperties = {
  height: "100%",
  width: "100%",
  display: "flex",
  flexDirection: "column",
  alignItems: "center",
};
```

### Breathing

```
interface TodayCircleProps {
  onClick: () => void;
  topLine: string;
  mainLine: string;
  fontColor: string;
  outerCircle: string;
  innerCircle: string;
  buttonText: string;
  buttonColor: string;
  dayNumber?: number;
}

const circleStyle: CSSProperties = {
  display: "flex",
  flexDirection: "column",
  justifyContent: "center",
  alignItems: "center",
  width: "70%",
  height: "70%",
  backgroundImage: "url(" + props.outerCircle + ")",
  backgroundRepeat: "no-repeat",
  backgroundPosition: "center",
  backgroundSize: "100% 100%",
  borderRadius: "50%",
  textAlign: "center",
  position: "relative",
  zIndex: 0,
};
const innerCircleStyle1: CSSProperties = {
  display: "flex",
  flexDirection: "column",
  justifyContent: "center",
  alignItems: "center",
  width: "80%",
  height: "80%",
  borderRadius: "50%",
  textAlign: "center",
  backgroundImage: "url(" + props.innerCircle + ")",
  backgroundRepeat: "no-repeat",
  backgroundPosition: "center",
  backgroundSize: "100% 100%",
  position: "absolute",
  zIndex: 1,
  color: "white",
};

.breathingCircle {
  animation: breathing 7s ease-out infinite normal
}
@keyframes breathing {
  0% {
    transform: scale(0.9);
  }

  25% {
    transform: scale(1);
  }

  60% {
    transform: scale(0.9);
  }

  100% {
    transform: scale(0.9);
  }
}

return (
    <div style={{ ...circleStyle }}>
      <div
        style={{
          ...innerCircleStyle1,
        }}
      >
        <div style={{ fontSize: "xxx-large" }}>{props.dayNumber}</div>
        <div style={{ fontSize: "x-large" }}>{props.mainLine}</div>
      </div>
      <div className={"breathingCircle"} style={circleStyle} />
      <div onClick={props.onClick} style={roundButtonStyle}>
        {props.buttonText}
      </div>
    </div>
  );
};
```



### gradient border

```css
#help{
    background: white;
    color: #333333;
    padding: 2rem;
}

#help-border-wrap {
    margin: auto 0.2em auto 0.2em;
    padding: 0.3rem;
    position: relative;
    background: linear-gradient(90deg,#be4b91 15%, #f0879b 50%, #fabe96 80%);
    position: relative;
}
```

## Text neben Bild

<img></img> text

```css
 vertical-align: middle;
```

oder

<img></img><p></p>

```
float: left;
```



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



