# Ejercicios Tema 5

### Ejercicio 1:
**Instalar los paquetes necesarios para usar KVM. Se pueden seguir estas instrucciones. Ya lo hicimos en el primer tema, pero volver a comprobar si nuestro sistema está preparado para ejecutarlo o hay que conformarse con la paravirtualización.**

Al intentar ejecutar la orden **kvm-ok** nos muestra un error de que no esta instalado, por lo que lo instalaremos ejecutando la siguiente orden:
```
sudo apt-get install cpu-checker
```
Una vez instalado volvemos a ejecutar la orden **kvm-ok** como administrado, mostrandonos que no lo soporta como podemos ver en la siguiente captura.

![img](https://github.com/manuelalonsobraojos/IV-Ejercicios/blob/master/Ejercicios-tema1/capturas/Captura3.PNG)

### Ejercicio 2:
**1.Crear varias máquinas virtuales con algún sistema operativo libre tal como Linux o BSD. Si se quieren distribuciones que ocupen poco espacio con el objetivo principalmente de hacer pruebas se puede usar CoreOS (que sirve como soporte para Docker) GALPon Minino, hecha en Galicia para el mundo, Damn Small Linux, SliTaz (que cabe en 35 megas) y ttylinux (basado en línea de órdenes solo).**

Ejecutamos el siguiente comando ```sudo modprobe fvm-intel``` con el cargaremos el módulo de kvm. Una vez hecho descargaremos una inagen de [Minino](http://minino.galpon.org/es/descargas), es este caso Árbatros. Una vez descargada instalaremos un disco duro virtual con el siguiente comando:
``` 
qemu-img create -f qcow2 disco.qcow2 3000M
```
Una vez aquí instalaremos la máquina virtual con la ISO que hemos descargado, para ello ejecutaremos el siguiente comando:
```
qemu-system-x86_64 -hda disco.qcow2 -cdrom minino-artabros-2.1_full.iso
```
Una vez ejecutado nos aparecerá la siguiente imagen para que instalemos el sistema operativo.

![imagen1](https://github.com/manuelalonsobraojos/IV-Ejercicios/blob/master/Ejercicios-tema5/imagenes/Captura1.PNG)

**2.Hacer un ejercicio equivalente usando otro hipervisor como Xen, VirtualBox o Parallels.**

Para este apartado utilizaré VirtualBox, que podremos instalarlo desde su [página oficial](https://www.virtualbox.org/wiki/Downloads).  

Una vez hemos intalado Virtual Box descargaremos una imagen de Ubuntu desde su [página oficial](http://www.ubuntu.com/download/desktop). Una vez se ha descargado la imagen, abrimos VirtualBox, hacemos clic en *Nueva* y le asignamos la imagen descargada. Para la instalación solo hará falta ir siguiendo los pasos que te va mostrando el asistende de instalación.


### Ejercicio 4:
**Crear una máquina virtual Linux con 512 megas de RAM y entorno gráfico LXDE a la que se pueda acceder mediante VNC y ssh.**

En este ejercicio instalaremos una máquina virtual de lubuntu con VirtualBox. Primero descargaremos la imagen de Lubuntu en este [enlace](https://help.ubuntu.com/community/Lubuntu/GetLubuntu). Durante el proceso de instalación le daremos una capacidad de disco duro de 5GB ya que el mínimo para que tenga un correcto funcionamiento es 4.4GB.

![imagen2](https://github.com/manuelalonsobraojos/IV-Ejercicios/blob/master/Ejercicios-tema5/imagenes/Captura2.PNG)

Una vez hemos instalado Lubuntu iremos a la configuración de red de la máquina virtual y le añadiremos una nueva interfaz de red solo anfitrión para poder conectarnos a la máquina.

![imagen3](https://github.com/manuelalonsobraojos/IV-Ejercicios/blob/master/Ejercicios-tema5/imagenes/Captura3.PNG)


![imagen](https://github.com/manuelalonsobraojos/IV-Ejercicios/blob/master/Ejercicios-tema5/imagenes/imagen3_5.jpg)

Para acceder por ssh lo haremos desde la terminal ejecutando la siguiente orden:
```
ssh [username]@[ssh server ip address]
```

### Ejercicio 6:
**Instalar una máquina virtual con Linux Mint para el hipervisor que tengas instalado.**

Para proceder con la instalación de una máquina virtual de Linux Mint en VirtualBox primero descargaremos la imagen desde su [página oficial](). Una vez descargada abriremos VirtualBox y haremos clic en *Nuevo*, asociaremos la imagen descargada y nos aparecerá una pantalla como la de la siguiente imagen:

![imagen4](https://github.com/manuelalonsobraojos/IV-Ejercicios/blob/master/Ejercicios-tema5/imagenes/Captura4.PNG)

Una vez aquí seleccionaremos la primera opción y comenzará el asistente de instalación muy similar al de ubuntu.




