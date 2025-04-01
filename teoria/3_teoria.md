# Teorica 3

- Mapeo uno a uno fundamental
- Cualquier tipo de analogia con la rama de "arquitectura" no va a ser muy buena
  - Es muy facil estimar como construir una casa, lo que es muy dificil es calcular cuanto nos va a costar
    *diseñar*, por que en el diseño y en el modelado hay **creatividad**
  - Hay una diferencia muy grande entre **construir y crear**
  - Nunca van a lograr perfectamente
  - Asi y todo, siempre nos van a pedir una estimación
    - para errarla lo menos posible en general se estima en rangos de tiempo chicos
- Desarrollo de software es un **proceso de aprendizaje**
  - no podemos reemplazar a las personas que desarrollan software como si fuesen máquinas
  - **Creativo,iterativo,incremental**

## Nos vamos a poner a definir mas formalmente Objetos...

En esta definición vamos a evitar usar palabras de otros paradigmas como:

- función
- ....?
  Para evitar que se nos confundan los conceptos, llevandonos a tener errores de definición

### Pero que es un programa?

- **Programa**(Segun el **Paradigma De Objetos Fundacional**): Es un
  conjunto de objetos que colaboran entre si enviandose **mensajes**
- Todo es un **Objeto** (si,todo,hasta la nada es un objeto)
- Hay que leer **varios libros y varios papers** para entender bien el paradigma de objetos
- **Definición normal de Objeto**: Generalmente se define como **Datos+Codigo**. ¿Que problema tiene esta definición?

  - muy ambiguo
  - Contradictorio con el axioma de que solo hay objeto + mensaje (que es Datos y Codigo? esta utilizando palabras **que todavia ni definimos**)
  - Si todo es un objeto que son los datos? un objeto! => Objeto=Objeto+Codigo (pero codigo es un objeto) => Objeto=2*objeto
- **Nuestra definición de objetos**: Representación esencial de un ente del **dominio del problema**

  - que es un *ente*?: todo aquello sobre lo que pueda pensar,actuar,sentir
  - que es la *esencia de algo*?: Lo que hace que algo sea lo que es y no sea otra cosa
  - Como vamos a representar a este ente? Segun a que mensajes responde
  - Que es lo no esencial? mensajes que no forman parte de la esencia del objeto
  - el metodo esencial de un objeto es ejecutarse
- **Mensaje**: nos dice que representa un **objeto**

  - sendTo
- **Metodos**: la **implementación** de un mensaje

  - la implementación del que
  - esta es la parte implementativa
  - valueWithReceiver: metodo importante
- **Acoplamiento**: Medida de relación entre objetos

  - cuanto **mas acoplado** esta algo, **mas relacionado esta**
  - por si solo no significa nada, el acoplamiento no es malo
  - Pero un acoplamiento incorrecto puede llevar problemas inesperados
  - Es donde el *efecto onda* del cambio se mueve
  - **Objetivo**: reducir acoplamiento
    - Acoplamiento de mas: no representando la *esencia del objeto*
- **El codigo fuente NO es el codigo**: es SOLO *una* manera de representar codigo

  - codigo fuente != codigo
- Puede haber varios metodos que responden al mismo mensaje estando definidos en el mismo objeto?
- El Paradigma fundacional de objetos nos permite definir el *que* y el *como* en lugares diferentes
- ¿Como se si un mensaje representa la esencia de un objeto?

  - si yo le borro un mensaje al objeto y sigue pudiendo representar bien al dominio de problema no forma parte de la esencia

- **¿Que es una colaboración?**:
    - El hecho de que un objeto le envíe un mensaje a otro.
    - En toda colaboración existen dos objetos:
        - **el emisor**  
        - **el receptor** 
    - cuando el receptor recibe un mensaje busca el metodo asociado a ese mensaje
        - lo ejecuta 
        - devuelve el resultado 
    - **caracteristicas de una colaboración**:
        - Dirigidas
        - Sincronicas
        - Siempre recibe respuesta
        - El receptor **desconoce** al emisor 
    - Para un objeto colabore con otro lo tiene que conocer 


## Charla de paper - Diseño  
Buen diseño => reducir la cantidad de tiempo que se necesita para aprender el lenguaje 
- **Visibilidad**
    - Visibilización de las mecanicas para interactuar con los objetos 
- **Feedback Inmediato**
    - Tiene que informar al usuario de que paso algo 
- **Mappeo natural**
- **Affordances**
    - Diferentes materiales te dan diferentes cualidades 