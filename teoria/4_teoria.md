# Teorica 4

## Smalltalk vs otros lenguajes:

- Capacidad de investigación del lenguaje adentro del lenguaje.
- En smalltalk estamos tocando **código,no texto**(i.e, modificamos el codigo y no tenemos que recompilar para ver los resultados)
  - En otros lenguajes como Java tendrias que "matar al programa" y volverlo a recompilar para ver un cambio significativo

## Refactoring sin cagarla

- **Rename**: cambias el nombre del mensaje y smalltalk se encarga de encontrar todas las veces donde el mensaje se usa y cambiarle el nombre al actual
- **Refactoring automatizado**: La cagas menos,lo haces mas rapido y es mucho mas rapido
- es para las personas, no para las computadoras

## ¿que es un sender y un implementer?

- **implementors**: todos aquellos objetos que implementan el mensaje sobre el que estamos actualmente
- **senders**: aquellos lugares donde se envia el mensaje
- Todo lenguaje de programación refleja el estado de conocimiento de los creadores al momento de su concepción
- **poder de investigación**
- Para evitar que el efecto **onda del cambio** sea muy grande intentamos reducir el **acoplamiento**
- **Cohesion**: Cuanto representa algo
- Vamos a querer maximizar la cohesion y minimizar el acoplamiento

## ¿Que pasa cuando un objeto no sabe responder un mensaje?

- Por mucho que no sepa responder un mensaje, el objeto puede responder al mensaje de alguna forma
- **Todo objeto sabe responder mensajes que no conoce**
- podemos implementar el does not understand y responder de cierta forma a objetos que no conocemos
- le podemos forwardear el mensaje a otro objeto
- Todo objeto en smalltalk sabe responder el mensaje doesNotUnderstand

## Relación de Conocimiento

- Un objeto tiene que conocer a otro para mandarle un mensaje
- El nombre es el rol que el objeto nombrado cumple desde el punto de vista de aquel que lo nombra
- Colaborador interno: colaborador que siempre se conoce
- Colaborador externo: me lo puedo "olvidar"
- No se puede modificarle un colaborador interno a un objeto desde afuera, salvo que el objeto te lo permita a traves de un mensaje

## Encapsulamiento

- Intentar que otros objetos no te modifiquen los colaboradores internos
- El **motivo** del encapsulamiento es la *scalability*,tomando ideas del cuerpo humano(el sistema nervioso,respiratorio?,etc) y asi hasta al nivel celular, donde cada celula puede **interactuar** con la otra, pero otro sistema/celula de nuestro cuerpo no se puede meter adentro de otro para poder modificarlo. Permitiendonos asi escalar el sistema eficazmente
- una *variable* es lo que nosotros vamos a llamar como *colaborador*
- un colaborador interno puede ser modificado por medio de un **getter** o un **setter**

## Sintaxis

- Receptor mensaje
- variable:=objeto
- ^objeto
- por que ":=" y "^" no son mensajes?
  - Esta pregunta se responde de dos maneras:
    - que objeto deberia responder este mensaje?
      - la variable, **pero eso generaria ambiguedad**(quien responde, la variable o el objeto?)
    - La otra pregunta era un jijo

## Pseudovariables

- **NO** hace falta definirlas
- **NO** hay que definirlas
- **NO** hay que asignarles nunca nada
- Un ejemplo de una *pseudo-variable* es **self**
- **¿Cual es un mejor nombre para auto-referenciarse, self o this?**
  - **Self**: significa *yo*
  - **This**: significa *Esto*
  - Entender que un objeto es algo vivo que tiene responsabilidades(**self**), a algo que tiene datos nomas(**this**) demuestra un diferente paradigma para encarar objetos. Albeit small
- Hay otra pseudovariable ademas de self! **thisContext**
- **thisContext**: pseudo-variable que va a referenciar al **contexto de ejecución del metodo actual**
- **self**: pseudo-variable que referencia al objeto en el contexto de ejecución  | actual
- aunque no lo veamos self siempre esta, **el emisor nunca se define, siempre es self**

