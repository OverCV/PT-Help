# Introducción a FastAPI

Ya que nos encontramos en la carpeta `Mini-Back`, vamos a entender FastAPI como un framework web moderno y rápido para crear APIs con Python 3.6+ *(3.6 en adelante)* basado en estándares abiertos y estándares de tipo de datos Python. Es fácil de aprender y usar, pero también es muy rápido y eficiente.

Lo primero que debemos hacer es configurar correctamente nuestro entorno de desarrollo, esto aplica para cualquier desarrollo que se realice en Python.

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
Si usamos `ctrl + shift + p` y escribimos `Python: Create Environment`, seleccionamos la opción `Venv` (Virtual Environment) y finalmente la versión de Python que deseemos.
```

*El uso de `-m` es para especificar un módulo, en este caso `venv` que es el módulo que nos permite crear entornos virtuales y así no tomar otro módulo que se pueda llamar igual.*
Este comando creará un directorio llamado `.venv` en la carpeta `Mini-Back`. No obstante **debemos activar siempre** el entorno virtual *(se desactiva al cerrar el editor)*, ejecutamos el siguiente comando:

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
Si no especificamos la versión en las librerías, se instalará la última versión disponible.
Para especificar una versión exacta, se puede hacer de la siguiente manera:

```text
fastapi==0.68.0
uvicorn>=0.15.0,<=0.17.0
pydantic<1.8.2
python-dotenv>=0.19.0
ruff~=0.1.0
```

```{note}
La instalación de Python en un entorno virtual está aislada de la instalación global. Esto significa que los paquetes instalados en el entorno virtual no afectarán a la instalación global y viceversa.
```

Sabiendo que tenemos activado el entorno vitual, vamos a instalar las librerías y módulos necesarios para nuestro proyecto. Para ello, ejecutamos el siguiente comando:

```powershell
python -m pip install -r requirements.txt
```

En este indicamos que ejecutaremos el módulo `pip` de Python para instalar mediante una acción de lectura (`-r`) las librerías y módulos que se encuentran definidas en el archivo `requirements.txt`.

Esperamos a que se instalen todas las librerías y módulos necesarios para nuestro proyecto.

## FastAPI

FastAPI nos permite hacer desarrollos en la web usando Python, no obstante tiene dependencia de `uvicorn` para poder ejecutar el servidor. Para ello, vamos a crear un archivo llamado `main.py` en la carpeta raíz y vamos a agregar el siguiente código:

```python
from fastapi import FastAPI

app: FastAPI = FastAPI(
    title="Mini Backend | Mi Nombre.",
    summary="Técnicas de programación, 2024B",
    version="1.0.0",
)


@app.get("/")
def root() -> dict[str, str]:
    return {"data": "Hello algorithms!"}
```

```{dropdown} Directorio actual
```markdown
Mini-Back
├── .venv/
├── main.py
└── requirements.txt
```

Para ejecutarlo y ver el resultado, vamos a abrir una terminal y ejecutamos el siguiente comando:

```powershell
uvicorn main:app --reload
```

```{note}
El comando `uvicorn` nos permite ejecutar el servidor web, `main:app` indica que el archivo `main.py` contiene la instancia de FastAPI y `--reload` nos permite recargar el servidor cada vez que se realice un cambio en el código.
```

De esta forma, cuando abramos un navegador y vayamos a la dirección indicada, cual por defecto es `http://127.0.0.1:8000/`, la previamente mencionada dirección IP de Localhost, donde lo que precede a los dos puntos es el puerto *(8080)*.

Deberíamos ver el mensaje `{"data": "Hello algorithms!"}` en el navegador.

```{note}
Para detener el servidor, basta con presionar `ctrl + c` en la terminal.
```

