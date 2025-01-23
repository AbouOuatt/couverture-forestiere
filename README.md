# Cartographie des types de couverture forestière à l’aide de modèles d’apprentissage automatique

## But du projet
Ce projet vise à classifier différents types de couvertures forestières en utilisant des modèles d’apprentissage automatique avancés. L’objectif est d’améliorer la précision des prédictions en combinant plusieurs modèles dans un cadre hybride. Les données utilisées proviennent des régions sauvages de la forêt nationale de Roosevelt, et les résultats sont destinés à mieux comprendre les dynamiques forestières et leur gestion dans le cadre des changements climatiques.

---

## Technologies utilisées
- **Langage de programmation** : Python
- **Modèles d’apprentissage automatique** :
  - **XGBoost** : Pour le boosting de gradient basé sur des arbres de décision.
  - **LightGBM** : Une variante optimisée pour des ensembles de données volumineux.
  - **Random Forest** : Utilisé comme méta-modèle pour combiner les prédictions des modèles précédents.
- **Librairies Python** :
  - **Scikit-learn** : Validation croisée, recherche d’hyperparamètres et modélisation.
  - **Pandas** et **NumPy** : Préparation et manipulation des données.
  - **Matplotlib** et **Seaborn** : Visualisation des performances.

---

## Approche méthodologique
### 1. Description et sélection des données
- Les données incluent 12 variables quantitatives (comme l’altitude, la pente, les distances horizontales) et des colonnes binaires pour désigner les types de sol et les zones sauvages.
- Après un prétraitement, des variables supplémentaires ont été créées pour améliorer la qualité des prédictions.

### 2. Modélisation
- **XGBoost** et **LightGBM** ont été optimisés à l’aide de GridSearchCV pour sélectionner les meilleurs hyperparamètres (profondeur des arbres, taux d’apprentissage, etc.).
- Un modèle **hybride (stacking)** a été créé en combinant les prédictions des deux modèles à l’aide d’un Random Forest comme méta-modèle.

### 3. Validation et évaluation
- Méthode de validation croisée k-fold à 4 plis utilisée pour éviter le surapprentissage.
- Évaluation des performances basée sur l’accuracy globale et par classe.

---

## Résultats
- **Modèle hybride** :
  - Accuracy globale : **82.13%** (avec Random Forest comme méta-modèle).
  - Précision accrue pour les classes spécifiques (par exemple, Cottonwood/Willow et Krummholz).
- **Modèles individuels** :
  - LightGBM : **79.4%**
  - XGBoost : **79%**
  - Random Forest : **79.4%**
  - Decision Tree : **71.95%**
- L'approche hybride a démontré la meilleure performance, mettant en avant l'intérêt du stacking pour combiner les forces des différents algorithmes.

---

## Auteur(s)
- Ouattara Aboubakar
- Borel Domgue
- Ruflin Tsasse

---

## Notes
Pour une meilleure performance, vérifiez que les dépendances sont installées correctement et utilisez une machine avec des ressources suffisantes pour gérer les calculs intensifs liés aux algorithmes de boosting.
