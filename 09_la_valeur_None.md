### La Valeur None en Python

Python fournit une valeur spéciale appelée `None` (notez la majuscule initiale), qui peut être utilisée pour initialiser un objet (qui sera abordé plus tard en POO). Par exemple :

```python
>>> x = None
>>> type(x)   # Obtenir le type
<class 'NoneType'>
>>> print(x)
None
```

### Vérification de la valeur `None`

Utilisez `is` et `is not` pour vérifier si une variable est `None` :

```python
>>> print(x is None)
True
>>> print(x is not None)
False
```

---

## Structures de données : Liste, Tuple, Dictionnaire et Ensemble

### Liste `[v1, v2, ...]`

Python dispose d'un puissant tableau dynamique intégré appelé `list`.

- Une liste est délimitée par des crochets `[]`.
- Elle peut contenir des éléments de types différents.
- Sa taille s'ajuste automatiquement.
- Elle est **mutable**, ce qui signifie que son contenu peut être modifié.

### Fonctions et opérateurs intégrés pour les listes

Une liste, comme une chaîne de caractères, est une séquence. Vous pouvez donc :

- Utiliser des fonctions intégrées comme `len()`.
- Utiliser des fonctions spécifiques aux séquences numériques, telles que `max()`, `min()`, et `sum()`.
- Employer des opérateurs comme `in`, `+` (concaténation), `*` (répétition), `del`, `[i]` (indexation) et `[m:n:step]` (tranchage).

### Indexation et tranchage

```python
lst = [8, 9, 6, 2]
print(lst[1])      # 9 (indexation positive)
print(lst[-2])     # 6 (indexation négative)
print(lst[1:3])    # [9, 6] (sous-liste)
print(lst[::-1])   # [2, 6, 9, 8] (liste inversée)
```

### Opérateurs courants sur les listes

| Opérateur | Utilisation | Description | Exemple |
|-----------|------------|-------------|---------|
| `in` / `not in` | `x in lst` / `x not in lst` | Vérifie la présence d'un élément | `9 in lst` → `True` |
| `+` | `lst + lst1` | Concaténation | `[8, 9] + [6, 2]` → `[8, 9, 6, 2]` |
| `*` | `lst * n` | Répétition | `[8, 9] * 2` → `[8, 9, 8, 9]` |
| `del` | `del lst[i]` | Suppression | `del lst[1]` → `[8, 6, 2]` |

### Fonctions spécifiques aux listes

| Fonction | Description | Exemple |
|----------|-------------|---------|
| `len(lst)` | Retourne la longueur de la liste | `len([8, 9, 6])` → `3` |
| `max(lst)`, `min(lst)` | Retourne le max/min d'une liste numérique | `max([8, 9, 6])` → `9` |
| `sum(lst)` | Retourne la somme des éléments | `sum([8, 9, 6])` → `23` |
| `lst.append(x)` | Ajoute un élément en fin de liste | `lst.append(5)` |
| `lst.extend(lst1)` | Étend la liste avec une autre | `lst.extend([4, 5])` |
| `lst.insert(i, x)` | Insère un élément à l'index i | `lst.insert(1, 99)` |
| `lst.pop(i)` | Supprime et retourne l'élément à l'index i | `lst.pop(1)` |
| `lst.remove(x)` | Supprime la première occurrence de x | `lst.remove(9)` |
| `lst.sort()` | Trie la liste sur place | `lst.sort()` |
| `lst.reverse()` | Inverse la liste sur place | `lst.reverse()` |

### Utilisation d'une liste comme pile (LIFO) et file (FIFO)

- **Pile** (Last-In-First-Out) : utilisez `append(x)` et `pop()`.
- **File** (First-In-First-Out) : utilisez `append(x)` et `pop(0)` (peu efficace, préférez `collections.deque`).

---

## Tuple `(v1, v2, ...)`

Un tuple est similaire à une liste mais **immuable** (comme les chaînes de caractères). Cela le rend plus efficace.

```python
>>> tup = (123, 4.5, 'hello')
>>> tup[1]       # Accès via index
4.5
>>> tup[1:3]     # Tranchage
(4.5, 'hello')
>>> tup[1] = 9   # Erreur : un tuple est immuable
TypeError: 'tuple' object does not support item assignment
```

Un tuple à un seul élément nécessite une virgule :

```python
>>> tup = (5,)  # Correct
>>> x = (5)     # Incorrect, traité comme un entier
```

### Conversion entre liste et tuple

```python
>>> tuple([1, 2, 3])  # Liste → Tuple
(1, 2, 3)
>>> list((1, 2, 3))   # Tuple → Liste
[1, 2, 3]
```

---

