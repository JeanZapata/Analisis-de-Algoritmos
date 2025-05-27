# Semana 1: La Importancia de los Algoritmos en la Computación
Referencia: Cormen et al., 2022 – Introducción a los algoritmos

# ¿Qué es un algoritmo? 
* Un algoritmo es un conjunto de pasos finitos y bien definidos diseñados para resolver un problema o realizar una tarea. En la informática, los algoritmos son esenciales para procesar datos, resolver problemas computacionales y automatizar tareas.

# Características esenciales de un algoritmo 
* **Entrada(s) definida(s)**
* **Salida(s) esperada(s)**
* **Claridad y precisión en los pasos**
* **Finitud**: el algoritmo termina después de un número finito de pasos
* **Efectividad**: cada paso debe ser ejecutable

# Ejemplo clásico 
* El algoritmo de Euclides para calcular el máximo común divisor (MCD) es un ejemplo de cómo se puede resolver eficientemente un problema matemático utilizando un conjunto claro de pasos.

# Los algoritmos como herramienta tecnológica 
* Los algoritmos no solo son fundamentales a nivel teórico, sino que también son cruciales en la tecnología moderna. Permiten desarrollar software eficiente, optimizar recursos y crear sistemas avanzados.

# Comparativa de algoritmos 
* La comparación entre diferentes algoritmos para resolver un mismo problema, como el de ordenación, demuestra cómo el rendimiento varía significativamente, lo cual impacta directamente en la escalabilidad y el rendimiento del sistema.

# Fundamentos Básicos en Algoritmia 
Referencia: Brassard & Bratley

# Diferencias con Cormen 
| Aspecto                | Cormen et al. (2022)               | Brassard y Bratley                |
|------------------------|------------------------------------|-----------------------------------|
| Enfoque                | Teórico y académico                | Enfoque práctico y pedagógico     |
| Ejemplos               | MCD, algoritmos clásicos           | Algoritmos simples y visuales    |
| Introducción al análisis| Asintótica desde el inicio         | Análisis gradual e intuitivo     |
| Público ideal          | Lectores con bases teóricas       | Estudiantes principiantes        |

# Semana 2: Fundamentos de Algoritmia
Referencia: Brassard & Bratley

# Introducción
 * Este capítulo introduce los principios básicos para diseñar algoritmos, usando ejemplos prácticos y explicaciones claras. Enseña cómo crear algoritmos sencillos y analizar su rendimiento de manera preliminar, empleando diagramas de flujo y pseudocódigo.

# Principales temas
 * Proceso de diseño de algoritmos

    * El diseño de algoritmos implica crear soluciones estructuradas paso a paso. Ejemplos incluyen ordenar listas o buscar un valor específico.

# Algoritmos secuenciales  
* Son algoritmos que ejecutan pasos de forma lineal, sin ramificaciones ni repeticiones. Ejemplos simples son la suma de números o la búsqueda del valor máximo en un conjunto pequeño.

# Algoritmos iterativos  
* Utilizan ciclos de repetición como "mientras" (while) o "para" (for). Ejemplos incluyen el cálculo del factorial de un número o la búsqueda en una lista.

# Algoritmos condicionales
* Emplean decisiones dentro del algoritmo utilizando estructuras de control como "si... entonces... sino".

# Ordenamiento por inserción (Insertion Sort)
Un algoritmo explicado con ejemplos visuales paso a paso, analizando su complejidad en casos ideales y desfavorables.

# Evaluación preliminar de eficiencia
* Se introduce la noción de medir el rendimiento del algoritmo contando los pasos, sin entrar aún en notaciones asintóticas complejas.

# Semana 3: Principios del Diseño de Algoritmos ==
Referencia: Cormen et al., 2022 – Introducción a los algoritmos

# ¿Qué implica diseñar un algoritmo? 
* Diseñar un algoritmo es el proceso de encontrar una solución estructurada y clara para un problema. Cormen aborda los fundamentos del diseño, destacando la importancia de la creatividad y el análisis en la resolución de problemas computacionales.

