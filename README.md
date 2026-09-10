# Proyecto de Cómputo Paralelo

"El proyecto consiste en estimar el valor de la constante matemática Pi, mediante una simulación de Monte Carlo masiva." 

Se simulará la generación de N coordenadas aleatorias sobre un cuadrado de área 4 que inscribe un circulo de radio r = 1. La proporción entre los puntos que caen dentro del área del círculo (evaluados matemáticamente mediante la ecuación x^2 + y^2 <= 1 y el total de puntos generados, permitirá aproximar el valor de pi a medida que N tiende al infinito.

Definiciones a tener en cuenta:

-Método de Monte Carlo: Técnica que usa la probabilidad y números aleatorios para aproximar el valor de pi (en este caso). En general, utiliza un muestreo aleatorio repetido para obtener la probabilidad de que ocurra una serie de resultados. 

  -Tiempo secuencial: Es la medición de cuánto tarda el programa en resolver el problema con un solo hilo para tener un punto de comparación con una versión futura del programa. Para medir este tiempo se hace uso del Speedup..
        Speedup: Métrica matemática que nos dice cuántas veces es más rápido el programa en                 paralelo en comparación con el secuencial. 

  -Versión secuencial: Este se define como las instrucciones que se ejecutan una detrás de otra. Utilizando un solo núcleo del procesador. 

VERSIÓN SECUENCIAL (V1) ---> También es llamado "Línea base" --- H0 - Propuesta 

Equipo: 10

*Problema candidato: Estimación de Pi (H0)

Imaginar que tenemos un tablero de dardos cuadrado que mide 2 x 2 metros. Justo en el centro, dibujamos un círculo que toca los cuatro bordes del cuadrado. Ese círculo tiene un radio de r = 1.Si lanzamos muchos dardos completamente al azar hacia el tablero, algunos caerán dentro del círculo y otros en las esquinas del cuadrado (fuera del círculo).

  ¿Esto qué tiene que ver con nuestro problema con el calculo del número Pi?

  Área del cuadrado: 4
  Área del circulo: 1

  Si dividimos el área del círculo entre el área del cuadrado, obtenemos la probabilidad exacta de que un dardo caiga dentro del círculo: pi/4 = 45 y si volvemos a multiplicar este resultado, nos da el mismo pi. 

  La computadora no puede ver si un dardo (punto aleatorio) cayó dentro del círculo dibujado, este necesita de reglas o ecuaciones matemáticas. Por eso usamos esa ecuación. 

  *¿POR QUÉ ES PARALELIZABLE?

  Cuando generamos un dardo aleatorio, dandole un plano (x,y), usamos el Teorema de Pitágoras. Calcula la distancia desde el centro del tablero (0,0) hasta donde cayó el dardo (x,y). Hay dos posibilidades: 
    -Si la suma de las coordenadas al cuadrado es menor o igual a 1, el dardo está a una distancia permitida y cayó dentro del circulo. 
    -Si es mayor a 1, el dardo cayó en una esquina, fuera del círculo. 

Hacemos uso de esto, porque si lanzamos muy pocos puntos (dardos) nos dará un valor muy malo y nada preciso de pi. Para que sea preciso, necesitamos muchos puntos (dardos). Es por eso que es un problema que se puede dividir el trabajo, en lugar de evaluar punto por punto, usando múltples hilos de procesamiento al mismo tiempo. 


DATOS: 



¿QUÉ VERSIONES SE HARÁN? 

  






