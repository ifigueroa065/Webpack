# Webpack 	:package:
Webpack es un module bundler o empaquetador de módulos para JavaScript. Domina el uso de loaders y plugins para integrar tus herramientas favoritas a un entorno de desarrollo o producción. Optimiza tus proyectos con compresión y minificación de archivos. Configura Webpack con HTML, CSS, JavaScript, React.js, imágenes y fuentes para convertirte en frontend profesional.

## Apuntes de clase :green_book:
    https://luis-ariza.notion.site/Asincronismo-con-JavaScript-7307b668977d416690103a4dbbf2843a


## Objetivos :rocket:
 
* Descubrir cuándo necesitas un module bundler.
* Configurar un entorno de desarrollo profesional con Webpack.
* Preparar un bundle para enviar a producción con Webpack.
* Compilar tu proyecto con webpacks.

## Init :beginner:
    npm init -y
    npm install webpack webpack-cli -D
    npx webpack
    
## Activar Modos :arrow_lower_left:
    npx webpack --mode development
    npx webpack --mode production
    
##  Babel Loader 💛 
    npm install -D babel-loader @babel/core @babel/preset-env @babel/plugin-transform-runtime

    - @babel/core es babel en general
    - @babel/preset-env trae y te permite usar las ultimas características de JavaScript
    - @babel/plugin-transform-runtime te permite trabajar con todo el tema de asincronismo como ser async y await
    - Debes crear el archivo de configuración de babel el cual tiene como nombre .babelrc


* Babel te permite hacer que tu código JavaScript sea compatible con todos los navegadores
* Debes agregar a tu proyecto las siguientes dependencias
* babel-loader nos permite usar babel con webpack


## :orange_book: HtmlWebpackPlugin 
Es un plugin para inyectar javascript, css, favicons, y nos facilita la tarea de enlazar los bundles a nuestro template HTML.

    npm i html-webpack-plugin -D

## 📘 Loaders para CSS y preprocesadores de CSS 

Un preprocesador CSS es un programa que te permite generar CSS a partir de la syntax única del preprocesador. Existen varios preprocesadores CSS de los cuales escoger, sin embargo, la mayoría de preprocesadores CSS añadirán algunas características que no existen en CSS puro, como variable, mixins, selectores anidados, entre otros. Estas características hacen la estructura de CSS más legible y fácil de mantener.

post procesadores son herramientas que procesan el CSS y lo transforman en una nueva hoja de CSS que le permiten optimizar y automatizar los estilos para los navegadores actuales.

    npm i mini-css-extract-plugin css-loader -D
    npm i stylus-loader -D
    
## 🗂️ Copia de archivos con Webpack
Si tienes la necesidad de mover un archivo o directorio a tu proyecto final podemos usar un plugin llamado “copy-webpack-plugin”

    npm i copy-webpack-plugin -D
    
## 🎴 Loaders de imágenes
Puedes usar una forma de importar las imágenes haciendo un import de las mismas y generando una variable
No es necesario instalar ninguna dependencia, webpack ya lo tiene incluido debemos agregar la siguiente configuración

    module.exports = {
        ...
      module: {
        rules: [
          {
            test: /\.png/,
            type: "asset/resource"
          }
        ]
      },
    }

Para empezar a usar esta configuración debemos importar la imagen de la siguiente forma
    
    import github from '../assets/images/github.png';

Para incluirlo en el HTML debes hacer lo siguiente

    // Ejemplo en Vanilla JS
    const imagen = `<img src=`${github}` />`;
    // Ejemplo en React
    <img src={`${github}`} />

## 🔤 Loaders de fuentes
Cuando utilizamos fuentes externas una buena práctica es descargarlas a nuestro proyecto
Debido a que no hara un llamado a otros sitios
Por ello es importante usarlo dentro de webpack
Para esta tarea instalaras y usaras “file-loader” y “url-loader”
instalación con NPM

    npm install url-loader file-loader -D
    
## 🏗️ Optimización: hashes, compresión y minificación de archivos

Unos de las razones por que utilizamos webpack es porque nos permite optimizar y comprimir nuestro proyecto

Debes utilizar los siguientes paquetes:

* css-minimizer-webpack-plugin ⇒ Nos ayuda a comprimir nuestros archivos finales CSS
* terser-webpack-plugin ⇒ Permite minificar de una mejor forma

        npm i css-minimizer-webpack-plugin terser-webpack-plugin -D

## 🔑 Variables de entorno

Es importante considerar las variables de entorno va a ser un espacio seguro donde podemos guardar datos sensibles
Por ejemplo, subir llaves al repositorio no es buena idea cuando tienes un proyecto open source
Para instalar debemos correr el comando

       npm install -D dotenv-webpack

Posteriormente debemos crear un archivo .env donde estarán la clave para acceder a la misma y el valor que contendrán

    Ejemplo 
    API=https://randomuser.me/api/
    
Es buena idea tener un archivo de ejemplo donde, el mismo si se pueda subir al repositorio como muestra de que campos van a ir
Una vez creado el archivo .env debemos agregar la siguiente configuración en webpack.config.js

    ...
    const Dotenv = require('dotenv-webpack');
    module.exports = {
        ...
        plugins: [
            new Dotenv()
      ],
    }
    
dotenv-webpack ⇒ Leera el archivo .env por defecto y lo agregar a nuestro proyecto
Para usarlas debes hacer lo siguiente

    const nombre = process.env.NOMBRE_VARIABLE;
    
Toda la configuración se podrá acceder desde process.env


## 🏭 Webpack en modo producción

Actualmente tenemos el problema de tener varios archivos repetidos los cuales se fueron acumulando por compilaciones anteriores
Para ello puedes limpiar la carpeta cada vez que hacemos un build, usando clean-webpack-plugin
Cabe recalcar que esta característica es mucho más util para la configuración de producción

    npm install -D clean-webpack-plugin
