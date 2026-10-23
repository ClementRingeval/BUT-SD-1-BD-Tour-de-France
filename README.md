# Tour de France 2022 — Base de Données & Analyse (BUT Science des Données)

Ce dépôt contient le projet académique de base de données réalisé dans le cadre du **BUT Science des Données (1ère année)**, centré sur l'analyse et la gestion des données de l'édition **2022 du Tour de France**.

---

## 📋 1. Présentation du Projet

L'objectif de ce projet est de concevoir, structurer et exploiter une base de données relationnelle à partir des données officielles du Tour de France 2022. Le projet couvre l'ensemble du cycle de vie des données :
* **Modélisation relationnelle** (Schéma entité-association, tables normalisées).
* **Intégration et nettoyage des données** sources issues de fichiers Excel et de requêtes SQL.
* **Gestion des classements, bonifications, pénalités et abandons** des coureurs tout au long des étapes.

---

## 🗂️ 2. Structure des Fichiers Sources

Le projet s'appuie sur plusieurs jeux de données principaux :
* `DONNEES_TOUR_FRANCE_22.xlsx` : Contient les informations détaillées sur les coureurs, les équipes, les caractéristiques des étapes (villes de départ et d'arrivée, distances, types d'étapes) et les résultats bruts.
* `BONIFICATION_EXCLUSION_TOUR_22.xlsx` : Répertorie les bonifications de temps, les pénalités ainsi que les dates et motifs d'exclusion / abandon des coureurs par étape.
* `sql-pays.xlsx` : Table de référence des pays et de leurs codes associés.

---

## 📐 3. Modélisation de la Base de Données

La base de données est structurée autour de plusieurs tables principales reliées par des clés primaires et étrangères :

| Table | Description Principale | Attributs Clés |
| :--- | :--- | :--- |
| **`Coureur`** | Informations personnelles et identifiant des cyclistes | `Num_dossard`, `Nom_coureur`, `Prenom_coureur`, `Date_naissance`, `Nationalite` |
| **`Equipe`** | Groupes sportifs engagés | `Num_Equipe`, `Nom_equipe`, `Pays_Equipe` |
| **`Etape`** | Détails géographiques et techniques de chaque étape | `Num_etape`, `Date_etape`, `Type_etape`, `Distance`, `Ville_Dep`, `Ville_Arr` |
| **`Competition` / `Participe`** | Suivi des performances, temps réalisés et classements | `Num_dossard`, `Num_etape`, `Temps_Realise`, `ID_Equipe` |
| **`Bonification_Exclusion`** | Gestion des incidents de course, pénalités et bonifications | `Num_etape`, `Num_dossard`, `Bonification`, `Pénalité`, `Motif_Exclusion` |

---

## 🛠️ 4. Fonctionnalités & Traitements

Le projet permet d'exécuter diverses requêtes et analyses décisionnelles :
1. **Suivi des étapes** : Consultation des profils d'étape (plaine, montagne, accidenté) et des villes traversées.
2. **Gestion des temps et classements** : Application des bonifications de temps et des pénalités sur les temps réels des coureurs.
3. **Analyse des abandons et exclusions** : Suivi des coureurs n'ayant pas terminé certaines étapes ou exclus de la course avec leurs motifs respectifs.
4. **Statistiques par équipe et par nationalité** : Agrégations sur les performances globales des écuries cyclistes.

---

## 🚀 5. Utilisation

Pour déployer et exploiter la base de données :
1. Importer les fichiers sources (`.xlsx`) dans votre SGBD relationnel (PostgreSQL, MySQL ou Access).
2. Vérifier les types de données et exécuter les scripts de création des tables et des clés étrangères.
3. Exécuter les requêtes d'analyse SQL pour générer les rapports de course.

---

*Projet réalisé dans le cadre du cursus BUT Science des Données — IUT de Lille (Campus de Roubaix).*
