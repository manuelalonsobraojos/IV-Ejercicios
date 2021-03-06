# Ejercicios Tema 4

### Ejercicio 1:
**Instala LXC en tu versión de Linux favorita. Normalmente la versión en desarrollo, disponible tanto en GitHub como en el sitio web está bastante más avanzada; para evitar problemas sobre todo con las herramientas que vamos a ver más adelante, conviene que te instales la última versión y si es posible una igual o mayor a la 1.0.**

Para instalarlo ejecutaremos el comando ```sudo apt-get install lxc```. Una vez se ha terminado de instalar ejecutaremos el comando ```lxc-checkconfig``` con el que comprobaremos si el kernel de nuestro pc soporta este tipo de virtualización, en mi caso si la soporta como podemos ver en la siguiente imagen que muestra el resultado de la ejecución del comando anterior.

![img](https://github.com/manuelalonsobraojos/IV-Ejercicios/blob/master/Ejercicios-tema4/capturas/captura1.png) 

### Ejercicio 2:
**Comprobar qué interfaces puente se han creado y explicarlos.**

Crearemos un contenedor, para ello ejecutaremos la siguiente orden:
```
sudo lxc-create -t ubuntu -n contenedor_lxc
```
Una vez se ha creado el contenedor podremos conectarnos a el ejecutando el siguiente comando:
```
sudo lxc-start -n contenedor_lxc
```
Para conectarnos nos pedirá un usuario y una contraseña, ambos campos los rellenaremos con *ubuntu*. Una vez introducidos estaremos logueados como root.  
Para comprobar las interfaces de red ejecutaremos el comando ```ifconfig -a``` que nos dará como resultado lo siguiente:  

![img](https://github.com/manuelalonsobraojos/IV-Ejercicios/blob/master/Ejercicios-tema4/capturas/captura2.png) 


### Ejercicio 3:
**1.Crear y ejecutar un contenedor basado en Debian.**

Para crear un contenedor basado en debian deberemos de ejecutar el siguiente comando:
```
sudo lxc-create -t debian -n contenedor_debian
```
Una vez instalado los arrancaremos con el comando ```sudo lxc-start -n contenedor_debian```.  

**2.Crear y ejecutar un contenedor basado en otra distribución, tal como Fedora.**

Para instalar unn contenedor basado en CentOS podemos seguir este [tutorial](http://www.bonusbits.com/wiki/HowTo:Setup_CentOS_LXC_Container_on_Ubuntu).  
Una vez instaladas todas las dependencias como nos dice el tutorial crearemos el contenedor ejecutando el siguiente comando:
```
lxc-create -t centos -n lxc_centos
```
Para arrancarlo será igual que en todos los contenedores creado anteriormente, con la orden ```lxc-start -n lxc_centos```.


### Ejercicio 4:
**1.Instalar lxc-webpanel y usarlo para arrancar, parar y visualizar las máquinas virtuales que se tengan instaladas.**
**2.Desde el panel restringir los recursos que pueden usar: CPU shares, CPUs que se pueden usar (en sistemas multinúcleo) o cantidad de memoria.**

Para instalar lxc-webpanel primero deberemos loguearnos como root con *sudo su*, una vez logueado ejecutaremos el siguiente comando en la terminal:
```
wget https://lxc-webpanel.github.io/tools/install.sh -O - | bash
```
![img](https://github.com/manuelalonsobraojos/IV-Ejercicios/blob/master/Ejercicios-tema4/capturas/captura3.png)

Una vez instalado accederemos a la dirección *localhost:5000* y nos loguearemos con los credenciales *admin*,*admin*.  

![img](https://github.com/manuelalonsobraojos/IV-Ejercicios/blob/master/Ejercicios-tema4/capturas/captura4.png)

Una vez logueados podremos ver como el contenedor esta creado correctamente, y desde el webpanel tendremos la opción de arrancarlo o de pararlo.

![img](https://github.com/manuelalonsobraojos/IV-Ejercicios/blob/master/Ejercicios-tema4/capturas/captura5.png)

Desde el panel tambien podremos limitar los recursos de memoria y procesador que use el contenedor.  

![img](https://github.com/manuelalonsobraojos/IV-Ejercicios/blob/master/Ejercicios-tema4/capturas/captura6.png)


### Ejercicio 6:
**Instalar docker.**

He instalado docker mediante el comando: ```wget -qO- https://get.docker.com/ | sh```.  
Una vez instalado ejecutaremos el comando ```sudo usermod -aG docker manuel``` para evitar tener que poner ```sudo``` cada vez que vayamos a instalar algo dentro de nuestro contenerdor.  


### Ejercicio 7:
**1.Instalar a partir de docker una imagen alternativa de Ubuntu y alguna adicional, por ejemplo de CentOS.**
**2.Buscar e instalar una imagen que incluya MongoDB.**

Con la orden ```docker pull ubuntu``` descargamos la imagen oficial de ubuntu para docker.  
Con la orden ```docker pull centos``` descargamos la imagen oficial de CentOS para docker.  
Tambien podemos conseguir una imagen que incluya mongoDB para ello ejecutaremos la orden ```docker pull mongo```.


### Ejercicio 8:
**Crear un usuario propio e instalar nginx en el contenedor creado de esta forma.**

Para crear un usuario propio primero entraremos a nuestro contenedor con el siguiente comando:
```
docker run -t -i ubuntu /bin/bash
```
Una vez dentro ejecutamos la orden ```adduser manuel``` con la que añadiremos un nuevo usuario, una vez hecho esto tan solo nos queda instalar nginx, que lo intalaremos con la orden ```sudo apt-get install nginx```.


### Ejercicio 10:
**Crear una imagen con las herramientas necesarias para el proyecto de la asignatura sobre un sistema operativo de tu elección.**

Lo podemos ver en el archivo [README.md](https://github.com/manuelalonsobraojos/proyectoIV/blob/master/README.md) del proyecto.

























