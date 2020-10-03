# FrontEnd  MVC  Tarea

## INTRODUCCIÓN 

Modelo vista controlador(MVC), es un estilo de arquitectura que separa los datos de una aplicación, la interfaz de usuario y la logica de control en tres componentes distintos.

El Modelo que contiene una representación de los datos que maneja el sistema, su lógica de negocio, y sus mecanismos de persistencia.

La Vista, o interfaz de usuario, que compone la información que se envía al cliente y los mecanismos interacción con éste.

El Controlador, que actúa como intermediario entre el Modelo y la Vista, gestionando el flujo de información entre ellos y las transformaciones para adaptar los datos a las necesidades de cada uno.

## MARCO TEÓRICO

### ¿Que frameworks utiliza el modelo MVC?

Un framework de aplicaciones web es un tipo de framework que permite el desarrollo de sitios web dinámicos, web services (servicios web) y aplicaciones web. El propósito de este tipo de framework es permitir a los desarrolladores construir aplicaciones web y centrarse en los aspectos interesantes, aliviando la típica tarea repetitiva asociada con patrones comunes de desarrollo web. 

**Struts**

Struts es un framework de aplicación web open source desarrollado por Apache. Struts está basado en el patrón MVC. Se utiliza para construir aplicaciones Web basadas en Servlets y JSP que pueden ejecutarse en cualquier contenedor de servlets incluyendo los servidores de aplicaciones J2EE.  

**Spring**

Spring es un framework open source que proporciona un marco de trabajo para el desarrollo de aplicaciones J2EE. El framework está basado en el uso de ficheros planos JavaBeans para la lógica de aplicación y archivos XML para la configuración.

**Ruby on Rails**

Ruby on Rails, también conocido como RoR o Rails, es un framework de aplicaciones web de código abierto escrito en el lenguaje de programación Ruby, siguiendo el paradigma del patrón Modelo Vista Controlador (MVC). Trata de combinar la simplicidad con la posibilidad de desarrollar aplicaciones del mundo real escribiendo menos código que con otros frameworks y con un mínimo de configuración.

**CodeIgniter**

CodeIgniter es un framework para el desarrollo de aplicaciones en php, que utiliza el MVC. Esto permite a los programadores o desarrolladores Web mejorar su forma de trabajar, además de dar una mayor velocidad a la hora de crear páginas Webs.

**Kohana**

Kohana es un framework para aplicaciones web para PHP5 que implementa el patrón de Modelo Vista Controlador Jerárquico (HMVC). Sus principales objetivos se basan en ser seguro, ligero, y fácil de utilizar.

**Django**
            
Django es un framework de desarrollo web de código abierto, escrito en Python, que respeta el patrón de diseño conocido como MVC (Modelo–Vista–Controlador).
        
**CakePHP**

CakePHP es un framework o marco de trabajo que "facilita" el desarrollo de aplicaciones web, utilizando el patrón de diseño MVC (Modelo Vista Controlador). Es de código abierto y se distribuye bajo licencia MIT. Al igual que Ruby On Rails, CakePHP facilita al usuario la interacción con la base de datos mediante el uso de Active record.
        
**Zend Framework**

Zend Framework (ZF) es un framework de código abierto para desarrollar aplicaciones web y con servicios web PHP 5. ZF es una implementación que usa código 100% orientado a objetos. En la estructura de los componentes de ZF cada componente está construido con una baja dependencia de otros componentes. Esta arquitectura débilmente acoplada permite a los desarrolladores utilizar los componentes por separado. 

**Yii**

Yii es un framework orientado a objetos, software libre, de alto rendimiento1​2​3​ basado en componentes, PHP y framework para aplicaciones web. 

**Symfony**

Symfony es un framework diseñado para desarrollar aplicaciones web basado en el patrón Modelo Vista Controlador. Para empezar, separa la lógica de negocio, la lógica de servidor y la presentación de la aplicación web. Proporciona varias herramientas y clases encaminadas a reducir el tiempo de desarrollo de una aplicación web compleja.  

### ¿Qué ventajas ofrece el modelo MVC?

*Estas son lgunas de las ventajas que nos ofrece el desarrollo MVC.

*Separación clara de dónde tiene que ir cada tipo de lógica, facilitando el mantenimiento y la escalabilidad de nuestra aplicación.

*Sencillez para crear distintas representaciones de los mismos datos.

