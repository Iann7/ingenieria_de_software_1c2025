# Introducción a la materia y la ingenieria de software
## Espiritu de la materia 

- Malditos influencers
- Maldito el dogma, nuestra posición esta **muy** lejos de lo dogmatico
- *Why?* (preguntarse siempre por que,INVESTIGUEN) (QEPD papadakis)
- Que es lo bueno de un paper?

  - la bibliografia? por que te permite leer mas de lo que estabas leyendo :D
  - Empiezen a investigar y **validar** la información que la catedra nos va a dar

- **Aprendizaje constructivista:** uno aprende **haciendo**
    - "El cerebro solo no vive in isolation" - Wilki 

- Vamos a ver mucho **OOP** (y solo en objetos)
    - por que solo en objetos? Rta simple: Calidad antes que cantidad
    - Los diferentes paradigmas **no son contradictorios**
    - Polimorfismo/Closures/Abstracción/etc

- **No es puro, es fundacional**
## Trabajamos sobre codigo, no sobre texto 
    Entre esas herramientas esta el  **Refactorings automatizados**
    - "Les vamos a enseñar a ser poetas"
    - Desarrollo incremental 
    - Testing! (Papadakis pasion)
    - No vamos a hablar de metodologias de desarollo 

- Es una materia exigente, pero no dificil  
- **Ojo** con el segundo parcial 

## Comunicación 

- isw2.com.ar **(Pagina Oficial)**
- alumnos@isw2.com.ar **(Lista de Alumnos)**
- docentes@isw2.com.ar **(Lista de docentes)**

## Parciales "A compu abierta"
## Hay promoción! Tiene que ser >=7

## ¿Que deben buscar hacer en los ejercicios?
    - Buenas practicas de diseño
    - Buenos nombres para las variables,clases,metodos,etc
    - Inteligible 
## ¿Por que smalltalk?
    - Baja complejidadUna caracter
    - meta-circular 
        - (para aprender un lenguaje meta-circular solo hay que aprender ese lenguaje)
        - Los lenguajes naturales son meta-circulares(lo mismo se traslada a los lenguajes de programación)
    - Live-coding
## ¿Por que CuisUniversity?
    - Cuis es ARGENTINO CARAJO
    - Ambiente de programación de objetos prototipicos3
    

## Que es hacer buen software? 
### Definición común 
Secuencia de inputs que devuelven  un output? 
### Nuestra definición  
Cuando nosotros desarollamos software, lo que estamos programando va a representar 
lo que entendemos del problema

Cuando nosotros leemos un programa, es analizar lo que entendio el implementador.

- Modelo Computable de un Dominio de Problema de la realidad
- Hacer un buen software es hacer un buen modelo **computable**
- Un modelo computable es un modelo declarativo e implementativo, no solo define que si no también tiene que implementar el como(la diferencia entre nuestros modelos y los modelos de los fisicos/matematicos/quimicos)

## Para que modela el ser humano? 
- Para entender la realidad
- Para explicar sobre aquello que esta modelando
- etc

## Definición de software
Modelo Computable de un Dominio de Problema de la Realidad 

Una caracteristica de mucho de estos dominios de problemas es que estan definidos por el ser humano, en contraposición con las otras ramas cientificas, que modelan sobre algo definido por la naturaleza.

Nuestro dominio de problema son caprichosos,ambiguos,por que las define el ser humano.Por eso el modelo tiene que estar preparado para el cambio,su adaptación 

Siempre vamos a estar modelando sobre cosas que interpretamos 

Una parte fundamental del desarrollo de software es **entender** el dominio de problema 
(eso no lo vamos a ver en la materia, pero tenganlo en cuenta!) es clave tener una buena comunicación con el cliente,experto del dominio,etc.

Cuando estamos modelando estamos pasando a algo definido de manera ambigua a algo formal,
estamos **formalizando el conocimiento**

El modelo (y la forma en la que pensamos acerca del modelo) esta atravesado por el paradigma que utilizemos para modelarlo

El modelado **es un proceso continuo**, a medida que vamos modelado vamos entendiendolo mejor, 
por ende modificando el modelo, ad inf.

Proceso continuo,iterativo e incremental 

Los programadores siempre vamos a estar modelando lo que nos dicen los **expertos del dominio**.Nunca creamos que sabemos mas que ellos(i.e nuestros clientes)

