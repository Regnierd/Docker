# Instalación de Docker en linux

![logo](https://github.com/Regnierd/Docker/blob/main/InslatacionDockerLinux/img/logo.png)

## Índice

- <a href="#1">1. Instalar Docker </a>
- <a href="#2">2. Trabajar con imagenes de Docker</a>
- <a href="#3">3. Administrar contenedores de Docker</a>

<a name="1"></a>

### 1. Instalar Docker
Para empezar esta instalación debemos de actualizar los repositorios de Ubuntu, con el comando <b>sudo apt update</b>.

![1](https://github.com/Regnierd/Docker/blob/main/InslatacionDockerLinux/img/1.png)

Después de actualizar, instalamos algunos paquetes para que permita a apt usar paquetes de HTTPS, con el comando: <b>sudo apt install apt-transport-https ca-certificates curl software-properties-common.</b>

![2](https://github.com/Regnierd/Docker/blob/main/InslatacionDockerLinux/img/2.png)

Añadimos la clave GPG para el repositorio de Docker con el siguiente comando: <b>curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -</b>

![3](https://github.com/Regnierd/Docker/blob/main/InslatacionDockerLinux/img/3.png)

Agregamos el repositorio de Docker a APT con el comando que se muestra a continuación: <b>sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"</b>

![4](https://github.com/Regnierd/Docker/blob/main/InslatacionDockerLinux/img/4.png)

Volvemos a actualizar los paquetes de Ubuntu con los paquetes de Docker. Después de hacerlo verificamos que vamos a instalar Docker desde los repositorios de Docker en vez de los de Ubuntu. Con el comando: <b>apt-cache policy docker-ce</b>

![5](https://github.com/Regnierd/Docker/blob/main/InslatacionDockerLinux/img/5.png)

Ya podremos instalar Docker con el comando <b>sudo apt install docker-ce.</b>

![6](https://github.com/Regnierd/Docker/blob/main/InslatacionDockerLinux/img/6.png)

Para comprobar que se instaló podemos usar el comando <b>sudo systemctl status docker</b> para ver si el servicio está activo.

![7](https://github.com/Regnierd/Docker/blob/main/InslatacionDockerLinux/img/7.png)

<a name="2"></a>

### 2. Trabajar con imágenes de Docker
A continuación verificamos si podemos descargar una imagen desde Docker Hub, con el comando <b>sudo docker run hello-world</b>.

![8](https://github.com/Regnierd/Docker/blob/main/InslatacionDockerLinux/img/8.png)

<a name="3"></a>

### 3. Administrar contenedores de Docker
Para ver todos los contenedores de Docker que tenemos activos usaremos el comando: <b>sudo docker ps -a</b>

![9](https://github.com/Regnierd/Docker/blob/main/InslatacionDockerLinux/img/9.png)

También podemos ver el último contenedor creado con el comando: <b>sudo docker ps -l</b>. Para ver las imágenes de Docker usaremos el comando: <b>sudo docker images.</b>

![10](https://github.com/Regnierd/Docker/blob/main/InslatacionDockerLinux/img/10.png)

