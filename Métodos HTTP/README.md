# Métodos HTTP

## INTRODUCCIÓN

HTTP contiene un grupo de peticiones HTTP (también llamadas HTTP verbs por, el tipo de nombre que manejan casi todos ellos 
pues si bien algunos son sustantivos, la gran mayoría no), que nos ayudan a especificar la acción que se requiere realizar
en un elemento determinado y aunque estas peticiones tienen distintas semánticas, también tienen muchas similitudes en las
mismas que evitan que este grupo se extienda demasiado.


## MARCO TEÓRICO

**GET**
Se usa para obtener información del servidor, puede ser algún archivo HTML, una imagen, un archivo de texto, un XML, etc.
Este método solo debe usarse para obtener información del servidor de acuerdo a los estándares de HTTP. El método GET no
debe cambiar el estado del servidor, es decir, no debe hacer ninguna modificación a cualquier archivo que en éste se encuentre.
En términos de CRUD, GET sería el Read (Leer).

**HEAD**
Se usa para obtener la cabecera de respuesta que devuelve el servidor al hacer una petición sobre éste. Similar a GET, estos dos
no cambian el estado del servidor, aunque HEAD solo devuelve los metadatos. Se puede usar para saber si cierto recurso está
en el servidor.

**POST**
Se podría decir que es el método HTTP más empleado, eso en parte a que permite hacer variedad de operaciones del CRUD, aunque
por estándar, es el encargado de crear un nuevo recurso y, por consiguiente, modificar el estado del servidor. En términos de
CRUD, el método POST se confunde en ocasiones con el método PUT, aunque la diferencia radica en una cualidad que se llama idempotencia.

La idempotencia se trata de la capacidad que tenga un ente (este caso el método) de realizar una misma operación varias veces,
y obtener el mismo resultado que si solo se hiciese una vez.

Despues de entender en que consiste la idempotencia se dice que el método POST no es idempotente, en cambio el método PUT si lo es.

**PATCH**
Aplica modificaciones parciales a un recurso.

A diferencia de PUT, el método PATCH no es idempotente, esto quiere decir que peticiones identicas sucesivas pueden tener
efectos diferentes. Sin embargo,  es posible emitir peticiones PATCH de tal forma que sean idempotentes.

Para averiguar si un servidor soporta PATCH, el servidor puede notificar su compatibilidad al añadirlo a la lista en el header:
Allow o Access-Control-Allow-Methods (para CORS).

Otra indicación (implícita) de que las peticiones PATCH son permitidas, es la presencia del header: Accept-Patch, el cual especifica
los formatos de documento patch aceptados por el servidor. 
 
**PUT**
El método PUT es usado para solicitar que el servidor almacene el cuerpo de la entidad en una ubicación específica dada por el URL.
Crea un nuevo elemento o reemplaza una representación del elemento de destino con los datos de la petición.

La diferencia entre el método PUT y el método POST es que PUT es un método idempotente: llamarlo una o más veces de forma sucesiva
tiene el mismo efecto, mientras que una sucesión de peticiones POST idénticas pueden tener efectos adicionales,
como envíar una orden varias veces.

**DELETE**
Este método es utilizado para solicitar al servidor que elimine un archivo en una ubicación específica dada por la URL.

El servicio de integración de datos utiliza el método HTTP Delete para eliminar los datos a través de un servicio web REST.

Cuando configure la transformación de consumidor de servicio web REST para utilizar el método Delete, debe configurar los
puertos de entrada, la entrada del método, la salida del método y los puertos de salida.

**OPTIONS**

Representa una solicitud de información acerca de las opciones de comunicación disponibles en el canal de solicitud/respuesta
identificada por el Request-URI. En otras palabras, éste método es el que utilizamos para describir las opciones de comunicación
existentes de un recurso destino.

Options se usa para saber que otros métodos HTTP están disponibles, para determinado recurso, en el servidor. Por ejemplo,
para saber si alguna imagen acepta los métodos GET o POST, haces la petición REST sobre ese recurso y en la cabecera de respuesta,
obtendrás la respuesta Allow con los métodos que pueden usarse sobre dicho recurso.

### Ejemplo Método GET

**PETICIÓN**
```
GET /index.html HTTP/1.1  
User-Agent: Mozilla/4.0 (compatible; MSIE5.01; Windows NT)
Host: www.yosoy.dev
Accept-Language: es-mx
Accept-Encoding: gzip, deflate
Connection: Keep-Alive
```

