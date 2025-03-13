# Exercices sur `while`

### 1. Afficher les nombres de 1 à 10 en utilisant une boucle `while`.
```python
n = 1
while n <= 10:
    print(n)
    n += 1
```

### 2. Demander à l'utilisateur un nombre et afficher sa table de multiplication jusqu'à 10 en utilisant `while`.
```python
n = int(input("Entrez un nombre : "))
i = 1
while i <= 10:
    print(f"{n} x {i} = {n * i}")
    i += 1
```

### 3. Demander un mot à l'utilisateur et le répéter tant qu'il ne tape pas "stop".
```python
mot = ""
while mot.lower() != "stop":
    mot = input("Entrez un mot (ou 'stop' pour arrêter) : ")
    print(mot)
```

### 4. Afficher la somme des nombres de 1 à 100 en utilisant `while`.
```python
somme = 0
n = 1
while n <= 100:
    somme += n
    n += 1
print("Somme de 1 à 100 :", somme)
```

### 5. Demander un mot et compter le nombre de voyelles (`a, e, i, o, u, y`) avec `while`.
```python
mot = input("Entrez un mot : ")
voyelles = "aeiouyAEIOUY"
count = 0
i = 0
while i < len(mot):
    if mot[i] in voyelles:
        count += 1
    i += 1
print("Nombre de voyelles :", count)
```

### 6. Afficher tous les nombres pairs de 2 à 20 en utilisant `while`.
```python
n = 2
while n <= 20:
    print(n)
    n += 2
```

### 7. Demander un mot et l'afficher lettre par lettre avec `while`.
```python
mot = input("Entrez un mot : ")
i = 0
while i < len(mot):
    print(mot[i])
    i += 1
```

### 8. Simuler un compte à rebours de 10 à 0 en utilisant `while`, puis afficher "Décollage !".
```python
n = 10
while n >= 0:
    print(n)
    n -= 1
print("Décollage !")
```

### 9. Demander un nombre à l'utilisateur et lui dire si c'est un multiple de 3 en utilisant `while`.
```python
n = int(input("Entrez un nombre : "))
while n % 3 != 0:
    n = int(input("Essayez encore, entrez un multiple de 3 : "))
print(f"{n} est un multiple de 3.")
```

### 10. Générer un nombre aléatoire entre 1 et 10, et demander à l'utilisateur de le deviner en utilisant `while`.
```python
import random
nombre_secret = random.randint(1, 10)
reponse = 0
while reponse != nombre_secret:
    reponse = int(input("Devinez le nombre entre 1 et 10 : "))
    if reponse < nombre_secret:
        print("Trop petit !")
    elif reponse > nombre_secret:
        print("Trop grand !")
print("Bravo, vous avez trouvé !")
```

# Exercices sur `for`

### 1. Afficher les nombres de 1 à 10 avec une boucle `for`.
```python
for n in range(1, 11):
    print(n)
```

### 2. Afficher la table de multiplication de 7 jusqu'à 10 avec `for`.
```python
for i in range(1, 11):
    print(f"7 x {i} = {7 * i}")
```

### 3. Afficher tous les éléments d'une liste donnée `["pomme", "banane", "orange"]` avec `for`.
```python
fruits = ["pomme", "banane", "orange"]
for fruit in fruits:
    print(fruit)
```

### 4. Afficher les caractères d'un mot donné par l'utilisateur un par un avec `for`.
```python
mot = input("Entrez un mot : ")
for lettre in mot:
    print(lettre)
```

### 5. Calculer la somme des nombres de 1 à 50 avec `for`.
```python
somme = sum(range(1, 51))
print("Somme de 1 à 50 :", somme)
```

### 6. Afficher tous les nombres impairs de 1 à 15 avec `for`.
```python
for n in range(1, 16, 2):
    print(n)
```

### 7. Afficher tous les nombres de 10 à 1 avec `for`.
```python
for n in range(10, 0, -1):
    print(n)
```

### 8. Demander une phrase et compter combien de fois la lettre "a" apparaît en utilisant `for`.
```python
phrase = input("Entrez une phrase : ")
count = sum(1 for lettre in phrase if lettre == "a")
print("Nombre de 'a' :", count)
```

### 9. Afficher les 5 premiers éléments d'une liste donnée `[10, 20, 30, 40, 50, 60]` avec `for`.
```python
liste = [10, 20, 30, 40, 50, 60]
for elem in liste[:5]:
    print(elem)
```

### 10. Afficher une pyramide de `*` avec 5 lignes en utilisant `for`.
```python
for i in range(1, 6):
    print("*" * i)
```

# Exercices sur les fonctions classiques (`def`)

### 1. Créer une fonction qui affiche "Bonjour !".
```python
def dire_bonjour():
    print("Bonjour !")
```

### 2. Créer une fonction qui prend un prénom en paramètre et affiche "Bonjour [prénom] !".
```python
def dire_bonjour_prenom(prenom):
    print(f"Bonjour {prenom} !")
```

### 3. Créer une fonction qui prend deux nombres et retourne leur somme.
```python
def somme(a, b):
    return a + b
```

### 4. Réécrire ces fonctions en utilisant la syntaxe `lambda`.
```python
dire_bonjour = lambda: print("Bonjour !")
dire_bonjour_prenom = lambda prenom: print(f"Bonjour {prenom} !")
somme = lambda a, b: a + b
```
