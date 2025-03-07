# Types de Données et Typage Dynamique en Python

Python offre une variété de types de données intégrés, notamment :

- **Numériques** (Entiers, Flottants, Booléens, Complexes)
- **Chaînes de caractères (String)**
- **Listes, Tuples, Ensembles et Dictionnaires**
- **Fichiers**

Des types plus avancés, tels que **Decimal** et **Fraction**, sont disponibles dans des modules externes.

## 1. Types Numériques

### Entiers (`int`)

Les entiers n'ont pas de limite de taille :

```

123 + 456 - 789

```
Résultat : -210

```

2 ** 888

```
Résultat : Très grand nombre

### Flottants (`float`)

Les nombres flottants sont en double précision :

```

1.23 * -4e5

```
Résultat : -492000.0

```

type(1.2)

```
Résultat : float

### Booléens (`bool`)

Les booléens sont `True` ou `False` :

```

8 == 8

```
Résultat : True

```

bool(0)

```
Résultat : False

### Complexes (`complex`)

Les nombres complexes ont une partie réelle et imaginaire :

```

x = 1 + 2j
x.real, x.imag

```
Résultat : (1.0, 2.0)

### Decimal et Fraction

Pour plus de précision, utilisez `decimal.Decimal` :

```

import decimal
x = decimal.Decimal('0.1')
x * 3

```
Résultat : 0.3

# Typage Dynamique et Opérateur d'Attribution

Python est un langage à typage dynamique (contrairement à C, C++ ou Java, qui sont à typage statique). En Python, le type est associé à l'objet, et non à la variable. Autrement dit, une variable n'a pas de type fixe et peut référencer des objets de différents types.

## Caractéristiques Clés
- Il n'est pas nécessaire de déclarer une variable avant de l'utiliser.
- Elle est créée automatiquement lorsqu'une valeur lui est attribuée.
- Le type d'une variable peut changer en lui réassignant une nouvelle valeur.
- On peut obtenir le type d'un objet référencé par une variable avec `type(var_name)`.

### Exemple :
```python
x = 1         # Assigner un entier
print(x)      # Afficher x
# Sortie : 1
print(type(x)) # Obtenir le type
# Sortie : <class 'int'>

x = 1.0       # Réassigner un flottant
print(type(x))
# Sortie : <class 'float'>

x = 'hello'   # Réassigner une chaîne de caractères
print(type(x))
# Sortie : <class 'str'>
```

---

## Conversion de Types (`int(x)`, `float(x)`, `str(x)`)
Python permet la conversion explicite des types via des fonctions intégrées comme `int(x)`, `float(x)`, `str(x)`, `bool(x)`, etc.

### Exemple :
```python
x = '123'     # Chaîne de caractères
print(type(x))
# Sortie : <class 'str'>

x = int(x)    # Convertir en entier
print(type(x))
# Sortie : <class 'int'>

x = float(x)  # Convertir en flottant
print(type(x))
# Sortie : <class 'float'>

x = str(x)    # Reconvertir en chaîne de caractères
print(type(x))
# Sortie : <class 'str'>

x = bool(x)   # Convertir en booléen
print(x)
# Sortie : True
```

---

## Vérifier le Type d'une Variable : `isinstance(instance, type)`
La fonction `isinstance()` permet de vérifier si un objet appartient à un type spécifique.

### Exemple :
```python
print(isinstance(123, int)) # True
print(isinstance('a', int)) # False
print(isinstance('a', str)) # True
```

---

## Opérateur d'Attribution (`=`)
Python permet d'attribuer des valeurs sans déclarer les variables au préalable.

```python
x = 8        # Créer une variable
x = 'Hello'  # Réassigner un autre type

print(y)     # Erreur : variable non définie
# NameError: name 'y' is not defined
```

### Attribution Chaînée et par Paires
```python
a = 1  # Attribution classique
b, c, d = 123, 4.5, 'Hello'  # Attribution par paires

print(b, c, d)
# Sortie : 123 4.5 Hello

e = f = g = 123  # Attribution en chaîne
print(e, f, g)
# Sortie : 123 123 123
```

---

## Opérateur `del`
On peut supprimer une variable avec `del`.

```python
x = 8
print(x)  # 8

del x
print(x)  # NameError: name 'x' is not defined
```

---

## Opérations Numériques
Python prend en charge les opérateurs arithmétiques suivants :

| Opérateur | Description          | Exemple        |
|----------|----------------------|---------------|
| `+`      | Addition             | `x + y`       |
| `-`      | Soustraction         | `x - y`       |
| `*`      | Multiplication       | `x * y`       |
| `/`      | Division flottante    | `1 / 2  # 0.5` |
| `//`     | Division entière      | `1 // 2  # 0` |
| `**`     | Exponentiation        | `2 ** 3  # 8` |
| `%`      | Modulo (reste)        | `9 % 2  # 1`  |

### Exemple :
```python
print(9 % 2)   # 1
print(-9 % 2)  # 1
print(8.9 // 2.5)  # 3.0
```

**Remarque :** Python utilise la division par plancher (`//`) pour les entiers, contrairement à Java qui tronque vers zéro.

---

## Opérateurs d'Attribution Composée
Python prend en charge des opérateurs comme `+=`, `-=`, `*=`, `/=`, `//=`, `**=`, `%=`.

```python
i = 5
i += 1  # Équivalent à i = i + 1
print(i)  # 6
```

**Remarque :** Python **NE** possède pas `++` ni `--` comme en C/C++/Java.

---

## Opérations avec Types Mixtes
Si une opération est effectuée entre des types différents, le type "inférieur" est converti en type "supérieur" avant l'opération.

Ordre des types : `int < float < complex`
```python
print(1 + 2.3)  # 3.3 (int + float => float)
```

---

## Opérateurs Relationnels (Comparaison)
Ces opérateurs retournent un booléen (`True` ou `False`).

| Opérateur | Description |
|----------|------------|
| `==`     | Égalité   |
| `!=`     | Différent |
| `<`      | Inférieur |
| `<=`     | Inférieur ou égal |
| `>`      | Supérieur |
| `>=`     | Supérieur ou égal |
| `in`     | Contenu dans une séquence |
| `is`     | Même objet en mémoire |

```python
x = [1, 2, 3]
print(2 in x)  # True
print(4 in x)  # False
```

---

## Opérateurs Logiques (`and`, `or`, `not`)

| Opérateur | Description      | Exemple |
|----------|-----------------|---------|
| `and`    | ET logique      | `x and y` |
| `or`     | OU logique       | `x or y`  |
| `not`    | NON logique | `not x`  |

```python
print(True and False)  # False
print(True or False)   # True
print(not True)        # False
```

---