**RESPUESTA**
```
Ejemplo respuesta del servidor:
HTTP/1.1 200 OK
Date: Wed, 08 Nov 2017 12:28:53 GMT
Server: Apache/2.2.14 (Win32)
Last-Modified: Mon, 22 Jul 2014 19:15:56 GMT
ETag: "34aa387-d-1568eb00"
Vary: Authorization,Accept
Accept-Ranges: bytes
Content-Length: 88
Content-Type: text/html
Connection: Closed
```

### Ejemplo Método HEAD

**PETICIÓN**
```
HEAD /index.html HTTP/1.1  
User-Agent: Mozilla/4.0 (compatible; MSIE5.01; Windows NT)
Host: www.yosoy.dev
Accept-Language: es-mx
Accept-Encoding: gzip, deflate
Connection: Keep-Alive
```

**RESPUESTA**
```
HTTP/1.1 200 OK
Date: Mon, 27 Jul 2009 12:28:53 GMT
Server: Apache/2.2.14 (Win32)
Last-Modified: Wed, 22 Jul 2009 19:15:56 GMT
ETag: "34aa387-d-1568eb00"
Vary: Authorization,Accept
Accept-Ranges: bytes
Content-Length: 88
Content-Type: text/html
Connection: Closed
```

### Ejemplo Método POST
```
POST /cgi-bin/process.cgi HTTP/1.1
User-Agent: Mozilla/4.0 (compatible; MSIE5.01; Windows NT)
Host: www.yosoy.dev
Content-Type: text/xml; charset=utf-8
Content-Length: 88
Accept-Language: es-mx
Accept-Encoding: gzip, deflate
Connection: Keep-Alive
```
### Ejemplo Método PUT

**PETICIÓN**
```
PUT /index.htm HTTP/1.1
User-Agent: Mozilla/4.0 (compatible; MSIE5.01; Windows NT)
Host: www.yosoy.dev
Accept-Language: es-mx
Connection: Keep-Alive
Content-type: text/html
Content-Length: 182
```
**RESPUESTA**
```
HTTP/1.1 201 Created
Date: Mon, 27 Nov 2017 12:28:53 GMT
Server: Apache/2.2.14 (Win32)
Content-type: text/html
Content-length: 30
Connection: Closed
```
### Ejemplo Método DELETE

**PETICIÓN**
```
DELETE /hello.htm HTTP/1.1
User-Agent: Mozilla/4.0 (compatible; MSIE5.01; Windows NT)
Host: www.yosoy.dev
Accept-Language: es-mx
Connection: Keep-Alive
```
**RESPUESTA**
```
HTTP/1.1 200 OK
Date: Mon, 27 Jul 2009 12:28:53 GMT
Server: Apache/2.2.14 (Win32)
Content-type: text/html
Content-length: 30
Connection: Closed
 
<html>
<body>
<h1>URL deleted.</h1>
</body>
```
#### Ejemplo Método OPTIONS

**PETICIÓN**
```
curl -X OPTIONS https://yosoy.dev -i
```

**RESPUESTA** 
```
HTTP/1.1 200 OK
Date: Wed, 8 Nov 2017 12:28:53 GMT
Server: Apache/2.2.14 (Win32)
Allow: GET,HEAD,POST,OPTIONS,TRACE
Content-Type: httpd/unix-directory
```


### TIPOS DE MENSAJE DE LAS PETICIONES HTTP.

Un código de estado HTTP es un mensaje que devuelve el servidor cada vez que el navegador realiza una petición al servidor.
Si el servidor es capaz de devolver el contenido que solicita el navegador y no existe ningún error, estos códigos HTTP no son
visibles para el usuario. En cambio, si algo va mal, verás que el servidor devuelve un código de estado HTTP que indica que algo
no salió como esperaba.

En función del código de estado que devuelve el servidor, podremos hacernos una idea del tipo de error que se ha producido.
Es por ello que decimos que cuando tienes una página web es muy importante que conozcas los tipos de código HTTP para que
puedas ver a qué se debe el error y solucionarlo rápidamente.

**Códigos de estado 1xx**: Se trata de respuestas de carácter informativo e indica que el navegador puede continuar realizando su petición.

**Códigos de estado 2xx**: El conjunto de códigos 2xx son respuestas satisfactorias, Simplemente indican que la petición fue procesada
correctamente, por lo que lo ideal es que todas las webs devuelvan este código HTTP. Generalmente como la petición fue exitosa no
se muestra el código de estado, el navegador únicamente devuelve el contenido que el usuario solicitó.

**Códigos de estado 3xx**: Estos códigos HTTP hacen referencia a cuando el navegador tiene que realizar una acción adicional como,
por ejemplo, una redirección.

