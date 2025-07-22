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
``
    ![Imagen de WhatsApp 2025-07-22 a las 09 56 13_00a10208](https://github.com/user-attachments/assets/0e793313-bdcc-4bf5-9432-247ee41d9283)
    
``
    ![Imagen de WhatsApp 2025-07-22 a las 09 56 29_7b0e4e3e](https://github.com/user-attachments/assets/79bfb7b2-ebb8-4e4d-8c0c-5f3990a6e5e6)


![Imagen de WhatsApp 2025-07-22 a las 09 56 44_0edaa3e3](https://github.com/user-attachments/assets/030c3aa8-3928-4c77-bf65-613cf5fbb537)

![Imagen de WhatsApp 2025-07-22 a las 09 56 57_27dd5f40](https://github.com/user-attachments/assets/45b632cb-6d67-4e9c-9e56-288cc9dde9ad)

![Imagen de WhatsApp 2025-07-22 a las 09 57 08_27ce589d](https://github.com/user-attachments/assets/e4590e6b-ff08-4cf1-86e7-809958996f5b)

![Imagen de WhatsApp 2025-07-22 a las 09 57 16_7ae03f75](https://github.com/user-attachments/assets/432f1faa-4301-41f0-b141-454fa9087222)

![Imagen de WhatsApp 2025-07-22 a las 09 57 28_161f58c7](https://github.com/user-attachments/assets/26d1e136-e6ac-4391-bd13-a83d6f89a831)
