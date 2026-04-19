# Procédure de calibration

Procédure complète pour reproduire la calibration, dans l'ordre exact. À suivre si un écran est reset ou remplacé.

## Préparation générale

1. Allumer les deux écrans, laisser chauffer 30 min
2. Régler l'éclairage ambiant de la pièce à son niveau habituel d'utilisation
3. Désactiver Windows *Éclairage nocturne* et *Luminosité adaptative*
4. Vérifier les résolutions natives :
   - iiyama : 3440 × 1440 @ 144 Hz (DisplayPort)
   - ViewSonic : 2560 × 1440 @ 165 Hz (DisplayPort)

## Phase 1 — iiyama (écran de référence)

### 1.1 Reset
- *Configuration* → *Rappel de mémoire* → Oui

### 1.2 Désactiver les modes
- *i-Style Mode* → Off
- *Configuration* → *FreeSync* → Off (temporairement)
- *Configuration* → *HDR* → Off

### 1.3 Appliquer les réglages OSD
Voir `iiyama-gb3461wqsu.md` pour la liste complète.

### 1.4 Installer le profil ICM
1. Clic droit sur `profiles/GB3461WQ.icm` → *Installer le profil*
2. Panneau de configuration → *Gestion des couleurs*
3. Onglet *Périphériques* → sélectionner iiyama → *Utiliser mes paramètres* + *Ajouter* → `GB3461WQ.icm` → *Définir comme profil par défaut*
4. Onglet *Avancé* → *Modifier les valeurs par défaut système* → onglet *Avancé* → cocher *Use Windows display calibration*

### 1.5 Validation
Trois tests avec la mire de gris + couleurs :
- Patches gris strictement neutres (aucune dominante)
- Dégradé 0→255 fluide sans banding
- Patch noir 4/4 très faiblement visible mais distinguable

### 1.6 Réactivation gaming
- *Configuration* → *FreeSync* → On
- Panneau NVIDIA/AMD : activer G-Sync Compatible / FreeSync

## Phase 2 — ViewSonic (alignement sur iiyama)

### 2.1 Reset
- *Setup Menu* → *Memory Recall* → Yes

### 2.2 Désactiver les modes
- *ViewMode* → Standard
- *Setup Menu* → *Adaptive Sync* → Off (temporairement)
- *Manual Image Adjust* → *1ms Mode* → Off
- *Manual Image Adjust* → *Advanced DCR* → Off

### 2.3 Appliquer les réglages OSD
Voir `viewsonic-vx2718-2kpc.md` pour la liste complète.

Valeurs finales après alignement visuel :
- Brightness 40
- Contrast 75
- User Color : R=92 / G=100 / B=86

### 2.4 Profil Windows
Laisser `VX2718-2KPC sRGB 6500K` par défaut. Rien à faire.

### 2.5 Alignement visuel côte à côte

Méthode (à refaire si matching imparfait après reset) :

1. **Luminance** : afficher une page blanche sur les deux écrans. Ajuster la Brightness du ViewSonic jusqu'à ce que le blanc paraisse de même intensité que sur l'iiyama. Détourner les yeux 5 s entre chaque comparaison.

2. **Teinte blanche** : identifier la dominante du ViewSonic par rapport à l'iiyama :
   - Bleu/froid → baisser Blue par paliers de 2
   - Jaune/chaud → baisser Red par paliers de 2
   - Rose/magenta → augmenter Green ou baisser Red
   - Vert → baisser Green
   
   Garder **au moins un canal à 100** pour préserver la luminance maximale du blanc.

3. **Vérification gris** : afficher les patches 12/31/50/71/92 %. Si les gris moyens-hauts sont trop foncés sur le ViewSonic → monter le Contrast à 75 (pas au-delà, sinon clipping).

4. **Compensation luminance** : monter le Contrast augmente légèrement la luminance du blanc. Baisser la Brightness de 2-5 points pour recompenser.

5. **Validation chairs** : afficher les patches chair. S'ils paraissent légèrement plus fades que sur l'iiyama, c'est la limite physique due à la différence de gamut natif — accepter.

### 2.6 Réactivation gaming
- *Setup Menu* → *Adaptive Sync* → On
- Panneau NVIDIA/AMD : activer G-Sync Compatible / FreeSync

## Phase 3 — Documentation

Après toute re-calibration, mettre à jour dans ce repo :
- Les valeurs finales dans les fichiers `.md` correspondants
- La date de dernière calibration (voir section ci-dessous)

## Journal des calibrations

| Date | Écran | Action | Valeurs clés |
|---|---|---|---|
| 2026-04-19 | iiyama + ViewSonic | Calibration initiale par matching visuel | iiyama Lum=55 / ViewSonic Brt=40 Ct=75 R/G/B=92/100/86 |
