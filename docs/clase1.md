
![type:video](videos\probablidad_1.mp4)
# Clase 1: Definición Formal de la probablidad y Teorema de Bayes



**¿Qué es la probablidad?**
La probabilidad es la lógica de la incertidumbre. Esta disciplina nos proporciona un marco lógico para cuantificar la incertidumbre y la aleatoriedad de una manera rigurosa

## Espacio Muestral y Eventos

El marco matemático de la probabilidad se construye alrededor de conjuntos.

**Espacio Muestral (S)**
El $\text{Espacio Muestral (S)}$ de un experimento es el conjunto de todos los posibles resultados de dicho experimento. Antes de realizar el experimento, se desconoce qué resultado ocurrirá. El espacio muestral puede ser finito, contablemente infinito o incontablemente infinito.

**Evento (A)**
Un $Evento (A)$ es un subconjunto del espacio muestral $S$ $(A⊆S)$. Decimos que el evento $A$ ocurrió si el resultado real del experimento es un elemento de $A$.

![espacioMuestral](images\space.png)

***

### Tipos de Eventos (Operaciones de Conjuntos)

Los conceptos de la Teoría de Conjuntos, como uniones, intersecciones y complementos, son esenciales ya que nos permiten construir nuevos eventos a partir de eventos previamente definidos.

| Evento | Notación de Conjuntos | Descripción en Palabras |
| :--- | :--- | :--- |
| **Espacio Muestral** | $S$ | Algo debe suceder. Ocurre con certeza. |
| **Evento Imposible** | $\emptyset$ | No puede ocurrir. Tiene probabilidad $0$. |
| **A o B** | $A \cup B$ | Ocurre al menos uno de $A$ o $B$. |
| **A y B** | $A \cap B$ | Ocurren tanto $A$ como $B$. |
| **No A** | $A^c$ | $A$ no ocurre. |
| **Eventos mutuamente excluyentes** | $A \cap B = \emptyset$ | $A$ y $B$ no pueden ocurrir simultáneamente (son disjuntos). |

## Definición no Formal de la Probablidad

Históricamente, la primera definición de probabilidad se basaba en el conteo de resultados

Para un evento $A$ en un experimento con un espacio muestral finito $S$, la probabilidad ingenua de $A$ es:

$$
P_{\text{naïve}}(A) = \frac{|A|}{|S|} = \frac{\text{número de resultados favorables a } A}{\text{número total de resultados en } S}
$$

***

### Restricciones de la Definicion no Formal

1. El espacio muestral $S$ debe ser finito.

2. Todos los resultados deben ser igualmente probables. 

El enfoque naive es aplicable cuando existe simetría en el problema que hace que los resultados sean igualmente probables (por ejemplo, lanzar un dado justo o un mazo de cartas bien barajado). 

**Advertencia:** Es un error común asumir resultados igualmente probables sin justificación (por ejemplo, argumentar "sucederá o no sucederá, por lo tanto, 50-50").

***


## Conteo: Multiplicación, Permutaciones y Combinaciones

Para calcular la probabilidad naive, a menudo es necesario contar el tamaño de los conjuntos $A$ y $S$, lo que requiere métodos de conteo.

***

### Regla de la Multiplicación

La Regla de la Multiplicación establece que si un experimento compuesto consta de dos sub-experimentos, Experimento $A$ con $a$ resultados posibles y Experimento $B$ con $b$ resultados posibles por cada resultado de $A$, entonces el experimento compuesto tiene $a×b$ resultados posibles. Este principio se extiende a múltiples sub-experimentos y es la base para las reglas de muestreo.


### Permutaciones (Muestreo Ordenado)

Cuando se selecciona una muestra, es crucial saber si el orden de la selección es relevante y si la selección se hace con o sin reemplazo,

| Tipo de Muestreo | Condición | Número de Resultados (Orden Importa) |
| :--- | :--- | :--- |
| **Con Reemplazo** | Se elige $k$ veces de $n$ objetos, volviendo a poner el objeto cada vez. | $n^k$ |
| **Sin Reemplazo (Permutación)** | Se elige $k$ veces de $n$ objetos, sin poder elegir el mismo objeto dos veces (requiere $k \le n$). | $n(n-1)\cdots(n-k+1)$ |

_Nota: Una Permutación de $n$ objetos es un arreglo de estos en algún orden, y hay $n!$ de estas (caso $k=n$ sin reemplazo)._

***

### Combinaciones (Muestreo No Ordenado)

Una Combinación o Coeficiente Binomial cuenta el número de subconjuntos de un cierto tamaño.

El coeficiente binomial $\binom{n}{k}$, leído como "n en k", es el número de maneras de elegir k objetos de un conjunto de tamaño $n$ donde el orden no importa.

