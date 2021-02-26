# React

### Schnell Erstellung:

1. npm init 
2. npm install create-react-app
3. Npx create-react-app nammederap

## Alg-React projekt erstellen stepBystep:
1. `npm init`

   1. Der Befehl npm init erzeugt automatisch eine neue Datei mit dem Namen **package.json**. package.json enthält Metadaten über Ihr neues Projekt.

      

2. **React**:`npm i -S react`

   1. Um ein Modul mit npm zu installieren, müssen Sie den Namen dieses Moduls kennen. Wenn Sie ein Modul installieren möchten und Sie sich nicht sicher sind, wie es genau heißt, können  Unser erstes Modul heißt react. Es wird **node_modules** & **package-lock.json** erzeugt. `node_modules` ist der Ort, an dem `npm` Module gespeichert werden.

3. **React-dom**: `npm i -S react-dom`

   1. Das nächste, was Sie installieren möchten, ist react-dom. Sobald Sie react-dom installiert haben, können Sie in Ihren Dateien mit dem Code var ReactDOM = require('react-dom') darauf zugreifen.

4. **Babel**: `npm install --save-dev babel-core babel-loader babel-preset-react` oder `npm i -d babel-{core,loader} babel-preset-react`

   1. Babel ist ein JavaScript-Compiler, der die Möglichkeit bietet, JSX in reguläres JavaScript zu kompilieren. Anstelle von `npm install --save babel-core ` werden Sie den Befehl `npm install --save-dev babel-core` verwenden

   2. Damit Babel funktioniert, müssen Sie eine Babel-Konfigurationsdatei schreiben.

      Erstellen Sie in Ihrem Stammverzeichnis eine neue Datei mit dem Namen `.babelrc`. Wenn Sie aufgefordert werden, einen Dateinamen mit einem Punkt zu beginnen, sagen Sie, dass es in Ordnung ist.

      Speichern Sie den folgenden Code innerhalb von .babelrc:

      ```typescript
      {present: ["react"]}
      ```

