# 🚀 6 mois d'informatique : le grand récap + un projet final

**Élève :** Victor
**Durée :** 1h de rappel + pause + 40 min de projet
**Au programme :** des schémas, un mini-quiz après chaque partie, et un vrai projet à la fin.

---

## 🗺️ Plan de la séance

| Durée | Partie |
|---|---|
| 5 min | 0. La carte de nos 6 mois |
| 10 min | 1. L'intelligence artificielle |
| 10 min | 2. Python |
| 10 min | 3. HTML / CSS |
| 10 min | 4. Entraîner un modèle (no-code / low-code) |
| 10 min | 5. Bases de données & SQL |
| 5 min | 6. Quiz final de rappel |
| 5 min | ☕ Pause |
| 40 min | 🏆 **Projet : construire une mini-IA from scratch** |

---

## 0. La carte de nos 6 mois

```mermaid
timeline
    title Notre parcours
    Mois 1 : Introduction à l'IA
    Mois 2 : Python (bases)
    Mois 3 : Python avancé
    Mois 4 : HTML et CSS
    Mois 5 : Entraînement de modèles (no-code / low-code)
    Mois 6 : Bases de données & SQL
```

```mermaid
mindmap
  root((Informatique))
    Intelligence artificielle
      Apprendre à partir d'exemples
      Modèles
    Programmation
      Python
    Web
      HTML : la structure
      CSS : le style
    Données
      Tables
      SQL
```

---

## 1. L'intelligence artificielle

### L'idée clé

Un programme classique suit des **règles écrites par un humain**.
Une IA **apprend les règles elle-même** à partir d'**exemples**.

```mermaid
flowchart LR
    subgraph Programme classique
    A1[Données] --> C1[Règles écrites par l'humain] --> R1[Résultat]
    end
    subgraph IA / Machine Learning
    A2[Données + Réponses connues] --> C2[L'ordinateur trouve les règles] --> R2[Un modèle]
    end
```

### Le vocabulaire à retenir

| Mot | Sens simple |
|---|---|
| **Donnée** | Un exemple (une image, un nombre, un texte) |
| **Étiquette (label)** | La bonne réponse associée à un exemple |
| **Entraînement** | L'ordinateur regarde plein d'exemples pour apprendre |
| **Modèle** | Le "cerveau" obtenu à la fin de l'entraînement |
| **Prédiction** | La réponse que donne le modèle pour un nouvel exemple |

### ✅ Mini-quiz
1. Quelle est la différence entre un programme classique et une IA ?
2. C'est quoi une "étiquette" ? Donne un exemple.

---

## 2. Python

### Les briques de base

```python
# Variables et types
age = 15              # nombre entier
nom = "Victor"        # texte
notes = [12, 15, 18]  # liste

# Condition
if age >= 18:
    print("Majeur")
else:
    print("Mineur")

# Boucle
for note in notes:
    print(note)

# Fonction
def moyenne(liste):
    return sum(liste) / len(liste)

print(moyenne(notes))
```

```mermaid
flowchart TD
    A[Variables] --> B[Conditions if/else]
    B --> C[Boucles for/while]
    C --> D[Fonctions]
    D --> E[Listes, dictionnaires]
    E --> F[Modules : math, sqlite3, requests...]
```

### 🔧 Défi express
Écrire une fonction `maximum(liste)` qui renvoie le plus grand nombre **sans utiliser** `max()`.

### ✅ Mini-quiz
1. Quelle est la différence entre une liste et une variable simple ?
2. À quoi sert `return` dans une fonction ?

---

## 3. HTML / CSS

### Les 2 rôles (l'analogie de la maison 🏠)

```mermaid
flowchart LR
    H["HTML<br/>les murs et les pièces<br/>(structure)"] --> C["CSS<br/>la peinture et la déco<br/>(style)"]
```

### Exemple minimal qui regroupe les deux

```html
<!DOCTYPE html>
<html>
<head>
  <style>
    h1 { color: royalblue; text-align: center; }
    p  { font-size: 20px; }
    .carte {
      background: lightyellow;
      padding: 15px;
      border-radius: 10px;
      width: 300px;
    }
  </style>
</head>
<body>
  <h1>Ma première page</h1>
  <div class="carte">
    <p>Je m'appelle Victor et j'apprends l'informatique.</p>
  </div>
</body>
</html>
```

### 🔧 Défi express
Modifier le code pour que le titre devienne rouge et que la carte ait un fond vert clair.

### ✅ Mini-quiz
1. Quelle technologie sert à changer la couleur d'un titre ? Et à créer le titre ?
2. C'est quoi une balise ? Cites-en trois.

---

## 4. Entraîner un modèle sans coder

### Le cycle de vie d'un modèle

```mermaid
flowchart LR
    A[1. Récolter des données] --> B[2. Les étiqueter]
    B --> C[3. Entraîner le modèle]
    C --> D[4. Tester sur de nouveaux exemples]
    D -->|Pas assez bon| A
    D -->|Bon| E[5. Utiliser le modèle]
```

### Les pièges à connaître

| Problème | Explication simple |
|---|---|
| **Pas assez de données** | Le modèle a trop peu d'exemples pour bien apprendre |
| **Données biaisées** | Si on n'entraîne qu'avec des photos de chats noirs, il ne reconnaîtra pas les chats blancs |
| **Sur-apprentissage** | Le modèle "apprend par cœur" au lieu de comprendre : parfait sur l'entraînement, nul sur du nouveau |

