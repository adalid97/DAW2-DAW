<!---
Ejemplos de inserciÃ³n de videos

<video class="stretch" controls><source src="http://clips.vorwaerts-gmbh.de/big_buck_bunny.mp4" type="video/mp4"></video>
<iframe width="560" height="315" src="https://www.youtube.com/embed/3RBq-WlL4cU" frameborder="0" allowfullscreen></iframe>

slide: data-background="#ff0000" 
element: class="fragment" data-fragment-index="1"
-->

## Despliegue de aplicaciones web
---
![Despliegue de aplicaciones web](http://jamj2000.github.io/despliegueaplicacionesweb/despliegueaplicacionesweb.png)
<small> 2018-19 - IES Luis VÃ©lez de Guevara - Ã‰cija - Spain </small>


## Arquitecturas web

[![cc-by-sa](http://jamj2000.github.io/despliegueaplicacionesweb/cc-by-sa.png)](http://creativecommons.org/licenses/by-sa/4.0/)


## Ãndice
--- 
- ### IntroducciÃ³n
- ### El protocolo HTTP
- ### Arquitecturas web
- ### Plataformas web
- ### Despliegue en Internet

<!--- Note: Nota a pie de pÃ¡gina. -->



## IntroducciÃ³n


### En esta Unidad aprenderemos a

- Valorar los fundamentos y protocolos en los que se basa el funcionamiento de un servidor Web.
- Clasificar y describir los principales servidores de aplicaciones.
- Instalar y configurar de forma bÃ¡sica servidores Web.
- Realizar pruebas de funcionamiento de los servidores web.


### Â¿QuÃ© es Internet?

![Internet](assets/internet.png)


### Â¿QuÃ© es Internet?

- Un conjunto de **nodos** (equipos) conectados en forma de malla parcial.
- Un conjunto de **protocolos** para comunicar dichos nodos.
- Cada protocolo permite ofrecer un **servicio** o parte de Ã©l.
- DiseÃ±o inicial **cliente/servidor**. 


### Protocolos de Internet

- **HTTP** (World Wide Web)
- **FTP** (Transferencia de archivos)
- **DNS** (ResoluciÃ³n de nombres)
- **SMTP**, **POP**, **IMAP** (Correo elÃ©ctrÃ³nico)
- **RIP**, **OSPF**, **BGP** (Enrutamiento de paquetes)
- **Telnet**, **SSH** (ConexiÃ³n remota por terminal)
- **VNC**, **RDP** (ConexiÃ³n remota grÃ¡fica)
- ... muchos mÃ¡s


###  Localizador Uniforme de Recursos (URL)

- Identifica un recurso en Internet. La forma bÃ¡sica es:
  ```
  protocolo://servidor:puerto/ruta/recurso
  ```
- En algunos casos puede incluir parÃ¡metros, credenciales, etc. Ejemplos:
  ```
  http://192.168.1.1/directorio/archivo.html
  ftp://archivos.example.com/descargas/ubuntu.iso
  https://pepe:1234@musica.com:1443/rock/descargar.php?album=37&formato=mp3
  ```



## El protocolo HTTP


### CaracterÃ­sticas

- Permite el **servicio WWW**.
- Desarrollado por el World Wide Web Consortium y la Internet Engineering Task Force.
- El servidor atiende peticiones en el **puerto 80**.
- La versiÃ³n mÃ¡s usada actualmente es HTTP/1.1 ( RFC 2616 ).
- TambiÃ©n existe la versiÃ³n HTTP/2, todavÃ­a poco usada.
- Existe la versiÃ³n segura, que es HTTPS, en la que el servidor atiende en el **puerto 443**.  
- Es es protocolo sin estado: no guarda ninguna informaciÃ³n sobre conexiones anteriores.


### TransacciÃ³n HTTP

![TransacciÃ³n HTTP](assets/transaccion-http.png)


### Ejemplo de peticiÃ³n

```
GET /index.html HTTP/1.1
Host: www.example.com
```


### Ejemplo de respuesta

```
HTTP/1.1 200 OK
Date: Mon, 23 May 2005 22:38:34 GMT
Content-Type: text/html; charset=UTF-8
Content-Length: 138
Last-Modified: Wed, 08 Jan 2003 23:11:55 GMT
Server: Apache/1.3.3.7 (Unix) (Red-Hat/Linux)
Connection: close

<html>
<head>
  <title>An Example Page</title>
</head>
<body>
  Hello World, this is a very simple HTML document.
</body>
</html>
``` 


### MÃ©todos HTTP
#### MÃ©todos bÃ¡sicos

- **GET**
- **POST**
- **PUT**
- **DELETE**


### MÃ©todos HTTP
#### Otros mÃ©todos

- **HEAD**
- **OPTIONS**
- **CONNECT**
- **PATCH**
- **TRACE**

https://es.wikipedia.org/wiki/Protocolo_de_transferencia_de_hipertexto


### CÃ³digos de respuesta HTTP

- **1xx**: Mensajes.
- **2xx**: OperaciÃ³n exitosa.
- **3xx**: RedirecciÃ³n. 
- **4xx**: Errores del cliente.
- **5xx**: Errores del servidor.

[Lista de cÃ³digos de estado (en inglÃ©s)](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes)


### Cabeceras de la peticiÃ³n

 Cabecera       |     Ejemplo                   |  DescripciÃ³n 
----------------|-------------------------------|--------------
Accept	        | Accept: text/html	            | Tipos de contenido que se admiten como respuesta.
Accept-Charset	| Accept-Charset: utf-8	        | Juegos de caracteres admitidos.
Accept-Encoding	| Accept-Encoding: gzip, deflate| Lista de codificaciones (compresiÃ³n) admitidas.


### Cabeceras de la peticiÃ³n

 Cabecera       |     Ejemplo                   |  DescripciÃ³n 
----------------|-------------------------------|--------------
Accept-Language	| Accept-Language: en-US	    | Lista de idiomas admitidos como respuesta.
Host            | Host: en.wikipedia.org:8080   | Nombre de dominio del servidor (:puerto si es distinto de 80)
User-Agent      |User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:12.0) | Agente del usuario.
...             | ...                           | ...


### Cabeceras de la respuesta

 Cabecera       |     Ejemplo                   |  DescripciÃ³n 
----------------|-------------------------------|--------------
Content-Encoding| Content-Encoding: gzip        | CodificiaciÃ³n de los datos enviados.
Content-Language| Content-Language: es          | Idioma en el que estÃ¡ el contenido.
Content-Type    | Content-Type: text/html; charset=utf-8 | Tipo MIME del contenido.


### Cabeceras de la respuesta

 Cabecera       |     Ejemplo                   |  DescripciÃ³n 
----------------|-------------------------------|--------------
Server          | Server: Apache/2.4.1 (Unix)   | Servidor web.
Status          | Status: 200 OK                | CÃ³digo de estado.
...             | ...                           | ...


### Tipos MIME 
**Multipurpose Internet Mail Extension**

Tipo MIME             | Tipo de contenido
----------------------|-----------------------------
text/plain            | Texto plano
text/html             | Texto en formato HTML
text/css              | Hoja de estilo en cascada
application/javascript| CÃ³digo javascript
application/json      | Datos en formato JSON
image/jpeg            | Imagen en formato JPEG
image/png             | Imagen en formato PNG


### Tipos MIME 
**Multipurpose Internet Mail Extension**

Tipo MIME             | Tipo de contenido
----------------------|-----------------------------
image/svg+xml         | Imagen vectorial SVG
audio/ac3             | Audio en formato AC3
audio/ogg             | Audio en formato OGG Vorbis
video/H264            | Video con codificaciÃ³n H.264
...                   | ...


### PeticiÃ³n HTTP

![PeticiÃ³n HTTP](assets/peticion-http.png)



## Arquitecturas web


### Capas de la arquitectura

- **Capa de presentaciÃ³n**: se encarga de la navegabilidad, validaciÃ³n de los datos de entrada, formateo de los datos de salida, presentaciÃ³n de la web, etc.; se trata de la capa que se presenta al usuario.
- **Capa de negocio**: recibe las peticiones del usuario y desde donde se le envÃ­an las respuestas; en esta capa se verifican que las reglas establecidas se cumplen.
- **Capa de acceso a datos**: es la formada por determinados gestores de datos que se encargan de almacenar, estructurar y recuperar los datos solicitados por la capa de negocio.


### Modelo de 2 capas

![Web 2 capas](assets/web-2-capas.png)


### Modelo de 3 capas

![Web 3 capas](assets/web-3-capas.png)


### PÃ¡ginas estÃ¡ticas

- **HTML**
- **CSS**
- **Javascript**
- **Assets** (imÃ¡genes, fuentes de letra, ...)


### PÃ¡ginas dinÃ¡micas

- **PHP**: PHP Hypertext Preprocessor.
- **JSP**: JavaServer Pages. 
- **ASP**: Active Server Pages. 


## Plataformas

- **LAMP**. Linux + Apache + MySQL + PHP. **Libre**.
- **WISA**. Windows + IIS + SQLServer + ASP. **Propietaria**.


### Servidores web

- **Apache**
- **nginx**
- **IIS** (Internet Information Server de Microsoft)
- **Tomcat** (servidor orientado a desarrollo Java)


### Apache
#### Directorios y archivos de configuraciÃ³n

![Apache2](assets/apache2-files.png)



## Despliegue en Internet


### Escalabilidad

- **Vertical** -> Servidores mÃ¡s potentes.  
- **Horizontal** -> MÃ¡s servidores.


### Tipos de servidores
#### EvoluciÃ³n

- Sin virtualizaciÃ³n (hosting tradicional)
  - **Servidor dedicado**
  - **Servidor compartido**

- Con virtualizaciÃ³n 
  - Servidor virtual (**VPS** - Virtual Private Server)
  - Nube (**Cloud**)


### La nube
#### Tipos de servicios ###

- **IaaS**. Infraestructura como Servicio. 
- **PaaS**. Plataforma como Servicio.
- **SaaS**. Servicio como Servicio. 

[Diferencias entre IaaS, PaaS y SaaS](https://www.genbeta.com/desarrollo/entendiendo-la-nube-el-significado-de-saas-paas-y-iaas)


### La nube
#### Proveedores ###

![Amazon - GCP - Azure](assets/cloud-amazon.png)


### La nube
#### Proveedores ###

![Heroku - Openshift - DigitalOcean](assets/cloud-heroku.png)
