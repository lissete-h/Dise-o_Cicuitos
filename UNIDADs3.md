# 🔢 Mapas de Karnaugh: Simplificación de Circuitos Lógicos (SEMANA 3)

El **Mapa de Karnaugh** es una representación gráfica utilizada para simplificar expresiones del Álgebra de Boole y obtener funciones lógicas mínimas en formato **SOP** (Suma de Productos) o **POS** (Producto de Sumas).

- **Teorema de Adyacencia:** Se basa en el postulado X · Y + X · Y' = X. Si dos minitérminos difieren en una sola variable, dicha variable se elimina al agruparlos.

---

## 1. Estructura y Código Gray

Para que las celdas contiguas del mapa representen adyacencia lógica (diferencias de exactamente 1 bit), las filas y columnas deben ordenarse mediante **Código Gray** (00, 01, 11, 10) en lugar del orden binario convencional (00, 01, 10, 11).

| Binario (Convencional) | Código Gray | Cambio en Bits |
| :---: | :---: | :---: |
| 00 | 00 | Cambia 1 bit |
| 01 | 01 | Cambia 1 bit |
| 10 | 11 | Cambia 1 bit |
| 11 | 10 | Cambia 1 bit (y de 10 a 00 también) |

[REGRESAR](UNIDAD1.md)

---

## 2. Estructuras de los Mapas (3 y 4 Variables)

### Mapa de 3 Variables (A, B, C -> 8 celdas)
- **Filas:** Variable A (0, 1).
- **Columnas:** Variables BC en Código Gray (00, 01, 11, 10).

| A \ BC | 00 | 01 | 11 | 10 |
| :---: | :---: | :---: | :---: | :---: |
| **0** | m0 | m1 | m3 | m2 |
| **1** | m4 | m5 | m7 | m6 |

> **Nota:** El minitérmino m3 antecede a m2 debido al ordenamiento Gray.

---

### Mapa de 4 Variables (A, B, C, D -> 16 celdas)
- **Filas:** Variables AB en Código Gray (00, 01, 11, 10).
- **Columnas:** Variables CD en Código Gray (00, 01, 11, 10).

| AB \ CD | 00 | 01 | 11 | 10 |
| :---: | :---: | :---: | :---: | :---: |
| **00** | m0 | m1 | m3 | m2 |
| **01** | m4 | m5 | m7 | m6 |
| **11** | m12 | m13 | m15 | m14 |
| **10** | m8 | m9 | m11 | m10 |

- **Patrón para memorizar los índices:**
  - Fila `00` -> 0, 1, 3, 2
  - Fila `01` -> 4, 5, 7, 6
  - Fila `11` -> 12, 13, 15, 14
  - Fila `10` -> 8, 9, 11, 10

[REGRESAR](UNIDAD1.md)

---

## 3. Reglas Estrictas de Agrupación

1. **Tamaño de grupos en potencia de 2 (2^k):** Solo se permiten grupos de 1, 2, 4, 8 o 16 celdas.
   - Un grupo de 2^k celdas elimina k variables de la expresión resultante.
2. **Forma rectangular:** No se permiten agrupaciones en L, T ni diagonales.
3. **Grupos lo más grandes posible:** Un grupo más grande genera un término con menor número de literales.
4. **Adyacencia en bordes y esquinas (Mapa enrollado):**
   - El borde superior es adyacente al borde inferior.
   - El borde izquierdo es adyacente al borde derecho.
   - Las 4 esquinas de un mapa de 4 variables forman un grupo válido de 4 celdas (m0, m2, m8, m10).

[REGRESAR](UNIDAD1.md)

---

## 4. Conceptos Clave: Implicantes Primos y Esenciales

- **Implicante:** Cualquier grupo válido de 1s (o condiciones indiferentes X).
- **Implicante Primo:** Grupo válido que ha sido expandido al máximo posible y no se puede agrandar más.
- **Implicante Primo Esencial:** Implicante primo que cubre al menos un 1 que no está cubierto por ningún otro grupo. Debe incluirse obligatoriamente en la solución final.

> **Solución Mínima =** Todos los Implicantes Primos Esenciales + los Implicantes Primos mínimos necesarios para cubrir los 1s restantes.

[REGRESAR](UNIDAD1.md)

---

## 5. Procedimiento General para Simplificación SOP

1. **Ubicar datos:** Colocar los 1, 0 y X en sus celdas correspondientes.
2. **Formar grupos:** Construir los Implicantes Primos de mayor tamaño posible.
3. **Identificar Esenciales:** Marcar los primos esenciales primero.
4. **Cubrir restantes:** Cubrir los 1s libres con la menor cantidad de grupos posibles.
5. **Lectura del mapa:**
   - Si la variable se mantiene constante en **1** -> se escribe normal (ej: A).
   - Si la variable se mantiene constante en **0** -> se escribe negada (ej: A').
   - Si la variable cambia de valor (de 0 a 1 o viceversa) -> **se elimina**.

[REGRESAR](UNIDAD1.md)

---

## 6. Simplificación en POS (Producto de Sumas)

Para obtener la expresión mínima en suma de maxitérminos:

1. **Agrupar ceros (0):** Se aplican las mismas reglas de agrupación (tamaño 2^k), pero armando grupos con los **0**.
2. **Lectura invertida:**
   - Si la variable constante en el grupo vale **0** -> se escribe sin negar (ej: A).
   - Si la variable constante en el grupo vale **1** -> se escribe negada (ej: A').
3. **Formar el producto:** Cada grupo genera una suma de variables, y la función final es el producto (AND) de todas las sumas.

[REGRESAR](UNIDAD1.md)

---

## 7. Criterio de Selección: ¿SOP o POS?

Para determinar cuál expresión es óptima antes de pasar a circuitos lógicos:
1. Se obtiene la expresión mínima en **SOP** y en **POS**.
2. Se realiza el conteo total de **literales**, compuertas y Circuitos Integrados (CI) requeridos.
3. Se selecciona la versión de **menor costo en hardware**.

[REGRESAR](UNIDAD1.md)
