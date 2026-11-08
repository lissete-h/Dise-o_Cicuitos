
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

[REGRESAR](UNIDAD1.md)
