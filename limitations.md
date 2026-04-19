# iiyama G-MASTER GB3461WQSU-B1

Écran de référence de la paire. Calibré via le profil ICM de Les Numériques (mesuré à la sonde X-Rite en septembre 2020).

## Profil ICM

Fichier : `profiles/GB3461WQ.icm`

Caractéristiques mesurées :
- Gamma R/G/B : 2.194
- Point blanc : D65
- Luminance cible : 150 cd/m²
- Gamut : ~106 % sRGB
- VCGT active (plafonds R=93.9 %, G=96.5 %, B=99.8 %)

## Réglages OSD

### Menu Image

| Paramètre | Valeur |
|---|---|
| Luminosité | **55** |
| Contraste | 50 |
| Black Tuner | 0 |
| Finesse | 50 |
| Overdrive | −2 |
| Contraste avancé (ACR) | Off |
| Mode ECO | Off |
| Technologie X-Res | Off |
| MBR | Off |

### Menu Couleur

| Paramètre | Valeur |
|---|---|
| Mode Couleur | **Normal** |
| Réducteur de lumière bleue | Off |
| Gamma | par défaut |

### Menu Configuration

| Paramètre | Valeur |
|---|---|
| HDMI RGB Range | Full Range (HDMI uniquement) |
| HDR | Off |
| FreeSync | On (après calibration) |
| i-Style Mode | Off |
| Direct Drive | Off |

## Installation du profil Windows

1. Clic droit sur `GB3461WQ.icm` → *Installer le profil*
2. Panneau de configuration → *Gestion des couleurs*
3. Onglet *Périphériques* → sélectionner l'iiyama → cocher *Utiliser mes paramètres pour ce périphérique*
4. *Ajouter…* → sélectionner `GB3461WQ.icm` → *Définir comme profil par défaut*
5. Onglet *Avancé* → *Modifier les valeurs par défaut système…* → onglet *Avancé* → cocher *Use Windows display calibration*

## Notes

- Luminosité 55 est un compromis entre fidélité (150 cd/m² visé) et confort en pièce éclairée normalement — à ajuster entre 25 (pièce sombre) et 70 (forte luminosité ambiante)
- Ne jamais toucher au Contraste ni au Black Tuner, ils invalideraient le profil
- Le Contraste avancé (ACR) doit rester Off en permanence : sinon la luminance varie selon le contenu et la calibration devient inopérante
- Connexion recommandée : DisplayPort (permet 144 Hz et évite la question du RGB Range)

## Référence

Profil et paramètres initiaux dérivés du test Les Numériques :
https://www.lesnumeriques.com/moniteur-ecran-lcd/iiyama-g-master-gb3461wqsu-b1-p59793/test.html
