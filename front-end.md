# Preguntas Front End

Esta lista de preguntas no es exhaustiva, es solo un ejemplo de preguntas que personalmente le haría a un candidato a desarrollador Front End.

Hazle fork a este repositorio y escribe tus respuestas debajo de cada pregunta. A veces uno cree saber la respuesta, pero no es hasta que la intenta escribir que se da cuenta que no la sabe expresar.

## HTML Y CSS

#### ¿Para qué se utiliza el `doctype` en HTML?
It lets the browser know how the document should be interpreted, by indicating what version or standard of HTML (or other markup language) is being used.

`<!DOCTYPE html>` HTML5

`<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">` HTML 4.01 Strict

#### ¿Por qué es una buena idea ubicar la referencia a archivos CSS dentro de la etiqueta `<head>`y la referencia a archivos JS antes de cerrar el `<body>`?
Tiene relevancia en el tiempo de carga de la página y en la experiencia del usuario mientras se realiza dicha carga.

El proceso de carga de una página web se puede simplificar de la siguiente manera:

1. El navegador obtiene la página HTML
2. Comienza la fase de parsing (análisis sintáctico)
3. El analizador encuentra una etiqueta script que hace referencia a un archivo externo
4. El navegador hace una petición para obtener el archivo. Mientras tanto el analizador entra en una fase de bloqueo.
5. El navegador obtiene el script, lo analiza y lo ejecuta.
6. El analizador continua con el resto de la página.

El paso 4 es potencialmente la causa de una demora en la carga de la página, porque antes de mostrar los elementos visuales, el navegador debe descargar y ejecutar todos los scripts.

La Solución

Tomando en cuenta el comportamiento del navegador cuando encuentra una etiqueta script, una posible solución es colocar dichas etiquetas lo más abajo posible dentro de la etiqueta body.

Al realizarse la descarga, si el CSS es el primer recurso externo al que llamamos en el `<head>`, nos aseguraremos que la página poseerá estilos en el momento más temprano posible.

#### ¿Cuál es la diferencia entre clases y id's en en CSS?
El valor del atributo “id” de un elemento es único.

#### ¿Qué es el modelo de caja (box model) en CSS?
Cada elemento que encontramos dentro de un documento HTML se encuentra contenido en una caja rectangular, la cual cuenta con una serie de propiedades que afectaran el cómo se muestran los elementos.

