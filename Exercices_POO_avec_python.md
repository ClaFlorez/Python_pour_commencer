# 🐍 Exercices Python - Programmation Orientée Objet (POO)

Ce document présente une série d'exercices pratiques en Python utilisant la **programmation orientée objet (POO)**. Chaque exercice inclut le code complet, des explications détaillées et des exemples d'utilisation.

---

## 📘 Exercice 1 : Classe `Cercle` et Fonction Générique

### 🎯 Objectif
Créer une classe `Cercle` avec une méthode `aire()` et une fonction `afficher_aire()` capable de gérer différents types de figures géométriques (rectangle ou cercle).

### 🧩 Code
```python
import math

class Cercle:
    def __init__(self, rayon):
        self.rayon = rayon

    def aire(self):
        return math.pi * self.rayon ** 2

class Rectangle:
    def __init__(self, largeur, hauteur):
        self.largeur = largeur
        self.hauteur = hauteur

    def aire(self):
        return self.largeur * self.hauteur

def afficher_aire(figure):
    print(f"L'aire de la figure est : {figure.aire():.2f}")
```

### 🧠 Explication
- `Cercle` et `Rectangle` ont une méthode `aire()`.
- La fonction `afficher_aire()` est polymorphe : elle fonctionne tant que l'objet passé a une méthode `aire()`.

---

## 📚 Exercice 2 : Système de gestion de bibliothèque

### 🎯 Objectif
Créer un mini système de gestion de livres et membres d’une bibliothèque avec POO.

### 🧩 Code Simplifié
```python
class Livre:
    def __init__(self, titre, auteur, isbn):
        self.titre = titre
        self.auteur = auteur
        self.isbn = isbn
        self.disponible = True

class Membre:
    def __init__(self, nom, identifiant):
        self.nom = nom
        self.id = identifiant
        self.livres_empruntes = []

class Bibliotheque:
    def __init__(self):
        self.livres = []
        self.membres = []

    def ajouter_livre(self, livre):
        self.livres.append(livre)

    def inscrire_membre(self, membre):
        self.membres.append(membre)

    def emprunter_livre(self, id_membre, isbn):
        membre = next((m for m in self.membres if m.id == id_membre), None)
        livre = next((l for l in self.livres if l.isbn == isbn and l.disponible), None)
        if membre and livre:
            membre.livres_empruntes.append(livre)
            livre.disponible = False

    def rendre_livre(self, id_membre, isbn):
        membre = next((m for m in self.membres if m.id == id_membre), None)
        if membre:
            livre = next((l for l in membre.livres_empruntes if l.isbn == isbn), None)
            if livre:
                membre.livres_empruntes.remove(livre)
                livre.disponible = True
```

### 🧠 Explication
- `Livre`, `Membre` et `Bibliotheque` sont trois entités essentielles.
- `Bibliotheque` gère les opérations (emprunter, rendre, inscrire).

---

## 🧩 Exercice 3 : Hiérarchie de formes géométriques

### 🎯 Objectif
Créer une hiérarchie de formes géométriques avec des méthodes abstraites et des fonctions spécifiques à chaque forme.

### 🧩 Code Simplifié
```python
from abc import ABC, abstractmethod
import math

class Forme(ABC):
    @abstractmethod
    def aire(self): pass

    @abstractmethod
    def dessiner(self): pass

    @abstractmethod
    def afficher_infos(self): pass

    def __lt__(self, autre):
        return self.aire() < autre.aire()

    def __eq__(self, autre):
        return self.aire() == autre.aire()

class Cercle(Forme):
    def __init__(self, rayon):
        self.rayon = rayon

    def aire(self):
        return math.pi * self.rayon ** 2

    def dessiner(self):
        print("   ***   \n *     * \n*       *\n *     * \n   ***   ")

    def afficher_infos(self):
        print(f"Cercle | Rayon: {self.rayon} | Aire: {self.aire():.2f}")
```

### 🧠 Explication
- `Forme` est une classe abstraite.
- Chaque forme hérite et implémente ses propres méthodes (`aire`, `dessiner`, `afficher_infos`).
- On peut comparer les formes par leur aire avec `__lt__` et `__eq__`.

---

## ⚔️ Exercice 4 : Jeu RPG simplifié

### 🎯 Objectif
Créer un système de jeu de rôle avec des classes dérivées, des attaques spéciales et la gestion de niveaux.

### 🧩 Code Simplifié
```python
class Personnage:
    def __init__(self, nom, vie, force, defense):
        self.nom = nom
        self.vie = vie
        self.force = force
        self.defense = defense
        self.experience = 0
        self.niveau = 1

    def attaquer(self, cible):
        degats = max(0, self.force - cible.defense)
        cible.vie -= degats

    def gagner_experience(self, points):
        self.experience += points
        if self.experience >= self.niveau * 10:
            self.niveau += 1
            self.force += 1
            self.vie += 5

class Guerrier(Personnage):
    def attaque_speciale(self, cible):
        degats = max(0, (self.force * 2) - cible.defense)
        cible.vie -= degats

class Mage(Personnage):
    def attaque_speciale(self, cible):
        degats = 10
        cible.vie -= degats

class Archer(Personnage):
    def attaque_speciale(self, cible):
        degats = max(0, self.force + 3 - cible.defense)
        cible.vie -= degats
```

### 🧠 Explication
- Chaque classe (`Guerrier`, `Mage`, `Archer`) a une attaque spéciale unique.
- La méthode `gagner_experience()` permet de monter en niveau automatiquement.
- Le combat peut être simulé en alternant les tours de chaque personnage.

---

