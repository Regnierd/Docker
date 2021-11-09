# Clusterizando una app en Wildfly

![logo](https://github.com/Regnierd/Docker/blob/main/ClusterizandoAppWildfly/img/logo.png)

## Índice

- <a href="#1">1. Requisitos </a>
- <a href="#2">2. Cluster con Docker y Wildfly </a>

<a name="1"></a>

### 1. Requisitos
Para realizar esta práctica necesitaremos tener instalado en nuestra máquina Ubuntu, <b>Docker</b> y <b>Docker-Compose</b>. Como en la práctica anterior instalamos Docker solo nos queda instalar Docker-Compose, para ello usaremos el comando <b>sudo apt install docker-compose</b>.

![7](https://github.com/Regnierd/Docker/blob/main/ClusterizandoAppWildfly/img/7.png)

También nos descargaremos un proyecto en Java para realizar la práctica, al cual tenemos que modificar algunos ficheros del mismo. En el fichero <b>web.xml</b> pondremos nuestro nombre en la etiqueta <b>display-name</b>.

![1](https://github.com/Regnierd/Docker/blob/main/ClusterizandoAppWildfly/img/1.png)

Y en el fichero pom.xml cambiamos la etiqueta <b>groupId</b> con nuestro nombre.

![2](https://github.com/Regnierd/Docker/blob/main/ClusterizandoAppWildfly/img/2.png)

Después de modificar todo, ya podremos realizar el comando: <b>mvn clean install</b>.

![3](https://github.com/Regnierd/Docker/blob/main/ClusterizandoAppWildfly/img/3.png)

<a name="2"></a>

### 2. Cluster con Docker y Wildfly
Si ejecutamos ahora el servicio de jetty con el comando <b>mvn clean jetty:run</b> y abrimos un navegador para comprobar que la app está en pleno funcionamiento poniendo en la url <b>localhost:8082</b>, ya que en el pom de la app tiene que se ejecute en el puerto <b>8082</b>.

![5](https://github.com/Regnierd/Docker/blob/main/ClusterizandoAppWildfly/img/5..png)

Ahora pasamos a ejecutarlo con Docker-Compose. Para ello en el fichero Dockerfile tendremos que tener la siguiente configuración. Lo que hará será crear un contenedor con la imagen de Wildfly y más configuraciones.

![6](https://github.com/Regnierd/Docker/blob/main/ClusterizandoAppWildfly/img/6.png)

Y en el fichero docker-compose.yml crearemos dos contenedores con la imagen de Wildfly al llamar al fichero Dockerfile, diciéndole que el primer contenedor tenga el puerto <b>8080</b> y el segundo contenedor el puerto <b>8081</b>.

![11](https://github.com/Regnierd/Docker/blob/main/ClusterizandoAppWildfly/img/11.png)

Una vez hecho estas dos cosas, ya podremos crear los dos contenedores con el siguiente comando: <b>sudo docker-compose up</b> y levantará los dos contenedores.

![8](https://github.com/Regnierd/Docker/blob/main/ClusterizandoAppWildfly/img/8.png)

Por último, abrimos un navegador y colocamos la siguiente ruta: <b>localhost:8080/app-web-demo</b>, que sería el nombre de la aplicación descargada anteriormente.

![9](https://github.com/Regnierd/Docker/blob/main/ClusterizandoAppWildfly/img/9.png)

Ahora cambiamos la ruta a: <b>localhost:8081/app-web-demo</b>.

![10](https://github.com/Regnierd/Docker/blob/main/ClusterizandoAppWildfly/img/10.png)
