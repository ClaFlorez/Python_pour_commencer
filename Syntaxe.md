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

# One Python statement in one line, terminated by a newline.
# There is no semicolon at the end of a statement.
```python
x = 1     # Assign 1 to variable x
print(x)  # Print the value of the variable x
```
> Output: 1
```python
x + 1
```
> Output: 2
```python
y = x / 2
y
```
> Output: 1

# You can place multiple statements in one line, separated by semicolon.
```python
print(x); print(x+1); print(x+2)  # No ending semicolon
```
> Output:
 1
 2
 3

# An expression in brackets [] (i.e., list) can span multiple lines
```python
x = [1,
     22,
     333]  # Re-assign a list denoted as [v1, v2, ...] to variable x
x
> Output: [1, 22, 333]
```
# An expression in braces {} (i.e., associative array) can also span multiple lines
```python
x = {'name':'Peter',
     'gender':'male',
     'age':21
    }   # Re-assign a dictionary denoted as {k1:v1, k2:v2,...} to variable x
x
```
> Output: {'name': 'Peter', 'gender': 'male', 'age': 21}

# An expression in parentheses () can also span multiple lines
# You can break a long expression into several lines by enclosing it with parentheses ()
```python
x =(1 +
    2
    + 3
    -
    4)
x
```
> Output: 2

# You can break a long string into several lines with parentheses () too
```python
s = ('testing '   # No commas
     'hello, '
     'world!')
s
```
> Output: 'testing hello, world!'
