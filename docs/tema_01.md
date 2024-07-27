# Tema 01: Introducción a la web 🌐

Bienvenid@ al primer tema del curso. En esta unidad, aprenderemos los conceptos básicos de desarrollo web y cómo crear una página web simple utilizando HTML y CSS.

## Motivación

Al momento de hacer cualquier desarrollo debemos ser capaces de adaptarnos a las necesidades del cliente, incluso si esto implica lanzarnos a aprender una **nueva tecnología**. El desarrollo web es un área que ha crecido exponencialmente en la última década y con ello la demanda de profesionales que puedan plasmar las ideas y necesidades creadas para cualquier **lógica del negocio**, sea financiero, educativo, del entretenimiento, etc.

Con ello vamos a ganar técnicas y habilidades que nos permitan desarrollar proficientemente la parte lógica de una aplicación y pueda luego extrapolarse a casi cualquier desarrollo presentado.

## Conceptos básicos 🧱

### ¿Qué es el internet?

El internet es una red global que conecta a millones de dispositivos en todo el mundo, permitiéndoles el intercambio de información. Por debajo se hace uso de protocolos que son, en esencia, reglas que permiten la comunicación entre los dispositivos, los más comunes son el **HTTP**/**HTTPS**, **FTP**, **TCP/IP**, entre otros.

Un sitio web es un conjunto de documentos que se encuentran relacionados entre sí y que comparten una temática en común. Estas páginas web se encuentran alojadas en un servidor web y son accesibles a través de un navegador web.

### ¿De qué partimos?

Como se mencionó antes, la web nos permite compartir información, pero esto sólo es posible si conocemos las direcciones o sitios que queramos visitar. Tu ordenador ahora mismo puede convertirse en un medio de información, para ello vamos a expresar el concepto de **Servidor** puesto que sirves información, tienes la capacidad de proveer un servicio a otro dispositivo *(o incluso a sí mismo)* cuando solicite.

Para ello, cada ordenador cuenta con una dirección IP que lo referencia a sí mismo, que en contexto de redes (IPv4) es como la ubicación actual de una persona en un mapa, pero como es complicado recordar la coordenada exacta de cada lugar, se crean los llamados **dominios** que son una dirección más amigable para el usuario, como por ejemplo `www.google.com` *(DNS/domain name system)*.

En este caso, vamos a exponer una dirección IP que de forma **local** se refiera a tu propio ordenador, pero que en el contexto de la web se refiera a un **servidor**. Para ello, haremos uso de la dirección `http://127.0.0.1`, mejor conocida con el alias de `localhost`. Esta dirección refiere a tu propio ordenador.

Más adelante ahondaremos en cómo exponer un host local para realizar procesos de desarrollo.

## ¿Peticiones y solicitudes?

Desde la arquitectura más común en la web conocida como **cliente-servidor**, un cliente solicita información a un servidor y este le responde con la información solicitada en lo posible. Ahora, ¿Qué es un *cliente*? Así como antes, también es un dispositivo como tu ordenador, tu celular, cualquier dispositivo que pueda conectarse a la web y realizar una solicitud a tu dominio o dirección IP. Por ejemplo, cuando pulsas un botón, este puede desencadenar una petición a un servidor para actualizar los ítems de tu lista de tareas, o incluso para mostrar un video en tu pantalla.

## La serpentosa amiga

En este proceso vamos a llevar a cabo muchos procesos de abstracción, es decir, entender la funcionalidad actual del mecanismo y dar por hecho que hay demasiadas cosas que no podremos construir desde cero puesto no es el fin del curso ni pertinente en tiempo, no obstante se invita a indagar siempre que la curiosidad lo permita.
Usaremos Python como medio para expresar la lógica del aplicativo en cuestión, donde luego haremos una conexión como servidor web.
