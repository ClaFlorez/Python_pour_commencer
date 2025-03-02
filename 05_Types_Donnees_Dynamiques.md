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

## 2. Typage Dynamique et Affectation de Variables

Python est dynamiquement typé. Les variables peuvent changer de type :

```

x = 1
type(x)

```
Résultat : int

```

x = 'bonjour'
type(x)

```
Résultat : str

### Conversion de Types

```

x = '123'
x = int(x)

```
Résultat : 123

## 3. Opérateurs d'Affectation Composés

Python supporte des opérateurs comme `+=` :

```

i = 5
i += 1

```
Résultat : 6

## Opérateurs Relationnels

Python utilise `==`, `!=`, `<`, `>`, etc. :

```

x = 5
x == 5

```
Résultat : True

## Opérateurs Logiques

Python utilise `and`, `or`, `not` :

```

True and False

```
Résultat : False

## Opérateurs au Niveau du Bit

Python supporte `&`, `|`, `~`, `^`, etc. :

```

x = 0b1001
y = 0b1100
x \& y

```
Résultat : 0b1000
```

---

# 3. Opérateurs en Python

## Opérateurs d'Attribution Composée

| Opérateur | Équivalent à  |
| --------- | ------------- |
| `+=`      | `x = x + y`   |
| `-=`      | `x = x - y`   |
| `*=`      | `x = x * y`   |
| `/=`      | `x = x / y`   |
| `//=`     | `x = x // y`  |
| `**=`     | `x = x ** y`  |
| `%=`      | `x = x % y`   |

## Opérateurs Relationnels (Comparaison)

| Opérateur | Description                |
| --------- | -------------------------- |
| `==`      | Égalité                    |
| `!=`      | Différent                  |
| `<`       | Moins que                  |
| `<=`      | Moins ou égal à            |
| `>`       | Plus que                   |
| `>=`      | Plus ou égal à             |
| `in`      | Contenu dans une séquence  |
| `not in`  | Non contenu dans une séquence |
| `is`      | Référence au même objet    |
| `is not`  | Ne référence pas le même objet |

## Opérateurs Logiques

| Opérateur | Description     |
| --------- | --------------- |
| `and`     | ET logique      |
| `or`      | OU logique      |
| `not`     | Négation logique |

## Opérateurs Bit à Bit

| Opérateur | Description                     |
| --------- | ------------------------------- |
| `&`       | ET bit à bit                    |
| \`        | \`                              | OU bit à bit |
| `^`       | XOR bit à bit                   |
| `~`       | NON bit à bit                   |
| `<<`      | Décalage vers la gauche         |
| `>>`      | Décalage vers la droite         |

## Fonctions Intégrées Utiles

| Fonction       | Description                           |
| -------------- | ------------------------------------- |
| `round(x, n)`  | Arrondit `x` à `n` décimales          |
| `pow(x, y)`    | Élève `x` à la puissance `y`          |
| `abs(x)`       | Valeur absolue de `x`                 |
| `hex(x)`       | Représentation hexadécimale de `x`    |
| `bin(x)`       | Représentation binaire de `x`         |
| `oct(x)`       | Représentation octale de `x`          |
