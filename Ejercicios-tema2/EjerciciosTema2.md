# Ejercicios Tema 1

### Ejercicio 1:
**Instalar alguno de los entornos virtuales de node.js (o de cualquier otro lenguaje con el que se esté familiarizado) y, con ellos, instalar la última versión existente, la versión minor más actual de la 4.x y lo mismo para la 0.11 o alguna impar (de desarrollo).**

Como entorno de **node.js**, voy a instalar nvm, para ello deberemos seguir varios pasos:

- Primero deberemos de obtener el script de instalación ejecutando el siguiente comando:   
```
curl https://raw.githubusercontent.com/creationix/nvm/v0.11.1/install.sh | bash
``` 
- Una vez ejecutado el comando anterior, ejecutaremos el siguiente comando:
```
source ~/.profile
```
- Comprobamos las versiones disponibles ejecutando ```nvm ls-remote```
- Una vez comprobadas las versiones instalamos la última de 4.x y lo mismo para la 0.11
```
nvm install v4.6.1
nvm install v0.11.16
``` 

### Ejercicio 2:
**Como ejercicio, algo ligeramente diferente: una web para calificar las empresas en las que hacen prácticas los alumnos. Las acciones serían, crear empresa, listar calificaciones para cada empresa, crear calificación y añadirla (comprobando que la persona no la haya añadido ya), borrar calificación (si se arrepiente o te denuncia la empresa o algo), hacer un ránking de empresas por calificación, por ejemplo Crear un repositorio en GitHub para la librería y crear un pequeño programa que use algunas de sus funcionalidades.**  

La aplicación ha sido desarrollada en python con el framework Django, además se ha utilizado la base de datos sqlite3. Para lanzar la aplicación debemos de crear un entorno virtual que podremos crearlo con el comando ```virtualenv .``` , y dentro de este entorno tener instalado python y Django. Para ejecutar la aplicación solo debemos de ejecutar el siguiente comando:
```
python manage.py runserver
```
Una vez ejecutado el comando anterior nos iremos a nuestro navegador y accederemos la url: 
```
http://localhost:8000/empresas/
```
Una vez accedido a la url anterior podremos visualizar la app como en la siguiente imagen:

![img](https://github.com/manuelalonsobraojos/IV-Ejercicios/blob/master/Ejercicios-tema2/capturas/captura2.png)


### Ejercicio 3:
**Ejecutar el programa en diferentes versiones del lenguaje. ¿Funciona en todas ellas?**

Al ejecutar con la version 2.7 de python la app se ejecuta correctamente, sin embargo al intentar ejecutar con la versión 3 de python nos muestra un mensaje de error como el que vemos en la imagen acontinuación, producido porque la versión de Django utilizada no soporta python3.

![img](https://github.com/manuelalonsobraojos/IV-Ejercicios/blob/master/Ejercicios-tema2/capturas/captura3.png)

### Ejercicio 4:
**Crear una descripción del módulo usando package.json. En caso de que se trate de otro lenguaje, usar el método correspondiente.**

Para el caso de Django, pip (PyPI) es la herramienta equivalente, utilizando los setup.py para los archivos de configuración. Un primer setup.py para la aplicación podría ser del siguiente modo:

```
from setuptools import setup

setup(name='Empresas',
      version='0.1',
      description='Aplicacion para valorar las practicas de empresas',
      long_description='Esta aplicacion permite registrar una empresa en la que se haya realizado las practicas y dar una valoracion de ella',
      classifiers=[
        'Development Status :: 3 - Alpha',
        'License :: GNU :: GNU License',
        'Programming Language :: Python :: 2.7',
        'Topic :: Text Processing :: Linguistic',
      ],
      keywords='aplicacion basica de valoracion',
      url='https://github.com/manuelalonsobraojos/AppEmpresa',
      author='ManuelAlonso',
      author_email='Manuel Alonso',
      license='GNU',
      install_requires=[
          'sqlite3',
      ],
      include_package_data=True,
      zip_safe=False)
```

### Ejercicio 5:
**Automatizar con grunt y docco (o algún otro sistema) la generación de documentación de la librería que se cree. Previamente, por supuesto, habrá que documentar tal librería.**

Para documentar la app vamos a utilizar **epidoc** que lo instalamos ejecutando la siguiente orden:
```
sudo apt-get install python-epydoc
```
Una vez instalado, pasamos a generar la documentación de las vistas y los modelos de la app. Para todo ello ejecutaremos la siguiente orden:
```
epydoc –html models.py views.py
```
Antes de ejecutar el comando anterior debemos de haber documentado los fichero correctamente como vemos a continuación en la siguiente imagen:

![img](https://github.com/manuelalonsobraojos/IV-Ejercicios/blob/master/Ejercicios-tema2/capturas/captura4.png)

Una vez ejecutado ya tendremos nuestra documentación.

![img](https://github.com/manuelalonsobraojos/IV-Ejercicios/blob/master/Ejercicios-tema2/capturas/captura5.png)


### Ejercicio 6:
**Para la aplicación que se está haciendo, escribir una serie de aserciones y probar que efectivamente no fallan. Añadir tests para una nueva funcionalidad, probar que falla y escribir el código para que no lo haga (vamos, lo que viene siendo TDD).**

El primer test que realizaremos es la creación de una empresa, para ello escribiremos el siguiente código:
```
from django.test import TestCase

from empresas.models import Empresas
from empresas.views import *


class EmpresasMethodTests(TestCase):

	def test_crea_empresa(self):
		emp = Empresas(nombre='nPrueba',correo='cprueba')
		emp.save()
		self.assertEqual(emp.nombre, 'nPrueba')
		self.assertEqual(emp.correo, 'cPrueba')

```
Una vez tenemos el código del test, podemos comprobar que el test se realiza correctamente.

![img](https://github.com/manuelalonsobraojos/IV-Ejercicios/blob/master/Ejercicios-tema2/capturas/captura6.png)

Ahora creamos los test para una nueva funcionalidad, que será la de consultar una empresa, una funcionalidad todavia no desarrollada, por lo que no superará el test.

![img](https://github.com/manuelalonsobraojos/IV-Ejercicios/blob/master/Ejercicios-tema2/capturas/captura7.png)

Una vez añadida la funcionalidad a nuestro código volvemos a realizar el test, y comprobaremos que la app supera los test.

![img](https://github.com/manuelalonsobraojos/IV-Ejercicios/blob/master/Ejercicios-tema2/capturas/captura8.png)


### Ejercicio 7:
**Convertir los tests unitarios anteriores con assert a programas de test y ejecutarlos desde mocha, usando descripciones del test y del grupo de test de forma correcta. Si hasta ahora no has subido el código que has venido realizando a GitHub, es el momento de hacerlo, porque lo vas a necesitar un poco más adelante.**

Con el framework Django esto ya está automatizado. Para lanzar los test solo tendremos que ejecutar la siguiente orden:
```
python manage.py test empresas
```

### Ejercicio 8:
**Haced los dos primeros pasos antes de pasar al tercero.**

Anadiremos un archivo .travis.yml a nuestro repositorio, este achivo contendrá el siguiente código:
```
language: python
python:
 - "2.7"

install:
 - sudo apt-get install python-dev
 - pip install --upgrade pip 
 - pip install Django 

script:
 - python manage.py test
```
Una vez añadido el archivo a nuestro repositorio, travis lo sincronizará automáticamente y comprobará que todo está correcto.

![img](https://github.com/manuelalonsobraojos/IV-Ejercicios/blob/master/Ejercicios-tema2/capturas/Captura9.PNG)