# Estrategias principales en diseño
* **Dividir y conquistar 
     * Consiste en descomponer un problema en subproblemas más pequeños, resolverlos de forma recursiva y luego combinar las soluciones obtenidas.

# Algoritmos codiciosos (Greedy)  
* Se toma la decisión más favorable en cada paso, con la esperanza de que esta elección local llevará a una solución global óptima.

# Programación dinámica  
* Resuelve subproblemas de manera eficiente almacenando soluciones intermedias para evitar cálculos repetidos.

# Fuerza bruta  
* Consiste en probar todas las posibles soluciones, siendo válida solo para problemas pequeños.

# Consideraciones importantes al diseñar un algoritmo ====
* Corrección**: El algoritmo debe generar resultados correctos para todas las entradas válidas.
* Eficiencia**: Evaluar el tiempo y espacio requerido utilizando notación asintótica.
* Claridad y mantenimiento**: El algoritmo debe ser fácil de entender, modular y fácil de modificar si es necesario.

# Proceso iterativo del diseño 
El diseño de un algoritmo no es un proceso lineal; es un ciclo continuo que involucra:
* Comprender el problema.
* Crear una solución inicial.
* Refinar y probar la solución.
* Optimizarla si es necesario.


```java
public class MergeSort {

    // Método para mezclar (merge) dos subarreglos de A[]
    // El primer subarreglo es A[p..q]
    // El segundo subarreglo es A[q+1..r]
    public static void merge(int[] A, int p, int q, int r) {
        int nL = q - p + 1; // longitud del subarreglo izquierdo
        int nR = r - q;     // longitud del subarreglo derecho

        // Crear arreglos temporales para L[] y R[]
        int[] L = new int[nL];
        int[] R = new int[nR];

        // Copiar datos a los arreglos temporales L[] y R[]
        for (int i = 0; i < nL; i++) {
            L[i] = A[p + i];
        }
        for (int j = 0; j < nR; j++) {
            R[j] = A[q + 1 + j];
        }

        // Mezclar los arreglos temporales de nuevo en A[p..r]
        int i = 0; // Índice inicial para L[]
        int j = 0; // Índice inicial para R[]
        int k = p; // Índice inicial para A[]

        while (i < nL && j < nR) {
            if (L[i] <= R[j]) {
                A[k] = L[i];
                i++;
            } else {
                A[k] = R[j];
                j++;
            }
            k++;
        }

        // Copiar los elementos restantes de L[], si hay alguno
        while (i < nL) {
            A[k] = L[i];
            i++;
            k++;
        }

        // Copiar los elementos restantes de R[], si hay alguno
        while (j < nR) {
            A[k] = R[j];
            j++;
            k++;
        }
    }
}
```

# Semana 4: Análisis de Algoritmos
**Referencia:** Brassard & Bratley

## Objetivo del análisis
El análisis de algoritmos permite comparar distintas soluciones para un mismo problema y decidir cuál es la más adecuada en función del tiempo de ejecución y otros recursos. No hay fórmulas exactas, pero existen técnicas útiles basadas en intuición, experiencia y el manejo correcto de estructuras de control y recurrencias.

---

## Análisis de estructuras de control

### Secuencias
* Si un algoritmo ejecuta dos fragmentos P₁ y P₂, el tiempo total será `t₁ + t₂`.
* En notación asintótica se toma el mayor: `O(max(t₁, t₂))`.

### Bucles “para” (for)
* Si una instrucción dentro del bucle se ejecuta `m` veces y cada una tarda `t`, el tiempo total es `mt`.
* Se debe considerar también el tiempo de control del bucle, especialmente si `m = 0`.

### Bucles “mientras” (while)
* Más difíciles de analizar, pues dependen de cuándo se cumple la condición de salida.
* Se usa una función monótona decreciente (función de medida) para estimar la cantidad de iteraciones.

---

## Llamadas recursivas
* Se modelan mediante ecuaciones de recurrencia.
* Por ejemplo, la versión recursiva de Fibonacci tiene tiempo exponencial.
* Resolver la recurrencia da el tiempo asintótico del algoritmo.

---