![alt text](https://mdn.mozillademos.org/files/8685/boxmodel-(3).png)

#### ¿Qué hace `box-sizing: border-box` en CSS?
La propiedad `box-sizing` se usa para modificar las propiedades por defecto del CSS box model que calculan el alto y el ancho de los elementos.

El valor `border-box`, width y el height incluyen el padding y el border, pero no el margin.

Cuando ajustas un elemento con `box-sizing: border-box`, el padding y border de ese elemento no incrementan su ancho.

#### ¿Para qué se utiliza la propiedad `z-index`?
The z-index property in CSS controls the vertical stacking order of elements that overlap.
 
Se utiliza en casos, en que dos elementos queden superpuestos, podemos determinar el orden en que se "apilarán". Un elemento con mayor z-index generalmente cubre a otro menor.

#### ¿Qué son los media queries? ¿Para qué se utilizan?
"Responsive Design" es la estrategia que busca la correcta visualizacion de una misma pagina en distintos dispositivos. Los media queries son la herramienta más poderosa para hacer esto.

La regla @media nos permite especificar que cierto conjunto de reglas CSS solo deben aplicarse a cierto tipo de dispositivo.
```
@media (min-width: 750px) and (max-width: 820px){
  .lateral{
    width: 33%;
    float: right;
    background-color: #6fe;
  }
 }
```
#### ¿Qué es un breakpoint en responsive design?
Breakpoints are the point a which your sites content will respond to provide the user with the best possible layout to consume the information. 

#### Nombra 3 nuevas características de CSS3.
1. New selectors. Using these selectors you can choose DOM elements based on their attributes. [attr^=val] matches a DOM element with the attribute attr and a value starting with val. p[title^="car"] {color: red;}
2. CSS Animations and Transitions
3. Gradients
4. Media Queries

#### ¿Qué es SASS? ¿Qué problemas soluciona?
Preprocesador CSS

Permite trabajar mucho más rápido en la creación de código con la posibilidad de crear funciones que realicen ciertas operaciones matemáticas y reutilizar código gracias a los mixins, variables que nos permiten guardar valores. 

#### ¿Qué es flexbox?
Flexbox es un nuevo módulo de diseño en CSS3 para mejorar la forma en que hacemos Responsive Design.

Con Flexbox podemoss controlar la orientación de un elemento, la distribución de espacio entre elementos,el orden y espacio intermedio entre elementos.

## Bootstrap

#### ¿Qué es Bootstrap y qué nos ofrece?

#### ¿De qué formas podemos incluir Bootstrap en nuestro proyecto?

#### ¿Cuáles son los breakpoints que define Bootstrap en su grilla?

#### ¿Qué formas existen de personalizar los estilos de Bootstrap?

#### ¿Cuál sería el resultado de aplicar las clases `col-xs-6 col-sm-4 col-lg-12` a un `div`?


## Git y Github

#### ¿Qué son las ramas en Git y para que se pueden utilizar?

#### ¿Cuál es la diferencia entre `git merge` y `git rebase`?

#### ¿Qué es un Pull Request en Github? ¿Para qué se utiliza?

#### ¿Cuál es la diferencia entre `git pull` y `git fetch`?

#### En el comando `git push -u origin mi-rama` ¿para qué significa la opción -u?

#### En Github ¿qué significan un fork y para qué se utiliza?


## JavaScript

#### ¿Cuál es la diferencia entre `==` y `===`?

#### ¿Qué es un callback? ¿Por qué se necesitan en JavaScript?

#### ¿Qué es un closure?

#### ¿Qué significa que JavaScript sea un lenguaje prototipado?

#### ¿Qué es una función inmediata? ¿Cuál es su sintaxis?

#### ¿A qué se refiere `this` en JavaScript? ¿Qué problemas puede ocasionar?

#### ¿Qué es programación funcional? ¿Es JavaScript un lenguaje funcional?

#### ¿Cómo podemos agregarle un método a todos los arreglos en JavaScript?

#### Nombra al menos 3 nuevas características de ES2015.

#### ¿Para qué se utiliza el método `bind` de las funciones?

#### ¿Cómo puedo recibir un número variable de argumentos en una función? Escribe un ejemplo que lo ejemplifique.

#### ¿Qué es TDD (Test Driven Development)?

#### ¿Qué son las Promesas en JavaScript y para qué se utilizan?


## API del navegador, jQuery y AJAX

#### ¿Qué es el DOM (Document Object Model)? ¿Cómo lo podemos manipular?

#### ¿Por qué surgió jQuery?

#### ¿Qué es una cookie? ¿Qué es el local storage? ¿Cuál es la diferencia entre los dos?

#### ¿Qué es AJAX?

#### Necesitamos hacer un `POST` a `/products` con la siguiente información en JSON: `{ "name": "Pan", "quantity": 4, price: 12000 }`. La respuesta también es JSON ¿Cuál sería la sintaxis para hacerlo? Puedes hacerlo con jQuery o JavaScript puro.

#### ¿Qué es Handlebars? ¿Para qué se utiliza?

#### ¿Qué es CORS (Cross-Origin Resource Sharing)?

#### ¿Qué son Web Sockets? ¿Para qué se utilizan?

#### Nombra tres casos para los que puedes utilizar las herramientas del desarrollador (developer tools) del navegador?

#### ¿Qué es Handlebars y para qué se utiliza?

#### ¿Para qué se utiliza `"use strict";`?
