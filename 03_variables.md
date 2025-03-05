# Variables, Identifiants et Constantes

Comme dans tous les langages de programmation, une variable est un emplacement de stockage nommé. Une variable a un nom (ou identifiant) et contient une valeur.

Comme la plupart des langages de script interprétés (comme JavaScript ou Perl), Python est **dynamiquement typé**. Il n'est **pas nécessaire** de déclarer une variable avant de l'utiliser. Une variable est créée lors de son affectation initiale. (Contrairement aux langages à typage statique comme C, C++, Java ou C#, où vous devez d'abord déclarer le nom et le type de la variable avant de l'utiliser.)

## Qu'est-ce que le REPL ?

Les instructions avec >>> cmd ou powershell. Le **REPL (Read-Eval-Print Loop)** est un environnement interactif qui permet d'exécuter des commandes Python en temps réel. Il est très utile pour tester du code rapidement sans avoir besoin de créer un fichier `.py`.
Par exemple :

```python
>>> somme = 1          # Création d'une variable 'somme' avec une valeur entière
>>> somme
1
>>> type(somme)       # Vérification du type de données
<class 'int'>

>>> moyenne = 1.23     # Création d'une variable 'moyenne' avec une valeur flottante
>>> moyenne
1.23
>>> moyenne = 4.5e-6   # Réaffectation avec une notation scientifique
>>> moyenne
4.5e-06
>>> type(moyenne)      # Vérification du type
<class 'float'>

>>> moyenne = 78       # Réaffectation avec une valeur entière
>>> moyenne
78
>>> type(moyenne)      # Changement de type vers 'int'
<class 'int'>

>>> msg = 'Bonjour'    # Création d'une variable 'msg' contenant une chaîne de caractères
>>> msg
'Bonjour'
>>> type(msg)         # Vérification du type
<class 'str'>
```

## Variables en Python

Comme mentionné, Python est **dynamiquement typé**. Python associe les types aux **objets**, et non aux variables. Cela signifie qu'une variable peut contenir des objets de types différents, comme illustré ci-dessus.

## Règles de Nomination des Identifiants

- Un identifiant commence par une lettre (A-Z, a-z) ou un tiret bas `_`, suivi de zéro ou plusieurs lettres, chiffres (0-9) et tirets bas `_`.
- Les caractères spéciaux comme `$` et `@` ne sont **pas autorisés**.
- Par convention, les variables commençant par `_` sont considérées comme **privées**.

## Mots-clés

Python 3 a **35 mots réservés** (ou mots-clés) qui **ne peuvent pas** être utilisés comme identifiants :

```
True, False, None  # Littéraux booléens et spéciaux
import, as, from
if, elif, else, for, in, while, break, continue, pass, with  # Contrôle de flux
def, return, lambda, global, nonlocal  # Fonctions
class
and, or, not, is, del  # Opérateurs
try, except, finally, raise, assert  # Gestion des erreurs
await, async, yield
```

## Conventions de Nomination des Variables

Deux conventions sont couramment utilisées :

1. **Mots en minuscules**, optionnellement séparés par des **tirets bas** `_` pour améliorer la lisibilité. Exemples : `nombre_etudiants`, `x_max`, `valeur_moyenne`.
2. **CamelCase**, où le premier mot est en minuscule et les suivants commencent par une majuscule. Exemples : `nombreEtudiants`, `xMax`, `yMin`, `estValide`.

- **Le CamelCase** est la convention de Java.
- **Les noms en minuscules avec underscores** sont plus courants en Python et C/C++.

## Recommandations

- Utilisez des noms **significatifs** qui reflètent la signification de la variable. Par exemple, `nb_etudiants` est plus clair que `n` ou `x`.
- Évitez les noms de variables inutiles comme `a`, `b`, `c`, `i1`, `i2`, `exemple12`.
- Préférez les noms explicites aux noms abrégés (sauf pour les index `i`, `j`, `k`).
- Différenciez **singulier/pluriel** : `ligne` (une seule ligne) et `lignes` (liste de lignes).

## Constantes en Python

Python ne prend **pas en charge** les constantes immuables (contrairement à `const` en C/C++ et `final` en Java).

Cependant, par convention, les **variables en majuscules** avec des underscores sont utilisées pour représenter des constantes **qui ne devraient pas** être modifiées :

```python
MAX_LIGNES = 100
ECRAN_X_MAX = 1920
```

Rien n'empêche leur modification en Python, mais leur usage indique qu'elles sont destinées à rester constantes dans le programme.
