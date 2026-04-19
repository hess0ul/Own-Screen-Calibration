# ViewSonic VX2718-2KPC

Écran secondaire, aligné visuellement sur l'iiyama (écran de référence).

## Profil ICM

Fichier : `profiles/VX2718_2KPC.icm` (profil constructeur générique, sans VCGT, équivalent à un sRGB standard renommé)

**Aucun effet réel sur le rendu** — laissé en place pour la sémantique Windows.

Toute la calibration se joue dans l'OSD du moniteur.

## Réglages OSD

### Menu ViewMode

| Paramètre | Valeur |
|---|---|
| ViewMode | **Standard** |

### Menu Color Adjust

| Paramètre | Valeur |
|---|---|
| Contrast | **75** |
| Brightness | **40** |
| Color Temperature | **User Color** |
| User Color — Red | **92** |
| User Color — Green | **100** |
| User Color — Blue | **86** |
| Color Space | RGB |
| Color Range | Full Range |

### Menu Manual Image Adjust

| Paramètre | Valeur |
|---|---|
| Sharpness | 50 |
| Blue Light Filter | 0 (Off) |
| Aspect Ratio | 16:9 |
| Overscan | Off |
| Black Stabilization | 50 |
| Advanced DCR / DCR avancé | Off |
| Response Time | Standard |

### Menu Setup

| Paramètre | Valeur |
|---|---|
| Adaptive Sync | On (après calibration) |
| 1ms Mode | Off |
| ECO Mode | Standard |

## Profil Windows

Laisser `VX2718-2KPC sRGB 6500K` par défaut. Pas d'action nécessaire dans Gestion des couleurs.

Ne jamais assigner le profil iiyama (`GB3461WQ.icm`) à ce moniteur — ça dégraderait le rendu.

## Notes

- Connexion : DisplayPort (obligatoire pour 165 Hz et RGB Range automatique en Full Range)
- Les valeurs R/G/B = 92/100/86 compensent une dominante magenta du blanc natif
- Le Contrast à 75 (au lieu de 70) compense un gamma natif légèrement supérieur à 2.2
- La Brightness à 40 aligne la luminance perçue sur celle de l'iiyama à Luminosité 55
- Laisser le moniteur chauffer 30 min avant toute comparaison visuelle — les VA dérivent davantage que les IPS au démarrage

## Écarts résiduels acceptés

Voir `limitations.md` pour le détail. Résumé :
- Noirs plus profonds sur le ViewSonic (VA 4000:1 vs IPS 1000:1) — non corrigible
- Chairs légèrement plus fades que sur l'iiyama — différence de gamut natif, non corrigible sans sonde
- Gris hauts (71-92 %) très légèrement plus gris que sur l'iiyama — résidu de gamma
