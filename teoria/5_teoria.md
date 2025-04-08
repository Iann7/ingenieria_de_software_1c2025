# Teorica 5 - Todo es un objeto

## Repaso

- metaprogramación: programando sobre el programa
  - nos da la posibilidad de tocar cualquier cosa
- un metodo noes la ejecuciónd de las colaboraciones si no que representa el conjunto de colaboraciones que se van a ejecutar
- Contexto de ejecución e
- **non local return**

## Modelado de semaforo

- NO puede haber ciclos en nodos mas altos del arbol de ejecución
- Stack de ejecución hace lo mismo que el arbol de ejecución
  - representan la ejecución de un programa
- **Arbol de ejecución**: cada vez que se crea un contexto de ejecución se crea una nueva rama del arbol
- ¿que es lo que tiene de interesante pensar la ejecución como un arbol?
  - el stack es una mejora en nivel uso de memoria del arbol (por que estamos guardando menos cosas,i.e una sola rama del arbol de ejecución)
  - Una de las cosas que tiene de bueno el arbol de ejecución es poder volver atras y ver los contextos de ejecución anteriores
  - Nos permite pensar en terminos de responsabilidades
    - las cosas que estan arriba tienen "muchas" cosas?
- Tenemos que modelar un semaforo q
- no tenes que modelar el ente fisico, si no que lo el ente fisico representa en el contexto del problema
- tenemos que hacer un modelo dinamico, computable
  - y hasta que el modelo no compute, cualquier cosa que se nos ocurra esta mal (probablemente)
- feedback inmediatio lo mas rapido posible!
- no es lo mismo 0,5 que 0,5 segundos.
- cuando los numeros no tienen unidad no significa nada
- cuando los numeros tienen unidad, el numero responde a la semantica de la unidad?
- *why?*
  - Por que es que los lenguajes de programación no tienen unidades?
    - mientras le vamos tirando mas laburo a la computadora y nos lo vamos sacando nosotros empezamos a ser mas productivos!
    - Ej garbage collector con los memory leaks
    - Uno de los motivos es una cuestión historica, por cuestión historica en los lenguajes de programación no
      hay medidas
    - Recordar que el lenguaje de programacion es el estado de conocimiento de la persona que lo hizo en el momento que lo hizo. Quizas conviene descartar algunas cosas de las assumptions de ese momento
    - El sistema de medidas no estaba implementado en smalltalk
- Codigo repetido implica que te falta una abstracción
- Codigo repetido no es lo mismo que texto repetido
  - **Codigo repetido significa patrones de colaboraciones repetida**
- ¿Como sacamos codigo repetido?
  - Moves el codigo repetido a una nueva abstracción
  - Parametrizar lo que cambia
  - **mover**: es una copia *contextualizada*
  - nombrar la nueva abstracción : paso importante, ya que resume lo que hace la abstracción
  - reemplazar el codigo repetido por la nueva abstraccion
- **Extract method**
- Titilar5Veces -> AvisaPrecauciónPorEncendido
  - El refactoring explica que hace, no el como lo hace
  - todo el tiempo tenemos que pensar en el significado
- No hay error mas grave en el proceso de aprendizaje que generalizar antes de tiempo
- La palabra semaforo es ambigua
- Proceso de aprendizaje y **formalización** del problema
  - al ser formal es computable!

## Paper - self

- Self solo tiene objetos, no hay clases.

  - Como JS
  - Prototipado
  - En el paradigma de objetos que es lo mas importante?
    - que todo es un objeto
- Self is a new OOP exploratory programming based on a small number of simple and concrete ideas:

  - prototypes
  - slots
  - behaviours
    - sus protocolos, que es lo que sabe responder
- ¿Que son los slots?

  - Atributos?
  - solo se pueden acceder a traves de mensajes
    - la idea es borrar la idea de variables
    - no es algo nuevo pero es interesante como lo nombra
- Exploratory Programming

  - Includes runtime typing (no type declarations)
  - prototype metaphor for object creation
- Messages at the bottom

  - provides access to stored state solely via messages
  - Los mensajes son la cosa mas importante
- Mensajes definen el comportamiento de lo que queremos modelar
- la colaboración entre objetos se da entre mensajes, que es el proceso clave del paradigma(la comunicación entre objetos)
- No tenemos estructuras de control

  - *Por que?*:
- In self an object is what it does
- Creation by copying 
- **Molecular biology of the cell**
    - los objetos son como *Algo vivo*
- **Delegación**:
    - Los metodos se ejecutan en el contexto del objeto que recibio el mensaje
    - el objeto no encuentra un mensaje,los busca en sus padres,de encontrar el metodo lo ejecuta en su contexto
    - El activation record (osea el metodo) se ejecuta en el con
- **Forwardeo**:
    - Se ejecuta en el contexto de otro, no del recibido 
- **Closures**:
    tanto los closures como los metodos son prototypeActivations 

## Ejercicios de hoy
- **new**: mensaje de creación de instancia 
    - en otros lenguajes se llama *constructor*

## Pasos para sacar IFs
1. crear una jerarquia polimorfica con una abstraccion para cada condicion de if(opcional)
2. mover el cuerpo de cada if a cada abstracción correspondiente usando el mismo mensaje 
3. nombrar las abstracciones de 1
4. nombrar el mensaje de 2
5. Reemplazar if por envío de mensaje polimófirco
6. Buscar objeto polimórfico (opcional)

- **Polimorfismo**: Dos objeto son polimorficos con respecto a un conjunto de mensajes si responden a esos mensaje de forma semanticamente igual