**Códigos de estado 4xx**: Los códigos de estado que comienzan con el dígito 4 hacen referencia a errores producidos por el navegador web.
En estos casos, el usuario normalmente recibe una página en HTML en la que es informado del error.

**Códigos de estado 5xx**: Estos códigos HTTP también muestran errores, pero por el lado del servidor web.

### Ejemplo de los Tipos de Mensaje

#### **Códigos de estado 1xx**

* **Código 100** – Coninue: Este código de estado notifica que el servidor ha recibido la primera petición y está esperando recibir más instrucciones del navegador.
* **Código 101** – Switching Protocols: Se utiliza cuando el servidor acepta un cambio propuesto por el navegador. Por ejemplo, un cambio de HTTP 1.0 a HTTP 1.1.
* **Código 102** – Processing: El servidor ha recibido la petición pero no la ha completado. Esto evita que el navegador interprete que la petición se ha perdido, sino que todavía no ha finalizado.
* **Código 103** – Checkpoint: Se utiliza para reanudar una petición que previamente fue perdida o cancelada.

#### **Códigos de estado 2xx**

* **Código 200** – OK: Se utiliza cuando la petición fue completada de manera exitosa. Como este código indica que “todo está bien” no suele mostrarse al usuario final.
* **Código 201** – Created: La petición del navegador se ha completado correctamente y se ha creado un nuevo recurso.
* **Código 203** – Non-Authoritative Information: La petición del navegador se ha completado correctamente, pero el contenido corresponde a un servidor diferente al que
se ha realizado la petición.
* **Código 204** – No Content: La petición del navegador se ha completado correctamente, pero la respuesta no muestra ningún tipo de contenido.
* **Código 205** – Reset Content: Se utiliza cuando la petición del usuario se completa, pero es necesario volver a cargar la página. Es muy habitual cuando se envían
datos a través de un formulario de contacto y se recarga la página.

#### **Códigos de estado 3xx**

* **Código 300** – Multiple Choices: Ante una solicitud, existe más de una opción para acceder al mismo recurso.
* **Código 301** – Moved Permanently: El recurso solicitado ha sido movido de manera permanente y el navegador es redirigido automáticamente a esa nueva ubicación.
Las redirecciones 301 son una buena opción para que Google nos penalice si tenemos demasiados errores 404 en nuestra web.
* **Código 302** – Moved Temporarily: El recurso solicitado ha sido movido de manera temporal y el navegador es redirigido automáticamente a esa nueva ubicación.
* **Código 303** – See Other: Este código indica que el recurso solicita ha sido movido, pero no se realiza una redirección.
* **Código 304** – Not Modified: Si el navegador pregunta al servidor si el recurso que solicita ha sido movido desde la última visita, y este no ha sido cambiado.
* **Código 305** – Use Proxy: Este código HTTP se utiliza cuando el recurso solicitado debe obtenerse a través de un proxy Location situado en la cabecera.

#### **Códigos de estado 4xx**

* **Código 400** – Bad Request: El servidor no entiende la petición del navegador porque su sintaxis no es correcta.
* **Código 401** – Unauthorized: La petición que realiza el navegador precisa autenticación.
* **Código 402** – Payment Required: Es un código HTTP reservado para futuros usos.
* **Código 403** – Forbidden: La petición que realiza el navegador es correcta, pero se ha denegado el acceso al recurso solicitado.
* **Código 404** -Not Found: El recurso que solicita el navegador no se encuentra o no está disponible en el servidor. No es posible detectar si esta ausencia es
temporal o permanente.
* **Código 405** – Method Not Allowed: El navegador utiliza un método para obtener el recurso que no es aceptado por el servidor.

#### **Códigos de estado 5xx**

* **Código 500** – Internal Server Error: No se puede completar la petición realizada por el navegador ya que se ha producido un error inesperado en el navegador.
* **Código 501** – Not implemented: El servidor no soporta alguna funcionalidad necesaria para responder a la solicitud que realiza el navegador.
* **Código 502** – Bad Gateway: El servidor no puede responder con la petición del navegador ya que este servidor está actuando como proxy o gateway,
o tiene instalado un proxy inverso y ha recibido una respuesta no válida desde dicho servidor.
* **Código 503** – Service Unavailable: El servidor no puede responder a la petición del navegador porque está saturado o se están realizando tareas de
mantenimiento en el mismo.
* **Código 504** – Gateway Timeout: El servidor no puede responder con la petición del navegador ya que este servidor está actuando como proxy o gateway,
o tiene instalado un proxy inverso y se ha agotado el tiempo de respuesta de dicho servidor.
* **Código 505** – HTTP Version Not Supported: El servidor no es compatible con la versión del protocolo HTTP utilizada en la petición del navegador.


