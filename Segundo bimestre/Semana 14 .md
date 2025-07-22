# 📚 Semana 14 – Algoritmos Probabilistas

**Referencia:**  
Brassard, G., & Bratley, P. (2006). *Fundamentals of Algorithmics*. Prentice Hall.

---

## 🎲 ¿Qué son los algoritmos probabilistas?

Un **algoritmo probabilista** emplea números aleatorios como parte de su lógica para tomar decisiones durante la ejecución.  
Como resultado, su comportamiento puede cambiar en diferentes ejecuciones, incluso con la misma entrada.

> Este tipo de algoritmos es útil cuando no se dispone de soluciones deterministas eficientes, o cuando se acepta una respuesta con cierta probabilidad de acierto.

---

## 🧪 Clasificación de algoritmos probabilistas

### 1. **Monte Carlo**
- Entregan resultados **altamente probables**, pero no garantizados.
- Suelen ser más rápidos.
- Tienen una **pequeña posibilidad de error**.
- Ejemplo: prueba de primalidad de **Miller-Rabin**.

```plaintext
P(correcta) ≥ 1 - ε
```
2. Algoritmos de Las Vegas
    Siempre devuelven la respuesta correcta, pero el tiempo de ejecución es aleatorio.
    La variabilidad está en el rendimiento, no en la corrección.
    Ejemplo: Randomized QuickSort.

P(error) = 0, pero tiempo es variable.

💡 Ejemplos clásicos

Miller-Rabin (Monte Carlo)

    Prueba si un número es primo con alta probabilidad.
    Es ampliamente usado en criptografía.
    
 QuickSort aleatorizado (Las Vegas)

    Selecciona el pivote al azar para evitar el peor caso.
    Esperanza de tiempo: O(n log n)

 Algoritmo de Freivalds

    Verifica si A·B = C en matrices usando vectores aleatorios.
    Verificación rápida con alta probabilidad de certeza.

 Ventajas

    Frecuentemente más simples y rápidos que sus contrapartes deterministas.
    Muy útiles para problemas intratables o de gran tamaño.
    Permiten técnicas aproximadas en contextos donde la exactitud no es esencial.

 Desventajas

    No garantizan resultados exactos (en el caso Monte Carlo).
    Su análisis puede ser más complejo (requiere teoría de probabilidad).
    No siempre es fácil estimar el número de repeticiones necesarias para obtener una probabilidad aceptable.

 Aplicaciones comunes
    Criptografía (generación de claves, primalidad)
    Aprendizaje automático (inicialización, muestreo)
    Simulación de sistemas complejos (Monte Carlo)
    Verificación de propiedades algebraicas y numéricas