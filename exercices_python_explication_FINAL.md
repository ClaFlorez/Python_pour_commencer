# 🐍 Exercices Python — Explications détaillées

![Logo CLAUDIA.ca](claud-iaca-noir.png)

Ce document contient des explications en français pour chaque exercice du fichier Python fourni. Il est destiné à une meilleure compréhension des concepts de programmation en Python.

---

## 1️⃣ Nombres pairs avec `while`
```python
def nombres_pairs_while(n: int) -> list:
    nombres_pairs = []
    i = 0
    while i <= n:
        if i % 2 == 0:
            nombres_pairs.append(i)
        i += 1
    return nombres_pairs
```
🎯 **Objectif :** Créer une liste de nombres pairs jusqu'à `n` en utilisant une boucle `while`.

🧠 **Principe :** On initialise `i = 0`, puis on l’incrémente tant qu’il est inférieur ou égal à `n`. Si `i` est pair (`i % 2 == 0`), on l’ajoute à la liste.

---

## 2️⃣ Nombres pairs avec `for`
```python
def nombres_pairs_for(n: int) -> list:
    nombres_pairs = []
    for i in range(n + 1):
        if i % 2 == 0:
            nombres_pairs.append(i)
    return nombres_pairs
```
🎯 Même objectif que le précédent, mais avec une boucle `for`. Cela rend le code plus compact.

---

## 3️⃣ Zippage de deux listes
```python
def zip_listes(liste1: list, liste2: list) -> list:
    longueur_min = min(len(liste1), len(liste2))
    resultat = []
    for i in range(longueur_min):
        resultat.append((liste1[i], liste2[i]))
    return resultat
```
🔗 **But :** Fusionner deux listes en une seule liste de couples (tuples).

🧠 **Astuce :** On s’arrête à la taille de la plus petite liste pour éviter les erreurs.

---

## 4️⃣ Intersection de deux listes (avec ou sans doublons)
```python
def intersection_listes(liste1: list, liste2: list) -> list:
    intersection = []
    for element in liste1:
        if element in liste2 and element not in intersection:
            intersection.append(element)
    return intersection
```
🎯 **Objectif :** Trouver les éléments communs dans deux listes sans doublons.

📌 **Note :** `intersection_listes` et `intersection_listes_sans_doublons` sont identiques ici, car on gère les doublons manuellement.

---

## 5️⃣ Somme des éléments d'une liste
```python
def somme_liste(liste: list) -> int:
    somme = 0
    for element in liste:
        somme += element
    return somme
```
➕ **Objectif :** Calculer la somme d’une liste de nombres, même si la liste est vide (dans ce cas, résultat = 0).

---

## 6️⃣ Quelques opérations sur les objets Python
```python
x = 4
y = 4
print(x is y)       # True car littéraux
print(x is not y)   # False

x = [1, 2, 3]
y = [1, 2, 3]
print(x is y)       # False car deux objets différents
print(x == y)       # True car contenu égal
```
💡 `is` vérifie **l'identité d'objet** (même emplacement en mémoire), alors que `==` compare les **valeurs**.

---

## 7️⃣ Listes en compréhension
```python
carres = [x**2 for x in range(10)]
```
✨ Une manière élégante de générer une liste. Ici, on crée les carrés des nombres de 0 à 9.

---

## 8️⃣ Différence entre listes mutables/immutables

![Illustration: paramètre mutable et comparaison NumPy vs Listes Python](A_digital_educational_comparison_graphic_in_the_im.png)
```python
def ajouter_element(element, liste=[]):
    liste.append(element)
    return liste

print(ajouter_element(1))  # [1]
print(ajouter_element(2))  # [1, 2] ❗️Effet de bord !
```
🚨 Mauvaise pratique : les paramètres par défaut mutables peuvent causer des effets indésirables. 

✔️ Bonne pratique :
```python
def ajouter_element(element, liste=None):
    if liste is None:
        liste = []
    liste.append(element)
    return liste
```
---

## 9️⃣ NumPy vs Listes Python
📊 Comparaison de performance entre opérations sur des listes natives et des tableaux NumPy :
- NumPy est **plus rapide** grâce à la vectorisation
- NumPy utilise **moins de mémoire**

```python
import numpy as np
import time

arr_np = np.arange(10_000_000)
arr_np = arr_np * 2
```
💡 À utiliser pour le traitement de grandes données.

---

## 🔟 Fonctions avec `*args` et `**kwargs`
```python
def somme(*args):
    total = 0
    for arg in args:
        total += arg
    return total
```
📌 `*args` permet de passer un nombre quelconque d’arguments positionnels.

```python
def repete_print(**kwargs):
    fois = kwargs.get("fois", 1)
    texte = kwargs.get("texte", None)
    if texte is None:
        return
    for _ in range(fois):
        print(texte)
```
📌 `**kwargs` permet de passer des paires clé/valeur nommées.

---

## 1️⃣1️⃣ Décomposition des arguments
```python
def ma_fonction(param1, param2, param3):
    print(param1, param2, param3)

args_liste = [1, 2, 3]
kwargs_dict = {"param1": 1, "param2": 2, "param3": 3}
ma_fonction(*args_liste)
ma_fonction(**kwargs_dict)
```
🔍 On peut appeler une fonction en « décompressant » une liste ou un dictionnaire.

---

## 1️⃣2️⃣ Fonctions avec retour multiple
```python
def calculer(a, b):
    return a + b, a * b

s, p = calculer(3, 4)
```
📦 Une fonction peut retourner plusieurs valeurs sous forme de tuple.

---

## 1️⃣3️⃣ Fonctions imbriquées — Exemple avec café ☕
```python
def preparer_cafe():
    eau = chauffer_eau(90)
    cafe = moudre_grains()
    print(f"Préparation du café avec {eau} et {cafe}.")
    return "café prêt"
```
🎬 Démonstration de fonctions appelées dans une autre fonction : un exemple réaliste.

---

Ce document est maintenant complet ✅. Tu peux le télécharger, l'étudier et me demander de l'exporter si tu veux un `.md` prêt à l’emploi pour GitHub 📘💻.
