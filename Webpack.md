

# Webpack

![Bildschirmfoto 2020-10-25 um 07.12.17](/Users/manu/Documents/MyLittleHerlpers/Typora_pics/Webpack/Bildschirmfoto 2020-10-25 um 07.12.17.png)

Ist ein bundle und build-tool

Ist wie eine Pipeline, hat Input(JS-Datei) und Output und dazuwischen passieren Dinge

![Bildschirmfoto 2020-10-25 um 07.15.46](/Users/manu/Documents/MyLittleHerlpers/Typora_pics/Webpack/Bildschirmfoto 2020-10-25 um 07.15.46.png)

![Bildschirmfoto 2020-10-25 um 07.17.51](/Users/manu/Documents/MyLittleHerlpers/Typora_pics/Webpack/Bildschirmfoto 2020-10-25 um 07.17.51.png)

- Tree-Shaking: Hohlt nur Teile aus einer Bibliothek die es wirklich braucht

- Code-Splitting: Eigene Code und Abhängigkeiten in verschiederne FIles trennen

  

  ![Bildschirmfoto 2020-10-25 um 07.24.17](/Users/manu/Documents/MyLittleHerlpers/Typora_pics/Webpack/Bildschirmfoto 2020-10-25 um 07.24.17.png)



![Bildschirmfoto 2020-10-25 um 07.28.30](/Users/manu/Documents/MyLittleHerlpers/Typora_pics/Webpack/Bildschirmfoto 2020-10-25 um 07.28.30.png)

```javascript
var path = require('path');

module.exports = {
  mode: 'development',
  entry: './foo.js',
  output: {
    path: path.resolve(__dirname, 'dist'),
    filename: 'foo.bundle.js'
  }
};


```



![](/Users/manu/Documents/MyLittleHerlpers/Typora_pics/Webpack/Bildschirmfoto 2020-10-25 um 07.31.22.png)

```json
module: {
  rules: [
    {
      test: /\.(js|jsx)$/,
      exclude: /node_modules/,
      use: {
        loader: 'babel-loader',
        options: {
          presets: ['@babel/preset-env']
        }
      }
    }
  ]
},
resolve: {
eatensions: [ ".js", ".jsx"]
}

```



Test: alle js und Jsx Datein sollen genommen werden 

## Installation:

- terminal: 

  ```bash
  npm install webpack webpack-dev-server webpack-cli babel-loader --save-dev
  ```

- neue File: "webpack.config.js" erstellen im Hauptverzeichnis und code rein

- Babel-loader einbauen in Webpack.config zwischen entry u. Output

  ```
  const path = require('path');
  
  module.exports = {
    entry: path.resolve("src", "index.jsx"),
    module: {
      rules: [
        {
          test: /\.(js|jsx)$/,
          exclude: /node_modules/,
          use: {
            loader: 'babel-loader'
          }
        },
        {
          test: /\.css$/,
          exclude: /node_modules/,
          use: [
            'style-loader',
            'css-loader'
          ]
        }
      ]
    },
    resolve: {
      extensions: [ '.js', '.jsx' ]
    },
    output: {
      path: path.resolve(__dirname, "dist"),
      filename: "bundle.js",
    },
  };
  ```

  

- Erstellen einer index.jsx in src file und da kommt dann unser code zum anzeigen des Projektes rein

```javascript
import {App} from './App'

const domTarget = document.querySelector('#my-react-app');
ReactDOM.render(<App/ >, domTarget);
```

- anpassen des compile und start sriptes in der package,json FIle für webpack von:

```json
"scripts": {
    "start": "npx servor ./public --reload",
    "compile": "babel src --out-dir public/lib",
```

zu:

```json
"scripts": {
    "start": "webpack-dev-server",
    "compile": "webpack",
```

- jetzt müssen bei den inputs noch .js entfernt werden, webpack findes selber hin

- Webpack hat jetzt alle datein zusammengefügt u ind dis Verzeichnis geschrieben (minifizierung)

  ![Bildschirmfoto 2020-10-25 um 08.55.17](/Users/manu/Documents/MyLittleHerlpers/Typora_pics/Webpack/Bildschirmfoto 2020-10-25 um 08.55.17.png)

- lib verzeichnis kann gelöscht werden
- nin muss in der index.html noch der neue Pfad angegben werden, damit unsere File dagestelt wird

```html
 <script type="module" src="../dist/bundle.js"></script>
```

![Bildschirmfoto 2020-10-25 um 18.57.58](/Users/manu/Documents/MyLittleHerlpers/Typora_pics/Webpack/Bildschirmfoto 2020-10-25 um 18.57.58.png)

- nun können wir react über npm einbinden und den verweis in der index.html File entfernen
- ACHTUNG: Muss in jeder Componente importiert werden

## DiesDas:

- `--save-dev`wird verwendet, um das Paket für Entwicklungszwecke zu speichern. Beispiel: Unit-Tests, Minimierung ..
- `--save` wird verwendet, um das Paket zu speichern, das für die Ausführung der Anwendung erforderlich ist.

![Bildschirmfoto 2020-10-25 um 19.16.50](/Users/manu/Documents/MyLittleHerlpers/Typora_pics/Webpack/Bildschirmfoto 2020-10-25 um 19.16.50.png)

```html
const HtmlWebPackPlugin = require('html-webpack-plugin');

plugins: [
    new HtmlWebPackPlugin({
      template: path.join(__dirname, 'src', 'index.html'),
      filename: 'index.html'
    })
  ]
```

 ## CSS importieren

![Bildschirmfoto 2020-10-25 um 19.36.47](/Users/manu/Documents/MyLittleHerlpers/Typora_pics/Webpack/Bildschirmfoto 2020-10-25 um 19.40.04.png)

- nun können css Klassen auch neben jsk klassen erzeugt werden um einen eigernen style dafür zu kreieren