## Bloque / Closure

- Objetos que Representan codigo
- **Para que tenemos closures si ya tenemos metodos?**

  - una de las diferencias es que los closures no tienen nombres
    - por eso en varios lenguajes se las denomina **funciones anonimas**/**funciones lambda**
  - El closure cuando se instancia se relaciona con el contexto en el que fue instanciado
- **value**: mensaje que ejecuta el codigo que representa
- los parametros de un closure siguen las mismas formas que las de un metodo, con la diferencia de que no hay que ponerle un keyword.
- como son objetos los puedo **asignar a una variable y pasarlo como parametro**
- su funcionalidad mas importante es **parametrizar código**(mandar codigo por parametro)
- **Full closures**

  - capacidad de referenciar variables temporales
- **binding dinamico**

  - cuando vos referencia unas variables, se busca esa variable en el stack de ejecución dinamicamente
- **binding lexicografico**

  - el que se usa ahora en todos lados
- El return ^ tambien bindea al contexto de ejecución

  - un return adentro del closure bindea con el metodo/objeto/ lo que sea

    ```
    m1
    |c|
    c:=[^20]
    ^c.
    ```

    esto devuelve el blockClosure la primera vez y si le pedimos value a ese closure tira error, por que ^20
    esta bindeado al metodo

## No silver bullets - Paper de hoy

en el '86
Brooks autor, gano un turing award?

- El software tiene dos problemas
  - **Accidentales**:
  - **Esenciales**: Es invisible,esta en el mundo de las ideas,dificil de graficar, tiene un monton de estados.
- La industria en su momento creía que habia una silver bullet para agilizar el desarrollo de software
- El paper dice que aunque no haya una bala de plata para resolver el problema, si hay una solución. El autor da el ejemplo del cambio de paradigma de las plagas, donde se tuvo que tomar decisiones muy dificiles y muy graduales para si poder resolver en el problema.
- Dice que las mayorias de las soluciones de software del momento se enfocaban en resolver problemas tareas/problemas accidentales y por eso no se iba a agiilzar el desarrollo con ordenes de magnitud, las soluciones que presentaban eran:
  - High level programming
  - AI
  - Sistema experto que te de recomendaciones
- Los mecanismos que se enseñaban para trabajar en computación eran bastante *offline*,donde computar un programa era super costosos por eso se hacia tanto enfasis en la verificación, lo cual en el auge de las computadoras personales empieza a hacer agua.
- Sugiere promover buenos diseñadores y fomentar la *creación* de buenos diseñadores, hay que ponerlos en el mismo lugar que los manangers
- Sugiere comprar software antes que diseñar el software in-house. El costo de desarrollar el software se **amortiza** un monton si varios usuarios lo utilizan
- Sugiere Desarrollo incremental
- Hacer crecer el software y no construirlas
- moving the goalpost, we have to specify in a higher level but it's still the same and we still have the conceptual level/essential level difficulties
- Diseñar y tener criterios para saber si los diseños son buenos o malos

## Paradigma de objetos con organizacion de conocimiento del modelo utilizando prototipos y delegación

- Modelo de prototipado:**que era?**
- Javascript tiene modelo de prototipado
- "Delegar comportamiento a tu prototipo"
- Las clases son **ideas** (osea el *arquetipo*)
- El de prototipado es mas sencillo
- La idea de un elemento tambien es un objeto
- Para que me sirve tener una idea?
  - para instanciarla a la realidad
- No necesariamente la idea sabe responder a lo que hace una instancia de zombie
- Codigo repetido = ausencia de conceptualización
  - patrones de colaboración repetido

### ¿Como sacamos el codigo repetido?

- **practicarlo**
- Identificar lo que se repite/la abstracción en si misma
  - En el unico paso en el que hay que pensar
  - encapsular lo repetido
- copiar lo repetido a una nueva abstraccion
- parametrizar lo que cambia
- nombrar a la nueva abstracción
- usarla