Pero entonces, ¿Qué hemos hecho? Hemos creado un servidor web que nos devuelve un mensaje en formato JSON *(JavaScript Object Notation)*, en este caso `{"data": "Hello algorithms!"}` es un diccionario con clave `data` y valor `Hello algorithms!`, pero se convierte en JSON en el proceso de respuesta de forma forzosa. Ahora, la dirección a la que accedemos después del puerto `8080` la hemos dejado en blanco en nuestro navegador, además, hemos definido que ante una petición de tipo `GET` a la dirección raíz `/`, se ejecute la función `root`, es por esto que nos devuelve el mensaje mencionado.

FastAPI nos permite hacer desarrollos web de manera rápida y eficiente, además de ser fácil de aprender y usar.

```{warning}
Es importante conocer el sitio de Endpoints de FastAPI, este es conocido como `Swagger UI`, el cual nos permite ver y probar los endpoints de nuestra API. Para acceder a él, vamos a la dirección `http://localhost:8000/docs`.
```

```{dropdown}
🎉 Felicidades 🎊 Has construído tu primer aplicativo FastAPI 🥳 De aquí en adelante vienen conceptos para dar una arquitectura sostenible y escalable al aplicativo.
```

### Rutas y Esquemas

Vamos a generar un nuevo archivo llamado `exec.py` al lado de `main.py` y vamos a agregar el siguiente código:

```python
import uvicorn


if __name__ == "__main__":
    uvicorn.run(
        app="main:app",
        host="127.0.0.1",
        port=8000,
        reload=True,
    )
```

En este definimos los parámetros sobre los que va a funcionar el servidor, en este caso iniciará el aplicativo en el archivo `main.py` con el objeto llamado `app` de tipo FastAPI en la dirección `localhost` y el puerto `8000`, además de recargar el servidor cada vez que se realice un cambio en el código.

Ahora creamos dos folders, uno llamado `routes` y otro llamado `schemas` dentro de un folder llamado `api`, en el de rutas creamos un archivo llamado `busqueda.py`, su objetivo es contener los algoritmos de búsqueda vistos en el curso, acá se podrá entender la implementación de al menos uno de ellos, `Sequential Search`.

El directorio actual debería verse de la siguiente manera:

```markdown
Mini-Back
├── .venv/
├── api/
│   ├── routes/
│   │   └── busqueda.py
│   └── schemas/
│       └── busqueda.py
├── main.py
├── exec.py
└── requirements.txt
```

Vamos a modificar sobre el esquema de `busqueda.py` para que contenga el siguiente código:

```python
from pydantic import BaseModel, ConfigDict, Field


class SolicitudBusqueda(BaseModel):
    arreglo: list[int] = Field(
        ...,
        title="Arreglo de enteros",
        description="Arreglo de enteros para buscar",
    )
    objetivo: int = Field(
        ...,
        title="Objetivo",
        description="Número a buscar en el arreglo de enteros",
    )
    model_config: ConfigDict = ConfigDict(
        title="Solicitud de búsqueda",
        description="Solicitud de búsqueda de un número en un arreglo",
        populate_by_name=True,
        json_schema_extra={
            "example": {
                "arreglo": [1, 0, 5, 4, 3],
                "objetivo": 3,
            }
        },
    )
```

En este definimos un esquema de tipo `BaseModel` *(Usado para crear modelos Pydantic)* que contiene un arreglo de enteros y un número objetivo. El objeto `Field` puede dejarse como sólo `Field(...)` pero por claridad se le ha añadido un título y una descripción, así mismo es importante definir los tipos de parámetros utilizados.

Ahora, `model_config` no es un parámetro de nuestra petición, sino que es un parámetro ajustable de BaseModel para ayudarnos a definir modelos, en este caso darle un título, descripción, permitir llenar los datos dándoselos a cada nombre pero, lo más importante, dar **un ejemplo** de cómo se vería la entrada de datos.

Debemos modificar el archivo `main.py` para que importe las rutas que vamos a definir en el archivo `busqueda.py`, además de importar las librerías necesarias para poder hacer uso de FastAPI.