### ✅ Mini-quiz
1. Pourquoi teste-t-on un modèle sur des données qu'il n'a **jamais vues** ?
2. Si un modèle a 100 % de réussite à l'entraînement mais 40 % en test, que s'est-il passé ?

---

## 5. Bases de données & SQL

### Le schéma à retenir

```mermaid
erDiagram
    ELEVES ||--o{ NOTES : possede
    ELEVES {
        int id PK
        string nom
    }
    NOTES {
        int id PK
        int eleve_id FK
        string matiere
        int note
    }
```

### Les 4 commandes essentielles

```sql
SELECT nom FROM eleves WHERE classe = '1ère A';   -- lire
INSERT INTO eleves (nom) VALUES ('Emma');          -- ajouter
UPDATE notes SET note = 15 WHERE id = 2;           -- modifier
DELETE FROM notes WHERE id = 5;                    -- supprimer
```

### ✅ Mini-quiz
1. C'est quoi une clé primaire ? Une clé étrangère ?
2. Pourquoi ne fait-on jamais `DELETE` sans `WHERE` ?

---

## 6. Quiz final de rappel

1. Cite 3 types de choses qu'on peut construire avec Python.
2. HTML et CSS : un mot pour chacun.
3. Cite les 4 étapes pour entraîner un modèle d'IA.
4. À quoi sert un `JOIN` en SQL ?
5. Quelle partie du programme t'a le plus plu, et pourquoi ?

---

## ☕ Pause

---

# 🏆 PROJET : construire une mini-IA *from scratch* (40 min)

Tu as déjà entraîné des modèles avec des interfaces "no-code". Aujourd'hui, on **ouvre la boîte** : tu vas coder une IA toi-même, uniquement avec du Python et des maths que tu connais déjà (Pythagore !).

## L'idée : l'algorithme des "plus proches voisins" (k-NN)

On veut que l'ordinateur devine si un fruit est une **pomme** ou une **orange**, à partir de son **poids** et de sa **taille**.

**Principe :** pour un nouveau fruit, on regarde **le fruit connu le plus proche** et on copie sa réponse.

```mermaid
flowchart LR
    A["Nouveau fruit<br/>195 g, 8 cm"] --> B["Calculer la distance<br/>avec chaque fruit connu"]
    B --> C["Trouver le plus proche"]
    C --> D["Copier son étiquette<br/>→ orange 🍊"]
```

La **distance** entre deux points, c'est le théorème de Pythagore :

```
distance = √( (poids₁ − poids₂)² + (taille₁ − taille₂)² )
```

## Étape 1 : les données (5 min)

```python
import math

# (poids en g, taille en cm, étiquette)
donnees = [
    (150, 7.0, "pomme"),
    (160, 7.5, "pomme"),
    (140, 6.8, "pomme"),
    (200, 8.0, "orange"),
    (210, 8.5, "orange"),
    (190, 7.8, "orange"),
]
```

✅ **Question :** Si on dessine ces fruits sur un graphique (poids en x, taille en y), à quoi ressemblent les deux groupes ?

## Étape 2 : la distance (10 min)

```python
def distance(a, b):
    return math.sqrt((a[0] - b[0])**2 + (a[1] - b[1])**2)

print(distance((150, 7.0), (200, 8.0)))
```

🔧 **À faire :** calculer d'abord à la main la distance entre `(150, 7.0)` et `(200, 8.0)`, puis vérifier avec Python.

## Étape 3 : la prédiction (15 min)

```python
def predire(nouveau, donnees):
    meilleur = None
    plus_petite = float("inf")  # "infini" : n'importe quelle distance sera plus petite

    for poids, taille, etiquette in donnees:
        d = distance(nouveau, (poids, taille))
        if d < plus_petite:
            plus_petite = d
            meilleur = etiquette

    return meilleur

print(predire((195, 8.0), donnees))   # → orange
print(predire((145, 7.1), donnees))   # → pomme
```

🔧 **À faire :** inventer 3 fruits "mystères", laisser l'ordinateur deviner, et vérifier si la réponse paraît logique.

## Étape 4 : améliorer avec k voisins (10 min)

Un seul voisin, c'est fragile (et si c'était une erreur dans les données ?). On regarde **les k plus proches** et on **vote**.

```python
from collections import Counter

def predire_k(nouveau, donnees, k=3):
    # Liste de (distance, étiquette) pour tous les fruits connus
    distances = []
    for poids, taille, etiquette in donnees:
        d = distance(nouveau, (poids, taille))
        distances.append((d, etiquette))

    distances.sort()                     # du plus proche au plus loin
    k_plus_proches = distances[:k]       # on garde les k premiers

    votes = Counter(etiquette for d, etiquette in k_plus_proches)
    return votes.most_common(1)[0][0]    # l'étiquette la plus fréquente

print(predire_k((195, 8.0), donnees, k=3))
```

✅ **Question :** pourquoi voter à plusieurs est-il plus fiable qu'un seul voisin ?

## 🎓 Ce qu'il faut retenir

- Une IA, ce n'est pas de la magie : ici, c'est **des distances + une comparaison**.
- Dans ce projet, on a utilisé **Python** (fonctions, boucles, listes), des **maths** (Pythagore) et des **concepts d'IA** (données, étiquettes, entraînement, prédiction).
- Les "vrais" modèles font la même chose en beaucoup plus gros : des millions d'exemples et des centaines de dimensions au lieu de 2.
