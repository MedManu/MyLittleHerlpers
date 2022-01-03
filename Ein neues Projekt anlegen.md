# Neues Projekt anlegen

1. Ordner anlegen -> in Ordner gehen

2. npm init

3. ```
   npm i react react-dom
   ```

   

4. ```
   1. npm i @babel/core @babel/cli @babel/preset-react babel-loader css-loader html-webpack-plugin style-loader webpack webpack-cli webpack-dev-server  --save-dev
   
   ```

   

5. Ordner Struktur:

   1. src

      1. app	

         1. app.jsx

            1. ```react
               export class App extends React.Component {
                 render () {
                   return (
                     <div/>
                   );
                 }
               }
               ```

               

      2. components usw

   2. index.jsx

      1. ```react
         import React from 'react';
         import ReactDOM from 'react-dom';
         import { App } from './app/App';
         
         import './styles.css';
         
         const domTarget = document.querySelector('#my-react-app');
         
         ReactDOM.render(<App />, domTarget);
         
         ```

         

   3. index.html

      1. ```
         <!DOCTYPE html>
         <html>
         
         <head>
           <title>Einführung in React-State</title>
           <meta charset="utf-8" />
         </head>
         
         <body>
           <div id="my-react-app"></div>
         </body>
         
         </html>
         
         ```

         

6. ### Babel: 

   1. `npm install --save-dev babel-core babel-loader babel-preset-react` oder `npm i -d babel-{core,loader} babel-preset-react`

7. babel.config.json

   1. ```
      {
        "presets": [
          "@babel/preset-react"
        ]
      }
      
      ```

      

8. webpack.config.json

   1. ```
      const path = require('path');
      const HtmlWebPackPlugin = require('html-webpack-plugin');
      
      module.exports = {
        entry: path.join(__dirname, 'src', 'index.jsx'),
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
        plugins: [
          new HtmlWebPackPlugin({
            template: path.join(__dirname, 'src', 'index.html'),
            filename: 'index.html'
          })
        ]
      };
      
      ```

      

9. .eslintrc.json

   1. ```
      {
        "extends": [
          "es/browser"
        ],
        "parserOptions": {
          "sourceType": "module"
        },
        "rules": {
          "class-methods-use-this": "off",
          "func-style": "off",
          "prefer-destructuring": "off",
          "prefer-named-capture-group": "off",
          "require-unicode-regexp": "off",
          "sort-imports": "off",
          "react/destructuring-assignment": "off",
          "react/prefer-stateless-function": "off"
        }
      }
      
      ```

10. package.json scripts:

   1. ```
      "scripts": {
          "start": "webpack-dev-server",
          "build": "webpack"
        },
      ```

      

   

   