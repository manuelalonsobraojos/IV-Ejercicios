# Ejercicios Tema 1

### Ejercicio 1:
**Consultar en el catálogo de alguna tienda de informática el precio de un ordenador tipo servidor y calcular su coste de amortización a cuatro y siete años.**

El equipo elegido para la realización del ejercicio es el **HP ProLiant BL460c Gen9 E5-2620v3** que está a la venta en la web de PcComponentes y podemos consultar en el siguiente enlace: https://www.pccomponentes.com/hp-proliant-bl460c-gen9-e5-2620v3  

El precio que tiene es de 2120€ y su precio sin iva es de 1752€, con este último calcularemos las amortizaciones.

Amortización para 4 años, cada año se le aplica un 25%:

-Primer año: 1752*0.25= 438€
-Segundo año: 1752*0.25= 438€
-Tercer año año: 1752*0.25= 438€
-Cuarto año: 1752*0.25= 438€

En caso de la amortización en 7 años se toma un gasto descendente:

-Primer año: 1752*0.25= 438€
-Segundo año: 1752*0.20= 350.4€
-Tercer año año: 1752*0.15= 262.8€
-Cuarto año: 1752*0.15= 262.8€
-Quinto año: 1752*0.10= 175.2€
-Sexto año: 1752*0.10= 175.2€
-Septimo año: 1752*0.05= 87.2€


### Ejercicio 2:
**Usando las tablas de precios de servicios de alojamiento en Internet y de proveedores de servicios en la nube, Comparar el coste durante un año de un ordenador con un procesador estándar (escogerlo de forma que sea el mismo tipo de procesador en los dos vendedores) y con el resto de las características similares (tamaño de disco duro equivalente a transferencia de disco duro) en el caso de que la infraestructura comprada se usa sólo el 1% o el 10% del tiempo.**

![img](https://github.com/manuelalonsobraojos/IV-Ejercicios/blob/master/Ejercicios-tema1/capturas/Captura.PNG)  

![img](https://github.com/manuelalonsobraojos/IV-Ejercicios/blob/master/Ejercicios-tema1/capturas/Captura2.PNG)  


Como hemos visto en las anteriores imagenes en el caso de **one and one** deberemos de pagar 14.99€ al mes dando igual lo que lo usemos.

En el caso de azure el precio variará segun el uso que le demos:

-Si lo usamos un 1% el precio a pagar será de 1.13€ al mes
-Si lo usamos un 10% el precio a pagar será de 11.29€ al mes

Por lo que llegamos a la conclusión que en ambos casos es más rentable pagar el de Azure


### Ejercicio 3:
**¿Qué tipo de virtualización usarías en cada caso? Comentar en el foro**
comentario en foro

**Crear un programa simple en cualquier lenguaje interpretado para Linux, empaquetarlo con CDE y probarlo en diferentes distribuciones.**

una vez instalado cde con la orden ```sudo apt-get install cde``` una vez instalado empaquetamos un programa en python ejecutando la siguiente orden ```cde python prueba.py```.

Una vez hecho esto se nos habrá creado en nuestro directorio una carpeta llamada **cde-package**, dentro de ella se habrá copiado la estructura de directorios que tenemos en nuestro pc.

Para ejecutarlo accederemos a la subcarpeta **/iv/cde-package/cde-root/home/usuario/iv** y una vez estemos en el directorio ejecutaremos nuestro programa con la siguiente orden ```./python.cde prueba.py ```.  


### Ejercicio 4:
**Comprobar si el procesador o procesadores instalados tienen estos flags. ¿Qué modelo de procesador es? ¿Qué aparece como salida de esa orden?**

El modelo de mi procesador es el **Intel(R) Core(TM) i5-3230M**

Al ejecutar el comando **egrep '^flags.*(vmx|svm)' /proc/cpuinfo** no me devuelve nada, por lo que no tiene dichos flags


### Ejercicio 5:
**1.Comprobar si el núcleo instalado en tu ordenador contiene este módulo del kernel usando la orden kvm-ok.**

Al intentar ejecutar la orden **kvm-ok** nos muestra un error de que no esta instalado, por lo que lo instalaremos ejecutando la siguiente orden:
```
sudo apt-get install cpu-checker
```
Una vez instalado volvemos a ejecutar la orden **kvm-ok** como administrado, mostrandonos que no lo soporta como podemos ver en la siguiente captura.

![img](https://github.com/manuelalonsobraojos/IV-Ejercicios/blob/master/Ejercicios-tema1/capturas/Captura3.PNG)

**2.Instalar un hipervisor para gestionar máquinas virtuales, que más adelante se podrá usar en pruebas y ejercicios.**

He instalado qemu ejecutando la siguiente orden:
``` 
sudo apt-get install qemu
```
![img](https://github.com/manuelalonsobraojos/IV-Ejercicios/blob/master/Ejercicios-tema1/capturas/Captura4.PNG)





