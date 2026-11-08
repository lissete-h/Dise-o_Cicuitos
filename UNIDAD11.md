
# 🔢 Sistemas Numéricos, Códigos y Compuertas Lógicas (SEMANA 1)

---

## 1. Sistemas Numéricos
Los sistemas numéricos son conjuntos de reglas y símbolos para representar cantidades. En computación, los más utilizados son:

### 1.1 Tabla Comparativa
| Sistema | Base | Dígitos Válidos | Aplicación Principal |
| :--- | :---: | :--- | :--- |
| **Decimal** | 10 | 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 | Uso humano cotidiano |
| **Binario** | 2 | 0, 1 | Electrónica digital y hardware |
| **Octal** | 8 | 0, 1, 2, 3, 4, 5, 6, 7 | Compactación de código binario |
| **Hexadecimal** | 16 | 0 al 9 y letras A a F (A=10 ... F=15) | Direcciones de memoria y colores RGB |

### 1.2 Tabla de Equivalencias Clave
| Decimal | Binario | Octal | Hexadecimal |
| :---: | :---: | :---: | :---: |
| 0 | `0000` | 0 | 0 |
| 1 | `0001` | 1 | 1 |
| 2 | `0010` | 2 | 2 |
| 3 | `0011` | 3 | 3 |
| 4 | `0100` | 4 | 4 |
| 5 | `0101` | 5 | 5 |
| 6 | `0110` | 6 | 6 |
| 7 | `0111` | 7 | 7 |
| 8 | `1000` | 10 | 8 |
| 9 | `1001` | 11 | 9 |
| 10 | `1010` | 12 | A |
| 11 | `1011` | 13 | B |
| 12 | `1100` | 14 | C |
| 13 | `1101` | 15 | D |
| 14 | `1110` | 16 | E |
| 15 | `1111` | 17 | F |

[REGRESAR](UNIDAD1.md)

---

## 2. Métodos de Conversión y Ejemplos Prácticos

### A. De Decimal a Binario
* **Método:** Se divide el número sucesivamente entre 2 y se anotan los residuos. El resultado se lee de abajo hacia arriba.
* **Ejemplo:** Convertir el número decimal **13** a binario.
  * 13 / 2 = 6 (Residuos: **1**)
  * 6 / 2 = 3  (Residuos: **0**)
  * 3 / 2 = 1  (Residuos: **1**)
  * 1 / 2 = 0  (Residuos: **1**)
  * **Resultado:** `1101`

### B. De Binario a Decimal
* **Método:** Se multiplica cada dígito por 2 elevado a su posición (empezando desde 0 a la derecha) y se suman los valores.
* **Ejemplo:** Convertir el binario **1011** a decimal.
  * (1 * 8) + (0 * 4) + (1 * 2) + (1 * 1)
  * = 8 + 0 + 2 + 1
  * **Resultado:** `11` (en decimal)

### C. De Binario a Hexadecimal
* **Método:** Se divide el número binario en bloques de **4 bits** de derecha a izquierda y se reemplaza cada bloque por su equivalente hexadecimal.
* **Ejemplo:** Convertir el binario **11010110** a hexadecimal.
  * Agrupamos: `1101` | `0110`
  * Bloque 1 (`1101`) = 13 en decimal = **D**
  * Bloque 2 (`0110`) = 6 en decimal = **6**
  * **Resultado:** `D6`

### D. De Binario a Octal
* **Método:** Se divide el número binario en bloques de **3 bits** de derecha a izquierda y se reemplaza cada bloque por su valor en octal.
* **Ejemplo:** Convertir el binario **101110** a octal.
  * Agrupamos: `101` | `110`
  * Bloque 1 (`101`) = **5**
  * Bloque 2 (`110`) = **6**
  * **Resultado:** `56`

[REGRESAR](UNIDAD1.md)

---

## 3. Aritmética Binaria Básica

| Operación de Suma | Operación de Resta |
| :--- | :--- |
| 0 + 0 = 0 <br> 0 + 1 = 1 <br> 1 + 0 = 1 <br> 1 + 1 = 10 *(Escribe 0 y lleva 1)* | 0 - 0 = 0 <br> 1 - 0 = 1 <br> 1 - 1 = 0 <br> 0 - 1 = 1 *(Pide un préstamo de 1)* |

### Ejemplos Prácticos de Aritmética Binaria:
* **Ejemplo de Suma (`101` + `011`):**
  ```text
    101  (5 en decimal)
  + 011  (3 en decimal)
  -----
   1000  (8 en decimal)

### Ejemplo de Resta (`110` - `011`):
* **Explicación paso a paso:**
  ```text
    110  (6 en decimal)
  - 011  (3 en decimal)
  -----
    011  (3 en decimal)

[REGRESAR](UNIDAD1.md)

---

## 4. Códigos Digitales
Permiten representar información utilizando combinaciones de bits:
* **BCD (Decimal Codificado en Binario):** Cada dígito decimal se representa independientemente con 4 bits (ej. el 9 es `1001`).
* **Código Gray:** Los números consecutivos difieren en un **solo bit**, lo que evita errores de lectura en dispositivos físicos.
* **Código ASCII:** Estándar que asigna un valor numérico/binario a cada letra, número y símbolo del teclado.

[REGRESAR](UNIDAD1.md)

