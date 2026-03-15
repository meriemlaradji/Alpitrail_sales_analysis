# Alpitrail Sales & CRM Data Analysis

## Contexte du projet
Alpitrail est une marque fictive de sport outdoor présente en Europe, Amérique du Nord et Asie.  
L’objectif est de simuler un projet réel de data analysis pour une entreprise internationale : analyser les ventes, nettoyer les données, produire des insights business et construire un modèle prédictif.

## Problématique business
- Comment améliorer la performance des ventes par région et par catégorie de produit ?  
- Quels produits génèrent le plus de marge et de revenu ?  
- Comment prédire les ventes futures pour optimiser la production, le stock et le budget marketing ?  
- Quels clients sont les plus rentables et fidèles ? Comment mieux les cibler pour maximiser la valeur client ?

## Description du dataset
Le projet contient plusieurs tables simulant un environnement business complet :

1. **Table ventes (`sales`)**
   - `order_id`, `date`, `region`, `country`, `category`, `product_name`, `units_sold`, `unit_price`, `production_cost`, `discount_rate`, `marketing_spend`  
   - 3050 lignes avec des erreurs volontairement introduites (prix négatifs, valeurs manquantes, colonnes inutiles)

2. **Table clients (`clients`)**
   - `customer_id`, `customer_name`, `segment`, `lead_score`, `acquisition_channel`, `country`  
   - Simule un CRM/ERP : informations client utilisées pour analyser la récurrence, le CA par client et le profil des acheteurs
   - `segment` : classification type “High value / Medium / Low”  
   - `lead_score` : score de potentiel du client  
   - `acquisition_channel` : canal d’acquisition (Organic search, Social Media, Direct…) 

Le dataset contient volontairement plusieurs erreurs pour simuler un vrai projet :  
- valeurs manquantes  
- prix négatifs  
- régions incorrectes  
- colonnes inutiles (`temp_id`, `random_notes`)

## Étapes de l’analyse
1. **Nettoyage des données (Python / Pandas)**  
   - Gestion des valeurs manquantes dans toutes les tables  
   - Correction des prix négatifs  
   - Conversion des dates  
   - Remplissage des régions manquantes à partir des pays  
   - Suppression des colonnes inutiles  
   - Arrondi des valeurs monétaires  

2. **Analyse business (SQL / Pandas)**  
   - Chiffre d’affaires et marge par produit, catégorie et région  
   - Analyse du ROI marketing  
   - Analyse du comportement client : CA par client, nombre de commandes, fidélité, segmentation par `segment` et `lead_score`  
   - Évaluation de l’efficacité des **canaux d’acquisition**  
   - Segmentation des clients selon CA et fréquence d’achat  

3. **Machine Learning (Python / Scikit-Learn)**  
   - Modèle pour prédire les ventes (`units_sold`)  
   - Possibilité de créer un modèle pour prédire la **valeur future d’un client (CLV)**  
   - Évaluation avec RMSE et R²

## Résultats principaux
- Les régions avec le CA le plus élevé : Europe et Amérique du Nord  
- Les catégories les plus rentables : chaussures et équipements  
- Les produits à forte marge identifiés  
- Identification des **top clients** par CA, fréquence d’achat et segment  
- Analyse de l’efficacité des canaux d’acquisition  
- Prédiction des ventes avec un RMSE acceptable, permettant de mieux planifier la production et le stock  

## Captures du dashboard
![Sales performance dashboard](images/dashboard_region.png)
![Feature Importance Machine Learning](images/feature_importance.png) 

## Outils utilisés
- Python (Pandas, NumPy, Scikit-learn, Matplotlib/Seaborn)  
- SQL (jointures, agrégations, calcul KPI)  
- Google Colab
- PowerBi
- GitHub
