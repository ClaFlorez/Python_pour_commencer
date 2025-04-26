# ⭐️ Guide Complet sur la Programmation Orientée Objet (POO) avec Python

---

## 📚 Table des Matières

1. [Introduction à la POO](#introduction-à-la-poo)
2. [Les Classes et les Objets](#les-classes-et-les-objets)
3. [Les Méthodes](#les-méthodes)
4. [L'Héritage](#lhéritage)
5. [Les Méthodes Spéciales](#les-méthodes-spéciales)
6. [Encapsulation et Modificateurs d'Accès](#encapsulation-et-modificateurs-daccès)
7. [Polymorphisme](#polymorphisme)
8. [Exercices Pratiques](#exercices-pratiques)

---

## 🧐 Introduction à la POO

### Définition Théorique

La Programmation Orientée Objet (POO) organise le code autour des **objets** qui contiennent à la fois des données (**attributs**) et des comportements (**méthodes**).

**Concepts Clés :**
- **Encapsulation** : regrouper données et méthodes ensemble.
- **Héritage** : créer de nouvelles classes à partir d'existantes.
- **Polymorphisme** : utiliser une interface commune pour différents objets.

### 💪 Avantages

- Meilleure organisation du code
- Réutilisation du code
- Facilité de maintenance
- Modélisation plus proche du monde réel

---

## 🏢 Les Classes et les Objets

### Définition

- **Classe** : Modèle d'objet.
- **Objet** : Instance concrète d'une classe.

```python
class NomDeLaClasse:
    def __init__(self, param1, param2):
        self.attribut1 = param1
        self.attribut2 = param2
```

### Exemple

```python
class Personne:
    def __init__(self, nom, age):
        self.nom = nom
        self.age = age

personne1 = Personne("Alice", 25)
print(personne1.nom)
```

### 📝 Exercice

Créer une classe `Rectangle` avec `longueur` et `largeur`.

**Solution :**

```python
class Rectangle:
    def __init__(self, longueur, largeur):
        self.longueur = longueur
        self.largeur = largeur
```

---

## 🔧 Les Méthodes

### Définition

Une méthode est une fonction à l'intérieur d'une classe.

```python
class MaClasse:
    def methode_instance(self, param):
        pass

    @classmethod
    def methode_classe(cls, param):
        pass

    @staticmethod
    def methode_statique(param):
        pass
```

### Exemple

```python
class Calculatrice:
    def __init__(self, valeur=0):
        self.valeur = valeur

    def ajouter(self, x):
        self.valeur += x

    @classmethod
    def info(cls):
        print("Ceci est une calculatrice")

    @staticmethod
    def multiplier(a, b):
        return a * b

calc = Calculatrice()
calc.ajouter(5)
print(calc.valeur)
Calculatrice.info()
print(Calculatrice.multiplier(3, 4))
```

**Exercice :** Ajouter `perimetre()`, `aire()`, et `description()` à `Rectangle`.

**Solution :**

```python
class Rectangle:
    def __init__(self, longueur, largeur):
        self.longueur = longueur
        self.largeur = largeur

    def perimetre(self):
        return 2 * (self.longueur + self.largeur)

    def aire(self):
        return self.longueur * self.largeur

    @staticmethod
    def description():
        return "Je suis un rectangle"
```

---

## 👑 L'Héritage

### Définition

Créer une nouvelle classe (fille) à partir d'une classe existante (mère).

```python
class ClasseMere:
    pass

class ClasseFille(ClasseMere):
    pass
```

### Exemple

```python
class Animal:
    def __init__(self, nom):
        self.nom = nom

    def parler(self):
        raise NotImplementedError("Cette méthode doit être implémentée")

class Chien(Animal):
    def parler(self):
        return "Woof!"

class Chat(Animal):
    def parler(self):
        return "Miaou!"

rex = Chien("Rex")
misty = Chat("Misty")
print(rex.parler())
print(misty.parler())
```

**Exercice :** Créer une classe `Carre` qui hérite de `Rectangle`.

**Solution :**

```python
class Carre(Rectangle):
    def __init__(self, cote):
        super().__init__(cote, cote)
```

---

## 🖊️ Les Méthodes Spéciales

### Méthodes Magiques

- `__init__` : constructeur
- `__str__` : affichage texte
- `__len__` : longueur
- `__add__` : addition
- `__eq__` : comparaison

### Exemple

```python
class Livre:
    def __init__(self, titre, auteur, pages):
        self.titre = titre
        self.auteur = auteur
        self.pages = pages

    def __str__(self):
        return f"{self.titre} par {self.auteur}"

    def __len__(self):
        return self.pages

    def __add__(self, autre):
        return Livre(
            f"{self.titre} et {autre.titre}",
            f"{self.auteur} et {autre.auteur}",
            self.pages + autre.pages
        )
```

**Exercice :** Ajouter `__str__`, `__eq__`, `__add__` à `Rectangle`.

**Solution :**

```python
class Rectangle:
    def __init__(self, longueur, largeur):
        self.longueur = longueur
        self.largeur = largeur

    def __str__(self):
        return f"Rectangle de longueur {self.longueur} et largeur {self.largeur}"

    def __eq__(self, autre):
        return self.aire() == autre.aire()

    def __add__(self, autre):
        return Rectangle(self.longueur + autre.longueur, self.largeur + autre.largeur)
```

---

## 🔐 Encapsulation et Modificateurs d'Accès

### Définition

Restreindre l'accès direct aux attributs.

**Convention en Python :**
- `attribut` : public
- `_attribut` : protégé
- `__attribut` : privé

### Exemple

```python
class CompteBancaire:
    def __init__(self, titulaire, solde):
        self.titulaire = titulaire
        self._solde = solde
        self.__code = "1234"

    def afficher_solde(self):
        print(f"Solde: {self._solde}")
```

**Exercice :** Modifier `Rectangle` pour :
- Rendre les attributs privés
- Ajouter getters/setters
- Valider les valeurs positives

**Solution :**

```python
class Rectangle:
    def __init__(self, longueur, largeur):
        self._longueur = longueur
        self._largeur = largeur

    def get_longueur(self):
        return self._longueur

    def set_longueur(self, valeur):
        if valeur > 0:
            self._longueur = valeur

    def get_largeur(self):
        return self._largeur

    def set_largeur(self, valeur):
        if valeur > 0:
            self._largeur = valeur
```

---

## 🐼 Polymorphisme

### Définition

Utiliser une interface commune pour différents types d'objets.

### Exemple

```python
class Oiseau:
    def voler(self):
        print("Je vole")

class Avion:
    def voler(self):
        print("Je vole aussi!")

def faire_voler(objet):
    objet.voler()

oiseau = Oiseau()
avion = Avion()
faire_voler(oiseau)
faire_voler(avion)
```

**Exercice :** Créer `Cercle` avec une méthode `aire()`.

**Solution :**

```python
class Cercle:
    def __init__(self, rayon):
        self.rayon = rayon

    def aire(self):
        return 3.14 * self.rayon ** 2
```

---

## 🔢 Exercices Pratiques

### 📖 1. Système de Bibliothèque

```python
class Livre:
    def __init__(self, titre, auteur, isbn):
        self.titre = titre
        self.auteur = auteur
        self.isbn = isbn
        self.emprunte = False

class Membre:
    def __init__(self, nom, id_membre):
        self.nom = nom
        self.id_membre = id_membre
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
        membre = next((m for m in self.membres if m.id_membre == id_membre), None)
        livre = next((l for l in self.livres if l.isbn == isbn and not l.emprunte), None)
        if membre and livre:
            livre.emprunte = True
            membre.livres_empruntes.append(livre)
            print(f"{membre.nom} a emprunté {livre.titre}")
        else:
            print("Livre indisponible ou membre introuvable.")
```

### △ 2. Formes Géométriques

```python
class Forme:
    def aire(self):
        raise NotImplementedError("Méthode aire() non implémentée")

class Cercle(Forme):
    def __init__(self, rayon):
        self.rayon = rayon

    def aire(self):
        return 3.14 * self.rayon ** 2

class Rectangle(Forme):
    def __init__(self, longueur, largeur):
        self.longueur = longueur
        self.largeur = largeur

    def aire(self):
        return self.longueur * self.largeur

class Triangle(Forme):
    def __init__(self, base, hauteur):
        self.base = base
        self.hauteur = hauteur

    def aire(self):
        return 0.5 * self.base * self.hauteur
```

### 💪 3. Jeu RPG Simple

```python
class Personnage:
    def __init__(self, nom, vie, force, defense):
        self.nom = nom
        self.vie = vie
        self.force = force
        self.defense = defense
        self.experience = 0
        self.niveau = 1

    def attaquer(self, adversaire):
        degats = max(0, self.force - adversaire.defense)
        adversaire.vie -= degats
        print(f"{self.nom} attaque {adversaire.nom} et inflige {degats} dégâts !")

    def gagner_experience(self, points):
        self.experience += points
        if self.experience >= 10 * self.niveau:
            self.niveau += 1
            self.force += 2
            self.defense += 1
            print(f"{self.nom} passe au niveau {self.niveau}!")

class Guerrier(Personnage):
    def attaque_speciale(self, adversaire):
        degats = max(0, (self.force * 2) - adversaire.defense)
        adversaire.vie -= degats
        print(f"{self.nom} utilise une attaque puissante !")

class Mage(Personnage):
    def attaque_speciale(self, adversaire):
        degats = max(0, (self.force + 5) - adversaire.defense)
        adversaire.vie -= degats
        print(f"{self.nom} lance un sort magique !")

class Archer(Personnage):
    def attaque_speciale(self, adversaire):
        degats = max(0, (self.force + 3) - (adversaire.defense // 2))
        adversaire.vie -= degats
        print(f"{self.nom} tire une flèche précise !")
```

---

# ✨ Fin du Guide ✨


