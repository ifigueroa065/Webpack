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


## HtmlWebpackPlugin :orange_book:
Es un plugin para inyectar javascript, css, favicons, y nos facilita la tarea de enlazar los bundles a nuestro template HTML.

    npm i html-webpack-plugin -D

## Loaders para CSS y preprocesadores de CSS 📘

Un preprocesador CSS es un programa que te permite generar CSS a partir de la syntax única del preprocesador. Existen varios preprocesadores CSS de los cuales escoger, sin embargo, la mayoría de preprocesadores CSS añadirán algunas características que no existen en CSS puro, como variable, mixins, selectores anidados, entre otros. Estas características hacen la estructura de CSS más legible y fácil de mantener.

post procesadores son herramientas que procesan el CSS y lo transforman en una nueva hoja de CSS que le permiten optimizar y automatizar los estilos para los navegadores actuales.

    npm i mini-css-extract-plugin css-loader -D
    npm i stylus-loader -D
    
## 🗂️ Copia de archivos con Webpack
Si tienes la necesidad de mover un archivo o directorio a tu proyecto final podemos usar un plugin llamado “copy-webpack-plugin”

    npm i copy-webpack-plugin -D

    
