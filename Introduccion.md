#Introducción

El taller de LiveCoding ESFM es un proyecto generado en la Escuela Superior de Física y Matemáticas del IPN para 
acercar la práctica de la programación en vivo y el desarrollo a la comunidad politécnica y a la comunidad en general.

En la página [TopLap](http://toplap.org/) pueden encontrar más información sobre la práctica del livecoding.

##Lenguajes

Existen una gran cantidad de ambientes de programación para crear música y visuales en tiempo real, estos son los
más importantes:

[SuperCollider](http://supercollider.sourceforge.net/) para síntesis de audio en tiempo real y composición algorítmica.

[Sonic Pi](http://sonic-pi.net/) herramienta para livecoding diseñado para la enseñanza de música y computación en escuelas.

[Tidal](http://yaxu.org/tidal/) pequeño lenguaje escrito en Haskell para programar patrones en vivo.

[Pure Data](https://puredata.info/) es un lenguaje de programación visual que permite generar sonido, visuales 2D y 3D, comunicación en red, sensores, etc.

[Fluxus](http://www.pawfal.org/fluxus/) motor para la generación de visuales en 3D, que usa como interfaz el lenguaje funcional Racket.

#Lua

El objetivo principal del taller es que el alumno aprenda los conceptos lógicos y matemáticos detrás de la programación,
para eso utilizaremos el lenguaje [Lua](http://www.lua.org/). 

Este lenguaje de programación rápido, ligero, integrable y muy fácil de usar. Fue desarrollado en 1993 en la PUC-Rio (Pontificia Universidad Católica de Rio de Janeiro) por Roberto Ierusalimschy, Waldemar Celes y Luiz Henrique de Figueiredo.

##Moonlet

[Moonlet](https://github.com/elihugarret/Moonlet) es un módulo para hacer live coding en Lua, es un proyecto personal y diseñado para el Taller de LiveCoding en la Escuela Superior de Física y Matemáticas.
A diferencia de otros lenguajes y librerías, este módulo carece de comunidad y se encuentra constantemente en desarrollo, a pesar de esto es muy estable y funcional.
El constante desarrollo del módulo permite que los alumnos e interesados agreguen nuevas funciones e implementaciones nuevas al proyecto, además de que es posible que generen su versión personalizada.
Usa la librería [proAudioRt](http://viremo.eludi.net/proteaAudio/index.html) escrita en C++ por Gerald Franz.

El objetivo de Moonlet no es la síntesis de audio, ya que existen programas que lo hacen de una mejor y más eficiente manera. La librería está diseñada para controlar otros programas de audio, enviando mensajes MIDI y OSC a otras aplicaciones.

##Fugu

[Fugu](http://www.csse.monash.edu.au/~cema/fugu/about.html) es una aplicación para modelar y manipular con código objetos en 3D. Y sí, usa Lua.


#Instalación (Windows)

Para fines prácticos, en el taller se distribuirá un archivo comprimido con lo necesario para comenzar con las clases. La ventaja de usar Lua es su portabilidad, no es necesario instalar nada, solo es necesario realizar algunas configuraciones en el sistema.
El diseño de la librería fue realizado en Windows 7, y se ha probado su compatibilidad en Windows XP, Vista y 8. También se han compilado librerías para Linux, en específico en Ubuntu 12.04.
El editor de textos a usar será [ZeroBrane Studio](http://studio.zerobrane.com/), considero que actualmente es el mejor framework para desarrollar proyectos en Lua.

#Comenzando

Para iniciar con el curso es escencial conocer el lenguaje de programación a usar. Lua tiene diversos tipos de estructuras que son simples y fáciles de entender.

###Números

Lua es un lenguaje dinámico, es decir que solo hay un tipo de números (ej. enteros, flotantes, etc.).
Pueden correr los siguientes ejemplos en su editor de textos presionando Ctrl + F6

```lua
-- Todo lo escrito despues de dos guiones es un comentario, por lo tanto no es ejecutado por el programa
-- la funcion print, imprime en pantalla el resultado

-- Suma

print('\nResultado suma',3 + 4)

-- Resta

print('\nResultado resta',3 - 4)

-- Multiplicación

print('\nResultado multiplicacion',3 * 4)

-- División

print('\nResultado division',3 / 4)

-- Módulo
-- esta operación regresa el residuo de la división

print('\nResultado módulo',3 % 4)

```

###Booleanos

Un booleano solo puede tener dos valores "true" y "false". Estos pueden obtenerse a partir de una comparación.

```lua

-- Igualdad

print("\nSon iguales?",3 == 4)

-- Diferencia

print("\nSon distintos?",3 ~= 4)

-- Mayor que

print("\nEs mayor?",3 >= 4)

-- Menor que

print("\nEs menor?",3 <= 4)

```

###Strings

Los strings en Lua son simplemnte secuencias de caracteres.

```lua
-- Un string puede representarse de distintas maneras

-- con comillas " " 

print "hola" -- si en una función el argumento es un string, pueden omitirse los paréntesis

-- con comillas simples ' '

print 'hola'

-- si es un string largo, podemos usar doble corchete 

print[[
  hola
  este
  es
  un
  string
  largo
]]

-- también podemos calcular la longitud de un string con el operador #

local a = "hola" -- asignamos a una variable local la palabra "hola"

print(#a) -- calculamos la cantidad caracteres

```

###Tablas

Las tabla es la única estructura de datos en Lua. En estas podemos guardar colecciones de cualquier tipo de objetos, incluso otras tablas.

```lua
-- El índice de las tablas en Lua comienza desde 1

local frutas = {'manzana', 'uva', 'piña', 'melon'} -- se asigna a la variable frutas una tabla

print("\nLafruta que esta en el índice 1 es", frutas[1]) -- se imprime "manzana" 
print("\nLafruta que esta en el índice 3 es", frutas[3]) -- se imprime "piña"

-- Si queremos cambiar un elemento por uno distinto, hacemos lo siguiente:

fruta[3] = "sandía" -- el elemento 3 de la tabla es cambiado por "sandía"

print("\nEl elemento cambió a ",fruta[3])

-- En una tabla podemos guardar de todo

local elementos = {'a', 'casa', {1,2,3,4}, true, 456.23}

-- También podemos hacer esto:

local libro = {Titulo = "1984", Autor = "G. Orwell", Fecha = "1949", Genero = "Novela"}

print("\nEl título del libro es ", libro['Titulo']) -- libro['Titulo'] es valido

print("\nEl título del libro es ", libro.Titulo) -- libro.Titulo también es valido

-- podemos calcular cuantos objetos tiene una tabla con el operador #

print("\nHay ", #elementos, " elementos")

```

###Funciones

Las funciones son estructuras que nos permiten crear procedimientos, para luego ser ejecutados por la computadora.
En Lua las funciones son de primera clase, es decir que pueden ser asignadas a variables, ser argumentos, guardadas en tablas, entre otras propiedades. Esta característica es propia de los lenguajes funcionales (Lisp, Clojure, Haskell, etc.).
Lua está integrado completamente con el lenguaje C, así que podemos ejecutar también funciones escritas en dicho lenguaje.

```lua
-- una funcion tiene la siguiente estructura:
local function suma (a,b) --creamos una funcion llamada "suma", que tiene a "a" y "b" como argumentos
  return a + b -- la funcion regresa el valor de la suma de los dos argumentos
end

print("\nEl resultado de la funcion es ", suma(3,4) ) -- se imprime y se ejecuta la función
```

