#  EKO AR — Mascotte 3D Interactive
### Solution pour le Défi IA — Réalité Augmentée

**Équipe:** ARSII  


## 📋 Résumé de la Solution

Application de **Réalité Augmentée** mobile/web qui transforme l'avatar 2D officiel EKO en mascotte 3D holographique interactive. Dès que la caméra détecte l'image imprimée, la mascotte apparaît en superposition avec **6 animations de danse différentes**, effets visuels et capture photo/vidéo.

---

## 🏆 Points forts pour le jury

| Critère | Notre approche |
|---------|---------------|
| **Détection d'image (CV)** | MindAR.js — détection robuste par features 2D en temps réel |
| **Rendu 3D** | Three.js — sprites holographiques multicouches avec chromatic aberration |
| **Performance** | 30+ FPS sur mobile, WebGL optimisé |
| **Animation IA** | 6 styles de danse + 5 effets visuels dynamiques |
| **UX** | Interface HUD gaming, sélecteur visuel, onboarding clair |
| **Innovation** | Effet holographique 3 couches (cyan + magenta + aberration) |

---

## 🛠 Technologies Utilisées

- **MindAR.js 1.2.1** — Computer Vision / Image Tracking
- **Three.js r128** — Rendu 3D WebGL
- **WebRTC** — Accès caméra en temps réel
- **MediaRecorder API** — Capture vidéo
- **Canvas API** — Composition photo
- **Web Share API** — Partage social

---

## 📁 Structure des fichiers

```
/
├── index.html          ← Application complète (fichier unique)
├── targets.mind        ← Fichier cible MindAR (à générer)
├── mascotte.png        ← Image officielle EKO
└── README.md           ← Ce fichier
```




## 🎮 Fonctionnalités

### Détection
- Détection automatique de l'image EKO via Computer Vision
- Tracking stable même en conditions de lumière variables
- Feedback visuel HUD en temps réel

### Animations (6 danses)
| Danse | Description |
|-------|------------|
| 👋 SALUT | Salutation douce, balancement |
| 🕺 DISCO | Rotations rapides, disco fever |
| 🤸 HIPHOP | Sauts, mouvements saccadés |
| 🌊 WAVE | Ondulations robotiques |
| 💫 SPIN | Tourbillon continu |
| ⚡ BOUNCE | Rebonds énergiques |

### Effets Visuels (5 effets)
- Normal — rendu holographique standard
- Glitch — décalage chromatique glitch
- Chromatique — cycle de couleurs arc-en-ciel
- Pulsation — scaling pulsé
- Scan — lignes de scan animées

### Capture
- 📸 **Photo** avec compte à rebours 3-2-1 et watermark
- 🎥 **Vidéo** jusqu'à 30 secondes en WebM
- 🔗 **Partage** via Web Share API (mobile natif)

---

## 💡 Architecture Technique

```
Caméra → WebRTC → Video Element
                       ↓
              MindAR Image Tracker
                       ↓
              Détection features 2D
              Calcul pose (R|T)
                       ↓
              Three.js Anchor Group
                       ↓
         ┌─────────────┴─────────────┐
         Sprite Principal    Halos Additifs
         Frame Holographique Particules
         Ring Ground         Scan Lines
                       ↓
              WebGL Renderer
                       ↓
              Canvas Composite
              (video + 3D + HUD)
```

---

## 🚨 Dépannage

**"Erreur cible AR"** → Vérifier que `targets.mind` est bien dans le dossier  
**"Accès caméra refusé"** → Utiliser HTTPS, autoriser caméra dans le navigateur  
**"Mascotte ne s'affiche pas"** → Vérifier que `mascotte.png` est dans le dossier  
**Lag/performance** → Réduire la résolution ou utiliser un appareil plus récent
## Demonstration
Video disponible dans les Issues
