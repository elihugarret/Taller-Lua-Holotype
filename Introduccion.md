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

###Midmoon

Midmoon es un módulo para secuenciar mensajes MIDI, se encuentra dentro del proyecto Moonlet. Usa la librería escrita en C++ [lovemidi](https://github.com/elihugarret/lovemidi).
