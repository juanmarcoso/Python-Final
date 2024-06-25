# Final del primer semestre de la Tecnicatura en la UTN

>> ***Hoy vamos a hacer actividad en Python en un día como programadores:***

### **1.Abrir la terminal de Git Bash o terminal en Linux, debe ser como administrador en Window.**

### **2.Creamos una carpeta o directorio:**

```sh
mkdir python-final 
```

### **3.Entramos en ella:**

```sh
cd python-final 
```

### **4.Iniciamos el repositorio:**

```sh
git init 
```

### **5.Creamos un archivo:**

```sh
touch finales.py 
```

### **6.Abrimos VSC:**

```sh
code . 
```

### **7.En terminal ingresamos el comando para saber la versión de Python que tenemos instalada:**

```sh
python -V 
python3 -V 
```

### **8.Creamos el entorno virtual en Python:**

```sh
python3 -m venv venv #Creamos el entorno virtual 
```

### **9.Activamos el entorno virtual:**

```sh
source venv/bin/activate #Activamos el entorno virtual en Linux 
```

```sh
venv/scripts/activate #En windows 
```

### **9.2.Para desactivar el entorno virtual:**

```sh
deactivate
```

### **10.Hacemos actualización del pip de Python:**

```sh
python3 -m pip install --upgrade pip #Actualizamos el pip 
```

### **11.Investigar ¿Qué es el pip y porque lo actualizamos?**

