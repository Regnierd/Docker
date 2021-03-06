# Balanceo de carga en Apache

![logo](https://github.com/Regnierd/Docker/blob/main/BalanceoCargaApache/img/logo.png)

## Índice

- <a href="#1">1. Activar módulos de Apache </a>
- <a href="#2">2. Configurar Apache para balanceo de carga </a>
- <a href="#3">3. Fichero .yml </a>
- <a href="#4">4. Fichero Dockerfile </a>
- <a href="#5">5. Acceso </a>

<a name="1"></a>

### 1. Activar módulos de Apache
Para hacer balanceo de carga hay que activar unos módulos de Apache usando un proxy inverso para activar el balanceo. Para ello usaremos el siguiente comando que vemos en la imagen.

![1](https://github.com/Regnierd/Docker/blob/main/BalanceoCargaApache/img/1.png)

<a name="2"></a>

### 2. Configurar Apache para balanceo de carga
Después de hacer la activación del proxy inverso, tenemos que resetear apache2. Comprobamos el estado del servicio de apache con el siguiente comando: <b>sudo systemctl status apache2</b>.

![2](https://github.com/Regnierd/Docker/blob/main/BalanceoCargaApache/img/2.png)

A continuación, configuramos el archivo virtual host default de Apache, para agregar el siguiente código en él. Que lo que hace es asignarle a los puertos 81, 82, 83, 84 las peticiones al servidor, el cual irá alternando los puertos.

![3](https://github.com/Regnierd/Docker/blob/main/BalanceoCargaApache/img/3.png)

<a name="3"></a>

### 3. Fichero .yml
El fichero docker-compose.yml, creará 4 contenedores con Wildfly, apuntando al fichero Dockerfile.

![5](https://github.com/Regnierd/Docker/blob/main/BalanceoCargaApache/img/5.png)

<a name="4"></a>

### 4. Fichero Dockerfile
El fichero Dockerfile tendrá la configuración de nuestros contenedores con Wildfly.

![4](https://github.com/Regnierd/Docker/blob/main/BalanceoCargaApache/img/4.png)

<a name="5"></a>

### 5. Acceso
Una vez hecho todo esto, levantaremos los contenedores con el comando <b>sudo docker-compose up -d</b>. Cuando acabe, abrimos un navegador y comprobamos que va cambiando de puerto sin tener que especificar el puerto al que llamar en la url.

![6](https://github.com/Regnierd/Docker/blob/main/BalanceoCargaApache/img/6.png)

Vemos como la primera llamada es en el puerto 81.

![7](https://github.com/Regnierd/Docker/blob/main/BalanceoCargaApache/img/7.png)

La segunda llamada es en el puerto 82.

![8](https://github.com/Regnierd/Docker/blob/main/BalanceoCargaApache/img/8.png)

La tercera en el puerto 83.

![9](https://github.com/Regnierd/Docker/blob/main/BalanceoCargaApache/img/9.png)

Y por último, en el puerto 84.


