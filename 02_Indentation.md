# Bloc, Indentation et Instructions Composées

Un bloc est un groupe d'instructions s'exécutant comme une unité. Contrairement à C/C++/C#/Java, qui utilisent des accolades `{}` pour regrouper les instructions dans un bloc, Python utilise l'indentation. En d'autres termes, l'indentation est syntaxiquement significative en Python - le bloc de code doit être correctement indenté. Cette syntaxe impose une bonne structuration, facilitant ainsi la lisibilité du code !

Une instruction composée, telle qu'une condition (`if-else`), une boucle (`while`, `for`) ou une définition de fonction (`def`), commence par une ligne d'en-tête terminée par deux-points (`:`), suivie d'un bloc de code indenté, comme suit :

```python
en_tete_1:          # Les en-têtes se terminent par un deux-points
    instruction_1_1  # Les blocs de code sont indentés (il est recommandé d'utiliser 4 espaces)
    instruction_1_2
    ......

en_tete_2:
    instruction_2_1
    instruction_2_2
    ......
```

Il est possible de placer le bloc de code sur une seule ligne en séparant les instructions par un point-virgule (`;`).
**Cela n'est PAS recommandé.**

```python
en_tete_1: instruction_1_1
en_tete_2: instruction_2_1; instruction_2_2; ......
```

## Exemples

### Instruction if-else
```python
x = 0
if x == 0:
    print('x est zéro')
else:
    print('x n'est pas zéro')
```

Ou sur une seule ligne :
```python
if x == 0: print('x est zéro')
else: print('x n'est pas zéro')
```

### Boucle while - Somme des nombres de 1 à 100
```python
somme = 0
nombre = 1
while nombre <= 100:
    somme += nombre
    nombre += 1
print(somme)
```

Ou sur une seule ligne :
```python
while nombre <= 100: somme += nombre; nombre += 1
```

### Définition de la fonction `somme_1_a_n()`
```python
def somme_1_a_n(n):
    """Somme des nombres de 1 à n"""
    somme = 0
    i = 0
    while i <= n:
        somme += i
        i += 1
    return somme

print(somme_1_a_n(100))  # Appel de la fonction
```

Python ne précise pas combien d'espaces doivent être utilisés pour l'indentation, mais toutes les instructions d'un **même bloc de code** doivent commencer à la **même distance** depuis la marge. Vous pouvez utiliser des espaces ou des tabulations, mais vous **ne pouvez pas** les mélanger dans un même bloc. Il est recommandé d'utiliser **4 espaces** par niveau d'indentation.

L'utilisation des deux-points (`:`) et de l'indentation pour structurer les blocs de code peut sembler inhabituelle si vous venez de C/C++/C#/Java. Cependant, Python impose ces règles strictes pour obliger les programmeurs à écrire du code clair et lisible !
