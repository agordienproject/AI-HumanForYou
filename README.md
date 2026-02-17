# Projet IA - Prédiction de l'Attrition des Employés

Ce projet utilise différents modèles de Machine Learning pour prédire l'attrition des employés chez HumanForYou.

## 📁 Structure du Projet

```
Projet/
├── Data_origin/           # Données brutes originales
│   ├── general_data.csv
│   ├── employee_survey_data.csv
│   ├── manager_survey_data.csv
│   ├── in_time.csv
│   └── out_time.csv
│
├── Data/                  # Données traitées et résultats
│   ├── prepared_data.csv  # Données nettoyées et préparées
│   ├── *.pkl              # Modèles et résultats sauvegardés
│   └── *.png              # Graphiques générés
│
├── environment.ipynb      # Configuration de l'environnement
│
└── Notebooks principaux (à exécuter dans l'ordre):
    ├── 01_data_wrangling.ipynb      # Préparation des données
    ├── 02_logistic_regression.ipynb # Modèle Régression Logistique
    ├── 03_perceptron.ipynb          # Modèle Perceptron
    ├── 04_svm.ipynb                 # Modèle SVM
    ├── 05_naive_bayes.ipynb         # Modèle Naive Bayes
    ├── 06_decision_tree.ipynb       # Modèle Arbre de Décision
    ├── 07_random_forest.ipynb       # Modèle Random Forest
    ├── 08_model_comparison.ipynb    # Comparaison des modèles
    └── 09_optimization.ipynb        # Optimisation du meilleur modèle
```

## 🚀 Guide d'Utilisation

### 1. Configuration de l'environnement

Exécutez d'abord le notebook `environment.ipynb` pour créer l'environnement virtuel et installer les dépendances :

```python
# Création de l'environnement
python -m venv env

# Activation (Windows)
env\Scripts\activate

# Installation des packages
pip install numpy pandas plotly matplotlib seaborn missingno scikit-learn scikit-optimize
```

### 2. Ordre d'exécution des notebooks

#### Étape 1 : Préparation des données
**Notebook:** `01_data_wrangling.ipynb`

- Importe les données brutes depuis `Data_origin/`
- Nettoie et traite les valeurs manquantes
- Fusionne toutes les sources de données
- Encode les variables catégorielles
- Normalise les variables numériques
- **Sortie:** `Data/prepared_data.csv` et encoders/scalers sauvegardés

#### Étape 2 : Entraînement des modèles individuels
**Notebooks:** `02_logistic_regression.ipynb` à `07_random_forest.ipynb`

Chaque notebook :
- Charge les données préparées
- Entraîne un modèle spécifique
- Évalue les performances (matrice de confusion, ROC, métriques)
- Sauvegarde le modèle et les résultats dans `Data/`

**Vous pouvez exécuter ces notebooks en parallèle** par plusieurs membres de l'équipe !

#### Étape 3 : Comparaison des modèles
**Notebook:** `08_model_comparison.ipynb`

- Charge tous les modèles entraînés
- Compare toutes les métriques (Accuracy, Precision, Recall, F1, AUC-ROC)
- Génère des visualisations comparatives
- Identifie le meilleur modèle
- **Sortie:** `Data/model_comparison_summary.pkl` et graphiques

#### Étape 4 : Optimisation
**Notebook:** `09_optimization.ipynb`

- Utilise l'optimisation bayésienne pour optimiser les hyperparamètres
- Teste deux stratégies (Accuracy vs F1 Score)
- Évalue le modèle final optimisé
- **Sortie:** `Data/final_optimized_model.pkl`

## 👥 Travail en Équipe

### Répartition suggérée

**Personne 1:** Data Wrangling
- Exécute `01_data_wrangling.ipynb`

**Personne 2-3:** Modèles linéaires
- `02_logistic_regression.ipynb`
- `03_perceptron.ipynb`

**Personne 4-5:** Modèles probabilistes et SVM
- `04_svm.ipynb`
- `05_naive_bayes.ipynb`

**Personne 6-7:** Modèles basés sur les arbres
- `06_decision_tree.ipynb`
- `07_random_forest.ipynb`

**Personne 8:** Comparaison et optimisation
- `08_model_comparison.ipynb`
- `09_optimization.ipynb`

## 📊 Résultats et Métriques

Chaque modèle est évalué sur :
- **Accuracy** : Précision globale
- **Precision** : Taux de vrais positifs parmi les prédictions positives
- **Recall** : Taux de vrais positifs détectés
- **F1 Score** : Moyenne harmonique de Precision et Recall
- **AUC-ROC** : Aire sous la courbe ROC

## 🔧 Dépendances

```
pandas
numpy
matplotlib
seaborn
missingno
scikit-learn
scikit-optimize
```

## 📝 Notes Importantes

1. **Ordre d'exécution** : Respectez l'ordre des notebooks (01 → 02-07 → 08 → 09)
2. **Données sources** : Les données originales sont dans `Data_origin/`, ne les modifiez pas
3. **Résultats** : Tous les résultats sont sauvegardés dans `Data/`
4. **Reproductibilité** : Tous les modèles utilisent `random_state=42`

## 🎯 Objectif du Projet

Prédire l'attrition des employés en analysant :
- Données démographiques et professionnelles
- Enquêtes de satisfaction
- Évaluations managériales
- Temps de travail quotidien

Le meilleur modèle permettra à HumanForYou d'identifier les employés à risque de départ et de prendre des mesures préventives.

## 📧 Support

Pour toute question, contactez votre équipe projet !
