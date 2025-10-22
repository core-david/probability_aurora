

## Bloque 1: VA, FMP y FDA
![type:video](videos\Variables_Aleatorias.mp4)

### Variable Aleatoria (RV)

> **Definición:**
Una **Variable Aleatoria (VA)**, denotada comúnmente como $X$, es fundamentalmente una **función**.

La función de la variable aleatoria es mapear los resultados de un experimento aleatorio (el espacio muestral, $S$) a valores numéricos reales ($\mathbb{R}$).

**Explicación Intuitiva:**
Piense en la VA como un resumen numérico del experimento. Realizamos un experimento (lanzar un dado, una secuencia de ensayos, etc.), y el resultado de ese experimento, aunque aleatorio, se traduce en un número. La aleatoriedad de la variable $X$ proviene enteramente de la aleatoriedad del experimento subyacente.

Por ejemplo, si lanzamos una moneda, el resultado no es un número ("Cara" o "Cruz"). Una VA simple podría asignar $1$ a "Cara" y $0$ a "Cruz".

**Ejemplo: Variable Indicadora / Bernoulli**

El tipo de variable aleatoria más simple, aparte de una constante, es aquella que solo toma dos valores posibles, $0$ o $1$. Esto se conoce como la distribución de Bernoulli, $Bern(p)$.

Una **variable indicadora** $I_A$ es un tipo de RV Bernoulli. Se define como:

$I_A = \begin{cases} 1 & \text{si el evento } A \text{ ocurre} \\ 0 & \text{si el evento } A \text{ no ocurre} \end{cases}$


### Distribuciones Discretas y Función de Masa de Probabilidad (FMP)

>**Definición:**
Una variable aleatoria es **discreta** si el conjunto de sus posibles valores es contable; es decir, si los valores pueden listarse (ya sea una lista finita o una lista infinita). Un ejemplo común es cuando la VA toma valores enteros no negativos, como $0$, $1$, $2$, $3$, etc.

Para describir la distribución de una VA discreta, utilizamos la **Función de Masa de Probabilidad (PMF)**.

La PMF de una VA discreta $X$ especifica la probabilidad de que $X$ tome exactamente un valor $x$. Se denota como $P(X = x)$.

**Propiedades de la FMP:**

$1$. La probabilidad de que $X$ tome cualquier valor particular debe ser no negativa ($P(X = x) \ge 0$).

$2$. La suma de todas las probabilidades para todos los valores posibles de $X$ debe ser igual a $1$.

**Ejemplo: FMP Binomial**

La distribución **Binomial** $Bin(n, p)$ es un ejemplo fundamental de una distribución discreta. Su historia es la de contar el número de éxitos en $n$ ensayos independientes de Bernoulli, donde $p$ es la probabilidad de éxito en cada ensayo.

La FMP para una RV $X \sim Bin(n, p)$ es:
$$
P(X = k) = \binom{n}{k} p^k (1 - p)^{n-k}
$$
donde $k$ es el número de éxitos, $0 \le k \le n$. Esta fórmula actúa como el "plano" de la VA, asignando una masa de probabilidad a cada número posible de éxitos.


### La Función de Distribución Acumulada (FDA)

> **Definición:** La **Función de Distribución Acumulada (FDA)**, denotada por $F(x)$, describe la probabilidad de que una variable aleatoria $X$ tome un valor menor o igual a un número real específico $x$.

**Su definición formal es:**
$$
F(x) = P(X \le x)
$$
La FDA es una función definida para todos los números reales $x$. Es importante porque, a diferencia de la FMP (que solo funciona para RVs discretas), la FDA puede describir la distribución de **cualquier** variable aleatoria (discreta, continua o mixta). Además, al conocer la FDA, se pueden calcular todas las demás probabilidades relacionadas con $X$.

**Discusión de las Propiedades de la FDA:**

La gráfica de cualquier FDA debe satisfacer tres propiedades clave, visibles en el ejemplo de una VA discreta:

**1. Monotonía (Creciente):** La FDA es una función no decreciente. A medida que el valor de $x$ (eje horizontal) aumenta, la probabilidad acumulada $F(x)$ debe aumentar o permanecer constante, pero nunca puede disminuir.

