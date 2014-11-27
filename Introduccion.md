Introducción
===================

Holotype es un ambiente de programación escrito en Lua para la práctica del live coding.

¿Qué es live coding?
========================

Es la manipulación de algorítmos en tiempo real, generalmente con fines estéticos.

http://toplap.org/wiki/ManifestoDraft

http://en.wikipedia.org/wiki/Live_coding

¿Por qué Lua?
====================

Lua es un lenguaje de programación (scripting language) rápido, portátil, ligero e integrable en otras aplicaciones.

http://www.lua.org/

Instalación
=====================

A los participantes del taller les fue enviado vía correo electrónico un archivo con formato ".zip", en caso de que alguien deseé el software, escríbame al siguiente correo electrónico: isomorphic_cluster@outlook.com

El software se distribuye de este modo para llevar un registro de la pequeña pero creciente comunidad que forma parte del proyecto. De igual modo el software esta disponible para su descarga y uso gratutito en la siguiente dirección: https://github.com/elihugarret/Holotype-Helix

El software está diseñado para Windows y Linux. En caso de que su sistema operativo sea MacOs, necesitará instalar el programa Wine, más al respecto en la página de Facebook del Taller de Live Coding ESFM.

1.- Extraer la carpeta  "HolotypeLua" en cualquier directorio.

2.- Dentro de esta carpeta encontrará un archivo ejecutable llamado "zbstudio.exe". Abrir ese archivo.

3.- Ese ejecutable es nuestro editor de textos, actualmente es el mejor editor para el lenguaje de programación Lua y sus derivados. El editor tiene por nombre ZeroBrane Studio, es software libre y está escrito por Paul Kulchenko. http://studio.zerobrane.com/

4.- Tómense su tiempo para conocer el editor. Intenten escribir el siguiente código y al terminar presionen "control + F6":

print "Hola Lua"

5.- En la parte superior del editor den "click" en donde dice "Archivo", después en "Abrir" y en la carpeta HolotypeLua buscar la carpeta "lualibs". Dentro de esta carpeta ábran el siguiente archivo: "main.lua".

6.- Nuevamente, en el mismo directorio busquen y ábran el archivo "htlang.lua". En la parte superior del editor encontrarán la opción que dice "Proyecto", dar click y buscar en el menú desplegable la opción "Project Directory", y dar click en la opción que dice "Set from current file". Esto pondrá en nuestro proyecto todas las librerías disponibles para hacer live coding.

7.- Ahora tienen dos páginas abiertas en su editor. En la página "htlang.lua" escriban el siguiente código:

def{
P = sound "x * o * ",
V = sound "x - o -  "
}

8.- Guarden el código con "control + s" o bien en "Archivos" >> "Guardar"

9.- Ahora es necesario regresar a la página "main.lua" y ejecutar con "control + F6". El resultado es un beat de bombo, hats y tarola de 4/4.

10.- Pueden modificar el sónido en tiempo real editando y guardando con "control +s" el patrón que esta entre comillas en el código de la página htlang.lua

Ahora están haciendo livecoding!!!!
Si lograron instalarlo compartanlo, y si no igual. Esto en la página de Facebook Taller de LiveCoding ESFM o en el grupo de Facebook "Lua Holotype".

