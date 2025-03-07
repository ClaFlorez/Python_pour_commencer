# Type de Caractère en Python

En Python, il n'existe pas de type de données dédié aux caractères. Un caractère est simplement une chaîne de longueur 1. Vous pouvez utiliser l'opérateur d'indexation pour extraire un caractère individuel d'une chaîne ou le parcourir avec une boucle `for`.

## Fonctions Intégrées : `ord()` et `chr()`
Python fournit les fonctions `ord()` et `chr()` pour manipuler les caractères :

```python
# ord(c) retourne l'entier Unicode du caractère
print(ord('A'))   # 65
print(ord('e'))   # 101
print(ord('水'))  # 27700

# chr(i) retourne le caractère correspondant à un entier Unicode
print(chr(65))    # 'A'
print(chr(27700)) # '水'
```

## Unicode vs ASCII
En Python 3, les chaînes sont par défaut en Unicode. Les chaînes ASCII sont représentées sous forme de `bytes`, préfixées par `b` :

```python
ascii_str = b'ABC'  # Chaîne ASCII
unicode_str = 'ABC'  # Chaîne Unicode
```

Il est recommandé d'utiliser Unicode pour la compatibilité internationale.

## Fonctions Utiles pour les Chaînes
Python propose de nombreuses fonctions de manipulation de chaînes via la classe `str` :

| Fonction | Description |
|----------|------------|
| `s.strip()` | Supprime les espaces en début et fin de `s` |
| `s.upper()` | Convertit `s` en majuscules |
| `s.lower()` | Convertit `s` en minuscules |
| `s.isupper()` | Vérifie si `s` est en majuscules |
| `s.islower()` | Vérifie si `s` est en minuscules |
| `s.find(sub)` | Trouve l'index du sous-texte `sub` (ou -1 si absent) |
| `s.startswith(sub)` | Vérifie si `s` commence par `sub` |
| `s.endswith(sub)` | Vérifie si `s` finit par `sub` |
| `s.split(delim)` | Divise `s` en une liste selon `delim` |
| `'delim'.join(liste)` | Concatène les éléments de `liste` avec `delim` |

### Exemples
```python
s = "Bonjour, monde"
print(s.upper())    # 'BONJOUR, MONDE'
print(s.find("mon"))  # 9
print(s.startswith("Bon"))  # True
print(s.split(", "))  # ['Bonjour', 'monde']
```

## Formatage des Chaînes
Python offre plusieurs manières de formater une chaîne :

### 1. `str.format()`
```python
msg = "|{}|{}|".format("Bonjour", "monde")
print(msg)  # '|Bonjour|monde|'
```

### 2. F-strings (Python 3.6+)
```python
nom = "Alice"
age = 25
print(f"Nom: {nom}, Age: {age}")  # 'Nom: Alice, Age: 25'
```

### 3. `str.ljust()`, `str.rjust()`, `str.center()`
```python
print("123".rjust(5))  # '  123'
print("123".center(5))  # ' 123 '
```

---
