# OpenClimateScience M4 – Science Ouverte pour la Santé des Sols  
### Cartographie haute résolution du carbone organique du sol (Algérie)

## Aperçu du projet
Les produits globaux sur les sols tels que **SoilGrids** fournissent des informations précieuses, mais leur résolution spatiale (≈250 m) est souvent trop grossière pour la **prise de décision agricole locale**.  
Les agriculteurs et gestionnaires de terres travaillent à des échelles spatiales beaucoup plus fines.

Ce projet présente un **workflow open-science, reproductible** pour générer des **cartes haute résolution (30 m) du Carbone Organique du Sol (SOC)** en utilisant une approche de *downscaling* qui combine des données globales grossières avec des images satellites haute résolution et des informations topographiques.

Le workflow est implémenté sous forme de **notebook Google Colab** et conçu pour :
- l’enseignement et la formation  
- le prototypage rapide  
- l’analyse géospatiale transparente et cloud-native  

---

## Objectifs
- Accéder à des données géospatiales hébergées dans le cloud (Landsat, NASADEM, SoilGrids)  
- Construire des prédicteurs environnementaux pertinents pour les processus pédologiques  
- Désagréger (*downscaling*) les données SOC grossières par apprentissage automatique  
- Produire une carte SOC à haute résolution avec **estimation d’incertitude**  
- Démontrer une **science géospatiale ouverte et reproductible**

---

## Zone d’étude
- **Région :** Atlas Tellien, Nord de l’Algérie  
- **Étendue :** ~10 × 10 km (zone agricole)  
- **Résolution spatiale :** 30 m (résultat final)

---

## Méthodologie (Conceptuelle)

### 1. Variable cible (Enseignant)
- Stock de carbone du sol SoilGrids (profondeur 0–30 cm, ~250 m)

### 2. Prédicteurs (Élèves)
- Indices de végétation issus de Landsat :
  - MSAVI (Indice de végétation ajusté au sol modifié)
  - Indice de sol nu (BSI)
- Variables topographiques :
  - Altitude (NASADEM)
  - Pente

### 3. Stratégie de downscaling
- Rééchantillonnage du SOC grossier sur la grille 30 m  
- Apprentissage des relations entre SOC et prédicteurs environnementaux  
- Prédiction continue du SOC à haute résolution

### 4. Modèle
- Régression Random Forest (scikit-learn)

### 5. Quantification de l’incertitude
- Approche en **ensemble** (plusieurs modèles RF)  
- Écart-type pixel par pixel comme indicateur d’incertitude

---

## Notebook
L’ensemble du workflow est implémenté dans le notebook :
