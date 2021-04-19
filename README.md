# Stylus
# Introducción
* Stylus es un pre-procesador de css. Lo que quire decir que este código se copila para luego guardarlo en un archivo CSS. Por lo tanto se traduce del lenguaje de Stylus al lenguaje de CSS.
* Stylus trabaja con NodeJS

# Tabla de contenido

 - [Compilación en Stylus](#Compilación-de-Stylus-a-CSS)
 - [Sintaxis](#Sintaxis)
 - [Anidaciones](#Anidaciones)
 - [Variables](#Variables)
 - [@import](#@import)
 - [@Mixin](#@Mixin)


# Compilación de Stylus a CSS
<p> Hay muchas formas de compilar Stylus, se puede con <strong>UI/Compiladores</strong>, editor de codigo <strong>Visual estudio code</strong> o desde la <strong>terminal de comando</strong></p>

 1. <h4>UI/compiladores</h4>
   - Codekit (macOS)
   - Prepos (Mac, Windows & Linux)
   - Webpack (Mac, Windows & Linux)
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
 
 # Sintaxis
  - Stylus es un preprocesador que difiere un poco del resto (SASS, LESS) por su sintaxis
  - Su sintaxis es anidada.
  - En stylus no es necesario usar los brackets <b>{}</b> y punto y coma <b>;</b> pero para tener mejores practicas deberian ser usadas
  <h3>Stylus</h3>
  
  ```Stylus
  body
  background: lightyellow
  ```
  <h3>CSS</h3>
  
  ```CSS
  body{
   background: lightyellow;
  }
  ```
# Anidaciones
Gracias a las anidaciones podemos añadir propiedades a través de la sintaxis de Stylus. Además, esto nos permite referenciar al padre.

 - sub
 <p> Hacemos referencia a todos los elementos que estén dentro de las etiquetas padres </p>
 
  ```Stylus
 body, .light-theme
  background lightyellow
  color #2c2c2c

  .primer-hijo
    margin-bottom 24px
  ```
 - child
 <p>Con el uso de <b>“>”</b> hacemos referencia a los hijos directos del elemento padre </p>
 
  ```Stylus
 body, .light-theme
  background lightyellow
  color #2c2c2c

  > .primer-hijo
    margin-bottom 24px
  ```
 - reference
 <p>Con el uso de <b>“&”</b> hacemos referencia al nombre del elemento padre </p>
 
  ```Stylus
  psudoe-element
  width 300px

  &:before
    content 'hola'
  
  .ie-8 &
    &:before
      content 'ciao'
  ``` 
 <p> Por buenas practicas nunca se debe anidar mas de 3 veces</p>
 
# Variables
Una de las mayores ventajas que tienen los preprocesadores son las variables, estas nos permiten controlar un entorno porque podemos manipular un entorno. Esto quiere decir que podemos cambiar muchas cosas a través de muchas variables.

 - Para declarar una variable en Stylus solo se utiliza <b>"="</b>
 
 ```Stylus
  // Variables
  font-size-normal = 18px
  font-size-small = font-size-normal - 2px
  font-size-paragraph = font-size-normal

// Texts
p
  font-size font-size-paragraph

span
  font-size font-size-normal

  &.small
    font-size font-size-small
  ``` 

# @import
Una de las ventajas de los preprocesadores es que podemos crear diferentes parciales(archivos, carpetas) para organizar nuestro código. 
Cuando creamos un parcial debemos tener un _, lo que quiere decir que ese archivo no se va a compilar y va a ser llamado en nuestro archivo principal con import.

 ```Stylus
   @import "abstracts/_variables.styl";
   @import "abstracts/_mixin.styl";
   @import "abstracts/_function.styl";

   @import "layout/_blocks.styl";
   @import "layout/_site.styl";

   @import "base/_buttons.styl";
   @import "base/_links.styl";
   @import "base/_tables.styl";
   @import "base/_typography.styl";

   @import "components/_grid.styl";
   @import "components/_utilities.styl";
  ```

# Mixin
Un mixin nos permite reutilizar valores dentro del mismo CSS
Se declara facilmente con su nombre, y como buena práctica usamos <b>minix-</b> antes del nombre que queremos darle

 <h3>Stylus</h3>
  
  ```Stylus
  mixin-max-width()
    max-width: 800px
    margin-left: auto
    margin-right: auto
   
  .container
    mixin-max-width()
    text-align: center
  ```
  <h3>CSS</h3>
  
  ```CSS
  .container {
    max-width: 800px;
    margin-left: auto;
    margin-right: auto;
    text-align: center;
}
  ```
 <h3>Mixins parametricos</h3>
 
 - Para dar parámetros a un mixin lo usamos dentro del paréntesis:
 
 ```Stylus
 mixin-max-width(width)
  max-width width
  margin-left auto
  margin-right auto

 .container
  mixin-max-width(800px)
 ```
 - Para usar valores por defecto igualamos el parametro al valor que queremos:

 ```Stylus
 page-max-width = 1024px

 mixin-max-width(width = page-max-width)
  mixin-max-width()
  margin-left auto 
  margin-right auto

 .container
   mixin-max-width(800px)
 ```











