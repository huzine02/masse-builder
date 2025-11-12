# 💪 MASSE BUILDER v3.2 ULTIMATE

## 🎯 Guide d'utilisation des nouvelles fonctionnalités

---

## 📋 TABLE DES MATIÈRES
1. [Vue d'ensemble](#vue-densemble)
2. [Auto-save permanent](#1-auto-save-permanent)
3. [Timer flottant](#2-timer-flottant-persistant)
4. [Guidage transitions](#3-guidage-transitions-automatique)
5. [Validation par couleurs](#4-validation-visuelle-par-couleurs)
6. [Toggle échauffement](#5-toggle-échauffement-optimalcomplet)
7. [Workflow optimal](#workflow-optimal-complet)
8. [FAQ & Troubleshooting](#faq--troubleshooting)

---

## Vue d'ensemble

**Masse Builder v3.2 Ultimate** est la version optimisée UX de ton tracker d'entraînement. Cette mise à jour apporte 5 améliorations majeures pour réduire la friction et améliorer la qualité de tes données.

### Nouveautés principales
- ✅ Sauvegarde automatique avec feedback visuel permanent
- ✅ Timer persistant qui reste visible partout
- ✅ Suggestions intelligentes entre chaque série
- ✅ Système de couleurs pour validation (Rouge/Jaune/Vert)
- ✅ Échauffement adaptable (15 min ou 28 min)

---

## 1. 💾 Auto-save permanent

### Comment ça marche?
Chaque fois que tu saisis une donnée, l'app sauvegarde **automatiquement** après 1.5 seconde.

### Indicateur visuel
- **Position**: Coin supérieur droit
- **États**:
  - 💾 "Sauvegarde..." → En cours
  - ✅ "Sauvegardé" → Confirmé (disparaît après 1.5s)

### Avantages
- ❌ **Plus besoin** de bouton manuel de sauvegarde
- ✅ Feedback permanent, tu sais toujours où tu en es
- ✅ Aucune donnée perdue

### Exemple d'utilisation
```
1. Tu saisis "28×8" dans S1
   → Champ devient VERT
   → Coin droit: "💾 Sauvegarde..."
   → 0.3s après: "✅ Sauvegardé"
2. Tu continues sur S2 sans te soucier
```

---

## 2. ⏱️ Timer flottant persistant

### Qu'est-ce que c'est?
Un overlay de timer qui **reste visible** même quand tu scrolles ou changes d'onglet dans l'app.

### Localisation
- **Position**: Coin inférieur droit
- **Toujours au-dessus** du contenu (z-index élevé)
- **Animation**: Slide-up fluide

### Fonctionnalités
- ⏱️ Affiche temps restant (format MM:SS)
- 📝 Affiche nom de l'exercice en cours
- 🟡 Alerte visuelle 10s avant fin (jaune + pulse)
- 🔔 Notification + vibration + son à la fin
- 🎛️ Boutons intégrés:
  - **+30s**: Ajoute 30 secondes
  - **Stop**: Arrête le timer

### Comment l'utiliser?
#### Méthode 1: Manuelle (timer principal)
```
1. Clique sur un bouton timer principal (60s/90s/2min/3min)
   → Timer principal ET flottant démarrent ensemble
2. Le timer flottant reste visible même si tu scrolls
3. Clique "+30s" si besoin plus de repos
4. Clique "Stop" pour arrêter avant la fin
```

#### Méthode 2: Automatique (guidage transition)
```
1. Complète une série (ex: "28×8")
2. Modal de guidage apparaît (800ms après)
3. Clique "⏱️ Repos [XXs]"
   → Timer flottant démarre avec suggestion intelligente
   → Nom exercice affiché automatiquement
```

### Exemple concret
```
Exercice: "Développé incliné haltères 30°"
Tu viens de finir S1 (28×8)

→ Modal suggère: "Repos 180s" (exercice composé)
→ Clic sur bouton
→ Timer flottant s'affiche:
   ┌─────────────────────┐
   │ ⏱️ Développé incliné│
   │      03:00         │
   │  [+30s]  [Stop]    │
   └─────────────────────┘

→ Tu peux scroller, lire notes, boire
→ Timer reste visible en bas à droite
→ À 00:10 → Devient jaune + pulse
→ À 00:00 → BIP + vibration + notification
```

---

## 3. 🎯 Guidage transitions automatique

### Concept
Après chaque série complétée, l'app **détecte automatiquement** et te propose les prochaines actions.

### Comment ça marche?
1. Tu saisis une performance (ex: "28×8")
2. L'app attend **800ms** (pour voir si tu continues à saisir)
3. Si pause → **Modal apparaît** au centre

### Modal de guidage
```
┌─────────────────────────────────┐
│     ✅ Série terminée !        │
│                                 │
│    Que veux-tu faire ?         │
│                                 │
│  [⏱️ Repos 180s] [➡️ Série +]  │
└─────────────────────────────────┘
```

### Options disponibles
- **⏱️ Repos [XXs]**:
  - Lance timer flottant avec suggestion intelligente
  - Temps adapté selon type exercice
- **➡️ Série suivante**:
  - Scroll automatique vers prochain champ
  - Focus automatique (clavier prêt)

### Suggestions intelligentes de repos
L'app analyse l'ID exercice pour suggérer le repos optimal:

| Type exercice | ID exercice | Repos suggéré | Exemples |
|---------------|-------------|---------------|----------|
| Composé principal | `*-1`, `*-2` | **180s (3 min)** | Développé incliné, Tractions, RDL, Rowing barre |
| Intermédiaire | `*-3`, `*-4` | **120s (2 min)** | Tirage horizontal, Développé Arnold, Goblet squat |
| Isolation | `*-5`, `*-6` | **90s** | Extensions triceps, Curl incliné, Face pull |

### Auto-hide
- Modal se cache automatiquement après **8 secondes**
- Tu peux la fermer manuellement en cliquant à côté

### Workflow exemple
```
Exercice: "Élévations latérales haltères" (exercice 1)

1. Tu saisis S1: "8×12"
   → Champ devient VERT
   → "✅ Sauvegardé" apparaît

2. Après 800ms:
   → Modal: "⏱️ Repos 180s" (car exercice 1 = composé)

3. Tu cliques "Repos 180s":
   → Timer flottant démarre (03:00)
   → Modal disparaît
   → Tu peux bouger, boire, etc.

4. Timer fini (BIP):
   → Modal réapparaît: "➡️ Série suivante?"
   → Clic → Focus auto sur S2
```

---

## 4. 🎨 Validation visuelle par couleurs

### Concept
Chaque champ de saisie a une **couleur** qui indique son statut.

### Système de couleurs

#### 🔴 ROUGE - Champ vide obligatoire
- **Signification**: Ce champ doit être rempli
- **Action**: Saisis ta performance
- **Exemple**: Champ vide attendant "28×8"

#### 🟡 JAUNE - Valeur pré-remplie (à vérifier)
- **Signification**: L'app a pré-rempli avec la valeur de la semaine dernière
- **Action**: Vérifie si correct, modifie si besoin
- **Exemple**: Champ contient "28×8" (copié de S1 précédente)
- **Passe VERT**: Dès que tu modifies la valeur

#### 🟢 VERT - Validé par utilisateur
- **Signification**: Valeur confirmée par toi
- **Action**: Rien, c'est bon !
- **Exemple**: Tu as saisi "30×8" (progression)

### Logique détaillée
```
Chargement page:
├─ Champ vide → 🔴 ROUGE
└─ Champ pré-rempli (semaine dernière) → 🟡 JAUNE

Pendant saisie:
├─ Tu supprimes tout → 🔴 ROUGE
├─ Tu modifies valeur pré-remplie → 🟢 VERT
└─ Tu saisis dans champ vide → 🟢 VERT

Après sauvegarde:
└─ Reste VERT (confirmé sauvegardé)
```

### Avantages
- ✅ **Vision instantanée** de la complétion
- ✅ **Détection rapide** des champs oubliés
- ✅ **Confiance** dans les données (sais ce qui est validé)

### Exemple concret
```
Développé incliné - Semaine 3

Au chargement:
├─ S1: "28×8" 🟡 (pré-rempli S2)
├─ S2: "28×8" 🟡 (pré-rempli S2)
├─ S3: "28×7" 🟡 (pré-rempli S2)
├─ S4: ""     🔴 (vide)
└─ S5: ""     🔴 (vide)

Tu progresses et saisis:
├─ S1: "30×8" 🟢 (modifié → progression!)
├─ S2: "30×8" 🟢 (modifié)
├─ S3: "30×7" 🟢 (modifié)
├─ S4: "30×7" 🟢 (saisi)
└─ S5: "30×6" 🟢 (saisi)

Vision finale: Tous VERTS = Séance complète ✅
```

---

## 5. 🔄 Toggle échauffement Optimal/Complet

### Concept
Choisis entre **2 modes d'échauffement** selon ton temps disponible.

### Modes disponibles

#### 🔵 COMPLET (28 min) - Défaut
**Structure 4 phases:**
1. Phase 1: Cardio léger (5 min)
2. Phase 2: Mobilité articulaire (5 min)
3. Phase 3: Pré-activation spécifique (5 min)
4. Phase 4: Montée progressive charges (5 min)
5. McGill Big 3 (8 min)

**Quand utiliser:**
- ✅ Tu as le temps (>60 min total séance)
- ✅ Début semaine (Lundi)
- ✅ Après repos (weekend)
- ✅ Exercices lourds (RDL, Squat)
- ✅ Douleurs articulaires

#### ⚡ OPTIMAL (15 min) - Rapide
**Structure essentielle:**
1. Phase 1: Cardio léger (5 min)
2. Phase 2: Mobilité réduite (2 min)
3. McGill Big 3 (8 min)
4. ❌ Phases 3-4 cachées

**Quand utiliser:**
- ✅ Pressé (<50 min total séance)
- ✅ Milieu/fin semaine (Mercredi/Vendredi)
- ✅ Déjà échauffé (2e séance du jour)
- ✅ Exercices légers/isolations
- ✅ Salle bondée (accès machines limité)

### Comment basculer?

#### Visuel du toggle
```
┌─────────────────────────────────────────┐
│ Mode Optimal 15min                  ○───│
│ McGill Big 3 + Activation essentielle   │
└─────────────────────────────────────────┘
         ↓ (tu cliques le toggle)
┌─────────────────────────────────────────┐
│ Mode Optimal 15min                  ───○│  ← Switch VERT
│ McGill Big 3 + Activation essentielle   │
└─────────────────────────────────────────┘

→ Modal: "⚡ Mode Optimal activé"
→ Phases 3-4 disparaissent (cachées)
→ Titre change: "OPTIMAL (15 min)"
```

### Localisation
- **Où**: En haut de chaque section échauffement
- **Quels jours**: Lundi, Mercredi, Vendredi
- **Indépendant**: Chaque jour a son propre réglage

### Sauvegarde préférence
- ✅ Choix sauvegardé dans localStorage
- ✅ Retrouvé au prochain lancement
- ✅ Indépendant par jour (Lundi ≠ Mercredi)

### Exemple d'utilisation
```
Lundi (temps libre):
→ Toggle OFF (défaut)
→ Échauffement COMPLET 28 min
→ Séance totale: 75 min

Mercredi (pressé):
→ Toggle ON
→ Échauffement OPTIMAL 15 min
→ Séance totale: 60 min

Vendredi (temps libre à nouveau):
→ Toggle OFF (retrouve réglage Lundi)
→ Échauffement COMPLET 28 min
```

### Best practices

#### Utilise COMPLET si:
- C'est ta première séance de la semaine
- Tu as des douleurs/raideurs
- Exercices lourds (>80% 1RM)
- Après 2+ jours repos
- Temps disponible suffisant

#### Utilise OPTIMAL si:
- Tu es pressé par le temps
- Déjà entraîné aujourd'hui
- Séance légère (hypertrophie/isolation)
- Salle bondée
- Mi/fin de semaine (déjà mobile)

---

## Workflow optimal complet

### 🚀 Configuration initiale (1ère fois)

1. **Activer notifications**
   ```
   Clique "✅ Activer notifications"
   → Autorise dans popup navigateur
   → Statut: "✅ Activées !"
   ```

2. **Choisir modes échauffement**
   ```
   Lundi: Toggle OFF (complet 28 min)
   Mercredi: Toggle ON (optimal 15 min)
   Vendredi: Toggle OFF (complet 28 min)
   ```

3. **Vérifier couleurs**
   ```
   Ouvre Lundi → Vérifie champs JAUNES (pré-remplis)
   → Normal si c'est pas la 1ère semaine
   ```

---

### 📋 Workflow séance complète

#### AVANT la séance
```
1. Ouvre l'app (index.html)
2. Vérifie semaine affichée (ex: "SEMAINE 3/10")
3. Clique onglet du jour (🔴 LUN / 🔵 MER / 🟢 VEN)
4. Vérifie toggle échauffement selon temps dispo
```

#### PENDANT l'échauffement
```
McGill Big 3 (8 min):
└─ Suis protocole détaillé (voir onglet Lundi)

Phase 1 Cardio (5 min):
└─ Vélo/Rameur léger

Phase 2 Mobilité (5 min):
└─ Suis exercices listés

Si mode COMPLET:
├─ Phase 3 Pré-activation (5 min)
└─ Phase 4 Montée progressive (5 min)
```

#### PENDANT la séance (exemple: Développé incliné)

**Série 1:**
```
1. Fais ta série (8 reps avec 28kg)
2. Saisis dans S1: "28×8"
   → Champ devient 🟢 VERT
   → "✅ Sauvegardé" apparaît (coin droit)
3. Après 800ms → Modal guidage:
   "⏱️ Repos 180s" suggéré
4. Clique "Repos 180s"
   → Timer flottant démarre (coin bas droit)
   → Modal disparaît
5. Pendant repos:
   → Bois, respire, notes
   → Timer visible même si tu scrolls
6. À 00:10 → Timer jaune + pulse (derniers instants)
7. À 00:00 → BIP + vibration + notification
   → Tu es prêt pour S2
```

**Série 2:**
```
1. Fais ta série (8 reps avec 28kg)
2. Saisis S2: "28×8"
   → Champ 🟢 VERT
   → "✅ Sauvegardé"
3. Modal suggère: "⏱️ Repos 180s" OU "➡️ Série suivante"
4. Si tu veux pas repos:
   → Clic "Série suivante"
   → Scroll auto vers S3
   → Focus auto (clavier prêt)
5. Continue...
```

**Série 5 (dernière):**
```
1. Fais ta série (6 reps avec 28kg)
2. Saisis S5: "28×6" (2 reps en moins = limite atteinte)
   → Champ 🟢 VERT
   → Analyse perfo apparaît:
     "🔴 Trop difficile, réduis charge (-2.5kg)"
3. Modal guidage:
   → Ignore ou clic "Série suivante"
   → Passe à exercice suivant
```

#### Exercice suivant (Développé Arnold)
```
Chargement auto des données semaine précédente:

S1: "16×10" 🟡 JAUNE (pré-rempli)
S2: "16×10" 🟡 JAUNE
S3: "16×9"  🟡 JAUNE

Tu décides progression:
→ Change S1: "18×10" → 🟢 VERT
→ Fais série, saisis, repos, etc.
```

#### FIN de séance
```
1. Vérifie tous champs 🟢 VERTS
   → Si 🟡 JAUNES restants: vérifie si correct ou oublié
   → Si 🔴 ROUGES: série oubliée? Complète

2. Clique "✅ Terminer & Exporter"
   → Timer session s'arrête
   → Modal feedback apparaît

3. Remplis feedback:
   ├─ Énergie: 7/10
   ├─ Sommeil: 8/10
   ├─ Congestion: 9/10
   ├─ Douleurs: 2/10
   ├─ RPE global: 7/10
   └─ Notes: "Excellente séance, bonne progression..."
      (min 20 caractères)

4. Clique:
   ├─ "📋 Copier" → Rapport copié presse-papier
   ├─ "🤖 ChatGPT" → Ouvre ChatGPT avec rapport
   └─ "📧 Email" → Envoie à coach
```

#### APRÈS la séance
```
Si Lundi ou Vendredi:
→ Protocole Anti-inflammatoire (16h30):
  ├─ Sauna 85°C: 2×10min
  ├─ Piscine froide: 3min
  └─ Spa 40°C: 10min

Si Mercredi (optionnel):
→ Protocole Détente (20h30):
  ├─ Spa 38-40°C: 15min
  ├─ Piscine froide: 2-3min
  └─ Sauna doux: 10min
```

---

## FAQ & Troubleshooting

### ❓ Questions fréquentes

**Q: Le timer flottant ne démarre pas?**
```
R: Vérifie que tu cliques bien sur un bouton timer (60s/90s/2min)
   OU que tu utilises le guidage "Repos XXs"
   Le timer flottant démarre automatiquement avec le principal.
```

**Q: Les couleurs ne changent pas?**
```
R: Assure-toi de saisir une valeur DIFFÉRENTE du placeholder
   Exemple: Si placeholder = "28×8"
   → Saisis "30×8" (progression) → 🟢 VERT
   → Si tu re-saisis "28×8" → Reste 🟡 JAUNE
```

**Q: Modal guidage n'apparaît jamais?**
```
R: La modal attend 800ms après ta saisie
   → Si tu continues à saisir rapidement, elle ne s'affiche pas (normal)
   → Elle détecte seulement les "pauses" après série
```

**Q: Toggle échauffement ne sauvegarde pas?**
```
R: Vérifie localStorage activé dans navigateur
   → Teste en mode navigation privée
   → Efface cache si problème persiste
```

**Q: Notifications ne marchent pas?**
```
R: 1. Vérifie autorisations navigateur (Paramètres > Notifications)
   2. Re-clique "Activer notifications"
   3. Sur mobile: autorise en premier plan
```

---

### 🐛 Problèmes connus

**Timer flottant reste bloqué à 00:00**
```
Solution: Recharge page (F5)
Cause: Rare bug si navigation rapide entre onglets
```

**Guidage apparaît en boucle**
```
Solution: Clique "Série suivante" OU attends 8s (auto-hide)
Cause: Input focus revient sur champ précédent
```

**Couleurs mélangées (vert devient jaune)**
```
Solution: Force sauvegarde (change onglet puis reviens)
Cause: Conflit avec anciennes données cache
```

---

### 💡 Astuces avancées

**Raccourcis clavier**
```
Tab → Passer au champ suivant
Entrée → Valide et passe au suivant
Échap → Ferme modal guidage
```

**Optimiser workflow**
```
1. Remplis séries PENDANT repos (utilise timer flottant)
2. Prépare charges suivantes pendant dernier repos
3. Utilise "Série suivante" pour navigation rapide
4. Vérifie couleurs en fin bloc (vue d'ensemble)
```

**Mode power user**
```
1. Active tous toggles échauffement optimal (gain 39 min/semaine)
2. Utilise guidage auto systématiquement (jamais toucher timer manuel)
3. Remplis feedback pendant douche post-workout
4. Export ChatGPT pour analyse IA automatique
```

---

## 📞 Support

### Besoin d'aide?
- 📧 Email: support@massebuilder.app (fictif)
- 💬 Discord: MasseBuilder Community (fictif)
- 📖 Docs: docs.massebuilder.app (fictif)

### Signaler un bug
1. Note version (v3.2)
2. Décris problème
3. Captures écran si possible
4. Envoie rapport via email

---

**Version:** v3.2 ULTIMATE
**Date:** 2025-11-12
**Prochaine mise à jour:** v3.3 (TBD)

---

💪 **BON TRAINING!** 🔥
