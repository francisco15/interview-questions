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
Bootstrap es un framework de HTML, CSS, y JS, para crear páginas Web que tengan un diseño consistente y adaptable a la pantalla. 

#### ¿De qué formas podemos incluir Bootstrap en nuestro proyecto?
Agregando el código CDN (content delivery network) a nuestro HTML para usarlo de manera remota 
Descargando bootstrap de su página web y agregando las carpetas al proyecto

#### ¿Cuáles son los breakpoints que define Bootstrap en su grilla?
xs - móviles, sm - tablets, md - desktop, lg - pantallas más grandes
```
// Small devices (landscape phones, 576px and up)
@media (min-width: 576px) { ... }

// Medium devices (tablets, 768px and up)
@media (min-width: 768px) { ... }

// Large devices (desktops, 992px and up)
@media (min-width: 992px) { ... }

// Extra large devices (large desktops, 1200px and up)
@media (min-width: 1200px) { ... }
```

#### ¿Qué formas existen de personalizar los estilos de Bootstrap?
No modificar ningún archivo de Bootstrap, así cuando se actualice el framework a una nueva versión no tendremos que modificar ningún archivo, simplemente enlazar el archivo que nosotros mismos creamos.

Crear nuestra hoja de estilo personalizada, la podemos escribir en LESS o CSS.

Si se quiere modificar algo que ya existe en Bootstrap, la mejor opción es copiarlo y añadir la modificación en nuestra hoja de estilo personalizada.

Eliminando los componentes innecesarios, utilizar el personalizador de Bootstrap, que permite crear una versión personalizada de Bootstrap que incluye solamente los componentes que se necesita.

#### ¿Cuál sería el resultado de aplicar las clases `col-xs-6 col-sm-4 col-lg-12` a un `div`?
Resolución XS: toma 6 columnas
Resolución SM: toma 4 columnas
Resolución LG: toma 12 columnas

## Git y Github

#### ¿Qué son las ramas en Git y para que se pueden utilizar?
La rama master es la rama "por defecto" cuando creas un repositorio.

Una rama es una extensión de la rama master.

Como buena práctica dentro de las ramas es donde deberíamos introducir los cambios a nuestro proyecto y solo luego de comprobar que dichos cambios funcionan y tienen el comportamiento deseado los unimos con la rama master.

#### ¿Cuál es la diferencia entre `git merge` y `git rebase`?
`git merge` solves the same problem as `git rebase`. 

Both of these commands are designed to integrate changes from one branch into another branch — they just do it in very different ways.

