# Dockeriza tu Wildfly

![logo]()

## Índice

- <a href="#1">1. Crear fichero dockerfile para Wildfly </a>
- <a href="#2">2. Usar la nueva imagen</a>

<a name="1"></a>

### 1. Crear fichero dockerfile para Wildfly
Para empezar esta práctica tendremos que tener instalado Docker y Wildfly, como hemos hecho en la práctica anterior.

Comenzamos creando el directorio wildfly-config y dentro del directorio creamos el fichero Dockerfile. En él introducimos la siguiente configuración de Wildfly que vemos en la imagen, para cuando se arranque el contenedor se ejecute el siguiente código.

![1]()

Después de crear el fichero anterior, construimos la imagen con el siguiente comando: <b>sudo docker build -q --rm --tag=jboss/wildfly:25.0.0.Final-config . </b>Cuando acabe de construir la imagen nos saldrá el siguiente código sha256.

![2]()

Una vez construida la imagen verificamos que existe la imagen creada con el comando: <b>sudo docker images</b>.

![3]()

<a name="2"></a>

### 2. Usar la nueva imagen
En este momento ya podremos usar la imagen creada, dándole un nombre al servidor como vemos en el siguiente comando (servidor-wilfly-config): <b>sudo docker run -d -p 8080:8080 -p 9990:9990 -p 8009:8009 --name servidor-wilfly-config -it jboss/wildfly:25.0.0.Final-config</b>

![4]()

Para ver que el contenedor está activo debemos de ejecutar el siguiente comando, que nos mostrará todos los contenedores activos: <b>sudo docker ps -a</b>

![5]()

Por último, para poder acceder a la consola de administración tendremos que abrir un navegador, y poner la ip que nos da docker, en nuestro caso será <b>172.17.0.1</b>, podremos poner algún puerto que declaramos en el fichero de configuración, los cuales fueron <b>8080, 9990 o 8009</b>, nosotros accederemos, por probar, con el 9990. Ponemos el usuario y contraseña de administrador, y vemos como ya estaremos en la consola de administración.

![6]()
