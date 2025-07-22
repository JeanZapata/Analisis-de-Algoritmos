# 📚 Semana 11 – Divide y Vencerás (Divide-and-Conquer)

**Referencias:**
- Brassard, G., & Bratley, P. (2006). *Fundamentals of Algorithmics*. Prentice Hall.
- Cormen, T. H., Leiserson, C. E., Rivest, R. L., & Stein, C. (2022). *Introduction to Algorithms*, 4ª edición. MIT Press.

---

## 🧠 ¿Qué es Divide y Vencerás?

La técnica de **Divide y Vencerás** es un enfoque de diseño algorítmico que consiste en descomponer un problema grande en varios subproblemas más pequeños, resolver cada uno de ellos de forma recursiva, y combinar sus soluciones para obtener la respuesta final.

> Es especialmente útil en problemas que presentan una estructura recursiva natural, y permite desarrollar algoritmos más eficientes que los métodos puramente iterativos o de fuerza bruta.

---

## 🔧 Esquema general

```plaintext
function DivideYVenceras(problema):
    si el problema es pequeño o simple:
        resolver directamente
    si no:
        dividir el problema en partes
        resolver cada parte recursivamente
        combinar las soluciones

 Ejemplos clásicos
📍 Ordenamiento por mezcla (Merge Sort)

    -Divide el arreglo en dos mitades.
    -Ordena recursivamente cada mitad.
    -Combina las mitades ordenadas.

Complejidad: O(n log n)
📍 Ordenamiento rápido (Quick Sort)

    -Selecciona un pivote.
    -Divide el arreglo en elementos menores y mayores que el pivote.
    -Ordena recursivamente los subconjuntos.

Complejidad promedio: O(n log n)
Peor caso: O(n²)
📍 Multiplicación rápida de enteros (Karatsuba)

    -Divide los números grandes en mitades.
    -Aplica tres multiplicaciones recursivas.
    -Combina con desplazamientos de base (potencias de 10).

Complejidad: O(n^log₂3) ≈ O(n^1.585)
📍 Búsqueda binaria

    -Divide el arreglo a la mitad.
    -Decide en qué mitad continuar la búsqueda.

Complejidad: O(log n)
⏱️ Análisis de complejidad

Muchos algoritmos de tipo divide y vencerás se expresan mediante relaciones de recurrencia. Ejemplo:

T(n) = 2T(n/2) + O(n)  ⟹  T(n) = O(n log n)

Se puede resolver usando:

    -Árboles de recurrencia
    -Master Theorem (Teorema maestro)

📘 Teorema Maestro (Cormen et al., 2022)

Se usa para resolver recurrencias de la forma:

T(n) = a·T(n/b) + f(n)

Donde:

    -a ≥ 1, número de subproblemas.
    -b > 1, factor de reducción de tamaño.
    -f(n), costo para dividir y combinar.