# Chocs_Petroliers_Croissance_Algerie
Étude sur l'impact des chocs pétroliers sur la croissance économique en Algérie
# 🛢️ Impact des Chocs Pétroliers sur la Croissance Économique en Algérie

[![Licence: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![R Version](https://img.shields.io/badge/R-4.3%2B-blue)](https://www.r-project.org/)
[![Status](https://img.shields.io/badge/Status-Completed-success)](https://github.com/TON_USERNAME/Chocs_Petroliers_Croissance_Algerie)

## 📋 Description

Ce projet analyse l'**impact asymétrique des chocs pétroliers** sur la croissance économique algérienne sur la période **1980-2023**, en utilisant trois modèles économétriques complémentaires :

- **ARDL** (Autoregressive Distributed Lag) : Relations court et long terme
- **NARDL** (Nonlinear ARDL) : Effets asymétriques
- **QARDL** (Quantile ARDL) : Hétérogénéité conditionnelle

### 🎯 Question de Recherche

> Comment les chocs pétroliers affectent-ils la croissance économique en Algérie, et cet impact suit-il un schéma linéaire, asymétrique, ou conditionnel selon l'état de l'économie ?

---

## 🔑 Résultats Principaux

### Découvertes Clés

1. **Absence d'effet significatif du prix du pétrole** sur la croissance à court-moyen terme
2. **Pas d'asymétrie détectée** entre hausses et baisses du prix
3. **Taux de change** : Seule variable significative (β = +0.26, p < 0.05)
4. **Convergence des 3 modèles** : Robustesse méthodologique

### Interprétation

Ces résultats contre-intuitifs s'expliquent par :
- ✅ Efficacité des **mécanismes de stabilisation** (FRR, subventions, contrôle des changes)
- ✅ Horizon temporel court (1-4 ans) vs effets structurels long terme (5-15 ans)
- ✅ Signal de **diversification économique** (rôle du taux de change)

📄 **[Voir l'interprétation détaillée](docs/interpretation_resultats.md)**

---

## 📊 Données

### Sources

- **PIB** : Banque Mondiale (World Development Indicators)
- **Prix du pétrole** : OPEC Statistical Bulletin / BP Statistical Review
- **Taux de change** : Banque d'Algérie
- **Inflation** : FMI (International Financial Statistics)

### Période

- **1980-2023** (44 observations annuelles)
- Variables transformées en **différences premières** (stationnarité)

---

## 🛠️ Méthodologie

### Modèles Utilisés

| Modèle | Objectif | Package R |
|--------|----------|-----------|
| **ARDL** | Relations court/long terme | `ARDL` |
| **NARDL** | Effets asymétriques | `ARDL` |
| **QARDL** | Hétérogénéité par quantiles | `quantreg` |


### Tests de Stationnarité

- ✅ ADF (Augmented Dickey-Fuller)
- ✅ KPSS (Kwiatkowski-Phillips-Schmidt-Shin)
- ✅ PP (Phillips-Perron) ← **Privilégié pour robustesse**

### Tests de Diagnostic

- Autocorrélation : Breusch-Godfrey ✅
- Hétéroscédasticité : Breusch-Pagan ✅
- Normalité : Jarque-Bera ✅

---

## 🚀 Installation et Utilisation

### Prérequis

- R version ≥ 4.3.0
- RStudio (recommandé)

### Installation des Packages
```r
# Installer les packages nécessaires
install.packages(c(
  "tidyverse",      # Manipulation de données
  "ARDL",           # Modèles ARDL/NARDL
  "quantreg",       # Régression quantile (QARDL)
  "tseries",        # Tests de stationnarité
  "lmtest",         # Tests de diagnostic
  "vars",           # Modèles VAR et causalité
  "gridExtra",      # Composition de graphiques
  "viridis"         # Palettes de couleurs
))
```

### Exécution

#### Option 1 : Script complet
```r
# Cloner le dépôt
git clone https://github.com/Rastaoui/Chocs_Petroliers_Croissance_Algerie.git

# Ouvrir RStudio et exécuter
source("code/analyse_complete.Rmd")
```

#### Option 2 : Étape par étape
```r
# 1. Préparation des données
source("code/01_preparation_donnees.R")

# 2. Tests de stationnarité
source("code/02_tests_stationnarite.R")

# 3. Modèle ARDL
source("code/03_modele_ARDL.R")

# 4. Modèle NARDL
source("code/04_modele_NARDL.R")

# 5. Modèle QARDL
source("code/05_modele_QARDL.R")

```

---

## 📈 Résultats et Visualisations

### Graphiques Disponibles

| Graphique | Description | Fichier |
|-----------|-------------|---------|
| **ARDL** | Résidus et diagnostics | `results/figures/ardl_residus.png` |
| **NARDL** | Effets asymétriques | `results/figures/nardl_asymetrie.png` |
| **QARDL** | Effets par quantile | `results/figures/qardl_quantiles.png` |


### Tableaux de Résultats

- `results/tables/summary_ardl.csv` : Summary ARDL
- `results/tables/summary_nardl.csv` : Summary NARDL
- `results/tables/summary_qardl.csv` : Summary QARDL

---

## 📚 Documentation

- **[Méthodologie détaillée](docs/methodologie.md)** : Explication des modèles
- **[Interprétation des résultats](docs/interpretation_resultats.md)** : Analyse approfondie

---

## 🤝 Contribution

Les contributions sont les bienvenues ! Pour contribuer :

1. Fork le projet
2. Crée une branche (`git checkout -b feature/amelioration`)
3. Commit tes changements (`git commit -m 'Ajout fonctionnalité X'`)
4. Push vers la branche (`git push origin feature/amelioration`)
5. Ouvre une Pull Request

---

## 📄 Licence

Ce projet est sous licence **MIT** - voir le fichier [LICENSE](LICENSE) pour plus de détails.

---

## 👤 Auteur

**Rastaoui**
- 🎓 Master en Statistique et Prospective Économique.
- 🏛️ Ecole Nationale Supérieure de Staistique et d'Economie Appliquée.
- 📧 Email : ahmed.sahraoui.dz@gmail.com

---

## 📖 Citation

Si vous utilisez ce travail dans vos recherches, veuillez citer :
```bibtex
@mastersthesis{Rastaoui_2025,
  author  = {Rastaoui},
  title   = {Impact des Chocs Pétroliers sur la Croissance Économique en Algérie : Une Analyse par Modèles ARDL, NARDL et QARDL},
  school  = {Ecole Nationale Supérieure de Staistique et d'Economie Appliquée},
  year    = {2025},
  type    = {Mémoire de Master},
  url     = {https://github.com/Rastaoui/Chocs_Petroliers_Croissance_Algerie}
}
```

---

## 📊 Statistiques du Projet

- **Période d'étude** : 1980-2023 (44 ans)
- **Observations** : 39-44 selon le modèle
- **Variables** : 4 principales (PIB, Pétrole, Change, Inflation)
- **Modèles** : 3 (ARDL, NARDL, QARDL)
- **Tests** : 8+ (Stationnarité, Diagnostic, Causalité)
- **Lignes de code** : ~800

---

**⭐ Si ce projet t'est utile, n'hésite pas à laisser une étoile !**

---

*Dernière mise à jour : 06/11/2025 *
