React

![Bildschirmfoto 2020-10-20 um 07.48.16](Typora_pics/Bildschirmfoto 2020-10-20 um 07.48.16.png)



## Bedeutung

### Declerative:

Geben Überschrift daten mit, welche sie darstellen soll

(Imperativ): Wenn in HTML Überschrift verändern wollen, müssen wir eact diese Überschrift suchen

### Component-Based:

Viele kleine Komponenten ergeben eine große

### VIrtual-DOM:

Dokument Apstract Moden - Abstraktion des HTML in JavaScript

![Bildschirmfoto 2020-10-21 um 11.27.21](/Users/manu/Documents/MyLittleHerlpers/Typora_pics/Bildschirmfoto 2020-10-21 um 11.27.21.png)

Ermöglich es über den Browser HTML mit JavaSript zu manipulieren 

Virtual Dom ist kopie des realen DOM in React

Änderungen, die wir durchführen, werden zuerst im Virtual Dom und dann im normalen DOM ausgeführt

 ![Bildschirmfoto 2020-10-21 um 18.00.06](/Users/manu/Documents/MyLittleHerlpers/Typora_pics/Bildschirmfoto 2020-10-21 um 18.00.06.png)

![Bildschirmfoto 2020-10-21 um 18.05.45](/Users/manu/Documents/MyLittleHerlpers/Typora_pics/Bildschirmfoto 2020-10-21 um 18.05.45.png)

![Bildschirmfoto 2020-10-21 um 18.06.52](/Users/manu/Documents/MyLittleHerlpers/Typora_pics/Bildschirmfoto 2020-10-21 um 18.06.52.png)

![Bildschirmfoto 2020-10-21 um 18.07.58](/Users/manu/Documents/MyLittleHerlpers/Typora_pics/Bildschirmfoto 2020-10-21 um 18.07.58.png)

- --reload erlaubt dem Server die Dateien in unseem Projekt zu beobachten uns bei einer Änderung, diese sofort im Browser darzustellen
- https://www.npmjs.com/package/servor

![Bildschirmfoto 2020-10-23 um 07.21.27](/Users/manu/Documents/MyLittleHerlpers/Typora_pics/Bildschirmfoto 2020-10-23 um 07.21.27.png)



## Erstellen eines Projekts im Ordner 

### 1) npm init:

erstellt Package.json Datei

### 2) index.html file anlegen

**index.html**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Einführung in React</title>
</head>
<body>
    <h1>Hello World</h1>
    <div id=react-app></div>
<script crossorigin src="https://unpkg.com/react@16/umd/react.development.js"></script>
<script crossorigin src="https://unpkg.com/react-dom@16/umd/react-dom.development.js"></script>
<script>src="./src/app.js"</script>
</body>
</html> 
```



- wenn React nicht über npm eingebettet wird, müssen CDN-URLs in die index datei geschrieben werden. Kann im development(mehr testtools dabei u deswegen größere Datei) oder production(kleiner u besser für produktiven Einsatz) modus eingeführt werden

  - https://reactjs.org/docs/cdn-links.html

  - ```html
    src="https://unpkg.com/react@16/umd/react.development.js"></script>
    <script crossorigin src="https://unpkg.com/react-dom@16/umd/react-dom.development.js"></script>
    ```

- Ein Skript text der auf unsere app.js verweht, wo der unser code ausgeführ wird mus serstellt werden

  - erstellen eine Ordners "src" und der Datei "app.js" im Projektapp.js

  - ```html
    <script>src="./src/app.js"</script>
    ```

- wohin wir unsere sachen gerendert haben wollen muss auch angegeben werden

  - ```html
    <div id=react-app></div>
    ```

### 3) Erstellen React-Elemnts in app.js:

## React Element:

- Grundlegendest Objekt in Virtual DOM

```react
React.creatElement("p",{id: "myId"}, "My Content")
```

1. Parameter: Tag
2. Parameter: Attribut
3. Parameter: Inhalt

```react

const myElement = React.createElement(
    "p",
    {},
    "Mein erstes React-Element"
)
```

- Zur Darstellung der Variable im Browser brauchen wir die render() Funktion, die uns ReactDOM liefert. 
- In der render() Funktion geben wir einmal unser Element an und dann wohin wir das gerendert haben wollen.

### 3) Babel konfigurieren:

![Bildschirmfoto 2020-10-23 um 09.28.35](/Users/manu/Documents/MyLittleHerlpers/Typora_pics/Bildschirmfoto 2020-10-23 um 09.28.35.png)

![Bildschirmfoto 2020-10-23 um 09.39.56](/Users/manu/Documents/MyLittleHerlpers/Typora_pics/Bildschirmfoto 2020-10-23 um 09.39.56.png)

**Babel Wörterbuch erstellen:**

- erstellen uns eine file namens: .babelrc.babelrc

- Babel übersetzt .jsx in js

  - Jsx = verschmelzung von HTML und JavaScript

- in die file schreiebn wir alle wärtetbücher, die wir übersetzten wollen

- ```html
  {
      "presetes": ["@babel/preset-react"]
  }
  ```

**Aus app.js wird app.jsx**

- Übersetzten mit babel im terminal: 

- ```bash
  npx babel src --out-dir lib
  ```

- Src: Verzeichnis das übersetzt werden soll

- --out-dir lib: wohin übersetzt werden  - Verzeichnis namens lib



## Skripte

in der package.json file unter "scripts" können alles Skripe dir wir brauchen eingfügt und dann mit npm run ausgeführt werden

```html
 "scripts": {
    "compile": "babel/ src --out-dir lib", 
  },