5. WebPack: `npm i -d webpack webpack-dev-server html-webpack-plugin`

   1. Sie haben Babel installiert, aber Sie haben es noch nicht an Ihre React-Anwendung "angeschlossen". Sie müssen ein System einrichten, in dem Ihre React-Anwendung automatisch durch Babel läuft und Ihr JSX kompiliert, bevor Sie den Browser erreichen.

      Außerdem ist JSX zu JavaScript nur eine von vielen Transformationen, die mit Ihrem React-Code vorgenommen werden müssen. Sie müssen einen "Transformations-Manager" einrichten, der Ihren Code nimmt und ihn in der richtigen Reihenfolge durch alle erforderlichen Transformationen laufen lässt. Wie erreichen Sie das?

      Es gibt viele verschiedene Softwarepakete, die dies ermöglichen können. Das derzeit populärste ist ein Programm namens webpack.

   2. ### WEBPACK.CONFIG.JS

      1. Die Aufgabe von Webpack ist es, Ihren React-Code durch verschiedene Transformationen laufen zu lassen. Webpack muss genau wissen, welche Transformationen es verwenden soll! Sie können diese Information einstellen, indem Sie eine spezielle Webpack-Konfigurationsdatei erstellen. Diese Datei muss sich in der äußersten Schicht Ihres Stammverzeichnisses befinden und den Namen webpack.config.js tragen. Dort werden Sie alle Details angeben, die für den Betrieb von Webpack erforderlich sind.
         Erstellen Sie in Ihrem Stammverzeichnis eine neue Datei namens `webpack.config.js.`

   3. ### CONFIGURE WEBPACK

      1. Webpack wird Ihr JavaScript nehmen, es durch einige Transformationen laufen lassen und eine neue, transformierte JavaScript-Datei erstellen. Diese Datei wird diejenige sein, die der Browser tatsächlich liest. Um dies zu tun, muss Webpack drei Dinge wissen: 

         1. Welche JavaScript-Datei es transformieren soll.
         2. Welche Transformationen es für diese Datei verwenden soll.
         3. Wohin die neue, transformierte Datei gehen soll.

      2. Schreiben Sie zunächst in **webpack.config.js:**

         ```javascript
         module.exports= {};
         ```

         - Die gesamte Konfiguration des Webpacks wird buchstäblich innerhalb dieses Objekts liegen!

   4. ### WELCHE JAVASCRIPT-DATEI SOLL WEBPACK TRANSFORMIEREN?

      1. Das erste, was ein Webpack wissen muss, ist ein Einstiegspunkt. Der Einstiegspunkt ist die Datei, die Webpack transformieren soll.

      2. Ihr Einstiegspunkt sollte die äußerste Komponentenklasse Ihres React-Projekts sein. Er könnte in etwa so aussehen:

         1. ```
            var React = require("react");
            var ReactDom = require("react-dom");
            var App = require("./cpmponents/App");
            
            ReactDom.render(
            <App />),
            dicument.getElementById("app");
            ```

      3. In diesem Beispiel wird Webpack das Ergebnis von <App /> transformieren. Wenn die Renderfunktion von <App /> Komponenten aus anderen Dateien enthält, dann werden diese Komponenten ebenfalls transformiert. Wenn Sie Ihren Einstiegspunkt zur äußersten Komponentenklasse Ihrer Anwendung machen, dann wird webpack Ihre gesamte Anwendung transformieren!

         Um einen Einstiegspunkt zu spezifizieren, geben Sie module.exports eine Eigenschaft namens entry. Der Wert von entry kann ein Dateipfad sein, oder ein Array von Dateipfaden, wenn Sie mehr als einen Einstiegspunkt haben möchten. Für dieses Projekt benötigen Sie nur einen.

         Aktualisieren Sie in webpack.config.js module.exports so, dass es wie folgt aussieht:

         - ```
           module.exports = {entry: __dirname + "/app/index.js"};
           ```

         - In Node.js bezieht sich __dirname auf die aktuell ausgeführte Datei. __dirname + /app/index.js erzeugt einen Dateipfad, der auf die aktuell ausgeführte Datei verweist, hinunter in einen Ordner namens app und landet auf einer Datei namens index.js.

      4. ### WELCHE TRANSFORMATIONEN SOLLTE WEBPACK DURCHFÜHREN?

         1. Webpack kann nun erfolgreich Ihre äußerste Komponenten-Klassendatei und damit Ihre gesamte React-Anwendung erfassen. Nun, da Webpack den gesamten Code erfassen kann, müssen Sie erklären, was Webpack damit tun soll, wenn es einmal erfasst wurde.

            Sie können Webpack erklären, was es mit dem gegrabbten Code machen soll, indem Sie eine zweite Eigenschaft zu module.exports hinzufügen. Diese Eigenschaft sollte den Namen des Moduls und den Wert eines Objektliterals enthalten, das ein Loader-Array enthält:

            ```json
            module.exports = { 
                entry: __dirname + "/app/index.js",
                module: {
                    loader:[]
                }
            
            };
            ```

            

      5. ### Wriate a loader

         1. Jede Loader-Transformation sollte als ein Objektliteral geschrieben werden. Hier ist Ihr erster Loader, vorerst leer:

            ```js
            module.exports = { 
                entry: __dirname + "/app/index.js",
                module: {
                    loader:[
                        {}
                    ]
                }
            };
            ```

         2. 

      6. 

### npm scrips:

- Suchen Sie in Ihrer Datei **package.json** das Objekt scripts. Mit diesem Objekt können Sie Ihren Befehlszeilen-Skripten einfachere Namen geben und sie nachschlagen, wenn Sie sie vergessen haben!
- Nehmen wir an, dass Sie das Skript npm run build && npm run git-commit && npm run git-push verwenden müssen. Das ist viel zu viel, um sich daran zu erinnern. In package.json könnten Sie hinzufügen:

```json
"scripts": {
    "deploy": "npm run build && npm run git-commit && npm run 				git-push",
    "build": "webpack",
    "start": "web-dev-server",
  },
```

- Danach brauchen Sie nur noch **npm run deploy** einzugeben, und der Befehl, der als deploy-Wert gespeichert ist, wird ausgeführt. Und noch besser, Sie können den Befehl in package.json nachschlagen, falls Sie ihn vergessen haben.
- npm run start started den localen server
- npm run start gibt Ihnen auch die Möglichkeit, Ihre Anwendung zu ändern und die Änderungen automatisch zu sehen, ohne den Server für jede neue Änderung neu starten zu müssen.

<h2> Erstellen einer Kompleten App (Mit ypeScript):
</h2>


1. Node u npm müssen installiert sein
2. (npm i -g(global) create-react-app -> vornbereitung)
3. npx create-react-app name-der-app -> in Kleinbuchstaben, erstellen der App
4. In die app gehen
5. npm i typescript @types/node @types/react @types/react-dom (installierne der Komponenten)
6. App.js zu App.ts umwandeln



