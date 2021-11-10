# Infraestructura LAMP con Docker

![logo](https://github.com/Regnierd/Docker/blob/main/InfraestructuraLAMPDocker/img/logo.png)

## Índice

- <a href="#1">1. Estructura del proyecto </a>
- <a href="#2">2. Dockerfile de php </a>
- <a href="#3">3. Archivo docker-compose.yml </a>
- <a href="#4">4. Fichero .sql </a>
- <a href="#5">5. Fichero .php </a>
- <a href="#6">6. Levantar contenedores </a>

<a name="1"></a>

### 1. Estructura del proyecto
El proyecto que desplegamos tendrá la siguiente estructura.

![1](https://github.com/Regnierd/Docker/blob/main/InfraestructuraLAMPDocker/img/1.png)

<a name="2"></a>

### 2. Dockerfile de php
Dentro del fichero Dockerfile creamos la imagen de php con su configuración específica, la cual tendrá mysql instalado también.

![2](https://github.com/Regnierd/Docker/blob/main/InfraestructuraLAMPDocker/img/2.png)

<a name="3"></a>

### 3. Archivo docker-compose.yml
En el fichero <b>docker-compose.yml</b> tendrá los 3 contenedores que vamos a crear con su configuración. Vemos que <b>php</b> tendrá el puerto <b>80</b>, mysql tendrá el <b>3306</b>, con un usuario creado con su contraseña y el <b>phpmyadmin</b> tendrá el puerto <b>8000</b> y con el usuario con el que vamos a acceder al gesto.

![3](https://github.com/Regnierd/Docker/blob/main/InfraestructuraLAMPDocker/img/3.png)

<a name="4"></a>

### 4. Fichero .sql
Como vemos en la imagen creamos la base de datos con el nombre <b>dbname</b> la cual tendrá una tabla con algunos datos.

![4](https://github.com/Regnierd/Docker/blob/main/InfraestructuraLAMPDocker/img/4.png)

<a name="5"></a>

### 5. Fichero .php 
Creamos el fichero index.php con el código html y php que vemos en la siguiente imagen.

![5](https://github.com/Regnierd/Docker/blob/main/InfraestructuraLAMPDocker/img/5.png)

<a name="6"></a>

### 6. Levantar contenedores
Para levantar todos los contenedores con docker-compose usaremos el siguiente comando: <b>sudo docker-compose up -d</b>

![6](https://github.com/Regnierd/Docker/blob/main/InfraestructuraLAMPDocker/img/6.png)

Para ver que se han levantado los contenedores usaremos el comando: <b>sudo docker ps</b>

![7](https://github.com/Regnierd/Docker/blob/main/InfraestructuraLAMPDocker/img/7.PNG)

<b>Nota:</b> No he podido solventar el error que me daba a la hora de conectarme a la base de datos.
Error el siguiente:

![8](https://github.com/Regnierd/Docker/blob/main/InfraestructuraLAMPDocker/img/8.PNG)
