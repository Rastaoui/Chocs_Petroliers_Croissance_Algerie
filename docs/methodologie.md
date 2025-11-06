# Méthodologie

## Vue d'ensemble:

Cette étude utilise trois modèles économétriques pour analyser l'impact des chocs pétroliers sur la croissance algérienne.

## 1. Modèle ARDL:

### Principe:
Le modèle ARDL (Autoregressive Distributed Lag) permet d'estimer les relations de court et long terme entre variables.

### Équation:
<img width="1077" height="95" alt="image" src="https://github.com/user-attachments/assets/8e9740af-8988-43f4-90d6-19a6f8012018" />
### Avantages
- Fonctionne avec variables I(0) ou I(1)
- Estime court et long terme simultanément
- Teste la cointégration (Bounds test)

## 2. Modèle NARDL:
<img width="1129" height="95" alt="image" src="https://github.com/user-attachments/assets/37297ad2-12e8-483c-afdd-af5c26a2a775" />


### Principe:
Extension du ARDL qui décompose la variable explicative en composantes positives et négatives.

### Décomposition:
X_t^+ = Σ max(ΔX_i, 0)  # Hausses cumulées

X_t^- = Σ min(ΔX_i, 0)  # Baisses cumulées

### Test d'asymétrie
H0: β^+ = β^-  (Symétrie)
H1: β^+ ≠ β^-  (Asymétrie)

## 3. Modèle QARDL
<img width="1265" height="106" alt="image" src="https://github.com/user-attachments/assets/25b8c755-0a26-4085-a2c4-2d915191327b" />

### Principe
Régression quantile appliquée au modèle ARDL pour capturer l'hétérogénéité conditionnelle.

### Quantiles
- Q10: Récession sévère
- Q50: Croissance médiane
- Q90: Boom économique

### Avantage
Détecte si l'asymétrie varie selon l'état de l'économie.

---

Pour plus de détails, voir le code dans `code/`.