$\binom{n}{k} = \frac{n(n-1)\cdots(n-k+1)}{k!} = \frac{n!}{k!(n-k)!} \quad \text{para } k \le n$


## Axiomas de Kolmogorov y Definición General de Probabilidad

Para ir más allá de las limitaciones de la definición naive (espacios infinitos o resultados no equiprobables), definimos una función de probabilidad $(P)$ que debe satisfacer solo dos reglas (axiomas).

Un **Espacio de Probabilidad** consiste en un espacio muestral $S$ y una función de probabilidad $P$ que toma un evento $A⊆S$ como entrada y devuelve un número real $P(A)$ entre 0 y 1 como salida.

### Axiomas de Kolmogorov

La función $P$ debe satisfacer los siguientes axiomas:

$1$. Rango y Normalización: 

$P(\emptyset) = 0, \quad P(S) = 1.$

Esto significa que un evento imposible tiene probabilidad 0, y el evento cierto (el espacio muestral completo) tiene probabilidad 1. 

$2$. Aditividad (Sumatoria) Contable: Si $A_1, A_2, ...$ son eventos disjuntos (mutuamente excluyentes), entonces la probabilidad de su unión es la suma de sus probabilidades: 

$P\left(\bigcup_{j=1}^{\infty} A_j\right) = \sum_{j=1}^{\infty} P(A_j).$


## Leyes y Propiedades Básicas de la Probabilidad

A partir de los dos axiomas, se pueden derivar muchas propiedades útiles que son válidas para cualquier función de probabilidad.

### 1. Regla del Complemento

Para cualquier evento $A$:

$$P(A^c) = 1 - P(A).$$

**Justificación:** El evento $A$ y su complemento $A^c$ son disjuntos, y su unión es el espacio muestral completo $S$. Aplicando el Axioma 2, $P(S) = P(A \cup A^c) = P(A) + P(A^c)$. Dado que $P(S) = 1$ (Axioma 1), se deduce la regla.

***

### 2. Monotonicidad (Ley de Inclusión)

Si un evento $A$ está contenido en un evento $B$ ($A \subset B$), entonces:

$$P(A) \le P(B).$$

**Justificación:** Si $A \subset B$, podemos descomponer $B$ en dos eventos disjuntos: $A$ y $B \cap A^c$ (la parte de $B$ que no está en $A$). Por el Axioma 2, $P(B) = P(A) + P(B \cap A^c)$. Dado que la probabilidad de cualquier evento es no negativa, $P(B \cap A^c) \ge 0$, lo que prueba que $P(B) \ge P(A)$.

***

### 3. Ley General de Adición (Inclusión-Exclusión para dos Eventos)

Para cualesquiera dos eventos $A$ y $B$, no necesariamente disjuntos:

$$P(A \cup B) = P(A) + P(B) - P(A \cap B).$$

**Justificación:** Al sumar $P(A) + P(B)$, la intersección $A \cap B$ se cuenta dos veces. Se resta $P(A \cap B)$ una vez para corregir esta doble cuenta. Este resultado se demuestra escribiendo la unión $A \cup B$ como la unión de eventos disjuntos, por ejemplo, $A \cup (B \cap A^c)$.


## Probabilidad condicional

La probabilidad condicional es fundamental ya que nos permite cuantificar la incertidumbre y actualizar nuestras creencias a la luz de nueva evidencia. Una perspectiva útil es que todas las probabilidades son condicionales, ya que siempre se basa en conocimientos o suposiciones previas, incluso si no se establece explícitamente.

**Definición**
Si $A$ y $B$ son eventos con $P(B)>0$, la probabilidad condicional de $A$ dado $B$, denotada por $P(A∣B)$, se define como:
$$
P(A \mid B) = \frac{P(A \cap B)}{P(B)}
$$

Aquí, $A$ es el evento cuya incertidumbre queremos actualizar, y $B$ es la evidencia que observamos o que se toma como dada.

• **Probabilidad a priori (Prior):** $P(A)$ es la probabilidad de $A$ antes de actualizarla con la evidencia.
• **Probabilidad a posteriori (Posterior):** $P(A∣B)$ es la probabilidad de A después de actualizarla con la evidencia $B$.

Intiución


**Propiedades clave:**
Un punto crucial es que la función de probabilidad condicional $P(⋅∣B)$ satisface todos los axiomas de probabilidad. Por lo tanto, cualquier resultado que hayamos derivado sobre la probabilidad incondicional sigue siendo válido si reemplazamos todas las probabilidades por probabilidades condicionales a $B$.

