# Instalación de Wildfly en Docker

![logo](https://github.com/Regnierd/Docker/blob/main/InstalacionWildflyDocker/img/logo.png)

## Índice

- <a href="#1">1. Descargar la imagen del docker Wildfly </a>

<a name="1"></a>

### 1. Descargar la imagen del docker Wildfly 
Como ya tenemos docker instalado de la práctica anterior procedemos a descargar una imagen de docker, que será la de Wildfly. Para ello usaremos el siguiente comando:   <b>sudo docker pull jboss/wildfly:25.0.0.Final</b>

![1](https://github.com/Regnierd/Docker/blob/main/InstalacionWildflyDocker/img/1.png)

Para ver el listado de todas las imágenes descargadas usamos el comando <b>sudo docker images</b>

![2](https://github.com/Regnierd/Docker/blob/main/InstalacionWildflyDocker/img/2.png)

Para arrancar el contenedor con la imagen descargada anteriormente usaremos el comando <b>sudo docker run -d -p 5000:8080 --name "servidor-desa" jboss/wildfly</b>

![3](https://github.com/Regnierd/Docker/blob/main/InstalacionWildflyDocker/img/3.png)

Para comprobar que el contenedor tiene una ip abrimos una terminal en nuestra máquina y ponemos <b>ip a</b> y veremos la siguiente imagen

![4](https://github.com/Regnierd/Docker/blob/main/InstalacionWildflyDocker/img/4.png)

Para comprobar que el contenedor está activo y en funcionamiento el servicio de Wildfly, abrimos un navegador y ponemos la siguiente url: <b>172.17.0.1:5000</b> y veremos la instalación de Wildfly

![5](https://github.com/Regnierd/Docker/blob/main/InstalacionWildflyDocker/img/5.png)