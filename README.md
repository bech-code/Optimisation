# Problème de Sac à Dos (Knapsack Problem)

## 📋 Description

Ce projet présente une implémentation du **problème de sac à dos** (Knapsack Problem) en utilisant le solveur GLPK. Le problème de sac à dos est un problème d'optimisation combinatoire classique qui consiste à choisir parmi un ensemble d'objets ceux qui doivent être placés dans un sac à dos de capacité limitée, de manière à maximiser la valeur totale des objets sélectionnés sans dépasser la capacité du sac.

## 🎯 Objectif

Maximiser la valeur totale des objets sélectionnés sous la contrainte que le poids total ne dépasse pas la capacité du sac à dos.

## 📐 Modèle Mathématique

### Données
- $n$ : nombre d'objets disponibles
- $u_i$ : valeur (utilité) de l'objet $i$, pour $i = 1, 2, \ldots, n$
- $p_i$ : poids de l'objet $i$, pour $i = 1, 2, \ldots, n$
- $B$ : capacité maximale du sac à dos

### Variables de décision
- $x_i \in \{0, 1\}$ : variable binaire indiquant si l'objet $i$ est sélectionné
  - $x_i = 1$ si l'objet $i$ est pris
  - $x_i = 0$ si l'objet $i$ n'est pas pris

### Formulation

$$
\begin{align}
\max \quad & \sum_{i=1}^{n} u_i \cdot x_i \\
\text{s.t.} \quad & \sum_{i=1}^{n} p_i \cdot x_i \leq B \\
& x_i \in \{0, 1\}, \quad \forall i = 1, 2, \ldots, n
\end{align}
$$

## 📁 Structure du Projet

```
.
├── devoir_a_domicile.ipynb    # Notebook Jupyter avec l'explication complète
├── sac_a_dos.mod             # Modèle GLPK (fichier modèle)
├── sac_a_dos.dat             # Données du problème (fichier données)
└── README.md                 # Ce fichier
```

## 🚀 Utilisation

### Prérequis

- [GLPK](https://www.gnu.org/software/glpk/) (GNU Linear Programming Kit) installé
- Jupyter Notebook ou JupyterLab
- Python 3.x

### Installation de GLPK

**Sur macOS :**
```bash
brew install glpk
```

**Sur Linux (Ubuntu/Debian) :**
```bash
sudo apt-get install glpk-utils
```

**Sur Windows :**
Télécharger depuis [le site officiel GLPK](https://www.gnu.org/software/glpk/)

### Exécution

1. **Ouvrir le notebook Jupyter :**
   ```bash
   jupyter notebook devoir_a_domicile.ipynb
   ```

2. **Exécuter les cellules dans l'ordre :**
   - Les premières cellules créent les fichiers `sac_a_dos.mod` et `sac_a_dos.dat`
   - La dernière cellule exécute le solveur GLPK

3. **Alternative : Exécution en ligne de commande :**
   ```bash
   glpsol -m sac_a_dos.mod -d sac_a_dos.dat
   ```

## 📊 Données du Problème

Le problème traité dans ce projet contient :
- **5 objets** avec les valeurs suivantes : [12, 15, 5, 16, 17]
- **Poids des objets** : [2, 6, 1, 7, 8]
- **Capacité du sac** : 20

## 🔧 Fichiers GLPK

### `sac_a_dos.mod`
Contient la définition du modèle :
- Paramètres (nombre d'objets, valeurs, poids, capacité)
- Variables de décision binaires
- Fonction objectif (maximisation)
- Contraintes
- Instructions d'affichage des résultats

### `sac_a_dos.dat`
Contient les données spécifiques du problème :
- Nombre d'objets
- Valeurs de chaque objet
- Poids de chaque objet
- Capacité maximale du sac

## 📚 Applications

Le problème de sac à dos trouve des applications dans de nombreux domaines :
- Allocation de ressources
- Découpe de matériaux
- Sélection de projets d'investissement
- Optimisation de chargement de véhicules
- Planification de budget
- Optimisation de réseaux

## 👤 Auteur

**Mohamed Bechir Diarra**

## 📝 Licence

Ce projet est sous licence Apache-2.0.

## 🔗 Liens Utiles

- [Documentation GLPK](https://www.gnu.org/software/glpk/)
- [MathProg Language Reference](https://en.wikibooks.org/wiki/GLPK/GMPL_(MathProg))
- [Problème de sac à dos sur Wikipedia](https://fr.wikipedia.org/wiki/Probl%C3%A8me_du_sac_%C3%A0_dos)

---

**Note :** Ce projet a été réalisé dans le cadre du cours de Fondements d'Optimisation (M1 Data Science).
