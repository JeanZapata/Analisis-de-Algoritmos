# 📚 Semana 15 – Algoritmos Probabilistas (Parte 2)

**Referencia:**  
Brassard, G., & Bratley, P. (2006). *Fundamentals of Algorithmics*. Prentice Hall.

---

## 🎲 Profundización: Algoritmos Probabilistas

Los algoritmos probabilistas integran la **aleatoriedad** como parte esencial del proceso de resolución.  
Esta semana se enfoca en su **análisis estadístico**, el uso de repeticiones para mejorar la precisión, y el estudio de los fundamentos matemáticos que los sustentan.

---

## 🔁 ¿Por qué repetir ejecuciones?

En algoritmos del tipo Monte Carlo, repetir el proceso varias veces permite **reducir drásticamente la probabilidad de error**.

```plaintext
Probabilidad de éxito con k repeticiones:
P = 1 - (error por ejecución)^k
Ejemplo: si el error por ejecución es 1/4, tras 5 repeticiones:
P = 1 - (1/4)^5 ≈ 0.999
```
📐 Análisis probabilístico

Para evaluar un algoritmo probabilista se consideran:

    Esperanza matemática (esperado) del tiempo de ejecución.
    Varianza para medir fluctuaciones.
    Probabilidad de error y cómo se controla.
    Distribuciones discretas (uniforme, binomial) para modelar entradas o decisiones aleatorias.

🔎 Casos detallados
📍 Miller-Rabin – Prueba de primalidad

    Dado un número impar n > 3, se prueba si es primo con alta probabilidad.
    Requiere selección aleatoria de testigos.
    Puede identificar compuestos con probabilidad ≥ 3/4 por ejecución.

📍 Algoritmo de Freivalds – Verificación matricial

    Dado A, B, C, verifica si A·B = C en O(n²) tiempo.
    Genera un vector aleatorio r, compara A·(B·r) con C·r.
    Si los resultados difieren, garantiza que A·B ≠ C.

📍 QuickSort aleatorizado

    Selección aleatoria del pivote mejora el rendimiento promedio.
    Tiempo esperado: O(n log n) sin importar el orden de entrada.