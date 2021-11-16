# Desplegar una aplicación en Node.js

![logo]()

## Índice

- <a href="#1">1. Crear aplicación Node.js </a>
- <a href="#2">2. Crear Dockerfile </a>
- <a href="#3">3. Crear fichero .dockerignore </a>
- <a href="#4">4. Construir imagen </a>
- <a href="#5">5. Encender imagen </a>
- <a href="#6">6. Acceso </a>

<a name="1"></a>

### 1. Crear aplicación Node.js
Lo primero que hay que hacer es crear un directorio, con el nombre que quieras, y creamos un fichero llamado package.json, que describe la  aplicación y las dependencias que tiene.

![1]()

Una vez creado debemos de hacer el siguiente comando: npm install, para ello tendremos que tenerlo instalado previamente, para ello usaremos el siguiente comando: sudo apt install npm.

![2]()

Una vez instalado procedemos hacer el siguiente comando <b> npm install</b>.

![3]()

A continuación crearemos otro fichero que define nuestra aplicación web con una serie de configuraciones. El fichero se llamará server.js.

![5]()

<a name="2"></a>

### 2. Crear Dockerfile 
Ahora procederemos a crear el fichero Dockerfile, el cual tendrá la configuración de la imagen que vamos a crear.

![6]()

<a name="3"></a>

### 3. Crear fichero .dockerignore
Creamos otro fichero llamado .dockerignore, lo que ignorará, en nuestro caso, sobreescribir módulos en nuestra imagen

![4]()

<a name="4"></a>

### 4. Construir imagen
Una vez hecho toda la configuración anterior construimos la imagen usando el siguiente comando: <b>sudo docker build . -t javier/node-web-app</b>, el nombre de la será javier/node-web-app.

![7]()

Para comprobar que la imagen se creó debemos de usar el siguiente comando:<b> sudo docker ps</b>, para listar todas las imágenes que tenemos construidas.

![8]()

<a name="5"></a>

### 5. Encender imagen
Para arrancar la imagen creada anteriormente usaremos el comando: <b>sudo docker run -p 49160:8080 -d javier/node-web-app</b>. Redireccionará un puerto público a un puerto privado con la etiqueta <b>-p</b>. Para comprobar que la imagen está activa usaremos el comando <b>sudo docker ps</b>.

![9]()

Para ver el log de la imagen podemos usar el comando <b>sudo docker logs -id-imagen-</b>. Y vemos como nos dice que la imagen está activa con la siguiente dirección.

![10]()

<a name="6"></a>

### 6. Acceso
En el último paso comprobamos que realmente está en funcionamiento la imagen. Para ello abrimos un navegador y colocamos en la url: <b>localhost:49160</b>, y nos debería salir una salida como esta.

![11]()