**2. Límite Inferior (a 0):** Cuando $x$ tiende a menos infinito ($x \to -\infty$), el valor de la FDA se aproxima a cero ($F(x) \to 0$). Intuitivamente, la probabilidad de que la VA tome un valor extremadamente pequeño es cero.

**3. Límite Superior (a 1):** Cuando $x$ tiende a infinito ($x \to \infty$), el valor de la FDA se aproxima a uno ($F(x) \to 1$). Esto significa que es seguro (probabilidad $1$) que la VA tomará algún valor real.


## Introducción al Concepto de Parámetro

**Definición:** Los **parámetros** son números que definen una distribución específica dentro de una familia de distribuciones. Si se cambian los valores de los parámetros, se obtiene una distribución diferente, aunque siga perteneciendo a la misma "familia" (por ejemplo, sigue siendo Binomial o Poisson).

**Ejemplos de Parámetros:**

* **Binomial:** La distribución $Bin(n, p)$ tiene dos parámetros:
    * $n$: el número fijo de ensayos.
    * $p$: la probabilidad de éxito individual.
* **Poisson:** La distribución $Pois(\lambda)$ tiene un solo parámetro, $\lambda$ ($\lambda > 0$). Este parámetro se interpreta como la tasa media de ocurrencia de los eventos que se están contando.


## Bloque 2: Valor Esperado y Linealidad
![type:video](videos\linealidad.mp4)

### Valor Esperado (Media)

> **Definición:** El **valor esperado** de una variable aleatoria (VA) $X$, también conocido como la esperanza o la media $E(X)$, es un número que se utiliza para resumir el "valor promedio" de la variable. Aunque la distribución de una variable aleatoria proporciona información completa sobre las probabilidades de que la VA caiga en cualquier conjunto particular, gestionar tantas probabilidades puede ser complicado, por lo que a menudo se busca un único número que resuma el valor medio.

La definición de la esperanza para una variable aleatoria discreta se inspira en el concepto de la media ponderada de una lista de números.

**Definición de $E(X)$**

Para una variable aleatoria discreta $X$ con posibles valores $x_1, x_2, ...$, el valor esperado se define como un promedio ponderado de sus posibles valores:

$$E(X) = \sum_{x} x P(X = x)$$

En palabras, el valor esperado de $X$ es un **promedio ponderado** de los posibles valores que $X$ puede tomar, ponderado por las probabilidades de cada valor.

**Explicación Intuitiva y Ejemplo**

Considera el lanzamiento de un dado justo de $6$ caras. La variable aleatoria $X$ toma los valores $1, 2, 3, 4, 5, 6$, cada uno con una probabilidad igual de $1/6$.

**1. Cálculo:** Aplicando la definición del valor esperado:

$$E(X) = (1)\frac{1}{6} + (2)\frac{1}{6} + (3)\frac{1}{6} + (4)\frac{1}{6} + (5)\frac{1}{6} + (6)\frac{1}{6}$$


**2. Resultado:**

$$E(X) = \frac{1}{6}(1 + 2 + 3 + 4 + 5 + 6) = 3.5$$

Intuitivamente, este resultado ($3.5$) es el promedio que esperaríamos obtener. Es importante notar que el valor esperado de $X$ no necesariamente es un valor que $X$ puede alcanzar. Por ejemplo, un dado nunca caerá en $3.5$.


### Linealidad de la Expectativa

La propiedad más importante de la esperanza es la **linealidad**. La linealidad permite simplificar enormemente el cálculo de valores esperados, a menudo permitiendo evitar la definición directa.

**Propiedades de la Linealidad**

Para cualesquiera variables aleatorias $X$, $Y$ y cualquier constante $c$, la linealidad establece dos reglas fundamentales:

**1. Suma de Expectativas:** El valor esperado de una suma de variables aleatorias es la suma de los valores esperados individuales:

$$E(X + Y) = E(X) + E(Y)$$

**2. Constantes:** Los factores constantes pueden ser sacados de la esperanza:

$$E(cX) = cE(X)$$

**Énfasis en la Dependencia**

Lo que resulta sorprendente de la Linealidad de la Expectativa es que la propiedad $E(X + Y) = E(X) + E(Y)$ se mantiene **incluso si $X$ y $Y$ son dependientes**.

**Intuición del caso extremo (Dependencia):**

Para construir una intuición, considera el caso extremo de dependencia: cuando $X$ siempre es igual a $Y$.

* En este caso, la variable $X + Y$ es en realidad $2X$.

* Aplicando la regla del factor constante: $E(X + Y) = E(2X) = 2E(X)$.

* La suma de las expectativas es: $E(X) + E(Y) = E(X) + E(X) = 2E(X)$.

Dado que $2E(X) = 2E(X)$, la linealidad se mantiene incluso en esta situación de dependencia máxima.

**Intuición mediante Simulación y Promedios Aritméticos:**

Una forma de entender por qué la linealidad se cumple sin importar la dependencia es viéndola como un simple hecho sobre la aritmética.

Imaginemos que realizamos un experimento un número muy grande ($n$) de veces, registrando los valores de $X$, los valores de $Y$, y los valores de la suma $X + Y$ en tres columnas.

$$
\begin{array}{|c|c|c|c|}
\hline
\textbf{Repetición} & \textbf{X} & \textbf{Y} & \textbf{X + Y} \\
\hline
1 & x_1 & y_1 & x_1 + y_1 \\
\hline
2 & x_2 & y_2 & x_2 + y_2 \\
\hline
... & ... & ... & ... \\
\hline
n & x_n & y_n & x_n + y_n \\
\hline
\end{array}
$$

Hay dos maneras de calcular la suma total de los números en la última columna ($X + Y$):

1. Sumar directamente todos los números en la columna $X + Y$.

2. Sumar todos los números en la columna $X$, sumar todos los números en la columna $Y$, y luego sumar estos dos resultados.


Estos dos procedimientos deben dar el mismo resultado. Si dividimos ambas sumas por $n$ (el número de repeticiones), obtenemos el promedio aritmético de cada columna.

* El promedio de la columna $X + Y$ se acerca a $E(X + Y)$.

* La suma de los promedios de las columnas $X$ y $Y$ se acerca a $E(X) + E(Y)$.

Dado que el promedio de la última columna es igual a la suma de los promedios de las dos primeras columnas, se demuestra que $E(X + Y) = E(X) + E(Y)$, y esto no depende de si los valores de $X$ y $Y$ en cada fila (repetición) están relacionados o no.


## Bloque 3: Varianza, Desviación Estándar y LOTUS

### Varianza

>**Definición:** 
La **Varianza** ($Var(X)$) es una medida fundamental que nos indica **qué tan dispersa o extendida está la distribución** de una variable aleatoria $X$. Mientras que la esperanza o media ($E(X)$) nos dice dónde está el "centro de masa" de la distribución, la varianza cuantifica su variabilidad.

**Definición Funcional: La Desviación Cuadrada Promedio**

La varianza de una variable aleatoria $X$ se define formalmente como la **esperanza de la desviación cuadrada** de $X$ respecto a su media $EX$:

$$Var(X) = E[(X - E(X))^2]$$

**Explicación Intuitiva (¿Por qué la cuadramos?):** La varianza mide qué tan lejos está $X$ de su media, en promedio. Podríamos intentar calcular la desviación promedio $E(X - EX)$, pero esta cantidad siempre es igual a cero debido a la propiedad de linealidad de la esperanza: las desviaciones positivas y negativas se anulan mutuamente.

Al elevar al cuadrado las desviaciones $(X - EX)^2$, nos aseguramos de que tanto las desviaciones positivas como las negativas contribuyan al cálculo de la variabilidad total.

**Definición para el Cálculo**

Una fórmula equivalente, a menudo más fácil de usar para cálculos reales, es:

$$Var(X) = E(X^2) - (E(X))^2$$

Esta expresión se deriva expandiendo la definición fundacional y aplicando la linealidad de la esperanza:

$E((X - \mu)^2) = E(X^2 - 2\mu X + \mu^2) = E(X^2) - 2\mu E(X) + \mu^2$, donde $\mu = E(X)$.

Partimos de:

$$E(X^2) - 2\mu E(X) + \mu^2$$

Sabemos por definición que $\mu = E(X)$. Sustituimos $E(X)$ por $\mu$ en el segundo término:

$$E(X^2) - 2\mu(\mu) + \mu^2$$

Ahora, multiplicamos los términos $\mu$:

$$E(X^2) - 2\mu^2 + \mu^2$$

Finalmente, combinamos los términos semejantes ($-2\mu^2$ y $+\mu^2$):

$$E(X^2) - \mu^2$$

### Desviación Estándar

La **Desviación Estándar** ($SD(X)$) es simplemente la raíz cuadrada de la varianza:

$$SD(X) = \sqrt{Var(X)}$$


**Explicación Intuitiva (Unidades):** Dado que la varianza es un promedio de distancias elevadas al cuadrado, tiene unidades incorrectas. Si $X$ se mide en dólares, $Var(X)$ se mide en "dólares cuadrados".
La Desviación Estándar nos permite volver a las unidades originales de la variable aleatoria $X$ al tomar la raíz cuadrada, lo cual facilita la interpretación de la dispersión.


### Varianza No Lineal

A diferencia de la esperanza, que es siempre lineal, la varianza **no es lineal**.

**1. Multiplicación por una constante:** Si multiplicamos $X$ por una constante $c$, esta sale de la varianza elevada al cuadrado:

$$Var(cX) = c^2Var(X)$$

*Intuitivamente:* La constante sale al cuadrado porque la varianza mide la distancia cuadrática a la media.

**2. Suma de variables aleatorias:** En general, la varianza de una suma no es la suma de las varianzas:

$$Var(X + Y) \neq Var(X) + Var(Y)$$

*Nota importante:* La aditividad de la varianza ($Var(X + Y) = Var(X) + Var(Y)$) solo es cierta si $X$ y $Y$ son variables aleatorias independientes. Si son dependientes, la igualdad no se mantiene.


### Ley Estadístico Inconsciente (LOTUS)

Para calcular la varianza usando la fórmula $Var(X) = E(X^2) - (EX)^2$, necesitamos calcular $E(X^2)$. Para hacer esto correctamente, utilizamos la **Ley del Estadístico Inconsciente (LOTUS)**.

LOTUS es crucial porque, en general, la esperanza de una función no lineal de $X$ **no** es igual a la función de la esperanza de $X$ (es decir, $E[g(X)] \neq g(E(X))$ si $g$ no es una función lineal).

**Definición de LOTUS**

Si $X$ es una variable aleatoria discreta y $g$ es una función, la esperanza de $g(X)$ se calcula como:

$$E[g(X)] = \sum_{x} g(x) P(X = x)$$


**Explicación Intuitiva (La Tentación del "Estadístico Inconsciente"):** El nombre de LOTUS proviene del hecho de que, para calcular $E[g(X)]$, es tentador simplemente reemplazar el valor $x$ en la definición de la esperanza por $g(x)$. Sorprendentemente, LOTUS afirma que este procedimiento mecánico, realizado casi inconscientemente, es correcto.

**LOTUS en el Cálculo de $E(X^2)$:** Para calcular $E(X^2)$, aplicamos LOTUS usando la función $g(x) = x^2$. Solo necesitamos la FMP de $X$ para calcular $E(X^2)$:

$$E(X^2) = \sum_{x} x^2 P(X = x)$$

**Ejemplo Intuitivo: $E[g(X)] \neq g(E(X))$** 

Considera el lanzamiento de una moneda justa hasta obtener la primera Cara (H). Sea $N$ el número total de lanzamientos (incluyendo el éxito). Si el pago $X$ es $2^N$ (dólares), queremos calcular $E(X)$.

* El número esperado de lanzamientos es $E(N) = 1/p = 1/(1/2) = 2$.

* Si calculamos $g(E(N))$, obtenemos $2^{E(N)} = 2^2 = 4$.

* Sin embargo, si calculamos el valor esperado real $E(X)$ usando la definición, se encuentra que $E(X) = \infty$ (la suma diverge).

Este ejemplo ilustra el peligro de confundir $E[g(X)]$ con $g(E(X))$ cuando la función $g$ (en este caso, $g(N)=2^N$) no es lineal.