### 1ste File in der App erstellen:

- App.js (ist die ressourcen File) zu App.tsx ändern
  - Npm run start um die App zu st

- Sollten keine bilder zum Importieern gehen
  - npmFile: react-app-env.d.ts erstellen
  - /// <reference *types*="react-scripts" /> einfügen



### Compilieren einer ts file:

- npm init 
  - generiert **package.json file**
    - npm i -s react
    - generiert **node_modules** & **package-lock.json**
- npm install --save -dev lite-server - oder npm i -s react
  - generiert **package-lock.json**
    - $ sudo npm i --global local-web-server  alternativ für localen webserve
- In package.json unter scripts:
  - "start": "lite-server"
- npm start zum starten



## Erstellen eines Projektes für Webpack - StepbyStep

1. Ordner für Projekt erstellen

   1.  mkdir react-ts-webpack

2. in den Ordner gehen

   1. cd react-ts-webpack

3. npm initialisieren

   1. npm init -y (y -> ja zu allem)

4. src Ordner erstellen

   1. mkdir src

5. In oOrdner gehen

   1. cd src

6. Index Datei erstellen

   1.  touch index.tsx

7. In äußeren Ordner zurückgehen

   1. cd ..

8. Weiter Files erstellen

   1. touch index.html **(für den code)** webpack.config.js **(für die configs)** .babelrc **(setting für babel um ts zu js zu kompilieren)**

9. html Standart-Code in index.html einfügen (ecmel: ! =Standart html, tap+element+#)

   ```html
   <!DOCTYPE html>
   <html lang="en">
   <head>
       <meta charset="UTF-8">
       <meta name="viewport" content="width=device-width, initial-scale=1.0">
       <title>Document</title>
   </head>
   <body>
     <div id="app-root"></div> --> hier kommt der ganze Code rein!!
   </body>
   </html>
   ```

   

10. In index.tsx Standart react-code einfügen:

    ```typescript
      import React from "react"
    import ReactDOM from "react-dom"
    
    
    export default function App(): JSX.Element {
        return (
            <h1>
                Hello World!!
            </h1>
        ) 
    }
    
    const root = document.getElementById("app-root") // index file
    
    ReactDOM.rander(<App />, root) //alles in der App-Methode wird gerendert nach root (React-Code, HTML zum rendern)
    
    ```

    

    

    11. Webpack konfigurieren:

        

        ```typescript
        const path = require("path") // gleiche wie = import path from "path"
        const rules = [
            {
                test:/\.tsx?/, //jedes Files das auf tsc endet
                exclude: /node_modules/, // außer die in node_modules
                loader: "babel-loader" // sollen babel-loader benutzen
            }
        ] //array of Objects
        
        module.eyports = {
            target: "web",
            mode: "development",
            entry: "./src/index.tsx",
            output: {
                path: path.resolve(_dirname, "build"),
                filename: "bundle.js"
            },
            module: { rules },
            resolve: {extentions: [".ts", ".tsx", ".js"]},
            devServer: {
                contentBase: "./",
                port: 5000
            }
        }
        ```

        

    12. Babel Config:

        ```json
        {
            "presets": ["@babel/env", "@babel/react", "@babel/typescript"] 
          //plugins from babel
        }
        ```

    13. Package.json editieren:

        ```json
        {
          "name": "react-ts-webpack",
          "version": "1.0.0",
          "description": "",
          "main": "index.js",
          "scripts": {
        -->    "start": "webpack-dev-server --open", // npm start -> to start Webserver and open new tap in browser
        -->    "build": "webpack" // npm run build -> build for productions as descripted  in webpack.config.js
          },
          "keywords": [],
          "author": "",
          "license": "ISC",
          "dependencies": {
            "react": "^16.13.1"
          }
        }
        ```

    14. Terminal:

        1. In der App (react-ts-webpack):

           1. npm i 

              @babel/core @babel/preset-env @babel/preset-react @babel/preset-typescript babel-loader  

              webpack webpack-cli webpack-dev-server 

              react react-dom @types/react @types/react-dom

    ​            

    

### Router anlegen:

- npm i @reach/router
- npm i @types/reach__router
- In App.tsx

- *import*{Link} *from* "@reach/router" in 
- <Link *to*="/faves">Favourites(s): {state*.**favourites**.*length}</Link> im html Teil

- **In  index.tsx file:**

  - *import*{Router, RouteComponentProps} *from* "@reach/router"

  - *import* Homepage *from* "./HomePage" usw

  - Erstellen der props für den Router

    - ```typescript
      const RouterPage = (props: {pageComponent: JSX.Element} & RouteComponentProps) => props.pageComponent
      //props is vom Typen JSX.Element und alles andere  vom typ RouteComponentProps
      ```

  - Html Aufbau:

    - ```html
        <Router>
            <App path="/">
              <RouterPage pageComponent={<HomePage />} path="/"/>
              <RouterPage pageComponent={<FavPage />} path="/FavPage"/>
            </App>
          </Router>
        
      ```



## Wichtige Befehle:

- npm start
      Starts the development server.
- npm run build
      Bundles the app into static files for production.
- npm test
      Starts the test runner.
- npm run eject
      Removes this tool and copies build dependencies, configuration files
      and scripts into the app directory. If you do this, you can’t go back!

### Redux:

- Geeignet für die Verwaltung Compexerer Anwednungen
  -  **Store**: Enthält zentralen zustand der Anwendung
  - **Reducer**: Genutz um Zustand zu ändern - wie Action behandelt werden soll. Wie sich der Zustand als reaction auf die Action ändern soll
  - **View**: Oberfläche der Anwendung
  - **Action**: Wenn der User mit View interagiert
    - Json Objekt wo beschrieben is, was passieren soll zb. neune task anlegen
  - **Dispatcher**: Zentrale Eingangsstelle für 
  - **State**: Neuer Zustand - wird wieder in der View dargestellt.

### Nesting :

- Verschachteln von Componenten

- Hier wird eine Comonente in einer eigenen Class erzeug und dann in der Hauptklasse dargestellt. 

- Nebenkomponenrten (Ninjas.ts)):

  - ```
    import React, {Component} from "react"
    
    
    class Ninjas extends Component {
        render() {
            return (
                <div className ="ninja" >
                <div>Name: Ryu</div>
                <div>Age: 30</div>
                <div>Belt: Black</div>
                </div>
            );
        }
    }
    
    export default Ninjas;
    ```