![alt](https://wac-cdn-a.atlassian.com/dam/jcr:e229fef6-2c2f-4a4f-b270-e1e1baa94055/02.svg?cdnVersion=em)
![alt](https://wac-cdn-a.atlassian.com/dam/jcr:5b153a22-38be-40d0-aec8-5f2fffc771e5/03.svg?cdnVersion=em)

El rebase unifica las ramas perdiendo el historial de los commit y el merge no. Esto puede resultar bien importante cuando se necesite llevar o saber el historial de commit y se esta trabajando con otros compañeros en esa rama.

#### ¿Qué es un Pull Request en Github? ¿Para qué se utiliza?
Un pull request es una petición que el propietario de un fork de un repositorio hace al propietario del repositorio original para que este último incorpore los commits que están en el fork.

#### ¿Cuál es la diferencia entre `git pull` y `git fetch`?
El comando `git fetch [remote-name]` sólo recupera la información y la pone en tu repositorio local —no la une automáticamente con tu trabajo ni modifica aquello en lo que estás trabajando.

Al ejecutar `git pull`, por lo general se recupera la información del servidor del que clonaste, y automáticamente se intenta unir con el código con el que estás trabajando actualmente.

git fetch = descarga nuevo contenido
git pull = git fetch + merge

#### En el comando `git push -u origin mi-rama` ¿qué significa la opción -u?
Pushes "mi-rama" branch to "origin" remote and sets up tracking

“Tracking” is essentially a link between a local and remote branch. When working on a local branch that tracks some other branch, you can git pull and git push without any extra arguments and git will know what to do.

An upstream is simply another branch name, usually a remote-tracking branch, associated with a (regular, local) branch.

Which will both create the remote branch with the same name and track it.

https://git-scm.com/docs/git-push

#### En Github ¿qué significan un fork y para qué se utiliza?
Hacerle fork a un repositorio significa copiarlo.

Por lo general, las copias se utilizan para proponer cambios en el proyecto de otra persona u organización ó para utilizar el proyecto de otra persona como punto de partida para nuevas ideas.

## JavaScript

#### ¿Cuál es la diferencia entre `==` y `===`?
`==` compara valor, mientras que `===` compara también tipo.

`===` operador de comparación estricta. Esto significa que si los operandos tienen tipos diferentes, no son iguales. Por ejemplo,

1 === "1" // false
null === undefined // false

1 == "1" // true
null == undefined // true

#### ¿Qué es un callback? ¿Por qué se necesitan en JavaScript?
Una funcion que se pasa como argumento y es invocada en el futuro.

Because functions are first-class objects (higher-order function), we can pass a function as an argument in another function and later execute that passed-in function or even return it to be executed later. 

Callback functions are probably the most widely used functional programming technique in JavaScript. A callback is a function to be executed after another function is executed. 

```
//Note that the item in the click method's parameter is a function, not a variable.​
​//The item is a callback function
$("#btn_1").click(function() {
  alert("Btn 1 Clicked");
});
```
We pass a function as a parameter to the click method. And the click method will call (or execute) the callback function we passed to it.

Your callback functions define the order that different actions occur.

#### ¿Qué es un closure?
A closure is an inner function that has access to the outer (enclosing) function’s variables—scope chain. The closure has three scope chains: it has access to its own scope (variables defined between its curly brackets), it has access to the outer function’s variables, and it has access to the global variables.

```
function showName (firstName, lastName) {
  ​var nameIntro = "Your name is ";
      // this inner function has access to the outer function's variables, including the parameter​
  ​function makeFullName () {       
  ​ return nameIntro + firstName + " " + lastName; 
  }
  ​
  ​return makeFullName ();
}
​
showName ("Michael", "Jackson"); // Your name is Michael Jackson
```

The power of closures is derived from the fact that the inner function remembers the environment in which it was created. In other words, the inner function has access to the outer function’s variables and parameters.

Closures are capable of not only reading, but also manipulating the variables of their outer functions.

One powerful use of closures is to use the outer function as a factory for creating functions that are somehow related.

Many object-oriented languages provide the ability to declare methods as either public or private. JavaScript doesn’t have this functionality built in, but it does allow to emulate this functionality through the use of closures, which is known as the module pattern.

#### ¿Qué significa que JavaScript sea un lenguaje prototipado?
A prototype-based language, does not make the distinction of classes vs objects: it simply has objects. A prototype-based language has the notion of a prototypical object, an object used as a template from which to get the initial properties for a new object. 

An object in JavaScript is any unordered collection of key-value pairs. If it’s not a primitive (undefined, null, boolean, number or string) it’s an object.

A prototype is an object from which other objects inherit properties

#### ¿Qué es una función inmediata? ¿Cuál es su sintaxis?
Immediate functions execute as soon as JavaScript encounters them. Immediate functions are useful for initialization tasks that are needed only once.

```
(function(){
    console.log('hello, I am an immediate function');
}())
```

#### ¿A qué se refiere `this` en JavaScript? ¿Qué problemas puede ocasionar?
In JavaScript, we use the `this` keyword as a shortcut, a referent; it refers to an object; that is, the subject in context, or the subject of the executing code.

```
var person = {
	    firstName: "Penelope",
	    lastName: "Barrymore",
	    fullName: function () {
	        console.log(this.firstName + " " + this.lastName);
	    ​// We could have also written this:​​
	        console.log(person.firstName + " " + person.lastName);
	    }
	}

person.showFullName (); // Penelope Barrymore
```

#### ¿Qué es programación funcional? ¿Es JavaScript un lenguaje funcional?
Functional Programming is a style of writing programs by simply composing a set of functions.

Essentially, FP asks us to wrap virtually everything in functions, write lots of small reusable functions and simply call them one after the other to get the result like: (func1.func2.func3) or in a compose fashion, like: func1(func2(func3())).

JavaScript is an object-oriented language first and foremost. That is not to say that you can't write JavaScript programs in a functional style, since you can adopt a functional style.

#### ¿Cómo podemos agregarle un método a todos los arreglos en JavaScript?
The Array.prototype property represents the prototype for the Array constructor and allows you to add new properties and methods to all Array objects. 

```
// If JavaScript doesn't provide a first() method natively,
// add a new method returning the first element of an array.

if (!Array.prototype.first) {
  Array.prototype.first = function() {
    return this[0];
  }
}
```

#### Nombra al menos 3 nuevas características de ES2015.
1. Support for constants (also known as "immutable variables"), i.e., variables which cannot be re-assigned new content. 
2. Arrow Functions 
```
  odds  = evens.map(v => v + 1) (new ECMAScript 6) 
  odds  = evens.map(function (v) { return v + 1; }); (ECMAScript 5)
```
3. Default Parameter Values
```
  function f (x, y = 7, z = 42) { return x + y + z } (new ECMAScript 6) 
  function f (x, y, z) { if (y === undefined) y = 7; if (z === undefined) z = 42; return x + y + z; }; (ECMAScript 5)
```
4. String Interpolation
```
  var customer = { name: "Foo" } 
  var card = { amount: 7, product: "Bar", unitprice: 42 } 
  var message = 'Hello ${customer.name},want to buy ${card.amount} ${card.product} for a total of ${card.amount * card.unitprice} bucks?'
```
#### ¿Para qué se utiliza el método `bind` de las funciones?
https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_objects/Function/bind

#### ¿Cómo puedo recibir un número variable de argumentos en una función? Escribe un ejemplo que lo ejemplifique.
The `arguments` object is an Array-like object corresponding to the arguments passed to a function.

```
x = sumAll(1, 123, 500, 115, 44, 88);

function sumAll() {
    var i, sum = 0;
    for (i = 0; i < arguments.length; i++) {
        sum += arguments[i];
    }
    return sum;
}
```

#### ¿Qué es TDD (Test Driven Development)?
It is a software development process that relies on the repetition of a very short development cycle: first the developer writes an (initially failing) automated test case that defines a desired improvement or new function, then produces the minimum amount of code to pass that test, and finally refactors the new code to acceptable standards.

#### ¿Qué son las Promesas en JavaScript y para qué se utilizan?
A promise is an object that may produce a single value some time in the future: either a resolved value, or a reason that it’s not resolved (e.g., a network error occurred). 

A promise can be in one of 3 states:

+ Pending - the promise’s outcome hasn’t yet been determined, because the asynchronous operation that will produce its result hasn’t completed yet.
+ Fulfilled - the asynchronous operation has completed, and the promise has a value.
+ Rejected - the asynchronous operation failed, and the promise will never be fulfilled. In the rejected state, a promise has a reason that indicates why the operation failed.

Promise users can attach callbacks to handle the fulfilled value or the reason for rejection.

Promises provide a simpler alternative for executing, composing, and managing asynchronous operations when compared to traditional callback-based approaches. 

The best way to handle asynchronous behavior.

## API del navegador, jQuery y AJAX

#### ¿Qué es el DOM (Document Object Model)? ¿Cómo lo podemos manipular?
The Document Object Model (DOM) is a programming interface for HTML and XML documents. It provides a structured representation of the document and it defines a way that the structure can be accessed from programs so that they can change the document structure, style and content. The DOM provides a representation of the document as a structured group of nodes and objects that have properties and methods. Essentially, it connects web pages to scripts or programming languages.

EL DOM (Document Object Model) es una representación de un documento HTML que nos permite interactuar con los elementos (etiquetas) del documento HTML. La estructura es en forma de árbol similar a como se organizan los directorios y archivos en un sistema operativo. 

#### ¿Por qué surgió jQuery?
jQuery se encarga de las diferencias de los navegadores exponiendo una interfaz clara y fácil de usar que le permite a los desarrolladores concentrarse en la funcionalidad de la aplicación, y no en los detalles de cada navegador.

#### ¿Qué es una cookie? ¿Qué es el local storage? ¿Cuál es la diferencia entre los dos?
Tanto localStorage, como las cookies, son soluciones que sirven para guardar información en el cliente, pero cada una tiene sus particularidades.

- Cookies are data, stored in small text files, on your computer. When a web server has sent a web page to a browser, the connection is shut down, and the server forgets everything about the user. Cookies were invented to solve the problem "how to remember information about the user". When a browser requests a web page from a server, cookies belonging to the page is added to the request. This way the server gets the necessary data to "remember" information about users.

A cookie is nothing but a small text file that's stored in your browser. It contains some data:

1. A name-value pair containing the actual data
2. An expiry date after which it is no longer valid
3. The domain and path of the server it should be sent to

- The localStorage object stores the data with no expiration date. The data will not be deleted when the browser is closed, and will be available the next day, week, or year.

In terms of capabilities, cookies only allow you to store strings. Local storage allow you to store JavaScript primitives but not Objects or Arrays.

Local storage data is not sent to the server on every request (HTTP header) as it is purely at the client side. All data is transferred to and from server, so bandwidth is consumed on every request 

#### ¿Qué es AJAX?
AJAX es una técnica para intercambiar información con servidores remotos sin necesidad de refrescar la página.

#### Necesitamos hacer un `POST` a `/products` con la siguiente información en JSON: `{ "name": "Pan", "quantity": 4, price: 12000 }`. La respuesta también es JSON ¿Cuál sería la sintaxis para hacerlo? Puedes hacerlo con jQuery o JavaScript puro.
```
$.ajax({
  type: "POST",
  url: /products,
  data: { "name": "Pan", "quantity": 4, price: 12000 },
  success: function(data){
        alert(data);
  },
  failure: function(errMsg) {
        alert(errMsg);
  },
  dataType: json
});
```

```
var xhr = new XMLHttpRequest();
var url = "/products";
xhr.open("POST", url, true);
xhr.setRequestHeader("Content-type", "application/json");
xhr.onreadystatechange = function () {
    if (xhr.readyState === 4 && xhr.status === 200) {
        var json = JSON.parse(xhr.responseText);
        alert(json);;
    }
};
var data = JSON.stringify({ "name": "Pan", "quantity": 4, price: 12000 });
xhr.send(data);
```

#### ¿Qué es CORS (Cross-Origin Resource Sharing)?

The `same-origin policy` restricts how a document or script loaded from one origin can interact with a resource from another origin. It is a critical security mechanism for isolating potentially malicious documents.

Una especificacion para sobrepasar el `same-origin policy`. Utilizando unos headers el servidor puede permitir el acceso a otro sevidor

#### ¿Qué son Web Sockets? ¿Para qué se utilizan?

WebSockets hacen posible tener comunicación interactiva y bidireccional entre el navegador del usuario y el servidor. Con WebSockets solo necesitas crear la conexión una vez. Por eso es llamada una conexión persistente. Una vez que te has conectado a un web socket puedes enviar datos en ambas direcciones de manera rápida y eficiente. 

#### Nombra tres casos para los que puedes utilizar las herramientas del desarrollador (developer tools) del navegador?

1. Experimentar con el DOM
2. Ejecutar código Javascript
3. Análisis de peticiones HTTP

#### ¿Qué es Handlebars y para qué se utiliza?

Handlebars is a template processor that dynamically generates your HTML page.

There are two primary reasons why you'd want to make a template for your site:

First of all, building a template encourages you to separate the logic-based code from the actual view, helping you adhere to a View/Controller pattern. 

Secondly, templates keep your code clean and maintainable, which, in turn, makes the process of updating your site a breeze. 

You don't create a site with Handlebars. Instead, you create guidelines and structures that dictate how the site should look without focusing on a page's data.

#### ¿Para qué se utiliza `"use strict";`?

The purpose of "use strict" is to indicate that the code should be executed in "strict mode".
With strict mode, you can not, for example, use undeclared variables.

Strict mode makes it easier to write "secure" JavaScript.

Strict mode changes previously accepted "bad syntax" into real errors.