### Años atras se trabajaba con modelo cascada 
Antes habian analistas que analizaban el dominio del problema (y que hablaban con el documento),donde generaban un "modelo" que era el analista pensaba que se tenia que hacer, 
despues venian los analistas y eran lo mismo practicamente. 

Terminabas con un modelo de un modelo,un telefono descompuesto!

"Hacer software era como hacer chorizo"

### En un momento se rompe con ese modelo,con el manifiesto Agile
Iteraciones cortas al final de cada iteración donde le mostramos al usuario lo que hicimos 
en ese ciclo

- **Realidad**: Todo aquello que podemos percibir,tocar,hablar sobre,etc.
- **Dominio de problema**: Un recorte de la realidad nos interesa para el problema que estamos modelando


**Un programador debe entender el dominio de problema**
"Nunca vas a saber implementar un bono sin saber que es un bono"

## ¿Cual es el modelo?
VandenBurg: Real software engineering

The source code is the detailed thorough design of our system 

The document is IN the source code 

Programming languages have reached the point where understanding the code is as 
easy as writing it 

Programming languages ARE formal languages

Donde esta expresado el modelo? **en el codigo fuente!**

### Un modelo es bueno cuando se lo puede entender y por lo tanto cambiar
    - importante buenos nombres
    - el codigo deber ser lindo
### Buen modelo - eje funcional
    - un modelo es bueno cuando puede representar correcatamente toda observación de aquello que modela
    - Si aparece algo nuevo en el domninio, DEBE aparecer algo nuemvo en el modelo
    - Relación 1:1 dominio modelo,evitas confusiones/abstracciones 
    - Es la parte "observacional" del desarrollo

### Todos los calendarios son un modelo! 
    - Representan el paso del tiempo
    - Calendario juliano:problema de representación
    - Aimara
        - apuntan hacia atras para hablar del futuro
        "El pasado ya lo viste,entonces tiene que estar adelante tuyo"
        "El futuro no,tiene que estar atras tuyo"
    - Ruby-JS-Java no se puede representar los meses apropiadamente

## ¿Que es un mal modelo?
Cuando con el mismo no podes represntar cosas del dominio del problema 
Falta de representación
reinventar la rueda pinchada 
Soluciones ad-hoc 
Representar cosas que NO existen en la realidad
Ambiguedad: un elemento del modelo puede representar muchas cosas

**Evitar singleton: el patrón del mal**
**Clase Calendar de Java: mal diseño**

## ¿Que representa null?
Significa tantas cosas que al final no significa nada 
(mal diseño!)
### Null references: The billion Dollar mistake - Tony Hoare 
Se hace cargo de la invención de null y de los quilombos que armo con su invención 

### nil != null?
null no es un objeto y nil si. 
Intentan representar lo mismo(la nada total)

### Una de las soluciones para evitar nil/null es representar la ausencia de algo en su respectivo modelo? 

### The design of everyday things 
### The evolution of physics - Don norman 

## ¿Que es el desarollo de software?
- ¿Que es un arquitecto de software?
- ¿Que es una arquitectura de software?
- Nuestra profesión es bastante inmadura

## Compsci es una ciencia realmente? 
Computer Science is not really about computer, it's more than that
nor is it really a science(according to the video)

- The reason we think compsci is about computers is that the field is kinda
new so it's hard to categorize it
- We're still  formalizing notions about the field 
    - Formalize process, how to do things
    - Talk *precisely* 
- Figuring out a way to talk is important 

### Es una ingenieria?
Viene de una convención de la NATO/OTAN, "se quizo que fuera una ingenieria"
"El desarrollo de software de descubrimiento y exploración, por lo tanto, para tener exito en ello, los ingenieros de software deben ser expertos en el aprendizaje" - Modern Software Engineering

### Entonces que es el desarrollo de software?
Nosotros lo vamos a ver como un aprendizaje, vamos adquiriendo conocimiento y lo vamos representando,ad infinitum.

Con feedback inmediato

## Feedback Inmediato 
Como seria obtener feedback inmediato cuando estoy construyendo un algoritmo? 
**El debugger es el mejor amigo del programador**
**Smalltalk nos permite este desarrollo interativo,incremental y con feedback inmediato** 

## Smalltalk 
**Objetos es anterior al paradigma estructurado**
**Smalltalk ERA el OS**

