# 🔢 Algebra de Boole y Formas Canónicas (SEMANA 2) 

## 1. Postulados de Huntington
Se define un conjunto {0, 1} con tres operaciones fundamentales: + (OR), · (AND) y ' (NOT).

| Postulado | Forma OR | Forma AND (Dual) |
| :--- | :--- | :--- |
| **Identidad** | X + 0 = X | X · 1 = X |
| **Complemento** | X + X' = 1 | X · X' = 0 |
| **Conmutativa** | X + Y = Y + X | XY = YX |
| **Distributiva** | X(Y + Z) = XY + XZ | X + YZ = (X + Y)(X + Z) |

> **Principio de Dualidad:** Si se intercambia + por · y 0 por 1 (sin complementar las variables), la identidad resultante sigue siendo valida.

[REGRESAR](UNIDAD1.md)

---

## 2. Teoremas

| Teorema | Forma OR | Forma AND |
| :--- | :--- | :--- |
| **Elemento nulo** | X + 1 = 1 | X · 0 = 0 |
| **Idempotencia** | X + X = X | X · X = X |
| **Involucion** | (X')' = X | — |
| **Absorcion** | X + XY = X | X(X + Y) = X |
| **Absorcion del complemento** | X + X'Y = X + Y | X(X' + Y) = XY |
| **Adyacencia** | XY + XY' = X | (X + Y)(X + Y') = X |
| **Consenso** | XY + X'Z + YZ = XY + X'Z | (X + Y)(X' + Z)(Y + Z) = (X + Y)(X' + Z) |

[REGRESAR](UNIDAD1.md)

---

## 3. Propiedad Distributiva Adicional
A + BC = (A + B)(A + C).

* **Punto de partida:** (A + B)(A + C)
* = AA + AC + AB + BC *(aplicando distributiva)*
* = A + AC + AB + BC *(por idempotencia: AA = A)*
* = A(1 + C + B) + BC *(sacando factor comun A)*
* = A + BC *(por elemento nulo: 1 + C + B = 1)*

[REGRESAR](UNIDAD1.md)

---

## 4. Leyes de De Morgan
* **Formula basica:** Permiten relacionar las operaciones AND y OR mediante la negacion.
* **Regla mnemotecnia:** "Rompe la barra, cambia el operador".
* **Generalizacion a n variables:** (A + B + C)' = A'B'C'

### Ejemplo resuelto de aplicacion
Resolver paso a paso la expresion: `(A + B'C)'`

1. **Aplicar De Morgan (romper la barra principal):**  
   `= (A)' · (B'C)'`
2. **Aplicar De Morgan en el segundo termino (producto):**  
   `= A' · ((B')' + C')`
3. **Aplicar involucion (`(B')' = B`):**  
   `= A' · (B + C')`

[REGRESAR](UNIDAD1.md)

---

## 5. Minitérminos y Maxitérminos

Para entender cómo se construyen las funciones lógicas, primero debemos conocer las piezas básicas. En un sistema de 3 variables (A, B, C), existen 8 combinaciones posibles (del 0 al 7). 

### Reglas:
* **Minitérmino (m_i):** 
  * Representa un producto lógico (**AND**).
  * Se usa cuando la variable vale **1** (se escribe normal, ej: `A`) y cuando vale **0** (se escribe negada, ej: `A'`).
* **Maxitérmino (M_i):** 
  * Representa una suma lógica (**OR**).
  * Se usa al revés: cuando la variable vale **0** (se escribe normal, ej: `A`) y cuando vale **1** (se escribe negada, ej: `A'`).
  * Relación directa: Cada maxitérmino es el complemento de su minitérmino (M_i = m_i').

[REGRESAR](UNIDAD1.md)

---

## 6. Formas Canónicas: SOP y POS 

Usaremos una tabla de verdad en una expresión algebraica:

| Índice (i) | Entradas (ABC) | Salida de la Función (F) |
| :---: | :---: | :---: |
| **0** | 000 | **0** |
| **1** | 001 | **1** |
| **2** | 010 | **1** |
| **3** | 011 | **0** |
| **4** | 100 | **1** |
| **5** | 101 | **0** |
| **6** | 110 | **0** |
| **7** | 111 | **0** |

---

### A. Forma Canónica SOP (Suma de Productos)

* Se enfoca exclusivamente en las filas donde la salida de la función es **F = 1**.
* Se toman los miniterminos de esas filas y se suman entre sí mediante el operador OR (`+`).

#### Filas seleccionadas para SOP (donde F = 1)
| Índice (i) | Entradas (ABC) | F | Minitérmino Asociado |
| :---: | :---: | :---: | :--- |
| **1** | 001 | **1** | A' · B' · C |
| **2** | 010 | **1** | A' · B · C' |
| **4** | 100 | **1** | A · B' · C' |

* **Expresión Canónica SOP resultante:**  
  `F = Σm(1, 2, 4) = (A' · B' · C) + (A' · B · C') + (A · B' · C')`

---

### B. Forma Canónica POS (Producto de Sumas)

* Se enfoca exclusivamente en las filas donde la salida de la función es **F = 0**.
* Se toman los maxitérminos de esas filas y se multiplican entre sí mediante el operador AND (`·`).

#### Filas seleccionadas para POS (donde F = 0)
| Índice ($i$) | Entradas (ABC) | F | Maxitérmino Asociado |
| :---: | :---: | :---: | :--- |
| **0** | 000 | **0** | A + B + C |
| **3** | 011 | **0** | A + B' + C' |
| **5** | 101 | **0** | A' + B + C' |
| **6** | 110 | **0** | A' + B' + C |
| **7** | 111 | **0** | A' + B' + C' |

* **Expresión Canónica POS resultante:**  
  `F = ΠM(0, 3, 5, 6, 7) = (A + B + C) · (A + B' + C') · (A' + B + C') · (A' + B' + C) · (A' + B' + C')`

[REGRESAR](UNIDAD1.md)
  
