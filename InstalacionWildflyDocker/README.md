# Instalación de Wildfly en Docker

![logo]()

## Índice

- <a href="#1">1. Descargar la imagen del docker Wildfly </a>

<a name="1"></a>

### 1. Descargar la imagen del docker Wildfly 
Como ya tenemos docker instalado de la práctica anterior procedemos a descargar una imagen de docker, que será la de Wildfly. Para ello usaremos el siguiente comando:   <b>sudo docker pull jboss/wildfly:25.0.0.Final</b>

![1]()

Para ver el listado de todas las imágenes descargadas usamos el comando <b>sudo docker images</b>

![2]()

Para arrancar el contenedor con la imagen descargada anteriormente usaremos el comando <b>sudo docker run -d -p 5000:8080 --name "servidor-desa" jboss/wildfly</b>

![3]()

Para comprobar que el contenedor tiene una ip abrimos una terminal en nuestra máquina y ponemos <b>ip a</b> y veremos la siguiente imagen

![4]()

Para comprobar que el contenedor está activo y en funcionamiento el servicio de Wildfly, abrimos un navegador y ponemos la siguiente url: <b>172.17.0.1:5000</b> y veremos la instalación de Wildfly

![5]()