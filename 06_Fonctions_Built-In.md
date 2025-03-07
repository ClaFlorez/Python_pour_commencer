# Fonctions Intégrées en Python

Python fournit de nombreuses fonctions intégrées pour manipuler les nombres et d'autres types de données.

## Fonctions Mathématiques
- `round(x)`: Arrondit un nombre.
- `pow(x, y)`: Exponentiation.
- `abs(x)`: Valeur absolue.

## Fonctions de Type
- `type(x)`: Retourne le type de l'objet `x`.
- `isinstance(x, type)`: Vérifie si `x` est une instance du type donné.

## Conversion de Type
- `int(x)`, `float(x)`, `str(x)`, `bool(x)`, etc.

## Conversion en Différentes Bases
- `hex(x)`: Convertit en hexadécimal.
- `bin(x)`: Convertit en binaire.
- `oct(x)`: Convertit en octal.

### Exemples
```python
# Test de la fonction round()
x = 1.23456
print(round(x))  # Arrondi à l'entier le plus proche : 1
print(round(x, 2))  # Arrondi à 2 décimales : 1.23

# Test d'autres fonctions intégrées
print(pow(2, 5))  # 32
print(abs(-4.1))  # 4.1

# Conversion de base
print(hex(1234))  # '0x4d2'
print(bin(254))   # '0b11111110'
print(oct(1234))  # '0o2322'
```

## Liste des Fonctions Intégrées
```python
print(dir(__builtins__))
# Affiche toutes les fonctions intégrées disponibles en Python
```

## Opérateurs Bit à Bit (Avancé)
Python prend en charge les opérateurs bit à bit suivants :

| Opérateur | Description                 | Exemple          |
|------------|-----------------------------|------------------|
| `&`       | ET bit à bit               | `x & y`         |
| `|`       | OU bit à bit              | `x | y`         |
| `~`       | NON bit à bit (négation)  | `~x`            |
| `^`       | XOR bit à bit              | `x ^ y`         |
| `<<`      | Décalage à gauche         | `x << 2`        |
| `>>`      | Décalage à droite        | `x >> 2`        |

## Chaînes de Caractères
Les chaînes de caractères en Python peuvent être délimitées par des guillemets simples (`'...'`) ou doubles (`"..."`). Python prend en charge les chaînes multi-lignes avec trois guillemets : `'''...'''` ou `"""..."""`.

### Exemples
```python
s1 = 'pomme'
s2 = "orange"
s3 = "'orange'"  # Pas besoin d'échappement
s4 = "\"orange\""  # Nécessite un échappement

s5 = """test
12345"""
print(s5)  # 'test\n12345'
```

### Séquences d'échappement
| Séquence | Description |
|-----------|-------------|
| `\t`      | Tabulation |
| `\n`      | Nouvelle ligne |
| `\r`      | Retour chariot |
| `\'`      | Apostrophe dans une chaîne entre guillemets simples |
| `\"`      | Guillemets doubles dans une chaîne entre guillemets doubles |
| `\\`      | Anti-slash |

### Opérateurs et Fonctions Intégrées pour les Chaînes
| Fonction / Opérateur | Description |
|----------------------|-------------|
| `len(s)`            | Longueur de la chaîne `s` |
| `s1 + s2`           | Concaténation |
| `s * n`             | Répétition `n` fois |
| `s[i]`              | Accès à l'index `i` |
| `s[m:n]`            | Extraction d'une sous-chaîne |
| `s[:]`              | Copie de la chaîne |
| `s.lower()`         | Conversion en minuscule |
| `s.upper()`         | Conversion en majuscule |

### Exemples
```python
s = "Bonjour"
print(len(s))     # 7
print(s[1:4])     # 'onj'
print(s + " !")   # 'Bonjour !'
print(s * 2)      # 'BonjourBonjour'
print(s.upper())  # 'BONJOUR'
```

---