## Barómetros
* Se elige una instrucción representativa (barómetro) que se repite frecuentemente.
* Se analiza su número de ejecuciones para estimar el tiempo total.
* Ejemplo: En Insertion Sort, el número de comparaciones en el peor caso es `O(n²)`.

---

## Algoritmo de Euclides
* Disminuye significativamente los valores en cada iteración.
* Su tiempo de ejecución está en `O(log n)` debido al rápido decrecimiento del número mayor.

---

## Caso medio vs peor caso
* El análisis del caso medio requiere suponer una distribución probabilística.
* En ordenación por inserción, el caso medio es más eficiente que el peor, pero depende de que las permutaciones sean igualmente probables.

---

## Análisis amortizado
* Útil cuando un algoritmo tiene operaciones costosas pero poco frecuentes.
* Se calcula el costo promedio por operación a lo largo de una secuencia de operaciones.
* Ejemplo: si una operación cuesta `O(log n)` solo ocasionalmente, pero normalmente es `O(1)`, el análisis amortizado da una mejor estimación.

---

## Resolución de recurrencias

### Suposiciones inteligentes
1. Calcular valores iniciales
2. Detectar un patrón
3. Proponer una fórmula general
4. Verificar por inducción

### Ecuación característica
* Aplica a recurrencias lineales con coeficientes constantes.
* Permite encontrar soluciones generales usando raíces del polinomio asociado.

### Recurrencias no homogéneas y cambios de variable
* Se pueden resolver emparedando la función entre dos recurrencias simples.
* A veces conviene transformar variables o el intervalo del problema.

---


## Semana 5: Estructuras de Datos
**Referencia:** Brassard & Bratley

### Tipos comunes

* **Arreglos (Arrays):**
  * Permiten acceso directo a cualquier elemento en tiempo constante `O(1)`.
  * Operaciones globales como inicialización o búsqueda requieren `O(n)`.

* **Registros y punteros:**
  * Un registro almacena múltiples campos de diferentes tipos.
  * Los punteros permiten crear estructuras dinámicas como listas y árboles enlazados.

* **Listas:**
  * Permiten operaciones como insertar, borrar o recorrer nodos.
  * Las implementaciones varían (simples, dobles, circulares), afectando el costo de las operaciones.

* **Pilas y colas:**
  * **Pilas (Stack):** estructura LIFO, útil en llamadas recursivas o evaluación de expresiones.
  * **Colas (Queue):** estructura FIFO, utilizada en planificación de tareas y sistemas de colas.

---

### Estructuras avanzadas

* **Árboles:**
  * Estructura jerárquica donde cada nodo puede tener varios hijos.
  * Base para estructuras como árboles binarios de búsqueda, AVL o heaps.

* **Grafos:**
  * Conjunto de nodos y conexiones (aristas), usados para modelar redes.
  * Se representan mediante listas de adyacencia o matrices de conexión.

* **Montículos (Heaps):**
  * Árbol binario esencialmente completo con la propiedad de orden del heap.
  * Usados para implementar colas de prioridad y el algoritmo heapsort.
  * Operaciones principales como insertar y eliminar el máximo requieren `O(log n)`.

* **Montículos binomiales:**
  * Permiten una fusión eficiente de montículos en `O(log n)`.
  * Se componen de árboles binomiales con propiedades estructurales combinatorias.

* **Tablas asociativas:**
  * Similar a un arreglo, pero el índice puede ser cualquier valor (incluidas cadenas).
  * Uso de funciones hash para indexación. Acceso esperado `O(1)`, aunque puede ser peor en caso de colisiones.

* **Conjuntos disjuntos (Union-Find):**
  * Gestiona particiones dinámicas de elementos.
  * Operaciones de unión y búsqueda eficientes con compresión de caminos (`O(α(n))`, donde α es la inversa de Ackermann).
  * Fundamental en algoritmos de grafos como el de Kruskal.

---

## Semana 6: Algoritmos Voraces
**Referencia:** Brassard & Bratley

### ¿Qué es un algoritmo voraz?
* Estrategia para resolver problemas de optimización.
* Toma decisiones paso a paso eligiendo siempre la opción más prometedora en el momento.
* No reconsidera decisiones previas, lo que simplifica la implementación.