---

## 5. Compuertas Lógicas
Circuitos electrónicos que operan con lógica binaria (0 y 1) basados en álgebra booleana.

### Tabla de Verdad de Compuertas Básicas (Entradas A y B)
| Compuerta | Operación Lógica | Tabla de Verdad (A y B -> Salida) |
| :--- | :--- | :--- |
| **AND (Y)** | A · B <br>*(Salida 1 solo si ambas son 1)* | 0 · 0 = 0 <br> 0 · 1 = 0 <br> 1 · 0 = 0 <br> 1 · 1 = 1 |
| **OR (O)** | A + B <br>*(Salida 1 si al menos una es 1)* | 0 + 0 = 0 <br> 0 + 1 = 1 <br> 1 + 0 = 1 <br> 1 + 1 = 1 |
| **NOT (INVERSOR)** | Inversor <br>*(Invierte el estado)* | Entra 0 -> Sale 1 <br> Entra 1 -> Sale 0 |
| **NAND (NO-AND)** | NOT (A · B) <br>*(Inversa de AND)* | 0 · 0 = 1 <br> 0 · 1 = 1 <br> 1 · 0 = 1 <br> 1 · 1 = 0 |
| **NOR (NO-OR)** | NOT (A + B) <br>*(Inversa de OR)* | 0 + 0 = 1 <br> 0 + 1 = 0 <br> 1 + 0 = 0 <br> 1 + 1 = 0 |
| **XOR (O Exclusiva)** | A XOR B <br>*(Salida 1 si son diferentes)* | 0 XOR 0 = 0 <br> 0 XOR 1 = 1 <br> 1 XOR 0 = 1 <br> 1 XOR 1 = 0 |

[REGRESAR](UNIDAD1.md)

---

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
  
---

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

# 🔢 ¿Cómo suma un circuito digital? (SEMANA 4)

La suma en circuitos binarios funciona con la misma lógica que la suma decimal por columnas: se calcula el dígito a escribir en la posición corriente y el valor de acarreo (*carry*) que se "lleva" hacia la siguiente columna a la izquierda.

- **S (Suma / Sum):** Es el resultado que se escribe en la columna actual.
- **C (Acarreo / Carry):** Es el dígito que "nos llevamos" hacia la columna de la izquierda cuando la suma supera 1 bit ($1 + 1 = 10_2$, se escribe `0` y se lleva `1`).

[REGRESAR](UNIDAD1.md)

---

## 1. Bloques Básicos de Construcción

### A. Semisumador (Half Adder)
Diseñado únicamente para la **columna 0** (la menos significativa), ya que solo recibe 2 entradas (A y B) y no procesa acarreos previos.

- **Ecuaciones lógicas:**
  - **Suma (S):** S = A ⊕ B *(Compuerta XOR, activa cuando A y B son distintos)*.
  - **Acarreo (C):** C = A · B *(Compuerta AND, activa solo cuando ambos son 1)*.

---

### B. Sumador Completo (Full Adder)
Utilizado para las **columnas 1 en adelante**. Procesa 3 entradas: los bits A y B, más el acarreo que llega de la derecha (Cin).

- **Lógica intuitiva:**
  - **Suma (S):** Se activa cuando hay un número **impar** de unos en las entradas (`S = A ⊕ B ⊕ Cin`).
  - **Acarreo de salida (Cout):** Se activa cuando hay **al menos dos unos** entre las entradas (`Cout = AB + A·Cin + B·Cin`).

---

## 2. Sumador de Varios Bits (Ripple Carry Adder)

Para sumar números de varios bits (por ejemplo, de 4 bits: $A_3 A_2 A_1 A_0 + B_3 B_2 B_1 B_0$), se encadenan varios sumadores completos.

- **Regla de conexión:** El acarreo de salida (Cout) de cada etapa se conecta directamente al acarreo de entrada (Cin) del sumador siguiente.
- **Propagación en ola (*Ripple*):** Como cada etapa debe esperar a que la etapa anterior genere su acarreo, el resultado se completa de derecha a izquierda en cadena.
- **Retardo:** A mayor cantidad de bits, más lento es el circuito (cada etapa requiere pasar por aproximadamente 2 compuertas lógicas).

[REGRESAR](UNIDAD1.md)

---

## 3. Adaptación para Restar (Sumador/Restador)

Restar un número equivale a sumar su negativo usando **complemento a 2** ($A - B = A + (-B)$).

- **Inversor controlado (XOR):** Se usa una entrada de control M conectada a compuertas XOR en la entrada B.
  - **Si M = 0 (Suma):** Las entradas B pasan sin modificar y Cin = 0.
  - **Si M = 1 (Resta):** Las entradas B se invierten (complemento a 1) y se introduce Cin = 1 en la etapa 0 para sumar el +1 del complemento a 2.

[REGRESAR](UNIDAD1.md)

---

## 4. Detección de Desbordamiento (Overflow)

Ocurre cuando el resultado de la suma/resta excede la capacidad de representación de bits disponibles.

- En aritmética con signo de 4 bits, se detecta comparando el acarreo que entra a la última etapa ($C_3$) con el que sale ($C_4$):
  
  $$\text{Overflow } (V) = C_3 \oplus C_4$$

[REGRESAR](UNIDAD1.md)
