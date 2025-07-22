# 📚 Semana 9 – Algoritmos Voraces

**Referencia:**  
Brassard, G., & Bratley, P. (2006). *Fundamentals of Algorithmics*. Prentice Hall.

---

## 🧠 ¿Qué es un algoritmo voraz?

Un **algoritmo voraz (greedy)** es una técnica de diseño que construye una solución eligiendo, en cada paso, la mejor opción disponible en ese momento (la más prometedora), con la esperanza de que lleve a una solución global óptima.

> ⚠️ Este enfoque no garantiza siempre la mejor solución, pero en ciertos problemas bien estructurados sí lo hace.

---

## 🎯 Características principales

- ✅ Toma decisiones locales óptimas sin mirar el futuro.
- 🔒 Cada decisión es definitiva (no hay retroceso).
- ❌ No recurre a backtracking ni exploración completa.
- ⚡ Suele ser rápido y fácil de implementar.

---

## ✅ Condiciones para que funcione correctamente

1. **Subestructura óptima**: La mejor solución global incluye soluciones óptimas de subproblemas.
2. **Propiedad de elección voraz**: En cada paso existe una elección local óptima que forma parte de la mejor solución global.

---

## 🧪 Problemas clásicos que sí se resuelven con algoritmos voraces

### 1. Cambio de monedas
- Objetivo: usar la menor cantidad de monedas posible.
- Funciona si el sistema monetario es canónico (no en todos los casos).

### 2. Mochila fraccionaria
- Se pueden tomar fracciones de objetos.
- Estrategia: tomar los objetos con mejor relación valor/peso.
- Siempre obtiene la solución óptima.

### 3. Árbol de expansión mínima
- Objetivo: conectar todos los nodos con el costo total más bajo.
- **Algoritmos**: Kruskal y Prim (ambos usan decisiones voraces).

### 4. Codificación de Huffman
- Asigna códigos más cortos a los símbolos más frecuentes.
- Crea un árbol binario óptimo usando una estrategia voraz.

---

## 🛠️ Esquema típico de un algoritmo voraz

```java
1. Inicializar una solución vacía.
2. Mientras la solución no esté completa:
   a. Escoger el mejor candidato disponible.
   b. Verificar si se puede incluir.
   c. Incluirlo en la solución si es válido.
