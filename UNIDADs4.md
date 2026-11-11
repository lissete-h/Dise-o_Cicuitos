# 🔢 ¿Cómo suma un circuito digital? (SEMANA 4)

La suma en circuitos binarios funciona con la misma lógica que la suma decimal por columnas: se calcula el dígito a escribir en la posición corriente y el valor de acarreo (*carry*) que se "lleva" hacia la siguiente columna a la izquierda.

- **S (Suma / Sum):** Es el resultado que se escribe en la columna actual.
- **C (Acarreo / Carry):** Es el dígito que "nos llevamos" hacia la columna de la izquierda cuando la suma supera 1 bit (1 + 1 = 10_2, se escribe `0` y se lleva `1`).

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