!!! Ejercicio_1
    Se baraja bien una baraja estándar de 52 cartas. Se extraen dos cartas al azar, una a la vez y sin reemplazo. Sea $A$ el evento de que la primera carta es un corazón, y $B$ el evento de que la segunda carta es roja. Encuentre $P(A∣B)$.

??? Respuesta_1
    $1.$ Hallar $P(A \cap B)$: El evento $A∩B$ es que la primera carta sea un corazón (hay 13) y la segunda carta sea roja. Una vez que se extrae un corazón, quedan 51 cartas, de las cuales 25 son rojas (las 12 cartas de diamantes restantes más las 13 cartas rojas no-corazón). 

    $$
    P(A \cap B) = \frac{13 \cdot 25}{52 \cdot 51} = \frac{25}{204}
    $$

    $2.$ Hallar $P(B)$: Por simetría, la segunda carta tiene la misma probabilidad de ser roja que la primera carta. Hay 26 cartas rojas en total. 

    $$
    P(B) = \frac{26}{52} = \frac{1}{2}
    $$

    $3.$ Aplicar la Definición: 

    $$
    P(A|B) = \frac{P(A \cap B)}{P(B)} = \frac{25/204}{1/2} = \frac{25}{102}
    $$

---

!!! Ejercicio_2
    Se reparten tres cartas de una baraja estándar bien barajada. Las dos primeras cartas se voltean, revelando el As de Picas como la primera carta y el 8 de Tréboles como la segunda carta.

    **Tarea:** Dada esta información, encuentre la probabilidad de que la tercera carta sea un as.


## Independencia de Eventos 

La independencia describe la situación en la que la ocurrencia de un evento no proporciona información que cambie la probabilidad de otro evento.

**Definición**
Los eventos $A$ y $B$ son independientes si la probabilidad de su intersección es igual al producto de sus probabilidades individuales:

$$
P(A \cap B) = P(A)P(B)\
$$


Si $P(A)>0$ y $P(B)>0$, la independencia es equivalente a que:

$$
P(A|B) = P(A) \quad \text{y} \quad P(B|A) = P(B)
$$


En otras palabras, aprender que B ocurrió no cambia nuestras probabilidades para $A$.

**Independencia vs. Disjunción:** Es un error común confundir independencia con disjunción (eventos mutuamente excluyentes). Si $A$ y $B$ son disjuntos $(A∩B=∅)$, entonces $P(A∩B)=0$. Por lo tanto, los eventos disjuntos solo pueden ser independientes si $P(A)=0$ o $P(B)=0$. Si A ocurre, sabemos con certeza que $B$ no ocurrió, lo que significa que $A$ sí proporciona información sobre $B$ y, por lo tanto, no son independientes (a menos que uno tenga probabilidad cero).

**Independencia Múltiple:** Para $n$ eventos $A_1, A_2,..., A_n$ sean independientes, se requiere que la probabilidad de la intersección de cualquier subconjunto de estos eventos sea igual al producto de sus probabilidades individuales. Por ejemplo, para tres eventos $A,B,C$, se requiere la independencia por pares $(P(A∩B)=P(A)P(B), etc.)$ y también: 

$$
P(A \cap B \cap C) = P(A)P(B)P(C)
$$


!!! Ejercicio_3
    Se lanzan 6 dados justos de seis caras. ¿Cuál es la probabilidad del evento $A$: obtener al menos un 6 cuando se lanzan 6 dados justos?


??? Solución_3
    Utilizaremos la estrategia de calcular el complemento, ya que "al menos un 6" es una unión complicada, mientras que el complemento, "ningún 6", es una intersección de eventos independientes.

    $1.$ Definir el complemento ($A^c$): $A^c$ es el evento de obtener ningún 6 en los 6 lanzamientos.

    $2.$ Calcular la probabilidad de no obtener un 6 en un lanzamiento: Es 1−1/6=5/6

    $3.$ Aplicar Independencia: Asumiendo que los lanzamientos de los dados son independientes (intuición que corresponde a la definición matemática), la probabilidad de que los 6 dados sean no-seises es el producto de las probabilidades individuales: 
    $$
    P(A^{c}) = \left( \frac{5}{6} \right)^{6}
    $$

    $4.$ Calcular $P(A)$: 
    $$
    P(A) = 1 - P(A^{c}) = 1 - \left( \frac{5}{6} \right)^{6}    
    $$

---

