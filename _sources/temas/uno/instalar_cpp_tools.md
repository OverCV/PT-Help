# Instalación de C++ Tools

Python es un lenguaje de programación muy versátil y flexible, no obstante está construído sobre C y C++ en su núcleo. Por ello, es necesario instalar las herramientas de desarrollo de C++ para poder compilar y ejecutar programas escritos en C++ y evitar posibles errores en la instalación de paquetes de Python que requieran compilación.

```{note}
Este paso no es absolutamente necesario, pero es recomendable para tener un entorno de desarrollo más completo.
```

## Instalación en Windows

Para instalar las herramientas de desarrollo de C++ en Windows, sigue estos pasos:

1. Abre el navegador y accede a la página de descarga de [Visual Studio - Build Tools](https://visualstudio.microsoft.com/downloads/?q=build+tools).
2. Descarga el instalador de Visual Studio Build Tools y ejecútalo. Asegúrate de seleccionar la opción de instalar las herramientas de desarrollo de C++.

<img src="../../_static/images/tema_01/cpp_tools_install.png" style='border-radius: 1rem;'/>

1. Espera a que finalice la instalación y reinicia tu computadora.
2. Abre una terminal *(busca cmd en windows o usa `win + r`, escribe `cmd` y pulsa `enter`)* y ejecuta el siguiente comando para verificar que las herramientas de C++ se hayan instalado correctamente:

```cmd
g++ --version
```

Si todo ha ido bien, deberías ver la versión del compilador de C++ que se ha instalado.

<!-- Código que no es copiable -->
```cmd
g++ (Rev3, Built by MSYS2 project) 14.1.0
Copyright (C) 2024 Free Software Foundation, Inc.
This is free software; see the source for copying conditions.
There is NO warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.
```
