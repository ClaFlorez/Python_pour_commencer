# Syntaxe de base de Python

## Commentaires de fin de ligne (EOL)

Un commentaire Python commence par un dièse (#) et se poursuit jusqu'à la fin de la ligne courante (EOL). Les commentaires sont ignorés par l'interpréteur Python, mais ils sont essentiels pour fournir des explications et de la documentation aux autres (et à vous-même trois jours plus tard) pour lire votre programme. Utilisez les commentaires généreusement.

> **Note :** Il n'y a PAS de commentaire multi-lignes en Python ! (Contrairement à C/C++/Java qui supportent les commentaires multi-lignes via /* ... */.)

## Instructions

Une instruction Python est délimitée par un saut de ligne. Une instruction ne peut pas traverser les limites de ligne, sauf dans les cas suivants :

- Une expression entre parenthèses (), crochets [], et accolades {} peut s'étendre sur plusieurs lignes.
- Un antislash (\) à la fin de la ligne indique une continuation sur la ligne suivante. Cette règle est ancienne et n'est PAS recommandée car elle est sujette aux erreurs.

> Contrairement à C/C++/C#/Java, vous ne mettez pas de point-virgule (;) à la fin d'une instruction Python. Mais vous pouvez placer plusieurs instructions sur une seule ligne, séparées par des points-virgules (;).

### Exemples :

## Une instruction Python sur une ligne, terminée par un saut de ligne.
## Il n'y a pas de point-virgule à la fin d'une instruction.
```python
x = 1     # Assigne 1 à la variable x
print(x)   # Affiche la valeur de la variable x
```
> Sortie : 1
```python
x + 1
```
> Sortie : 2
```python
y = x / 2
y
```
> Sortie : 1

## Vous pouvez placer plusieurs instructions sur une ligne, séparées par des points-virgules.
```python
print(x); print(x+1); print(x+2)  # Pas de point-virgule à la fin
```
> Sortie :
> 1
> 2
> 3

## Une expression entre crochets [] (c'est-à-dire une liste) peut s'étendre sur plusieurs lignes
```python
x = [1,
     22,
     333]  # Réassigne une liste notée [v1, v2, ...] à la variable x
x
```
> Sortie : [1, 22, 333]

## Une expression entre accolades {} c'est-à-dire un tableau associatif - dictionnaire peut aussi s'étendre sur plusieurs lignes.
```python
x = {'name':'Peter',
'gender':'male',
'age':21
    }   # Réassigne un dictionnaire noté {k1:v1, k2:v2,...} à la variable x
x
```
> Sortie : {'name': 'Peter', 'gender': 'male', 'age': 21}

## Une expression entre parenthèses () peut aussi s'étendre sur plusieurs lignes
## Vous pouvez diviser une longue expression en plusieurs lignes en l'entourant de parenthèses ()
```python
x =(1 +
    2
    + 3
    -
    4)
x
```
> Sortie : 2

## Vous pouvez aussi diviser une longue chaîne en plusieurs lignes avec des parenthèses ()
```python
s = ('testing '   # Pas de virgules
     'hello, '
     'world!')
s
```
> Sortie : 'testing hello, world!'
