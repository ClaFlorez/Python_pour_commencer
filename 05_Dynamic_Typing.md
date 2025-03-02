# Data Types and Dynamic Typing

Python tiene muchos tipos de datos incorporados, como:
- **Nombres** (Enteros, Flotantes, Booleanos, Complejos)
- **Cadenas de texto (String)**
- **Listas, Tuplas, Conjuntos y Diccionarios**
- **Archivos**

Tipos más avanzados, como **Decimal** y **Fraction**, se encuentran en módulos externos.

Puedes usar la función incorporada `type(variable)` para verificar el tipo de una variable o un valor literal.

---

## 1. Number Types

Python admite los siguientes tipos numéricos:

### Enteros (`int`)

Los enteros en Python no tienen un límite de tamaño:

```python
>>> 123 + 456 - 789
-210
>>> 12345678901234567890 + 1
12345678901234567891
>>> 2 ** 888  # 2 elevado a 888
...
>>> len(str(2 ** 888))  # Longitud del número
268
>>> type(123)
<class 'int'>
```

Puedes representar enteros en:
- **Hexadecimal** (`0x1abc` o `0X1ABC`)
- **Octal** (`0o1776` o `0O1776`)
- **Binario** (`0b11000011` o `0B11000011`)

### Flotantes (`float`)

Los números de punto flotante son de **doble precisión (64 bits)**:

```python
>>> 1.23 * -4e5
-492000.0
>>> type(1.2)
<class 'float'>
>>> import math
>>> math.pi
3.141592653589793
>>> import random
>>> random.random()  # Número aleatorio entre [0, 1)
0.890839384187198
```

### Booleanos (`bool`)

Los booleanos solo pueden ser `True` o `False`:

```python
>>> 8 == 8
True
>>> 8 == 9
False
>>> type(True)
<class 'bool'>
>>> bool(0)  # 0, None y valores vacíos son False
False
>>> bool('hello')  # Cualquier valor no vacío es True
True
```

### Complejos (`complex`)

Los números complejos tienen una parte real e imaginaria:

```python
>>> x = 1 + 2j
>>> x.real, x.imag
(1.0, 2.0)
>>> type(x)
<class 'complex'>
>>> x * (3 + 4j)
(-5+10j)
```

### Decimal y Fraction

Los flotantes pueden ser imprecisos:

```python
>>> 0.1 * 3
0.30000000000000004
```

Para mayor precisión, usa `decimal.Decimal`:

```python
>>> import decimal
>>> x = decimal.Decimal('0.1')
>>> x * 3
Decimal('0.3')
>>> type(x)
<class 'decimal.Decimal'>
```

---

## 2. Dynamic Typing y Asignación de Variables

Python es **dinámicamente tipado** (a diferencia de C/C++/Java). Las variables pueden cambiar de tipo:

```python
>>> x = 1
>>> type(x)
<class 'int'>
>>> x = 1.0
>>> type(x)
<class 'float'>
>>> x = 'hello'
>>> type(x)
<class 'str'>
```

Puedes verificar el tipo con `isinstance()`:

```python
>>> isinstance(123, int)
True
>>> isinstance('a', str)
True
>>> isinstance('a', int)
False
```

### Conversión de Tipos (`int()`, `float()`, `str()`, `bool()`)

```python
>>> x = '123'  # String
>>> x = int(x)  # Convertir a int
>>> x = float(x)  # Convertir a float
>>> x = str(x)  # Convertir a string
>>> x = bool(x)  # Convertir a booleano
>>> x
True  # Cualquier string no vacío es True
```

---

## 3. Operador de Asignación (`=`)

No necesitas declarar variables antes de usarlas:

```python
>>> x = 8
>>> x = 'Hello'
>>> y  # Error, variable no definida
NameError: name 'y' is not defined
```

### Asignación Múltiple

```python
>>> b, c, d = 123, 4.5, 'Hello'
>>> e = f = g = 123  # Asignación en cadena
```

### `del` para eliminar variables

```python
>>> x = 8
>>> del x
>>> x
NameError: name 'x' is not defined
```

---

## Tableau des Types de Données en Python

| Type de Donnée | Description | Exemple |
|---------------|------------|---------|
| **int** (Entier) | Nombres entiers sans limite de taille | `123`, `-456`, `0x1A` (hex) |
| **float** (Flottant) | Nombres avec décimales ou notation scientifique | `3.14`, `-2.7`, `1.2e3` |
| **bool** (Booléen) | Valeurs `True` ou `False` | `True`, `False`, `8 == 8` |
| **complex** (Complexe) | Nombres avec une partie réelle et imaginaire | `1+2j`, `-3-4j` |
| **str** (Chaîne) | Séquence de caractères | `"Bonjour"`, `'Python'` |
| **list** (Liste) | Collection modifiable et ordonnée | `[1, 2, 3]`, `['a', 'b', 'c']` |
| **tuple** (Tuple) | Collection immuable et ordonnée | `(1, 2, 3)`, `('x', 'y', 'z')` |
| **set** (Ensemble) | Collection mutable sans doublons | `{1, 2, 3}`, `{'a', 'b'}` |
| **dict** (Dictionnaire) | Collection clé-valeur | `{'nom': 'Ana', 'âge': 25}` |
| **NoneType** | Représente l'absence de valeur | `None` |

---

### Résumé

- Python prend en charge le **typage dynamique**, les variables peuvent changer de type.
- Les nombres incluent `int`, `float`, `bool`, `complex`, `Decimal` et `Fraction`.
- Les types peuvent être convertis avec `int()`, `float()`, `str()`, `bool()`, etc.
- Vous pouvez attribuer plusieurs valeurs sur une seule ligne avec `b, c, d = 1, 2, 3`.
- `del` supprime les variables de la mémoire.

---
# Operadores Aritméticos en Python

Python admite los siguientes operadores aritméticos:

| Operador | Modo   | Uso      | Descripción                      | Ejemplo                        |
|----------|--------|----------|----------------------------------|--------------------------------|
| `+`      | Binario, Unario | `x + y`, `+x`  | Suma, Positivo                 | `2 + 3` → `5`                 |
| `-`      | Binario, Unario | `x - y`, `-x`  | Resta, Negativo                 | `5 - 2` → `3`, `-5` → `-5`    |
| `*`      | Binario | `x * y`  | Multiplicación                   | `2 * 3` → `6`                 |
| `/`      | Binario | `x / y`  | División flotante (retorna `float`) | `5 / 2` → `2.5`              |
| `//`     | Binario | `x // y` | División entera (retorna el piso) | `5 // 2` → `2`, `-5 // 2` → `-3` |
| `**`     | Binario | `x ** y` | Exponenciación                   | `2 ** 3` → `8`                |
| `%`      | Binario | `x % y`  | Módulo (resto de la división)    | `5 % 2` → `1`                 |

> ⚠️ **Nota:** En Java, `-1/2` retorna `0`, mientras que en Python `-1 // 2` retorna `-1` debido al redondeo hacia abajo.

---
