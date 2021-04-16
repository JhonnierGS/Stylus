# Stylus
# Introducción al curso
* Stylus es un pre-procesador de css. Lo que quire decir que este código se copila para luego guardarlo en un archivo CSS. Por lo tanto se traduce del lenguaje de Stylus al lenguaje de CSS.
* Stylus trabaja con NodeJS


# Compilación de Stylus a CSS
<p> Hay muchas formas de compilar Stylus, se puede con <strong>UI/Compiladores</strong>, editor de codigo <strong>Visual estudio code</strong> o desde la <strong>terminal de comando</strong></p>

 1. <h4>UI/compiladores</h4>
   - Codekit
   - Prepos
   - Webpack
 2. <h4>VS Code</h4>
   - Con VS Code se pueden usar varias extensiónes como <strong>Live Stylus Compiler</strong>
 3. <h4>Terminal de comando</h4>
    Hay que tener <strong>NODE</strong> instalado, ya instalado en la terminal vamos a instalar el compilador de stylus con el siguiente comando
   > npm install -g stylus
   - Compilar archivo .styl a .css
   > stylus archivo.styl -o css/archivo.css
   - compilar y comprimir el archivo
   > stylus archivo.styl --compress
   - activar un watcher para no tener que hacerlo manualmente
   > Stylus -w archivo.styl -o css/archivo.css
