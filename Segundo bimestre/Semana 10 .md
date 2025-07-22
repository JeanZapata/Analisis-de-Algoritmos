# 📚 Semana 10 – Algoritmos Voraces  
## Subtema 6.4: Caminos mínimos en grafos

**Referencia:**  
Brassard, G., & Bratley, P. (2006). *Fundamentals of Algorithmics*. Prentice Hall.

---

## 🗺️ ¿En qué consiste el problema de caminos mínimos?

En un **grafo con pesos en sus aristas**, el objetivo es encontrar la ruta de **menor costo** desde un nodo inicial hacia los demás nodos del grafo.

Existen dos variantes comunes:

- Determinar el camino más corto desde un solo nodo hacia todos los otros (fuente única).
- Calcular el camino mínimo entre cada par de nodos del grafo.

Este tema se concentra en el enfoque de fuente única usando un método voraz: el **algoritmo de Dijkstra**.

---

## 🧠 Algoritmo de Dijkstra

### ✔️ Supuestos

- El grafo puede ser **dirigido o no dirigido**.
- Los pesos de las aristas deben ser **mayores o iguales a cero**.

### 🚀 Idea central

El algoritmo mantiene un conjunto de nodos cuya distancia mínima al nodo de origen ya ha sido determinada. De manera voraz, en cada paso se elige el nodo no procesado más cercano y se expande la frontera de caminos conocidos.

---

## 🛠️ Descripción general del algoritmo

```plaintext
1. Asignar distancia infinita a todos los nodos, excepto al nodo de origen (0).
2. Marcar todos los nodos como no visitados.
3. Mientras existan nodos no visitados:
   a. Seleccionar el nodo con menor distancia actual.
   b. Marcarlo como visitado.
   c. Para cada vecino, actualizar su distancia si se encuentra un camino más corto.
### Ejemplo
```plaintext
A --1--> B --2--> C
 \       |
  \--4--> D --1--> C
```
Camino más corto desde A:

    A → B → C (costo 1 + 2 = 3)

    A → D → C = 4 + 1 = 5 → No óptimo
  # 🔧 Pseudocódigo del Algoritmo de Dijkstra

```plaintext
Entrada:
    - Grafo G = (V, E), con pesos positivos en las aristas
    - Nodo origen s ∈ V

Salida:
    - dist[v]: distancia mínima desde s hasta cada nodo v ∈ V
    - prev[v]: nodo anterior en el camino mínimo desde s hasta v

Procedimiento Dijkstra(G, s):
    para cada nodo v en V hacer:
        dist[v] ← ∞
        prev[v] ← indefinido
    dist[s] ← 0

    Q ← conjunto de todos los nodos en V

    mientras Q no esté vacío hacer:
        u ← nodo en Q con menor dist[u]
        eliminar u de Q

        para cada vecino v de u:
            si (u, v) ∈ E entonces:
                alt ← dist[u] + peso(u, v)
                si alt < dist[v] entonces:
                    dist[v] ← alt
                    prev[v] ← u

    retornar dist, prev
```

![Imagen de WhatsApp 2025-07-22 a las 09 53 49_a0c70046](https://github.com/user-attachments/assets/ef6f26f1-02d1-477a-b008-fcbd1d3d9b77)

![Imagen de WhatsApp 2025-07-22 a las 09 54 07_844adfe8](https://github.com/user-attachments/assets/3ea76369-efa2-4d96-b513-caeb62a649cd)
