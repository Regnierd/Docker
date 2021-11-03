# Instalación de Docker en linux

![]()

## Índice

- <a href="#1">1. Instalar Docker </a>
- <a href="#2">2. Trabajar con imagenes de Docker</a>
- <a href="#3">3. Administrar contenedores de Docker</a>

<a name="1"></a>

### 1. Instalar Docker
Para empezar esta instalación debemos de actualizar los repositorios de Ubuntu, con el comando <b>sudo apt update</b>.

![1]()

Después de actualizar, instalamos algunos paquetes para que permita a apt usar paquetes de HTTPS, con el comando: <b>sudo apt install apt-transport-https ca-certificates curl software-properties-common.</b>

![2]()

Añadimos la clave GPG para el repositorio de Docker con el siguiente comando: <b>curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -</b>

![3]()

Agregamos el repositorio de Docker a APT con el comando que se muestra a continuación: <b>sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"</b>

![4]()

Volvemos a actualizar los paquetes de Ubuntu con los paquetes de Docker. Después de hacerlo verificamos que vamos a instalar Docker desde los repositorios de Docker en vez de los de Ubuntu. Con el comando: <b>apt-cache policy docker-ce</b>

![5]()

Ya podremos instalar Docker con el comando <b>sudo apt install docker-ce.</b>

![6]()

Para comprobar que se instaló podemos usar el comando <b>sudo systemctl status docker</b> para ver si el servicio está activo.

![7]()

<a name="2"></b>

### 2. Trabajar con imágenes de Docker
A continuación verificamos si podemos descargar una imagen desde Docker Hub, con el comando <b>sudo docker run hello-world</b>.

![8]()

<a name="3"></a>

### 3. Administrar contenedores de Docker
Para ver todos los contenedores de Docker que tenemos activos usaremos el comando: <b>sudo docker ps -a</b>

![9]()

También podemos ver el último contenedor creado con el comando: <b>sudo docker ps -l</b>. Para ver las imágenes de Docker usaremos el comando: <b>sudo docker images.</b>

![10]()

