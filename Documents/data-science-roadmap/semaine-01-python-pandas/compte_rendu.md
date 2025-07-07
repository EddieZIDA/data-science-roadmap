
# Compte Rendu d'Analyse : Jeux Olympiques – Données des athlètes

## 🎯 Objectif
L’objectif de ce projet est d’explorer, nettoyer et analyser les données relatives aux athlètes ayant participé aux Jeux Olympiques, afin d’en dégager des tendances significatives (répartition par âge, par sport, par sexe, obtention de médailles, etc.).

---

## 1. 📥 Importation des données

Les bibliothèques suivantes ont été utilisées :
- `pandas` pour la manipulation de données,
- `numpy` pour les calculs numériques,
- `matplotlib.pyplot` et `seaborn` pour les visualisations.

Le fichier CSV `athlete_events.csv` a été chargé dans un DataFrame nommé `df`.

---

## 2. 🧭 Exploration initiale

- **Dimensions** du DataFrame : via `df.shape`
- **Colonnes** et leurs types : `df.columns`, `df.info()`
- **Résumé statistique** : `df.describe()`
- **Aperçu des données** : `df.head()` et `df.tail()`

---

## 3. 🔍 Exploration approfondie

- Sélection de données avec `iloc` et `loc`
- **Analyse de la distribution de l'âge** des athlètes via un graphique en barres (`value_counts()` + `plot.bar()`)
- **Identification des valeurs manquantes** :
  - Par colonne : `df.isnull().sum()`
  - Total général : `df.isnull().sum().sum()`

---

## 4. 🧹 Nettoyage des données

- Suppression des **lignes** contenant des valeurs nulles : `df_clean_1 = df.dropna(axis=0)`
- Suppression des **colonnes** avec des valeurs nulles : `df_clean_2 = df.dropna(axis=1)`

---

## 5. 📈 Analyses groupées et statistiques

- **Regroupement par sexe** : `df.groupby('Sex').count()`
- **Regroupement par âge** : `df.groupby('Age').count()`
- **Âge moyen par sport** : `df.groupby("Sport")["Age"].mean()`
- **Top 10 des équipes ayant gagné le plus de médailles d’or**

---

## 6. 🧪 Traitements supplémentaires

- Transformation de la variable `Sex` de catégorielle à numérique (F→0, M→1)
- Création d’un DataFrame centré sur les colonnes clés : `Sex`, `Age`, `Sport`, `City`
- Filtrage des athlètes âgés entre 30 et 33 ans

---

## ✅ Conclusion

Cette analyse permet d’avoir une meilleure compréhension des profils types d’athlètes olympiques selon leur âge, leur sexe, leur discipline et leur performance. Le nettoyage a permis d’assurer la fiabilité des résultats, et plusieurs insights intéressants ont été mis en lumière (âge moyen par sport, pays les plus performants...).
