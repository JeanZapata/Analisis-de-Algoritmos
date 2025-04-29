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