---

### Características generales
* **Construcción progresiva de la solución:** se va armando paso a paso.
* **Función de selección:** elige el mejor candidato en cada paso.
* **Condición de factibilidad:** verifica si la solución parcial puede llegar a ser válida.
* **Función objetivo:** evalúa la calidad de la solución obtenida (valor, costo, tiempo, etc.).
* **Criterio de solución:** determina si la solución es completa y válida.

---

### Ejemplos clásicos

#### Árboles de recubrimiento mínimo

* **Algoritmo de Kruskal:**
  * Añade aristas de menor peso sin formar ciclos.
  * Utiliza conjuntos disjuntos (union-find).
  * Eficiente para grafos dispersos.

* **Algoritmo de Prim:**
  * Expande una sola componente conectada añadiendo la arista más barata.
  * Eficiente con montículos (colas de prioridad).

#### Caminos mínimos en grafos

* **Algoritmo de Dijkstra:**
  * Calcula la distancia más corta desde un nodo origen a todos los demás.
  * Usa dos conjuntos: uno con distancias conocidas (S) y otro con nodos candidatos (C).
  * Iterativamente selecciona el nodo más cercano.

---

### Problemas de planificación

* **Minimización del tiempo medio en el sistema:**
  * Se ordenan las tareas por tiempo de ejecución ascendente.
  * Minimiza el tiempo de espera acumulado de todas las tareas.

* **Planificación con plazos y beneficios:**
  * Cada tarea tiene un beneficio y un plazo.
  * Se seleccionan tareas con mayor beneficio siempre que la planificación siga siendo válida.

---

### Problema de la mochila fraccionaria

* Se pueden fraccionar los objetos.
* Se ordenan por valor/peso y se agregan en ese orden.
* Se detiene cuando se llena la mochila.
* Solución óptima garantizada con estrategia voraz.

---

## Semana 7: Divide y Vencerás
**Referencia:** Brassard & Bratley

### ¿Qué es la técnica de divide y vencerás?
* Estrategia algorítmica que divide un problema en subproblemas más pequeños del mismo tipo, los resuelve de forma recursiva y luego combina las soluciones.
* Mejora la eficiencia al reducir el tamaño del problema en cada paso.

---

### Esquema general del enfoque

1. **Dividir:** separar el problema en uno o más subproblemas más pequeños.
2. **Vencer (resolver):** resolver recursivamente cada subproblema.
3. **Combinar:** integrar las soluciones de los subproblemas en una solución global.

---

### Aplicaciones y ejemplos

#### Búsqueda binaria
* Caso más simple de divide y vencerás.
* Divide la búsqueda en mitades sucesivas.
* Requiere tiempo `O(log n)` para encontrar un elemento en una lista ordenada.

#### Ordenamiento

* **Mergesort:**
  * Divide el arreglo en mitades, ordena cada una y luego las fusiona.
  * Complejidad: `O(n log n)`.

* **Quicksort:**
  * Selecciona un pivote y particiona el arreglo alrededor de él.
  * Ordena las particiones recursivamente.
  * Promedio: `O(n log n)`, Peor caso: `O(n²)` si el pivote es mal elegido.

#### Búsqueda de la mediana y selección
* Se puede encontrar la mediana sin ordenar completamente.
* Selección basada en partición similar a quicksort, eligiendo pivotes inteligentes.

#### Multiplicación rápida de enteros
* Algoritmos como Karatsuba reducen el número de multiplicaciones.
* El enfoque divide números grandes en mitades y los multiplica recursivamente.

#### Multiplicación de matrices
* Algoritmos como el de Strassen reducen las multiplicaciones necesarias de `n³` a aproximadamente `O(n^2.81)`.

---

### Exponenciación rápida
* Utiliza la técnica de descomposición del exponente en potencias de 2.
* Permite calcular potencias grandes en `O(log n)` multiplicaciones.

---

### Ventajas y consideraciones
* Reduce significativamente el tiempo para problemas grandes.
* Los algoritmos recursivos consumen más memoria (uso de pila).
* A veces se puede transformar la recursividad en iteración para ahorrar espacio.

---






