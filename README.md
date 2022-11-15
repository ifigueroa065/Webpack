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


    
