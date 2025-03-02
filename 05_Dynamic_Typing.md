# Types de Données et Typage Dynamique

Python possède de nombreux types de données intégrés, tels que :
- **Numériques** (Entiers, Flottants, Booléens, Complexes)
- **Chaînes de texte (String)**
- **Listes, Tuples, Ensembles et Dictionnaires**
- **Fichiers**

Des types plus avancés, comme **Decimal** et **Fraction**, se trouvent dans des modules externes et sont particulièrement utiles pour les calculs financiers.

Vous pouvez utiliser la fonction intégrée `type(variable)` pour vérifier le type d'une variable ou d'une valeur littérale.

---

## 1. Types Numériques

Python prend en charge les types numériques suivants :

### Entiers (`int`)

Les entiers en Python n'ont pas de limite de taille :

> 123 + 456 - 789 
# réponse -210
12345678901234567890 + 1
# réponse 12345678901234567891
2 ** 888  # 2 élevé à 888
...
len(str(2 ** 888))  # Longueur du nombre
# réponse 268
type(123)
<class 'int'>


Vous pouvez représenter des entiers en :
- **Hexadécimal** (`0x1abc` ou `0X1ABC`)
- **Octal** (`0o1776` ou `0O1776`)
- **Binaire** (`0b11000011` ou `0B11000011`)

### Flottants (`float`)

Les nombres flottants sont en **double précision (64 bits)** :

```python
> 1.23 * -4e5
-492000.0
> type(1.2)
<class 'float'>
> import math
> math.pi
3.141592653589793
> import random
> random.random()  # Nombre aléatoire entre [0, 1)
0.890839384187198
```

### Booléens (`bool`)

Les booléens peuvent seulement être `True` ou `False` :

```python
> 8 == 8
True
> 8 == 9
False
> type(True)
<class 'bool'>
> bool(0)  # 0, None et valeurs vides sont False
False
> bool('hello')  # Toute valeur non vide est True
True
```

### Complexes (`complex`)

Les nombres complexes ont une partie réelle et imaginaire :

```python
> x = 1 + 2j
> x.real, x.imag
(1.0, 2.0)
> type(x)
<class 'complex'>
> x * (3 + 4j)
(-5+10j)
```

### Decimal et Fraction

Les flottants peuvent être imprécis :

```python
> 0.1 * 3
0.30000000000000004
```

Pour plus de précision, utilisez `decimal.Decimal` :

```python
> import decimal
> x = decimal.Decimal('0.1')
> x * 3
Decimal('0.3')
> type(x)
<class 'decimal.Decimal'>
```

---

## 2. Typage Dynamique et Affectation de Variables

Python est **dynamiquement typé** (contrairement à C/C++/Java). Les variables peuvent changer de type :

```python
> x = 1
> type(x)
<class 'int'>
> x = 1.0
> type(x)
<class 'float'>
> x = 'hello'
> type(x)
<class 'str'>
```

Vous pouvez vérifier le type avec `isinstance()` :

```python
> isinstance(123, int)
True
> isinstance('a', str)
True
> isinstance('a', int)
False
```

### Conversion de Types (`int()`, `float()`, `str()`, `bool()`)

```python
> x = '123'  # Chaîne
> x = int(x)  # Convertir en int
> x = float(x)  # Convertir en float
> x = str(x)  # Convertir en chaîne
> x = bool(x)  # Convertir en booléen
> x
True  # Toute chaîne non vide est True
```

---

## 3. Opérateurs d'affectation composés

Python prend en charge des opérateurs d'affectation abrégés comme `+=`, `-=`, `*=`, `/=`, `//=`, `**=`, et `%=`. Par exemple :

```python
> i = 5
> i += 1  # Équivaut à i = i + 1
> i
6
```

## Incrémentation/Décrémentation

Python ne prend pas en charge `++` et `--` comme en C/C++/Java. Vous devez utiliser `i = i + 1` ou `i += 1` pour incrémenter.

---

## Opérateurs relationnels (comparaison)

Python prend en charge `==`, `!=`, `<`, `<=`, `>`, `>=`, `in`, `not in`, `is`, et `is not`. Ces opérateurs renvoient `True` ou `False`.

Exemple :

```python
> x = 5
> x == 5
True
> x is 5
True
> x in [1, 2, 3, 5]
True
```

---

## Opérateurs logiques

Python utilise `and`, `or` et `not` pour les opérations logiques.

Exemple :

```python
> True and False
False
> True or False
True
> not True
False
```

---

## Opérateurs au niveau du bit (avancé)

Python prend en charge `&`, `|`, `~`, `^`, `<<`, et `>>` pour les opérations au niveau du bit.

Exemple :

```python
> x = 0b1001
> y = 0b1100
> x & y
0b1000
> x | y
0b1101
> x ^ y
0b0101
```
