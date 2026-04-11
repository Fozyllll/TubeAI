# 🎬 TubeAI — YouTube Intelligence

![Version](https://img.shields.io/badge/Version-5.0-red?style=flat-square)
![Groq AI](https://img.shields.io/badge/Groq%20AI-LLaMA%203.3-orange?style=flat-square)
![YouTube API](https://img.shields.io/badge/YouTube%20API-v3-red?style=flat-square)
![No Backend](https://img.shields.io/badge/No%20Backend-100%25%20Client--Side-blue?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)

**TubeAI** est une application web 100% client-side qui analyse n'importe quelle chaîne YouTube, génère des conseils IA personnalisés, compare des chaînes et optimise ton contenu — propulsée par **Groq AI (LLaMA 3.3 70B, gratuit)**.

---

## ✨ Fonctionnalités

### 📊 Analyse complète de chaîne
- Tous les formats d'URL : `@handle`, `/channel/UC...`, `/c/...`, nom direct
- **Score de chaîne /100** basé sur l'engagement, la cohérence et la croissance
- Statistiques : abonnés, vues totales, vues moyennes/vidéo, taux d'engagement
- Badges de performance (Excellent / Moyen / Faible)
- 15 dernières vidéos avec taux d'engagement individuel et lien cliquable
- Détection automatique Shorts vs vidéos longues
- Historique des 6 dernières chaînes analysées

### 📈 Graphiques interactifs
- 4 graphiques : Vues, Likes, Commentaires, Taux d'engagement
- Labels avec titre tronqué des vidéos
- Tooltip riche : titre complet, date de publication + métriques croisées
- Barre maximale mise en évidence automatiquement
- **S'adapte automatiquement au thème clair/sombre**

### 🔍 Analyse SEO par vidéo *(NOUVEAU)*
- Score SEO lettre (A/B/C/D) pour chaque vidéo
- Vérification : longueur du titre, description, nombre de tags, qualité de miniature, engagement
- Indicateurs visuels vert/jaune/rouge par critère
- Actionnable : chaque problème est expliqué avec la correction à apporter

### 🤖 Conseils IA personnalisés
- Analyse structurée : résumé, points forts, axes d'amélioration, stratégie, priorité #1
- Basé sur tes vraies données YouTube

### 💡 Idées de vidéos générées par l'IA
- 9 idées personnalisées selon ta niche et tes dernières vidéos
- Types variés : Long, Short, Série, Tuto, Challenge, Vlog, Analyse, Réaction, Tendance
- Bouton **Copier** le titre
- Bouton **Développer** → envoie l'idée au Chat IA avec demande de plan détaillé

### ⚖️ Comparaison de deux chaînes *(NOUVEAU)*
- Entre deux URLs ou handles, compare côte à côte
- Tableau comparatif : abonnés, vues, vidéos, vues moy/vidéo, engagement, score global
- Barres de progression visuelles
- Badge "Meilleur score" pour le gagnant
- Conclusion automatique par l'app

### 🔔 Alertes de performance *(NOUVEAU)*
- Générées automatiquement après chaque analyse
- Détecte : vidéo qui surperforme, sous-performance, excellent engagement global, manque de Shorts, ratio Shorts/longs déséquilibré
- Alertes persistantes (localStorage) avec compteur dans le header
- Possibilité d'ignorer chaque alerte individuellement ou tout effacer

### 📄 Export PDF *(NOUVEAU)*
- Exporte un rapport complet en HTML (imprimable en PDF via Ctrl+P)
- Contient : infos chaîne, score, stats, analyse IA complète, liste des vidéos
- Nom de fichier automatique avec nom de la chaîne et date

### 💬 Chat IA contextuel
- Conversation avec Groq AI (LLaMA 3.3 70B)
- Contexte automatique si une chaîne a été analysée
- Historique de 12 messages
- Suggestions rapides cliquables
- Le bouton "Développer" des idées envoie directement ici

### ✍️ Générateur de titres & hashtags
- 3 titres optimisés CTR + score CTR /10
- 15 hashtags pour les Shorts
- Explication psychologique
- Multilingue : FR / EN / ES / PT

### 🌙 Mode sombre / clair *(NOUVEAU)*
- Bouton en haut à droite pour basculer
- Préférence sauvegardée dans le navigateur
- Graphiques, couleurs et fonds s'adaptent automatiquement

---

## 🚀 Utilisation

### GitHub Pages
👉 **[fozylll.github.io/YouTubeAnalyzer](https://fozylll.github.io/YouTubeAnalyzer)**

### En local
```bash
git clone https://github.com/fozylll/YouTubeAnalyzer.git
cd YouTubeAnalyzer
# Ouvrir index.html dans le navigateur
python3 -m http.server 8080   # ou double-clic sur index.html
```

---

## 🔑 Configuration des clés API

Au premier lancement, la fenêtre de configuration s'ouvre automatiquement.
Les clés sont sauvegardées dans `localStorage` — **tu n'as à les entrer qu'une seule fois**.

Le bouton **Config** devient vert 🟢 quand les deux clés sont configurées.

### 1. Clé YouTube Data v3 — Gratuit
1. [Google Cloud Console](https://console.cloud.google.com/) → Bibliothèque → Active **YouTube Data API v3**
2. Identifiants → Créer une **Clé API**
3. (Recommandé) Restreins-la à ton domaine GitHub Pages

> Quota gratuit : 10 000 unités/jour. Une analyse complète ≈ 20 unités.

### 2. Clé Groq AI — 100% Gratuit
1. [console.groq.com](https://console.groq.com) → API Keys → Create API Key
2. Clé commence par `gsk_...`

> Modèle : `llama-3.3-70b-versatile` · Quota : ~6000 tokens/min, sans limite journalière stricte.

> 🔒 Tes clés restent dans ton navigateur. Elles ne transitent jamais par un serveur tiers.

---

## 🏗️ Structure du projet

```
YouTubeAnalyzer/
├── index.html      # Application complète (HTML + CSS + JS en un seul fichier)
└── README.md       # Ce fichier
```

---

## 🛠️ Stack technique

| Technologie | Usage |
|-------------|-------|
| HTML / CSS / JS vanilla | Zéro dépendance, zéro build |
| [YouTube Data API v3](https://developers.google.com/youtube/v3) | Stats chaîne, vidéos, playlists |
| [Groq API](https://console.groq.com) — LLaMA 3.3 70B | Conseils IA, idées, titres, chat |
| [Chart.js 4.4](https://www.chartjs.org/) | Graphiques interactifs (CDN) |
| Google Fonts — Syne + Instrument Sans + DM Mono | Typographie |

---

## ⚙️ Fonctionnement technique

### Score de chaîne /100
Calculé localement : ratio vues/abonnés, taux d'engagement moyen, nombre de vidéos, taille de la communauté.

### Score SEO par vidéo
Vérifie : longueur du titre (idéal 40-70 car.), longueur de description (min 150 car.), nombre de tags (min 5), qualité de miniature, taux d'engagement. Grade de A à D.

### Alertes de performance
Détectées automatiquement après chaque analyse : vidéo qui surperforme (+80% au-dessus de la moyenne), sous-performance (<0.5% engagement), absence de Shorts, déséquilibre Shorts/longs, engagement exceptionnel ou faible global.

### Export PDF
Génère un fichier HTML complet contenant le rapport. L'utilisateur peut l'imprimer en PDF via le menu d'impression du navigateur (Ctrl+P → Enregistrer en PDF).

### Détection des Shorts
Durée ISO 8601 < 2 minutes.

---

## 📋 Limitations

- **Vidéos privées** : non accessibles via l'API publique YouTube
- **Quota YouTube** : 10 000 unités/jour — suffisant pour ~400 analyses
- **Quota Groq** : 6000 tokens/minute, largement suffisant pour un usage normal
- **SEO Tags** : les tags ne sont visibles via l'API que pour les vidéos de ta propre chaîne (ou si publics)

---

## 📄 Licence

MIT — Utilise, modifie, distribue librement.

---

*Fait avec ❤️ — Propulsé par Groq AI (LLaMA 3.3) × YouTube Data API v3*
