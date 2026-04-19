# Screen Calibration

Réglages et profils ICM de calibration pour mes deux écrans, calibrés en matching visuel sans sonde colorimétrique.

## Écrans concernés

| Écran | Modèle | Rôle | Dalle |
|---|---|---|---|
| 1 (gauche) | iiyama G-MASTER GB3461WQSU-B1 | Référence colorimétrique | IPS-ADS, 34", 3440×1440, 144 Hz |
| 2 (droite) | ViewSonic VX2718-2KPC | Aligné sur iiyama | VA curved 1500R, 27", 2560×1440, 165 Hz |

## Objectif

Minimiser l'écart colorimétrique entre les deux écrans pour un usage **mixte jeu + travail visuel**, sans utiliser de sonde colorimétrique.

## Méthode

- **iiyama** calibré à partir du profil ICM fourni par Les Numériques (sonde X-Rite, septembre 2020)
- **ViewSonic** aligné visuellement sur l'iiyama par comparaison côte à côte
- Cibles : gamma 2.2, point blanc D65, luminance ~150 cd/m²

## Résultat

Delta E estimé : 2-3 sur les tons chair (imperceptible en usage normal, légèrement perceptible en comparaison directe sur mires synthétiques).

## Structure

```
.
├── README.md                    # ce fichier
├── iiyama-gb3461wqsu.md         # réglages complets iiyama
├── viewsonic-vx2718-2kpc.md     # réglages complets ViewSonic
├── procedure.md                 # procédure de calibration reproductible
├── limitations.md               # écarts résiduels et raisons
└── profiles/
    ├── GB3461WQ.icm             # profil ICM iiyama (Les Numériques)
    └── VX2718_2KPC.icm          # profil ICM ViewSonic (constructeur, générique)
```

## En cas de reset d'un moniteur

1. Consulter le fichier `.md` correspondant à l'écran concerné
2. Appliquer les réglages OSD dans l'ordre indiqué
3. Pour l'iiyama : réinstaller le profil ICM depuis `profiles/`
4. Le ViewSonic ne nécessite pas d'intervention Windows (profil générique)
