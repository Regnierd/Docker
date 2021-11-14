# Infraestructura LAMP con Docker

![logo](https://github.com/Regnierd/Docker/blob/main/InfraestructuraLAMPDocker/img/logo.png)

## Índice

- <a href="#1">1. Requisitos </a>
- <a href="#2">2. Desplegar apliación </a>
- <a href="#3">3. Acceso </a>

<a name="1"></a>

### 1. Requisitos
Usaremos una imagen de docker de <b>Wildfly</b>, para crear 3 nodos en Wildfly. También haremos una instalación de una <b>BBDD</b> y <b>phpmyadmin</b>, incluyendo el uso de <b>Docker compose</b>.

<a name="2"></a>

### 2. Desplegar apliación
De primera mano nos descargaremos un proyecto ya pre-hecho, llamado <b>helloworld-rs</b>. Creamos los archivos <b>Dockerfile</b> y <b>docker-compose-yml</b>. Como en nuestro caso necesitamos dos Dockerfile y no se pueden poner dos Dockerfile en el mismo sitio creamos una carpeta llamada <b>www</b> y dentro colocamos el segundo <b>Dockerfile</b>.

![1]()

El Dockerfile de la raíz tendrá la configuración de Wildfly.

![2]()

El fichero docker-compose.yml contendrá los parámetros que tendrá cada contenedor, tanto puertos, como usuario y contraseña.

![3]()

Y por último, el Dockerfile que está dentro del directorio www/ contendrá la configuración del contenedor php.

![4]()

<a name="3"></a>

### 3. Acceso
Una vez que tengamos toda la configuración de los contenedores, tendremos que levantar las imágenes, para ello usaremos el comando: <b>sudo docker-compose up -d</b>

![5]()

Comprobamos que están activas con el siguiente comando: <b>sudo docker images</b>.

![6]()

Por último, abrimos un navegador y colocamos en la url:<b> localhost:8081/helloworld-rs</b>, que sería uno de los 3 contenedores de Wildfly.

![7]()