- Hauptkomponente (App.js):

  - ```javascript
    import React, {Component} from 'react';
    import Ninjas from "./Ninjas"
    
    
    
    class App extends Component {
      render (){
      return (
        <div className="App">
          <h1>My first React app!</h1>
          <p>Welcome =)</p>
          <Ninjas/> <-- Unsere Nebenkomponente
        </div>
      );
      }
    }
    
    export default App;
    
    ```

### Props:

- Daten vom ElternElement zum KindElement übergeben

- werden in Eleernelement vergeben.

  - ```html
     <Ninjas name="Ryu" age="30" belt="Black"/>
    ```

- Können dann im Kinderelement verwendet werden:

  - ```html
    class Ninjas extends Component {
        render() {
            console.log(this.props)
            return (
                <div className ="ninja" >
                <div>Name: {this.props.name}</div> 
                <div>Age: {this.props.age}</div>
                <div>Belt: {this.props.belt}</div>
                </div>
            );
        }
    }
    ```

- Kürzerer Weg durch destrukturierung:

  - *const* { *name*, *age*, *belt* } = *this**.**props*;  --> die namen müssen gelich wie bei der vergabe sein

  - ```html
     const { name, age, belt } = this.props;
        return (
          <div className="ninja">
            <div>Name: {name}</div>
            <div>Age: {age}</div>
            <div>Belt: {belt}</div>
          </div>
        );
      }
    }
    ```

- Durch props Können Komponenten öffters mit anderen Werten verwendet werden.

  - ```html
     <Ninjas name="Ryu" age="25" belt="Black" />
          <Ninjas name="Yoshi" age="28" belt="Black" />
          <Ninjas name="Mario" age="35" belt="Black" />
    ```

### State:





### Listen übergeben:

- Mittels states:

  - ```html
    state = {
        ninjas: [
          { name: "Ryu", age: 25, belt: "Black", id : 1 },
          { name: "Yoshi", age: 28, belt: "Green", id : 2 },
          { name: "Mario", age: 30, belt: "Red", id : 3},
        ],
      };
    ```

- Referenz des state als props:

  - ```html
     <Ninjas ninjas={this.state.ninjas} />
    ```