!!! Ejercicio_4
    Usted va a jugar 2 partidas de ajedrez con un oponente al que nunca se ha enfrentado. Su oponente tiene la misma probabilidad de ser un principiante, un intermedio o un maestro (1/3 cada uno). Dependiendo del nivel de habilidad de su oponente, sus posibilidades de ganar una partida individual son 90%, 50% o 30%, respectivamente.

    1. ¿Cuál es su probabilidad de ganar la primera partida?
    2. ¡Felicidades, usted ganó la primera partida! Dada esta información, ¿cuál es la probabilidad de que también gane la segunda partida? (Asuma que, dado el nivel de habilidad de su oponente, los resultados de las partidas son condicionalmente independientes).
    3. Explique la distinción entre asumir que los resultados de las partidas son independientes y asumir que son condicionalmente independientes dado el nivel de habilidad del oponente.


## Teorema de Bayes

El Teorema de Bayes es una herramienta esencial que nos permite relacionar $P(A∣B)$ con $P(B∣A)$, una relación que es a menudo necesaria ya que una de estas probabilidades suele ser mucho más fácil de encontrar directamente que la otra.


**El Teorema de Bayes y la Ley de Probabilidad Total**
La forma más útil de aplicar el Teorema de Bayes es combinándolo con la Ley de Probabilidad Total (LPT), especialmente cuando la probabilidad del evento de la evidencia,$ P(B)$, no se conoce fácilmente.

### Definición Teorema de Bayes
$$
P(A|B) = \frac{P(B|A)P(A)}{P(B)}
$$

### Definición Ley de Probabilidad Total (LPT): 
Si $A_1, A_2,..., A_n$ es una partición del espacio muestral $S$ (es decir, los $A_i$ son disjuntos y su unión es $S$), entonces la probabilidad de cualquier evento $B$ es la suma ponderada de las probabilidades de $B$ condicionadas por cada pieza de la partición:

$$
P(B) = \sum_{i=1}^{n} P(B|A_{i})P(A_{i})
$$

Al combinar ambos, se reemplaza el denominador $P(B)$ de Bayes con la expansión de la LPT:

$$
P(A_{i}|B) = \frac{P(B|A_{i})P(A_{i})}{P(B|A_{1})P(A_{1}) + P(B|A_{2})P(A_{2}) + \dots + P(B|A_{n})P(A_{n})}
$$

!!! Ejercicio_5
    Un paciente es sometido a una prueba para la enfermedad "conditionitis", que afecta al 1% de la población. El resultado de la prueba es positivo $(T)$. El test es "95% preciso", lo que se interpreta como:

    - Sensibilidad (tasa de verdadero positivo): $P(T∣D)=0.95$ (Prob. de positivo dado que tiene la enfermedad $D$).

    - Especificidad (tasa de verdadero negativo): $P(T^c|D^c)=0.95$ (Prob. de negativo dado que no tiene la enfermedad $D^c$)

    Calcule la probabilidad condicional de que el paciente tenga conditionitis dado un resultado positivo, $P(D∣T)$

??? Solución_5
    **1. Definir Priores:**
    $P(D) = 0.01$ (prevalencia de la enfermedad).
    $P(D^{c}) = 1 - 0.01 = 0.99$

    **2. Definir Probabilidades de la Prueba (Likelihoods):**
    $P(T|D) = 0.95$ (dado que tiene la enfermedad, el test es positivo).
    $P(T|D^{c}) = 1 - P(T^{c}|D^{c}) = 1 - 0.95 = 0.05$ (tasa de falso positivo)

    **3. Aplicar Bayes y LPT:** Utilizamos la partición $D$ y $D^{c}$ (tiene o no tiene la enfermedad).

    $$P(D|T) = \frac{P(T|D)P(D)}{P(T|D)P(D) + P(T|D^{c})P(D^{c})}$$

    Sustituyendo los valores:

    $$P(D|T) = \frac{0.95 \cdot 0.01}{(0.95 \cdot 0.01) + (0.05 \cdot 0.99)}$$

    $$P(D|T) = \frac{0.0095}{0.0095 + 0.0495} = \frac{0.0095}{0.0590} \approx 0.16$$

    Conclusión: Hay solo un 16% de probabilidad de que el paciente tenga la enfermedad dado que la prueba fue positiva, a pesar de que la prueba es "95% precisa". Esto se debe a que la rareza de la enfermedad (1%) juega un papel crucial, haciendo que los falsos positivos superen en número a los verdaderos positivos en la población general.

---

!!! Ejercicio_6
    Un filtro de spam está diseñado observando frases comunes en el spam. Suponga que el 80% del correo electrónico es spam.

    - En el 10% de los correos spam, se utiliza la frase "dinero gratis".

    - Esta frase solo se usa en el 1% de los correos no spam.

    Acaba de llegar un nuevo correo electrónico que menciona "dinero gratis". ¿Cuál es la probabilidad de que sea spam?

    (Sugerencia: Defina S como el evento de que el correo es spam y F como el evento de que contiene la frase "dinero gratis". Busque P(S|F)).