*Facilidad para la realización de pruebas unitarias de los componentes, así como de aplicar desarrollo guiado por pruebas (Test Driven Development o TDD).

*Reutilización de los componentes.

*No existe ciclo de vida de las páginas. Con menos peso, menos complejidad.

*Motor de Routing asociando una URL concreta con su correspondiente controlador, permitiendo URL semánticas. Las URL semánticas se indexan mejor en los buscadores, siendo más adecuadas para el posicionamiento web.

*Recomendable para el diseño de aplicaciones web compatibles con grandes equipos de desarrolladores y diseñadores web que necesitan gran control sobre el comportamiento de la aplicación.
        
### ¿Que otros modelos/frameworks existen de patrones de diseño?

Los patrones de diseño son el esqueleto de las soluciones a problemas comunes en el desarrollo de software.

Brindan una solución ya probada y documentada a problemas de desarrollo de software que están sujetos a contextos similares. Debemos tener presente los siguientes elementos de un patrón: su nombre, el problema (cuando aplicar un patrón), la solución (descripción abstracta del problema) y las consecuencias (costos y beneficios).

#### **Patrones Creacionales**

Como su nombre indica, estos patrones vienen a solucionar o facilitar las tareas de creación o instanciación de objetos.
Estos patrones hacen hincapié en la encapsulación de la lógica de la instanciación, ocultando los detalles concretos de cada objeto y permitiéndonos trabajar con abstracciones.
        
* **Factory**: Desacoplar la lógica de creación de la lógica de negocio, evitando al cliente conocer detalles de la instanciación de los objetos de los que depende.
            
* **Abstract Factory**: Nos provee una interfaz que delega la creación de una serie de objetos relacionados sin necesidad de especificar cuáles son las implementaciones concretas.
            
* **Factory Method**: Expone un método de creación, delegando en las subclases la implementación de este método.
            
* **Builder**: Separa la creación de un objeto complejo de su estructura, de tal forma que el mismo proceso de construcción nos puede servir para crear representaciones diferentes.
        
#### **Patrones estructurales**
        
Los patrones estructurales nos ayudan a definir la forma en la que los objetos se componen.

Los patrones estructurales más habituales son:
            
* **Adapter**: Nos ayuda a definir una clase intermedia que sirve para que dos clases con diferentes interfaces puedan comunicarse. Esta clase actúa como mediador, haciendo que la clase A pueda ejecutar métodos de la clase B sin conocer detalles de su implementación. También se conoce como Wrapper.
            
* **Decorator**: Permite añadir funcionalidad extra a un objeto (decora el objeto) sin modificar el comportamiento del resto de instancias.
            
* **Facade**: Una fachada es un objeto que crea una interfaz simplificada para tratar con otra parte del código más compleja.

#### **Patrones comportamentales**

Los patrones comportamentales nos ayudan a definir la forma en la que los objetos interactúan entre ellos.
            
Algunos de los más conocidos (por citar unos pocos) son:

* **Command**: Son objetos que encapsulan una acción y los parámetros que necesitan para ejecutarse.
            
* **Observer**: Los objetos son capaces de suscribirse a una serie de eventos que otro objeto va a emitir, y serán avisados cuando esto ocurra.

* **Strategy**: Permite la selección del algoritmo que ejecuta cierta acción en tiempo de ejecución.

* **Template Method**: Especifica el esqueleto de un algoritmo, permitiendo a las subclases definir cómo implementan el comportamiento real. 

## Ejemplos

#### **index.html**

```
<!DOCTYPE html>
<html ng-app>

  <head>
    <script data-require="angular.js@1.2.0-rc3-nonmin" data-semver="1.2.0-rc3-nonmin" src="http://code.angularjs.org/1.2.0-rc.3/angular.js"></script>
    <link rel="stylesheet" href="style.css" />
    <script src="script.js"></script>
  </head>

  <body ng-controller="controll">
    <h1>Angular</h1>
    
    <div class="msj">
      <h3>Mensaje:</h3>
      {{msj}}
      <hr />
      <input ng-model="msj" /> 
      <br />
      <button ng-click="obtenerMsj()">Generar Mensaje</button>
    </div>
  </body>

</html>
```
#### **script.js**

```
function controll($scope) {
  $scope.msj = 'escriba';
  
  $scope.obtenerMsj = function() {
    $scope.msj = Math.random();
  }
}
```