- In der Klasse greifen wir auf die props zu

  - ```javascript
        const { ninjas } = this.props; //gleich wie const { ninjasProps } = this.props.ninjas;
    ```

- Durchlaufen des Arrays und für jeden Eintrag einen Element erzeigen:

- Dafür verwenden wir map: 

  - ```html
    const ninjaList = ninjas.map((ninja) => {
          return (
            <div className="ninja" key= {ninja.id}>
              <div>Name: {ninja.name}</div>
              <div>Age: {ninja.age}</div>
              <div>Belt: {ninja.belt}</div>
              <br />
            </div>
          );
    ```

- unsere liste geben wir dann aus:

  - ```javascript
    import React, { Component } from "react";
    
    class Ninjas extends Component {
      render() {
        const { ninjas } = this.props; //gleich wie const { ninjasProps } = this.props.ninjas;
        const ninjaList = ninjas.map((ninja) => {
          return (
            <div className="ninja" key= {ninja.id}>
              <div>Name: {ninja.name}</div>
              <div>Age: {ninja.age}</div>
              <div>Belt: {ninja.belt}</div>
              <br />
            </div>
          );
        });
        return <div className="ninja-list">{ninjaList}</div>;
      }
    }
    
    export default Ninjas;
    
    ```



### Typen von Komponenten:

| Container-Komponenten**               |              UI-Komonenten               |
| ------------------------------------- | :--------------------------------------: |
| beinnhalten den State                 |         Beinhalten keine States          |
| hinhalten Livecycle hooks             |      Bekommen ihre Daten von Props       |
| Keine Verbindung zum UI               |         Nur mit de mUi Verbunden         |
| Brauchen Klassen um Kreiert zu werden | Brauchen Fubktionen um Kreiert zu werden |

- Container-Component - Class Components:

  - props sind automatisch zu haben und mit this Übergenen

  - ```html
    class App extends Component {
     
      render() {
        return (
          <div className="App">
       
          </div>
        );
      }
    }
    
    export default App;
    
    ```

- UI-Component - Functional- Components:

  - props müssen als Parameter  übergeben werden!!

  - es können aber keine States erzeug werden, innerhalb der Funktion

  - ```javascript
    const Ninjas = (props) => { //<- props als Parameter
      //destructured:
    // const Ninjas = ({ourNinjas}) => {  und dann ohne const {ourNinjas} .... 
        const { ourNinjas } = props; <- Können ohne this erzeugt werden
        const ninjaList = ourNinjas.map((ninjaAttribute) => {
          return (
            <div className="ninja" key={ninjaAttribute.id}>
              <div>Name: {ninjaAttribute.name}</div>
              <div>Age: {ninjaAttribute.age}</div>
              <div>Belt: {ninjaAttribute.belt}</div>
              <br />
            </div>
          );
        });
        return(
            <div className="ninja-list">{ninjaList}</div>
        )
      }
    
    
    export default Ninjas;
    
    ```

  - 

# Ternary Operator:

- The *Java* *ternary operator* functions like a simplified [Java if](http://tutorials.jenkov.com/java/if.html) statement. The ternary operator consists of a condition that evaluates to either `true` or `false`, plus a value that is returned if the condition is `true` and another value that is returned if the condition is `false`. Here is a simple Java ternary operator example:

- condition ? (retun if *true*) : (retun if *false*)

- ```javascript
  return ninjaAttribute.age > 20 ? (
       <div className="ninja" key={ninjaAttribute.id}>
         <div>Name: {ninjaAttribute.name}</div>
         <div>Age: {ninjaAttribute.age}</div>
         <div>Belt: {ninjaAttribute.belt}</div>
         <br />
       </div>
     ) : null;
  ```


# Redux

-  npm i redux 
- Npm i react-redux
- central datastor for all app data
- can be accessed by every component to get date
- akes state management easy

![Bildschirmfoto 2020-10-07 um 17.41.52](/Users/manu/Documents/MyLittleHerlpers/Typora_pics/Bildschirmfoto 2020-10-07 um 17.41.52.png)

- Centra so every component gets easy acess

![Bildschirmfoto 2020-10-07 um 17.43.07](/Users/manu/Documents/MyLittleHerlpers/Typora_pics/Bildschirmfoto 2020-10-07 um 17.43.07.png)

-  Create store in index.js
-  component witch wants access data subscribes to changes to the data and redux passes that data in **props**
- there is a process for changes:
  -  decide to make a change
  - dispatch an action - actions describe the changes we like to make (**eg addpost**)
  - with the action we can pass an optional **payload** - **payload** is any kind of data we want to pass with (**e.g the new post**)
  - This actions is passed to a **reducer** - reducer takes the actions, looks at its type a know that is is a addpost action - he now goes to the center **store** the state and I gonna update it - **the reduces updates the state**  n**ot the component itself** - 
- the reducer is a function that interactions with the store to change the state/date inside of it
- the store is like a warehouse and the reducer is like a robot, who is the only one going inside the warehouse

[https://cdnjs.cloudflare.com/ajax/libs/redux/4.0.0-rc.1/redux.js](https://www.youtube.com/redirect?redir_token=QUFFLUhqa3pCRlFFMGE5bXBQdUNOTWJRd043Z19UUlFkQXxBQ3Jtc0ttQldEekc4amlWT05LclpjTktDSFFUVXI3TUN5WWVzVzZuTF9ESXV6SDgyTFY3cktLbXVieF9FdVJOdmFvc18yZkNTV19RbVFoWE1sVUpYWWg2YjdjUUVXVWs5TjVZVUI0aG9qQ3h4OVlRX0NZZHFSYw%3D%3D&stzid=Ugx6kyGouuJV0DOHyB54AaABAg&q=https%3A%2F%2Fcdnjs.cloudflare.com%2Fajax%2Flibs%2Fredux%2F4.0.0-rc.1%2Fredux.js&event=comments)

- ``` javascript
  // 1. holen von redux
  const {createStore} = Redux;
  
   // 4.erstellen eines anfangsstatus, in diesem fall leer
  const initState = {
    todos: [ ],
    posts: [ ]
  }
  
  //3.unsere Reducer-Function hat immer einen State(gleich unserme anfangsstate) und eine action
  function myReducer (state = initState, action) {
    
    //7.check what type of action we get an than do it
    if (action.type == `ADD_TODO` ) {
      //8.return new objekt that repesents the new state of the store
      return {
        //9.update todos - create new array
        //spreat ... states of todo, to to get individual states, add new elements(e.g Buy Milk)
        //we also need to pass the stuff we dont want to change, else we only get the store and not the              post
        //todos: [ ... state.todos,action.todo]
      //  posts: [ ], // could do that but if we have more stuff it gets to much to ride we else could use the spreat operator of the state with grap everything of the current state and than override the todos agaien
        ...state,
        todos: [ ... state.todos,action.todo]
      }
    } 
    //same for posts
    
    if(action.type == "ADD_POST") {
      return {
        ...state,
        posts: [...state.posts, action.post]
      }
    }
  }
  
  //2.unser Store wo alle daten sind und dem der reducer übergeben wir, damit der reducer zugang auf die daten hat
  const store = createStore(myReducer);
  
  //10.listen for changes in the store and than react to those changes
  //funktion mit funtion als parpameter
  //function fires everxtime a state is changes
  //momentan wollen wir jedesmal wenn das passiert nur was ausgeben
  store.subscribe(() => {
    console.log("state updated")
    //get the state
    console.log(store.getState())
  })
  //5.unsere action mit der payload für die Daten
  //adding a new todo
  //const todoAction = { type: `ADD_TODO`, todo: `Buy Milk`}
  
  const todoAction = { type: `ADD_TODO`, todo: `Sleep More`}
  
  //6.dispatch the action: take store us dispatch-Method and in it pass die action
  store.dispatch(todoAction)
  
  //11 add more posts and todod direct in dispatch function and 
store.dispatch({ type: `ADD_TODO`, todo: `Buy some Eggs`})
  store.dispatch({ type: `ADD_POST`, post: `Egg hunt with Yoshi`})
  
  
  ```
  
- 

### DiesDas:

- referenz mit () heist das funktion gleich nach aufrufen der Seite abgefeuert wird -> {handleClick}
- Ohne (), wird sie erst nach cklcken auf den Button abgefeuert ->{handleClick}

## Abfolge der Programs

1. componentWillMount() {/** Bevor die Seite geladen ist */}
2. render(){/** Alles was hier steht, wird immer ausgeführt, wenn sich eine prop oder der state ändert ausgeführt. aber nur das was geändert wird*/}
3.   componentDidMount() {
    /**Wenn die Seite geladne ist  */
    this.setState({ anzahl: this.state.anzahl + 5 });
    }s