```



![Bildschirmfoto 2020-10-23 um 10.20.45](/Users/manu/Documents/MyLittleHerlpers/Typora_pics/Bildschirmfoto 2020-10-23 um 10.20.45.png)

## React-Components:

Es gint hierbei Funktionale und Klassenbasierte-Components!

### Funktionale definition:

- Für funktional Programmierung 
  - Komponente wird als JavaScript Fuktion implementiert
  - Bekommt Properties mitgeliefert
  - Gibt JSX-Element/React-Element zurück

```react
function MyComponente(props) {
return(
<p>{this.props.text}</p>
);
}
```

### Klassenbasierte definiton:

- Für Objektorientiert Programmierung 
  - JavaScript Klasse wird erstellt und durch React.Component erweitert
  - React.Component verlangt eine render() Funktion
  - Die render() Funktion gint dann wieder eine JSX/React-Element zurück

```react
class MyComponent extends React.Component {
render() {
return(
<p>{this.props.text}</p>
)
 }
}
```



### Einbettung einer React-Komponente:

Geht auf 2 Arten:

1. Einbettung in der Obersten Komponente. Im React.DOM. Sollte nur FIx und fertige Komponente eingebettet werden

   ```react
   React.Dom.render(
   <MyComponent />
   document.getElementById("my-id")
   );
   ```

   

2. Einbettung in einer anderen React-Komponente. Sollte in einer Klassenbasiereten Komponente sein.

   ```react
   class MyOuterComponent extends React.Component {
   render() {
   return(
   <MyComponent />
   );
    }
   }
   ```

   ![Bildschirmfoto 2020-10-24 um 07.41.45](/Users/manu/Documents/MyLittleHerlpers/Typora_pics/Bildschirmfoto 2020-10-24 um 07.41.45.png)

   - Über props kann man von außen verschiedene Varablen in die React-Komponente bringen und damit dann dinge tun.
   - **React-Komponenten können beliebig ineinander verschachtlet werden!**

![Bildschirmfoto 2020-10-24 um 07.45.02](/Users/manu/Documents/MyLittleHerlpers/Typora_pics/Bildschirmfoto 2020-10-24 um 07.45.02.png)

- Input sind props
- Output ist ein React-Element

## ESM - Export and Import

![Bildschirmfoto 2020-10-24 um 12.19.37](/Users/manu/Documents/MyLittleHerlpers/Typora_pics/Bildschirmfoto 2020-10-24 um 12.19.37.png)

Export und inport von Variablen, Objekte oder Klassen

Um das machen zu können, muss in der index.html unser Typ als module deklariert werden

### Verwednung von Props

![Bildschirmfoto 2020-10-24 um 12.37.25](/Users/manu/Documents/MyLittleHerlpers/Typora_pics/Bildschirmfoto 2020-10-24 um 12.37.25.png)

- Werden von außen im Tag übergeben

  ```html
  <MyComponent myProps="Hallo" />
  ```

- Und innerhalb der Komponente dann ausgelesen:
  - klassenbasiert mit **this.props.nameMeinerVarable**

- ```
  class MyComponent extends React.Componente {
  redner() {
  <p>{this.props.myProps}</p>
  return()
  }
  }
  ```

  - Funktional mit **props.nameMeinerVarable**

- ```
  function myComponent(props) {
  return(
  <p>{props.myProps}</p>
  )
  }
  ```

## Einbindung mit CSS:

![Bildschirmfoto 2020-10-24 um 17.59.28](/Users/manu/Documents/MyLittleHerlpers/Typora_pics/Bildschirmfoto 2020-10-24 um 17.59.28.png)

Nicht empfohlen weil: Verlierne schnell überblich wenn jeden Komponent eigenen style hat..

![Bildschirmfoto 2020-10-24 um 18.05.49](/Users/manu/Documents/MyLittleHerlpers/Typora_pics/Bildschirmfoto 2020-10-24 um 18.05.49.png)

CSS Datei muss dann noch in die index.html file eingebunden werden 

![Bildschirmfoto 2020-10-24 um 18.22.54](/Users/manu/Documents/MyLittleHerlpers/Typora_pics/Bildschirmfoto 2020-10-24 um 18.22.54.png)

## Webpack



## Abfolge der Programs

1. componentWillMount() {/** Bevor die Seite geladen ist */}
2. render(){/** Alles was hier steht, wird immer ausgeführt, wenn sich eine prop oder der state ändert ausgeführt. aber nur das was geändert wird*/}
3. componentDidMount() {
   /**Wenn die Seite geladne ist  */
   this.setState({ anzahl: this.state.anzahl + 5 });
     }s

## Dies das:

- Aktuelle Version: **16.13.1** = 
  - 16-->Major, erhör sich wenn sich an der API ein "Breaking change" ändert. Es hat sich grob was an der Application geänder
  -  13 --> Minor, erhöht sich, wenn z.b. Additive Aänerung - neu features in der Library 
  - 1--> Patch, sind Bugfixes oder andere kleine Änderungen
- Natives JavaSript wir in {eckigen Klammern geschrieben}