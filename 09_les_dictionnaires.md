# Les Dictionnaires (Tableaux Associatifs) en Python

Un dictionnaire (ou tableau associatif) est une structure de données qui stocke des paires clé-valeur sous la forme `{clé1: valeur1, clé2: valeur2, ...}`.

## Caractéristiques des Dictionnaires

* **Paires Clé-Valeur :** Les dictionnaires Python supportent des paires clé-valeur (aussi appelées paires nom-valeur, tableaux associatifs ou mappings).
* **Délimiteurs :** Un dictionnaire est délimité par une paire d'accolades `{}`. La clé et la valeur sont séparées par deux-points (`:`) sous la forme `{clé1: valeur1, clé2: valeur2, ...}`.
* **Indexation par Clé :** Contrairement aux listes et aux tuples, qui indexent les éléments en utilisant un index entier (0, 1, 2, 3, ...), les dictionnaires peuvent être indexés en utilisant n'importe quel type de clé, y compris les nombres, les chaînes de caractères ou d'autres types.
* **Mutable :** Les dictionnaires sont mutables, ce qui signifie que leur contenu peut être modifié après leur création.

## Exemples d'Utilisation

```python
>>> dct = {'nom':'Pierre', 'genre':'masculin', 'âge':21}
>>> dct
{'âge': 21, 'nom': 'Pierre', 'genre': 'masculin'}
>>> dct['nom']       # Obtenir la valeur via la clé
'Pierre'
>>> dct['âge'] = 22   # Ré-assigner une valeur
>>> dct
{'âge': 22, 'nom': 'Pierre', 'genre': 'masculin'}
>>> len(dct)
3
>>> dct['email'] = '[email address removed]'   # Ajouter un nouvel élément
>>> dct
{'nom': 'Pierre', 'âge': 22, 'email': '[email address removed]', 'genre': 'masculin'}
>>> type(dct)
<class 'dict'>
