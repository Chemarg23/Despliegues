# Trabajo Docker

###  1. Instalación de docker

Lo primero a hacer será instalar curl con 

```bash
 $ sudo apt-get update
 $ sudo apt-get install ca-certificates curl gnupg
```
<img src="img/curl.png">

A continuación, conseguiremos docker la clave GPG oficial de coker y su repositorio

<img src="img/install.png">
<img src="img/repository.png">

lo siguiente seráinstala docker engine con
```bash
$ sudo apt-get update
$ sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```
Y creamos un usuario sin privilegios

<img src="img/user.png">

Con el siguiente comando, podemos ver la versión

<img src="img/version.png">

Instalamos a version de la comunidad con 

```bash
$ apt install docker.io
```
### 2. Creación de contenedor con la imagen hello-world

Para instalarla, hemos de haber instalado la versión de la comunidad, con el siguiente comando se descargará y ejecutará el contenedor

<img src="img/first.png">

Para ver las imagenes instaladas que tenemos, debemos usar

<img src="img/images.png">

En mi caso tenía otras dos instaladas, y para mostrar los contenedores:

<img src="img/firstps.png">

Con docker ps -a nos mostrará todos los contenedores, si solo queremos ver los activos, debemos quitar e -a, aunque en este caso, al ser un contenedor que solo hace un print de hello world, no saldrá ahí, ya que se parará solo al hacerlo

### 3. Descarga de imagenes y ejecución de contenedores

Las tres imágenes a instalar serán hello-worl, la cual ya está instalada, ubuntu y nginx. Para ello debemos usar

```bash 
$ docker pull imagen
```

<img src="img/ubuntu.png">

<img src="img/images.png">

Para crear un contenedor con el nombre personalizado; debemos usar, en este caso:

```bash 
$ docker run --name myhello1 hello-world
$ docker run --name myhello2 hello-world
$ docker run --name myhello3 hello-world
```

Al hacer docker ps -a veremos:

<img src="img/allhello.png">

Para parar los contenedores, en caso de que estén en ejecución debemos ejecutar en este caso:

```bash
$ docker stop myhello1
$ docker stop myhello2
```

Una vez parados, se podrán eliminar con

```bash
$ docker rm  myhello1
```
Aquí el resultado después de borrar

<img src="img/hellodeleted.png">

Y para borrar todos, repetiremos el proceso

<img src="img/deleteall.png">


### 4. Almacenamiento y redes de docker

###### Ejemplo1. Guestbook
Lo primero será establecer la red que conectará los dos contenedores`
```bash
$ docker network create red_guestbook
```

Una vez creada, creamos los contenedores conectados por esa misma red

<img src="img/guest1.png">
Ahora solo queda ir al navegador y acceder por local
<img src="img/guest1access.png">

Los otros dos ejemplos seguirán los mismo pasos, por lo que solo pondré las imágenes

###### Ejemplo2. Temperaturas
<img src="img/tempt1.png">
<img src="img/tempt1access.png">

###### Ejemplo3. Wordpress
<img src="img/wp1.png">
<img src="img/wp1.1.png">
<img src="img/wp1access.png">

###5. Uso y creación del docker-compose

###### Ejemplo1. Guestbook
Lo primero a hacer, es crear el archivo docker-compose.yaml y editarlo en función de nuestras necesidades

<img src="img/guestdc.png">

Una vez creado, lo ejecutamos

<img src="img/guestup.png">

Podremos acceder a él de la misma manera que en los ejemplos anteriores

<img src="img/guest2.png">

Lo último será pararlos y eliminarlos 

<img src="img/stop1.png">
<img src="img/down1.png">

De la misma manera que en el anterior apartado, simplemente pondré las imágenes para evitar la redundancia con el ejemplo anterior

###### Ejemplo2. Temperatura

<img src="img/dc2.png">
<img src="img/up2.png">
<img src="img/tem2.png">
<img src="img/down2.png">

###### Ejemplo3. Wordpress

<img src="img/dc3.png">
<img src="img/up3.png">
<img src="img/wp2.png">
<img src="img/down3.png">