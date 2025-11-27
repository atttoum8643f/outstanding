# 🌾 Analyse statistique d’expériences sur des variétés d’avoine  
Collaboration avec l’Institut Agro

## 📌 Contexte
Ce dépôt accompagne un projet mené en collaboration avec **l’Institut Agro**, dans lequel nous apportons un soutien statistique aux étudiants réalisant des expériences sur différentes variétés d’avoine.  
Les travaux ont débuté il y a environ un mois et nous nous sommes rencontrés pour la première fois **le jeudi 6 novembre**.

---

## 🌱 Première expérience : interactions autour de la variété témoin A

### 🎯 Objectif
Étudier comment la variété **A** (servant de témoin) réagit lorsqu’elle est cultivée en présence :

- d’autres variétés d’avoine,
- d’elle-même,
- ou d’un objet inerte.

L’objectif général est de déterminer si la variété A modifie sa croissance ou sa morphologie selon la nature de son voisin.

---

## 🧪 Dispositif expérimental

### Variétés utilisées
- Quatre variétés d’avoine : **A, B, C, D**
- **A est la variété témoin**

### Confrontations étudiées
Dans chaque boîte, la variété **A** est confrontée à :

- **B** → `AB`
- **C** → `AC`
- **D** → `AD`
- **elle-même** → `AA`
- **un objet plastique inerte** → `AObj`

Chaque confrontation est répétée **3 fois**, notées `k = 1, 2, 3`.

---

## 📏 Variables mesurées
Pour chaque confrontation, les étudiants mesurent :

- **Angle** par rapport à la verticale  
- **Biomasse**  
- **Nombre de ramifications**  
- **Distance entre les deux racines** (éloignement entre les deux individus ou entre la plante et l’objet)

---

## 🧮 Problématique statistique
Un **modèle mixte à deux facteurs** était initialement envisagé pour analyser les données.  
Cependant, le nombre de réplicats disponibles est insuffisant pour garantir la stabilité des estimations dans un tel modèle.

La question centrale devient alors :

> **Comment modéliser la relation entre la variété témoin A et les autres traitements avec un échantillonnage limité ?**

Cette question oriente la réflexion statistique menée dans ce projet.

---
## 🌱 Deuxième expérience : interactions pairwise entre 10 variétés d’avoine

### 🎯 Objectif
La seconde expérience vise à étudier les interactions **entre toutes les paires possibles** parmi **10 variétés d’avoine**, notées de **A à J**.

L'objectif est de comprendre comment chaque variété influence la croissance et le développement de son voisin.

---

### 🧪 Dispositif expérimental

#### Variétés
- 10 variétés : **A, B, C, D, E, F, G, H, I, J**

#### Confrontations
Dans chaque boîte, on plante **une paire de variétés** :

- A est confronté successivement à B, C, …, J  
- B est confronté à C, D, …, J  
- …  
- I est confronté à J  

Cela représente au total :

- **55 paires uniques** (combinaison 10 × 9 / 2)
- **3 répétitions par paire**
- **165 individus (boîtes) au total**

Pour chaque boîte, on note :

- `var1` : variété 1  
- `var2` : variété 2  
→ celles qui partagent la boîte.

---

### 📏 Variables mesurées

Les mesures sont réalisées sur chaque variété au **début (t1), milieu (t2) et fin (t3)** de l’expérience.

Variables mesurées :

- **Taille de la plante** :  
  - `taille1_t1`, `taille1_t2`, `taille1_t3`  
  - `taille2_t1`, `taille2_t2`, `taille2_t3`

- **Nombre de feuilles** :
  - `nb_flle1_t1`, `nb_flle1_t2`, `nb_flle1_t3`  
  - `nb_flle2_t1`, `nb_flle2_t2`, `nb_flle2_t3`

- **Biomasse** :
  - `b_masse1`  
  - `b_masse2`

Les indices **1** et **2** désignent respectivement la variété `var1` et `var2`.

---

### 📊 Analyse exploratoire
Comme l’expérience n’est pas encore terminée, des **données simulées** ont été utilisées pour :

- construire des graphes (moyennes ± erreur-type)  
- visualiser d’éventuelles tendances ou interactions entre variétés

Ce travail sert de base pour préparer l’analyse finale.

---

### 📈 Calcul de puissance et taille d’échantillon

Une **analyse de puissance** a été réalisée avec un seuil de **0.90** afin d’estimer la taille d’échantillon nécessaire.

- La taille totale requise (pour détecter un effet donné) a été **divisée par 55**, le nombre de paires uniques,  
- ce qui permet d’obtenir une estimation du **nombre de répétitions nécessaires (k)** par confrontation.

---

### 🔬 Modélisation et correction des tests multiples

Étant donné le **faible nombre de réplicats**, un modèle général (global) ne serait pas fiable.  
La stratégie retenue est donc :

- d’effectuer **des modèles pairwise (deux à deux)** pour chaque paire de variétés  
- puis d'appliquer une **correction des tests multiples** afin de contrôler l’erreur de type I.

Méthodes utilisées :
- **Holm**  
- **Bonferroni**

Cela permet de **ne pas sous-estimer l’erreur de première espèce**.