**<sub>[Documentacion oficial de Python](https://docs.python.org/es/3/tutorial/venv.html)</sub>**

>> **pip** es el programa de instalación preferido. Desde Python 3.4 viene incluido por defecto con los instaladores binarios de Python.

*Puede instalar, actualizar y eliminar paquetes usando un programa llamado pip. De forma predeterminada, pip instalará paquetes desde el [Indice de Paquetes de Python](https://pypi.org/). Puede navegar por el índice de paquetes de Python yendo a él en su navegador web.*

*pip tiene varios subcomandos: **«install», «uninstall», «freeze», etc**. (Consulte la guía [Instalando módulos de Python](https://docs.python.org/es/3/installing/index.html#installing-index) para obtener la documentación completa de pip).*

Se puede instalar la última versión de un paquete especificando el nombre del paquete:

```sh
(tutorial-env) $ python -m pip install novas
Collecting novas
  Downloading novas-3.1.1.3.tar.gz (136kB)
Installing collected packages: novas
  Running setup.py install for novas
Successfully installed novas-3.1.1.3
```

También se puede instalar una versión específica de un paquete ingresando el **nombre del paquete** seguido de **==** y el **número de versión**:

```sh
(tutorial-env) $ python -m pip install requests==2.6.0
Collecting requests==2.6.0
  Using cached requests-2.6.0-py2.py3-none-any.whl
Installing collected packages: requests
Successfully installed requests-2.6.0
```

Si se ejecuta de nuevo el comando, pip detectará que la versión ya está instalada y no hará nada. Se puede ingresar un número de versión diferente para instalarlo, o se puede ejecutar pip install --upgrade para actualizar el paquete a la última versión:

```sh
(tutorial-env) $ python -m pip install --upgrade requests
Collecting requests
Installing collected packages: requests
  Found existing installation: requests 2.6.0
    Uninstalling requests-2.6.0:
      Successfully uninstalled requests-2.6.0
Successfully installed requests-2.7.0
```

```sh
pip -m pip uninstall #seguido de uno o varios nombres de paquetes eliminará los paquetes del entorno virtual.
```

```sh
python -m pip show #mostrará información de un paquete en particular:
```

```sh
(tutorial-env) $ python -m pip show requests
---
Metadata-Version: 2.0
Name: requests
Version: 2.7.0
Summary: Python HTTP for Humans.
Home-page: http://python-requests.org
Author: Kenneth Reitz
Author-email: me@kennethreitz.com
License: Apache 2.0
Location: /Users/akuchling/envs/tutorial-env/lib/python3.4/site-packages
Requires:
```

```sh
python -m pip list #mostrará todos los paquetes instalados en el entorno virtual:
```

```sh
(tutorial-env) $ python -m pip list
novas (3.1.1.3)
numpy (1.9.2)
pip (7.0.3)
requests (2.7.0)
setuptools (16.0)
```

```sh
python -m pip freeze #retorna una lista de paquetes instalados, pero el formato de salida es el requerido por python -m pip install. Una convención común es poner esta lista en un archivo requirements.txt:
```

```sh
(tutorial-env) $ python -m pip freeze > requirements.txt
(tutorial-env) $ cat requirements.txt
novas==3.1.1.3
numpy==1.9.2
requests==2.7.0
```

El archivo **requirements.txt** puede ser agregado al controlador de versiones y distribuido como parte de la aplicación. Los usuarios pueden entonces instalar todos los paquetes necesarios con **install -r**:

```sh
(tutorial-env) $ python -m pip install -r requirements.txt
Collecting novas==3.1.1.3 (from -r requirements.txt (line 1))
  ...
Collecting numpy==1.9.2 (from -r requirements.txt (line 2))
  ...
Collecting requests==2.7.0 (from -r requirements.txt (line 3))
  ...
Installing collected packages: novas, numpy, requests
  Running setup.py install for novas
Successfully installed novas-3.1.1.3 numpy-1.9.2 requests-2.7.0
```

**pip** tiene muchas más opciones. Consulte la guía [Instalando módulos de Python](https://docs.python.org/es/3/installing/index.html#installing-index) para obtener documentación completa de pip. Cuando haya escrito un paquete y desee que esté disponible en el índice de paquetes de Python, consulte la [Guía de usuario de empaquetado de Python](https://packaging.python.org/en/latest/tutorials/packaging-projects/).

>> **Para finalizar, nos queda claro que Python trabaja con pip para sus entornos virtuales y la instalacion de paquetes de forma aislada. Se recomienda su uso para no tener demasiados paquetes intalados en nuestra computadora que despues no vamos a utilizar.**

#### ***Es importante actualizar pip en entornos virtuales!!!***

**1. Seguridad y correcciones de errores:**

Al igual que cualquier software, pip recibe actualizaciones periódicas que corrigen errores de seguridad y vulnerabilidades. Mantener pip actualizado garantiza que tu entorno virtual esté protegido contra las últimas amenazas. Las actualizaciones también pueden incluir mejoras en el rendimiento y la estabilidad de pip.

**2. Compatibilidad con paquetes nuevos y actualizados:**

Los desarrolladores de paquetes de Python publican actualizaciones con frecuencia, que pueden introducir nuevas funciones, corregir errores o modificar la forma en que funciona el paquete. Para asegurarte de que tu entorno virtual pueda aprovechar estas nuevas versiones y funcionar correctamente con los paquetes más recientes, es fundamental mantener pip actualizado.

**Consideraciones adicionales:**

>> Independencia de los entornos virtuales: Actualizar pip en un entorno virtual no afecta a las instalaciones de pip en otros entornos virtuales o en la instalación global de Python. Esto te permite mantener diferentes versiones de pip para diferentes proyectos según sea necesario.
Buenas prácticas: Se recomienda actualizar pip con regularidad, junto con las dependencias de tu proyecto. Esto ayuda a mantener un entorno de desarrollo seguro y estable.

*En resumen, actualizar pip en entornos virtuales es crucial para mantener la seguridad, la compatibilidad y el buen funcionamiento de tus proyectos Python. Es una práctica sencilla que puede tener un impacto significativo en la confiabilidad y la longevidad de tu código.*

**Aquí hay algunos comandos para actualizar pip en entornos virtuales:**

Para actualizar pip a la última versión estable:

```sh
pip install --upgrade pip
```

Para ver qué versión de pip tienes instalada:

```sh
pip --version
```

### **12.Hacer al primer commit de este trabajo y unirlo al repositorio remoto.**

### **13.Enviar el enlace del repositorio remoto donde tiene que tener un README.md con todos los detalles de lo que les fui mostrando en comandos, y las respuesta del punto 11 de más arriba.**