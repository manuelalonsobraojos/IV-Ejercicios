# Ejercicios Tema 5

### Ejercicio 1:
**Instalar chef en la máquina virtual que vayamos a usar**

Para instalar **chef** deberemos de tener instalado el comando *curl*, en caso de no estarlo lo instalaremos ejecutando el siguiente comando ```sudo apt-get install curl```.  

Una vez instalado, ejecutaremos la siguiente orden: ```curl -L https://www.opscode.com/chef/install.sh | sudo bash```. Con la orden anterior instalaremos **chef** como vemos en la siguiente imagen.

![img](https://github.com/manuelalonsobraojos/IV-Ejercicios/blob/master/Ejercicios-tema6/imagenes/Captura1.PNG)

### Ejercicio 4:
**Instalar una máquina virtual Debian usando Vagrant y conectar con ella.**

Primero deberemos de instalar vagrant, para ello ejecutaremos el siguiente comando:
```
sudo apt-get install vagrant```
```
Una vez instalado vagrant ejecutaremos el siguiente comando con el que descargaremos la imagen de debian:
``` 
vagrant box add https://github.com/holms/vagrant-jessie-box/releases/download/Jessie-v0.1/Debian-jessie-amd64-netboot.box --name debian
```
Una vez descargada la imagen accederemos al directorio donde queremos que se almacenado el archivo vagrantfile que lo iniciaremos ejecutando el siguiente comando:
```
vagrant init debian
```
Una vez aquí ejecutamos el comando ```vagrant up``` con el que iniciaremos la máquina y acto seguido el comando ```vagrant ssh``` con el que accederemos a la máquina virtual.


### Ejercicio 5:
**Crear un script para provisionar `nginx` o cualquier otro servidor web que pueda ser útil para alguna otra práctica**

Para aprovisionar nginx modificaremos el archivo vagrantfile creado, escribiendo lo siguiente en el documento:

![img](https://github.com/manuelalonsobraojos/IV-Ejercicios/blob/master/Ejercicios-tema6/imagenes/Captura2.PNG)

Una vez hecho esto aprovisionamos la máquina y comprobamos el estado de nginx, para ello utilizaremos estos comando:
```
vagrant provision
vagrant ssh
sudo service nginx status
```


### Ejercicio 6:
**Configurar tu máquina virtual usando vagrant con el provisionador chef.**

Para añadir el provisionamiento con chef, abrimos el archivo Vagrantfile y lo editaremos quedando de la siguiente forma:

![img](https://github.com/manuelalonsobraojos/IV-Ejercicios/blob/master/Ejercicios-tema6/imagenes/Captura3.PNG)




