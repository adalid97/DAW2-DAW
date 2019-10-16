<!---
Ejemplos de inserción de videos

<video class="stretch" controls><source src="http://clips.vorwaerts-gmbh.de/big_buck_bunny.mp4" type="video/mp4"></video>
<iframe width="560" height="315" src="https://www.youtube.com/embed/3RBq-WlL4cU" frameborder="0" allowfullscreen></iframe>

slide: data-background="#ff0000" 
element: class="fragment" data-fragment-index="1"
-->

## Despliegue de aplicaciones web
---
![Despliegue de aplicaciones web](http://jamj2000.github.io/despliegueaplicacionesweb/despliegueaplicacionesweb.png)
<small> 2018-19 - IES Luis Vélez de Guevara - Écija - Spain </small>


## Arquitecturas web

[![cc-by-sa](http://jamj2000.github.io/despliegueaplicacionesweb/cc-by-sa.png)](http://creativecommons.org/licenses/by-sa/4.0/)


## Índice
--- 
- ### Introducción
- ### El protocolo HTTP
- ### Arquitecturas web
- ### Plataformas web
- ### Despliegue en Internet

<!--- Note: Nota a pie de página. -->




## Introducción


### En esta Unidad aprenderemos a

- Valorar los fundamentos y protocolos en los que se basa el funcionamiento de un servidor Web.
- Clasificar y describir los principales servidores de aplicaciones.
- Instalar y configurar de forma básica servidores Web.
- Realizar pruebas de funcionamiento de los servidores web.


### ¿Qué es Internet?

![Internet](assets/internet.png)




### ¿Qué es Internet?

- Un conjunto de **nodos** (equipos) conectados en forma de malla parcial.
- Un conjunto de **protocolos** para comunicar dichos nodos.
- Cada protocolo permite ofrecer un **servicio** o parte de él.
- Diseño inicial **cliente/servidor**. 

_Una red en forma de malla de area extensa, donde cada nodo es un enrutador del tráfico(equipos intermedios), lo equipos finales (clientes)_



### Protocolos de Internet

- **HTTP** (World Wide Web)
- **FTP** (Transferencia de archivos)
- **DNS** (Resolución de nombres)
- **SMTP**, **POP**, **IMAP** (Correo eléctrónico)
- **RIP**, **OSPF**, **BGP** (Enrutamiento de paquetes)
- **Telnet**, **SSH** (Conexión remota por terminal)
- **VNC**, **RDP** (Conexión remota gráfica)
- ... muchos más


_Conjunto de protocolos para comunicar los nodos, cada protocolo permite ofrecer un servicio o parte de él_
_protocolo ftp(transferencia de archivos), ssh(permite conexion remota), http(transferencia de páginas webs)_
_Servicios P2P (torrent), distinto del normal: cliente/servidor_
_*Puede caer tipo test. Buscar las siglas*_
_Hipertext Protocolo. CERN para???????????????_
_Antes de cargar la página el navegador solicita un dns_
_smtp para enviar, pop e imap para recibir_
_rip:va actualizando la tabla de rutas. Rutas estáticas en los equipos, distinto de los enrutadores.ospf: más moderno, camino más corto: mira la ruta más accesible, más rápida. Telefonica tiene el enrutamiento de todos sus nodos en una u otra de ellas. Para conectar entre ellas se usan estos mismos protocolos. PAra unirlas hace falta un enrutador frontera que utiliza el bgp para conectar con otras redes 
_bgp: enruta solo en ciertos nodos: pasarela frontera: entre distintos sistemas autonomos(redes)_
_Telnet, ssh_
_vnc: protocolo abierto (opensource). rdp (Microsoft), linux lo soporta  como escritorio remoto de un servidor windows, como servidor funciona peor_


###  Localizador Uniforme de Recursos (URL)

- Identifica un recurso en Internet. La forma básica es:
  ```
  protocolo://servidor:puerto/ruta/recurso
  ```
- En algunos casos puede incluir parámetros, credenciales, etc. Ejemplos:
  ```
  http://192.168.1.1/directorio/archivo.html
  ftp://archivos.example.com/descargas/ubuntu.iso
  https://pepe:1234@musica.com:1443/rock/descargar.php?album=37&formato=mp3
  ```
_formato que tiene cada recurso en internet: protocolo(http)://servidor:puerto(opcional, solo obligatorio cuando sea distinto del habitual)/ruta/recurso(muchos tipos: imágenes... (buscar)), el resto son parámetros que le pasamos: habitual en php. https(seguro, el correo va cifrado), cada vez se usa más. http puerto normalmente 80, https 443_
_ pepe:1234 credenciales, usuario contraseña. Los parámetros al final._

## El protocolo HTTP


### Características

- Permite el **servicio WWW**.
- Desarrollado por el World Wide Web Consortium y la Internet Engineering Task Force.
- El servidor atiende peticiones en el **puerto 80**.
- La versión más usada actualmente es HTTP/1.1 ( RFC 2616 ).
- También existe la versión HTTP/2, todavía poco usada.
- Existe la versión segura, que es HTTPS, en la que el servidor atiende en el **puerto 443**.  
- Es es protocolo sin estado: no guarda ninguna información sobre conexiones anteriores.

_w3c y ietf_
_http/2 aumenta rendimiento, empezó a desarrollarlo google_
_para que funcione la conexion segura tiene que tener el servidor un certificado digital_
_por ser protocolo sin estado, inventaron las cookies_


### Transacción HTTP

![Transacción HTTP](assets/transaccion-http.png)


### Ejemplo de petición

```
GET /index.html HTTP/1.1
Host: www.example.com
```

_texto plano_


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
_cabecera y cuerpo(código html, con su head y body...) _

### Métodos HTTP
#### Métodos básicos

- **GET**
- **POST**
- **PUT**
- **DELETE**

_post para insertar o guardar. put para modificarlo.get y post soportados por el navegador, put y delete no_

### Métodos HTTP
#### Otros métodos

- **HEAD**
- **OPTIONS**
- **CONNECT**
- **PATCH**
- **TRACE**

https://es.wikipedia.org/wiki/Protocolo_de_transferencia_de_hipertexto


### Códigos de respuesta HTTP

- **1xx**: Mensajes.
- **2xx**: Operación exitosa.
- **3xx**: Redirección. 
- **4xx**: Errores del cliente.
- **5xx**: Errores del servidor.

_404 si no escribe la página en el servidor, si por ejemplo se ha escrito bien..._

[Lista de códigos de estado (en inglés)](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes)


### Cabeceras de la petición

 Cabecera       |     Ejemplo                   |  Descripción 
----------------|-------------------------------|--------------
Accept	        | Accept: text/html	            | Tipos de contenido que se admiten como respuesta.
Accept-Charset	| Accept-Charset: utf-8	        | Juegos de caracteres admitidos.
Accept-Encoding	| Accept-Encoding: gzip, deflate| Lista de codificaciones (compresión) admitidas.
 _cliente_

### Cabeceras de la petición

 Cabecera       |     Ejemplo                   |  Descripción 
----------------|-------------------------------|--------------
Accept-Language	| Accept-Language: en-US	    | Lista de idiomas admitidos como respuesta.
Host            | Host: en.wikipedia.org:8080   | Nombre de dominio del servidor (:puerto si es distinto de 80)
User-Agent      |User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:12.0) | Agente del usuario.
...             | ...                           | ...

_cliente_
_user-agent: cliente que se conecta al servidor, con sus datos_

### Cabeceras de la respuesta

 Cabecera       |     Ejemplo                   |  Descripción 
----------------|-------------------------------|--------------
Content-Encoding| Content-Encoding: gzip        | Codificiación de los datos enviados.
Content-Language| Content-Language: es          | Idioma en el que está el contenido.
Content-Type    | Content-Type: text/html; charset=utf-8 | Tipo MIME del contenido.

_servidor_
_mime: empezó con el correo_

### Cabeceras de la respuesta

 Cabecera       |     Ejemplo                   |  Descripción 
----------------|-------------------------------|--------------
Server          | Server: Apache/2.4.1 (Unix)   | Servidor web.
Status          | 200 OK                        | Código de estado.
...             | ...                           | ...


### Tipos MIME 
**Multipurpose Internet Mail Extension**

Tipo MIME             | Tipo de contenido
----------------------|-----------------------------
text/plain            | Texto plano
text/html             | Texto en formato HTML
text/css              | Hoja de estilo en cascada
application/javascript| Código javascript
application/json      | Datos en formato JSON
image/jpeg            | Imagen en formato JPEG
image/png             | Imagen en formato PNG

_multiproposito_
_json es para enviar datos, pero aquí está clasificado como aplicación_

### Tipos MIME 
**Multipurpose Internet Mail Extension**

Tipo MIME             | Tipo de contenido
----------------------|-----------------------------
image/svg+xml         | Imagen vectorial SVG
audio/ac3             | Audio en formato AC3
audio/ogg             | Audio en formato OGG Vorbis
video/H264            | Video con codificación H.264
...                   | ...

_svg cada vez se usa más, es una imagen, con formato xml???_

### Petición HTTP

![Petición HTTP](assets/peticion-http.png)

_primero se hace una consulta de dns: por eso a veces da errores, el dns devuelve la ip, y con ese ip se hace la petición al servidor(resolver el nombre:conseguir la ip). Tanto moodle como aula están en un servidor virtual_
_valanceador de carga, proxi inverso?_


## Arquitecturas web


### Capas de la arquitectura

- **Capa de presentación**: se encarga de la navegabilidad, validación de los datos de entrada, formateo de los datos de salida, presentación de la web, etc.; se trata de la capa que se presenta al usuario.
- **Capa de negocio**: recibe las peticiones del usuario y desde donde se le envían las respuestas; en esta capa se verifican que las reglas establecidas se cumplen.
- **Capa de acceso a datos**: es la formada por determinados gestores de datos que se encargan de almacenar, estructurar y recuperar los datos solicitados por la capa de negocio.

_acceso a datos, no aparece en todas, pero es lo normal_

### Modelo de 2 capas

![Web 2 capas](assets/web-2-capas.png)

_páginas estáticas_


### Modelo de 3 capas

![Web 3 capas](assets/web-3-capas.png)

_páginas dinámicas(PHP). Backend y frontend_

### Páginas estáticas

- **HTML**
- **CSS**
- **Javascript**
- **Assets** (imágenes, fuentes de letra, ...)

_Javascript: para mucha gente dinámico, pero para esta asignatura no: javascript muestra u oculta partes de la página, el recurso sigue ahí_


### Páginas dinámicas

- **PHP**: PHP Hypertext Preprocessor.
- **JSP**: JavaServer Pages. 
- **ASP**: Active Server Pages. 

_páginas (vistas) que se generan en el servidor al vuelo_
_Jso. Asp de microsoft. Ahora se usan poco, solo para mantenimiento de las que se hicieron en esos lenguajes en su momento_

## Plataformas

- **LAMP**. Linux + Apache + MySQL + PHP. **Libre**.
- **WISA**. Windows + IIS + SQLServer + ASP. **Propietaria**.

_Plataformas web: wisa menos conocida->microsoft_

### Servidores web

- **Apache**
- **nginx**
- **IIS** (Internet Information Server de Microsoft)
- **Tomcat** (servidor orientado a desarrollo Java)

_Apache el más conocido, cuota de mercado muy grande, un 40%.nginx está subiendo mucho. iis no se usa mucho. Tomcat contenedor de sevlet, se usa para jsp. contenedor de sevlet diferente servidor de aplicaciones_

### Apache
#### Directorios y archivos de configuración

![Apache2](assets/apache2-files.png)

_Dentro de la carpeta, hay una llamada apache2.conf archivo principar de configuración. envaars: port.conf: son los puertos,incluye a otros, datos: usuario, variable de entorno w3data... módulos:mods- redrigth habilitado enlace simbólico????? sites: se accede por un sitio virual_
_ngin más modular_

## Despliegue en Internet


### Escalabilidad

- **Vertical** -> Servidores más potentes.  
- **Horizontal** -> Más servidores.


### Tipos de servidores
#### Evolución

- Sin virtualización (hosting tradicional)
  - **Servidor dedicado**
  - **Servidor compartido**

- Con virtualización 
  - Servidor virtual (**VPS** - Virtual Private Server)
  - Nube (**Cloud**)

_vps ya se está quedando desfasado_
_ahora se usa más la nube_

### La nube
#### Tipos de servicios ###

- **IaaS**. Infraestructura como Servicio. 
- **PaaS**. Plataforma como Servicio.
- **SaaS**. Servicio como Servicio. 

[Diferencias entre IaaS, PaaS y SaaS](https://www.genbeta.com/desarrollo/entendiendo-la-nube-el-significado-de-saas-paas-y-iaas)

_iaas: te dan una máquina virtual, con ubuntu o windows, te conectas por ssh o lo que quieras y montas la plataforma que quieras (apache, ngint…)
letencript certificados digitales gratis. Amazon ofrece iaas, un año gratis._
_Paas, te dan la plataforma_
_Saas: te dan el servicio directamente drive… se puede entender así wordpress_

### La nube
#### Proveedores ###

![Amazon - GCP - Azure](assets/cloud-amazon.png)


### La nube
#### Proveedores ###

![Heroku - Openshift - DigitalOcean](assets/cloud-heroku.png)
