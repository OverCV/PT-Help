# Introducción a FastAPI

Ya que nos encontramos en la carpeta `Mini-Back`, vamos a entender FastAPI como un framework web moderno y rápido para crear APIs con Python 3.6+ *(3.6 en adelante)* basado en estándares abiertos y estándares de tipo de datos Python. Es fácil de aprender y usar, pero también es muy rápido y eficiente.

Lo primero que debemos hacer es configurar correctamente nuestro entorno de desarrollo, esto aplica para cualquier desarrollo que se realice en Python

## Entorno virtual

Un entorno virtual es un directorio que tiene como función aislar todas las librerías, módulos y dependencias para un proyecto en particular. Esto se hace porque cada proyecto puede tener diferentes versiones de las librerías y módulos, y a veces pueden ser incompatibles entre sí.

Para crear un entorno virtual, debemos instalar la librería `virtualenv` que nos permitirá crear un entorno virtual. Para ello, abrimos una terminal y ejecutamos el siguiente comando:

```powershell
pip install virtualenv
```

Una vez instalado `virtualenv`, vamos a crear un entorno virtual en la carpeta `Mini-Back`. Para ello, ejecutamos el siguiente comando:

```powershell
python -m venv .venv
```

```{note}
Si usamos `ctrl + shift + p` y escribimos `Python: Create Environment`, seleccionamos la opción `Python: Select Interpreter` y elegimos la opción `Create New Environment`, seleccionamos Venv y finalmente la versión de Python que deseemos.
```

*El uso de `-m` es para especificar un módulo, en este caso `venv` que es el módulo que nos permite crear entornos virtuales y así no tomar otro módulo que se pueda llamar igual.*
Este comando creará un directorio llamado `.venv` en la carpeta `Mini-Back`. No obsatante **debemos activar siempre** el entorno virtual *(se desactiva al cerrar el editor)*, ejecutamos el siguiente comando:

```powershell
.venv\Scripts\activate
```

Podremos notar cómo en la terminal aparece el nombre del entorno virtual activo, en este caso `(.venv)`. En caso se necesite desactivar el entorno virtual, se ejecuta el comando:

```powershell
deactivate
```

## Requerimientos

En desarrollos colaborativos, es importante tener un archivo que contenga todas las librerías y módulos que se necesitan para ejecutar el proyecto. Para ello, vamos a crear un archivo llamado `requirements.txt` en la carpeta raíz (`Mini-Back`) y vamos a agregar las siguientes librerías:

```text
fastapi
uvicorn
pydantic
python-dotenv
ruff
```

```{note}
En python 3.8+ se puede usar `pip freeze > requirements.txt` para habiendo ya instalado las dependencias, generar este archivo `requirements.txt` con todas las librerías instaladas en el entorno virtual.
```{dropdown} Más sobre versionamiento!
Si no espacificamos la versión en las librerías, se instalará la última versión disponible.
Para especificar una versión exacta, se puede hacer de la siguiente manera:

```plaintext
fastapi==0.68.0
uvicorn>=0.15.0,<=0.17.0
pydantic<1.8.2
python-dotenv>=0.19.0
ruff~=0.1.0
```

```{note}
instalación de Python aislada de la instalación global. Esto significa que los paquetes instalados en el entorno virtual no afectarán a la instalación global y viceversa.
```

Ahora sí vamos a instalar FastAPI, para ello, abrimos una terminal y ejecutamos el siguiente comando:
