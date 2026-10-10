# Proyecto Integrador: Estimación de $\pi$ mediante Simulación de Monte Carlo
**Materia:** Cómputo Paralelo  
**Equipo:** 10  
**Fase Actual:** Propuesta H0 - Línea Base  

---

## 1. Descripción del Proyecto
El presente proyecto tiene como objetivo estimar el valor de la constante matemática $\pi$ a través de una simulación masiva utilizando el método de Monte Carlo. 

La simulación consiste en generar $N$ coordenadas aleatorias $(x, y)$ dentro de un cuadrado de área 4 que inscribe un círculo de radio $r = 1$. La proporción de puntos que caen dentro del área del círculo —evaluados matemáticamente mediante la inecuación $x^2 + y^2 \leq 1$— respecto al total de puntos generados, permite aproximar el valor de $\pi$ a medida que $N$ tiende al infinito ($N \to \infty$).

## 2. Marco Teórico y Conceptos Clave
Para la evaluación del rendimiento de este proyecto, se establecen los siguientes conceptos fundamentales:

* **Método de Monte Carlo:** Técnica computacional que utiliza muestreo estadístico y generación de números aleatorios para aproximar expresiones matemáticas complejas. En este caso, se emplea para calcular probabilidades geométricas.
* **Tiempo Secuencial:** Medición del tiempo total de ejecución que requiere el algoritmo para resolver el problema utilizando un único núcleo e hilo de procesamiento. Representa el punto de referencia absoluto.
* **Speedup (Ganancia de Velocidad):** Métrica de rendimiento que cuantifica cuántas veces es más rápida la ejecución paralela en comparación con su contraparte secuencial ($S = T_{secuencial} / T_{paralelo}$).

## 3. Fundamento Matemático
El problema se puede visualizar mediante la analogía de lanzar dardos aleatorios sobre un tablero cuadrado de $2 \times 2$ metros que contiene un círculo inscrito de radio $r = 1$:

* **Área del cuadrado:** $4r^2 = 4$
* **Área del círculo:** $\pi r^2 = \pi$

Dado un muestreo aleatorio uniforme, la probabilidad exacta ($P$) de que una coordenada caiga dentro del círculo es equivalente a la proporción de las áreas: 
$$P = \frac{\text{Área del círculo}}{\text{Área del cuadrado}} = \frac{\pi}{4}$$

Al multiplicar esta probabilidad experimental por 4, se aproxima el valor de $\pi$. Computacionalmente, la pertenencia al círculo se determina calculando la hipotenusa desde el origen $(0,0)$ usando el Teorema de Pitágoras:
* Si $x^2 + y^2 \leq 1$, el punto se encuentra **dentro** del círculo.
* Si $x^2 + y^2 > 1$, el punto se encuentra **fuera** del círculo.

## 4. Justificación de la Paralelización
La naturaleza algorítmica de este problema presenta un alto grado de paralelismo de datos. Dado que la generación y evaluación matemática de cada punto $(x, y)$ es un proceso estrictamente independiente de los demás, no existen dependencias de datos que bloqueen la ejecución. 

Para lograr una estimación con una precisión aceptable de $\pi$, se requiere que el volumen de iteraciones ($N$) sea computacionalmente masivo. Por lo tanto, el cálculo iterativo secuencial resulta ineficiente, haciendo de este algoritmo un candidato ideal para ser distribuido entre múltiples hilos y núcleos de procesamiento.

## 5. Metodología y Versiones de Desarrollo

### Versión 1 (V1): Línea Base Secuencial y Perfilado
Desarrollo de un programa base en lenguaje **C** ejecutado de forma escalar en un único núcleo. El algoritmo consistirá en un ciclo iterativo masivo para generar las coordenadas de punto flotante y contarlas. El objetivo estricto de esta fase es capturar el tiempo secuencial absoluto para las futuras métricas de rendimiento.

### Versión 2 (V2): Memoria Compartida (OpenMP)
Implementación de paralelismo de CPU mediante directivas de compilador **OpenMP**. El volumen masivo de iteraciones $N$ se fragmentará equitativamente y se distribuirá entre los múltiples hilos lógicos del procesador local, operando de manera simultánea sobre el mismo espacio de memoria RAM compartida.

### Versión 3 (V3): Aceleración Masiva por GPU (CUDA)
Escalamiento de la simulación trasladando el cómputo a un hardware acelerador. Se desarrollará un *kernel* en **CUDA** de NVIDIA. En lugar de utilizar los hilos del procesador central, la carga computacional será distribuida a través de bloques de hilos simultáneos dentro de la tarjeta gráfica (GPU), aprovechando su arquitectura paralela masiva.
