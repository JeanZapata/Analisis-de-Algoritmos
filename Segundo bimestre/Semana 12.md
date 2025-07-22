# 📚 Semana 12 – Ordenación por Fusión (Merge Sort)

**Referencias:**  
Brassard, G., & Bratley, P. (2006). *Fundamentals of Algorithmics*. Prentice Hall.  
Cormen, T. H., Leiserson, C. E., Rivest, R. L., & Stein, C. (2022). *Introduction to Algorithms*, 4.ª edición. MIT Press.

---

## 🧠 ¿Qué es Merge Sort?

**Merge Sort**, o algoritmo de ordenación por fusión, es una técnica eficiente de ordenamiento que sigue el paradigma de **Divide y Vencerás**.  
Consiste en dividir un arreglo en partes más pequeñas, ordenar esas partes de manera recursiva y luego fusionarlas para formar una lista ordenada.

---

## 🔧 Esquema general del algoritmo

```plaintext
MergeSort(A):
    si longitud(A) ≤ 1:
        retornar A
    dividir A en dos mitades: izquierda y derecha
    izquierda_ordenada = MergeSort(izquierda)
    derecha_ordenada = MergeSort(derecha)
    retornar Merge(izquierda_ordenada, derecha_ordenada)
```
🛠️ Pseudocódigo
```plaintext
procedure MergeSort(A, inicio, fin):
    si inicio < fin:
        medio ← (inicio + fin) / 2
        MergeSort(A, inicio, medio)
        MergeSort(A, medio + 1, fin)
        Merge(A, inicio, medio, fin)

procedure Merge(A, inicio, medio, fin):
    n1 ← medio - inicio + 1
    n2 ← fin - medio
    crear arreglos temporales L[1...n1], R[1...n2]

    copiar A[inicio...medio] en L
    copiar A[medio+1...fin] en R

    i ← 1, j ← 1, k ← inicio
    mientras i ≤ n1 y j ≤ n2:
        si L[i] ≤ R[j]:
            A[k] ← L[i]
            i ← i + 1
        sino:
            A[k] ← R[j]
            j ← j + 1
        k ← k + 1

    copiar elementos restantes de L (si hay)
    copiar elementos restantes de R (si hay)
```
![Imagen de WhatsApp 2025-07-22 a las 09 55 20_60dcac4e](https://github.com/user-attachments/assets/8d43ebac-f713-4cc5-9100-0399ceeb215b)

![Imagen de WhatsApp 2025-07-22 a las 09 55 35_68b9acda](https://github.com/user-attachments/assets/4b51bf2c-39c5-457c-9bf3-00e35afe272f)

![Imagen de WhatsApp 2025-07-22 a las 09 55 48_a8503c86](https://github.com/user-attachments/assets/2546704a-5951-43d1-b85d-db7d819dfadc)
