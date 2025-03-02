# Types de Données : Nombre, Chaîne et Liste

Python prend en charge divers types de nombres tels que :
- `int` (entiers comme `123`, `-456`)
- `float` (nombres à virgule flottante comme `3.1416`, `1.2e3`, `-4.5E-6`)
- `bool` (booléens : `True` ou `False`)

Python prend également en charge les chaînes de texte (suite de caractères). Les chaînes peuvent être délimitées par des guillemets simples ou doubles, par exemple : `'hello'`, `"world"`, `''` ou `""` (chaîne vide).

Python dispose d'une structure de tableau dynamique appelée **liste**, notée `lst = [v1, v2, ..., vn]`. Vous pouvez référencer le i-ème élément via `lst[i]`. Contrairement aux tableaux en C/C++/Java, une liste Python **n'a pas de taille fixe** et peut être modifiée dynamiquement à l'exécution.

## Entrée/Sortie Console : Fonctions `input()` et `print()`

La fonction `input()` permet de lire une entrée clavier sous forme de chaîne, tandis que `print()` affiche du texte sur la console.

Exemple :

```python
x = input('Entrez un nombre : ')
print(x)  # Affiche l'entrée utilisateur
```

### Conversion de types :

```python
x = int(input('Entrez un entier : '))
print(x, type(x))  # Convertit l'entrée en entier
```

## Fonction `print()`

La fonction `print()` a la signature suivante :

```python
print(*objects, sep=' ', end='\n', file=sys.stdout, flush=False)
```

### Exemples :

```python
print('pomme')  # Un seul élément
print('pomme', 'orange', 'banane')  # Plusieurs éléments
```

#### Modifier le séparateur et la fin de ligne

```python
# Sans saut de ligne
for item in [1, 2, 3, 4]:
    print(item, end='')  # Affiche : 1234

# Avec un séparateur personnalisé
print('pomme', 'orange', 'banane', sep=', ')  # Affiche : pomme, orange, banane
```

## `print()` en Python 2 vs Python 3

Python 2 et Python 3 **ne sont pas compatibles**. En Python 2, `print` était un mot-clé et pouvait s'utiliser sans parenthèses. En Python 3, c'est une fonction, donc les parenthèses sont obligatoires.

Exemple en **Python 3** :

```python
print('bonjour')  # Correct
print 'bonjour'   # Erreur de syntaxe en Python 3
```

Exemple en **Python 2** :

```python
print 'bonjour'   # Correct en Python 2
print('bonjour')  # Fonctionne aussi
```

🔹 **Recommandation :** Toujours utiliser `print()` avec des parenthèses pour assurer la portabilité entre versions de Python.
