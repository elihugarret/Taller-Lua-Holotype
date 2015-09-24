#Variables.

Una variable es un espacio en la memoria a la que se le asigna un nombre. Esto sirve para poder realizar abstracciones de operaciones y procedimientos complejos.

En Lua tenemos dos tipos de variables: locales y globales.

```lua
-- Las variables locales se escriben anteponiendo la palabra "local" y luego el nombre.

local a = 2 -- A la variable "a" se le asigna el número "2"

-- Esta variable puede ser usada después

print(a + 10) -- El resultado es 12, ya que "a" vale "2" 

-- Las variable globales se esciben solo con el nombre:

b = 11 -- Se asigna 11 a la variable global "b"

print(a + b) -- El resultado es 13, porque "a" vale 2 y "b" vale 11

```
A las variables se le pueden asignar cualquier tipo de datos. Y también le podemos poner cualquier nombre siempre y cuando no inicie con un número.

```lua
-- Asignamos números:
local numero = 3

print("\n", numero)

-- Asignamos strings:
local hola = "hola"

print("\n", hola)

-- Asignamos tablas:
local tabla = {1, 2, 3, hola} -- Sí también podemos guardar variables en tablas.

print("\n", unpack(tabla)) -- la función "unpack" descomprime los elementos guardados en la tabla

-- Asignamos booleanos:
local bool = true

print("\n", bool)

-- También podemos asignar funciones y renombrarlas:
local imprime = print -- Reasignamos el nombre de la función "print" por "imprime"
-- Hay que aclarar que solo se reasigna el nombre, en Lua todas las funciones son anónimas.
-- Más adelante en el curso veremos de que se trata.

-- Aquí usaremos la función "imprime" y hará exactamente lo mismo que "print"

imprime("\n", numero)
```

En Lua también es posible realizar asignaciones múltiples, en una sola línea de código podemos asignar a varias variables diversos valores.

```lua
local a, b, c = 1, "hola", {1,2,3}
-- En este ejemplo creamos 3 variables locales: "a, b y c", y a cada uno le asignamos los valores en el orden correspondiente.

-- También puedes reasignarle el valor a una variable local, ya no es necesario usar nuevamente la palabra "local"

a = 3 -- Cambiamos el valor de "a" a 3. Antes tenía un valor de 1.
```

El tema de las variables en Lua es muy extenso, y no solo en este lenguaje de programación. La inquietud a estas alturas, seguramente es cuál es la diferencia entre una variable local y una global. Y porqué la diferencia si es practicamente lo mismo.

En Lua se programa por bloques (como en muchos otros lenguajes), una variable global se designa cuando va a ser usada en un contexto general. El uso de variables globales no es recomendado en Lua, ya que si un procedimiento cambia el valor de la variable el estado que tenía anteriormente se pierde.
En este curso todas las variables se escribiran como locales. La razón es que son más eficientes y son ideales para contextos específicos (como la creación músical o visual).

En el script luna.lua, tienen una pieza sonora muy sencilla, aquí es explícito el uso de variables.
```lua
local a = ([[ -- La variable "a" guarda una funcion que convierte símbolos en sonido.
  x c4 d3 d3 x p g4 g3
  h a#2 x d4 x p d2 c4
  x c3 c4 x p d2 a#4
  h c3 x f3 a#3 x p g4 c3
  ]]):n()

local b = ([[
  - 32 32 16 - - 16 16
  - 16 - 16 - - 16 16
  - 16 16 - - 16 16
  - 16 - 32 32 - - 16 16
  ]]):r(4)

local d = {'a3','c4','e4'} -- La variable "d" guarda una tabla con las notas de un acorde (a3,c4,e4).
-- Pueden cambiar el nombre "d" por acorde


for _, v in ipairs(a) do -- Aquí se usa la variable "a"
  moon.chord(d, _, 3, 13,70) -- Esta función hace sonar el acorde, el primer argumento es "d"
  moon.m_seq{
  --pitch = moont.choose(0.2,0.1),
  --disparity = moont.choose(.4,.2),
  seq = v,
  dur = b[_],
  R = 1,
  L = 1,
  port = 0,
  vel = 70
  }
end

```

En Fugu:

```lua
module(...,package.seeall) 

local nodo, figura -- creamos una variable local llamada "nodo" y otra "figura" en una sola línea. Asignación múltiple

-- Podemos asignar figuras a las variables
local esfera = sphere
local cubo = cube
local cilindo = cylinder
local dode = doceahedron
local tetra = tetrahedron
local ico = icosahedron

function setup()
 figura = esfera() -- Aquí se hace uso de la variable "figura" y "esfera"
 nodo = meshnode(figura) -- Aquí se hace uso de la variable "nodo"
 fgu:add(nodo)
end
```
