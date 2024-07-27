# Instalación y configuración de Python

Python es un lenguaje de programación muy versátil y flexible, que se ha convertido en uno de los más populares en actualidad.

```{note}
Python es un lenguaje de programación de alto nivel, interpretado y orientado a objetos. Fue creado por Guido van Rossum y lanzado por primera vez en 1991.
```

## Instalación de Python en Windows

Para instalar Python en tu computadora, sigue los siguientes pasos:

1. Abre el navegador y accede a la página de descarga de [Python Windows](https://www.python.org/downloads/windows/).
2. Descarga el instalador de Python y ejecútalo *(puedes descargar más de una versión e instalarlas paulatinamente)*.
   <img src='../../_static/images/tema_01/py-vers.png.jpg'></img>
3. Asegúrate de seleccionar la opción de **Add Python to PATH**.
4. Haz clic en "Install Now" y espera a que finalice la instalación.
5. Abre una terminal *(busca cmd en Windows o usa `win + r`, escribe `cmd` y pulsa `enter`)* y ejecuta el siguiente comando para validar todas las versiones de Python que se hayan instalado en tu computadora:

::::{grid} 1 1 2 2
:gutter: 3

:::{grid-item-card}

```cmd
py -0p
```

:::

:::{grid-item-card}

```cmd
-V:3.12 *        C:\Program Files\Python312\python.exe
-V:3.11          C:\Program Files\Python311\python.exe
-V:3.9           C:\Program Files\WindowsApps\...\python3.9.exe
-V:3.7           C:\Program Files\WindowsApps\...\python.exe
```

:::

::::


```{tip}
Si eres usuario Windows es posible instalar Python a través de la Microsoft Store, para ello busca Python en la tienda (en la versión deseada) y sigue los pasos de instalación.
```
