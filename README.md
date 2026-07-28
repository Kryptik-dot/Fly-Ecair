# FlyECAir — Conception d'une app voyageurs pilotée par l'IA

Devoir : piloter un assistant IA (ChatGPT / Gemini) pour concevoir l'interface d'une application mobile voyageurs pour une compagnie aérienne, en documentant la démarche (analyse, prompts, itérations, choix).

**Compagnie choisie :** ECAir (Equatorial Congo Airlines), pour ancrer l'exercice dans une réalité congolaise concrète plutôt que sur un cas générique.

**Aperçu de l'interface :** [`index.html`](./index.html) — écran d'accueil de l'app, à ouvrir directement dans un navigateur ou via GitHub Pages (lien plus bas).

---

## 1. Analyse du métier

ECAir est une compagnie en reconstruction de confiance : plusieurs arrêts d'activité (2016, puis 2025) suivis de relances, la dernière en avril 2026. Le réseau actuel est volontairement restreint : Brazzaville, Pointe-Noire et Ollombo en domestique ; Douala, Yaoundé et Libreville en régional.

Trois contraintes locales structurent les choix de conception :

- **Connexion instable** → les informations critiques (billet, statut du vol) doivent rester accessibles même hors-ligne.
- **Usage mobile-first** → interface pensée pour un petit écran avant tout, pas d'adaptation d'un site desktop.
- **Paiement Mobile Money dominant** → la carte bancaire ne peut pas être le seul moyen de paiement mis en avant.

Contrairement à une grande compagnie internationale (Air France, etc.) qui doit gérer la complexité (alliances, multi-devises, programmes de fidélité), ECAir doit avant tout gérer la **simplicité et la confiance** : moins d'écrans, plus de clarté sur la fiabilité du vol.

## 2. Persona

**Diane**, voyageuse régulière entre Brazzaville et Pointe-Noire pour raisons professionnelles. Elle a connu les arrêts précédents d'ECAir et reste vigilante sur la fiabilité de ses réservations. Elle voyage avec son téléphone comme seul terminal, paie en Mobile Money, et a besoin de vérifier rapidement le statut de son vol avant de se déplacer.

## 3. Stratégie de prompts

Plutôt qu'un prompt unique et vague ("fais-moi une app de compagnie aérienne"), la démarche a été construite en prompts successifs et contextualisés :

1. **Prompt de cadrage** : poser le métier, le persona et les contraintes locales avant de demander le moindre écran.
2. **Prompt de structure** : demander un écran d'accueil précis avec une liste de blocs fonctionnels nommés (statut du vol, réservation, accès rapides, historique), plutôt que de laisser l'IA improviser une structure.
3. **Prompt d'intégration de marque** : une fois la structure validée, fournir les éléments de marque (logo, visuel, slogan) et demander leur intégration ciblée, écran par écran et bloc par bloc, en précisant explicitement ce qui ne doit pas changer (structure, responsive, fonctionnalités déjà en place) — pour éviter qu'un nouveau prompt ne régénère tout l'écran depuis zéro.

Cette structuration limite les résultats trop génériques et force l'IA à justifier chaque proposition par rapport au persona et au contexte ECAir, plutôt que de proposer un design d'app aérienne interchangeable.

## 4. Itérations

- **Itération 1** : premier écran d'accueil générique, structure validée (statut du vol, CTA réservation, accès rapides, historique).
- **Itération 2** : ajout d'un indicateur de connexion/synchronisation, pour répondre directement à la contrainte de réseau instable identifiée en phase d'analyse.
- **Itération 3** : intégration des éléments de marque (logo, couleurs, slogan "Votre vol à portée de clic") et mise en avant du Mobile Money sur le bouton de réservation.

## 5. Justification des choix UX/UI

- **Statut du vol en tête d'écran** : réponse directe à l'enjeu de confiance identifié en phase d'analyse — l'utilisateur voit en un coup d'œil que son vol est confirmé.
- **Bannière de connexion visible** : rend explicite l'état de synchronisation des données, pertinent pour un contexte réseau parfois instable.
- **CTA de réservation en carte distincte et contrastée** : action principale isolée visuellement des informations de consultation, pour guider l'utilisateur mobile sans surcharge cognitive.
- **Accès rapides en grille d'icônes** : les actions fréquentes (enregistrement, statut, bagages, aide) restent accessibles en un tap depuis l'accueil, sans navigation profonde.
- **État vide explicite sur l'historique** : plutôt qu'un écran vide silencieux, un message qui explique la situation et invite à l'action, cohérent avec une compagnie qui reconstruit sa relation client.
- **Mobile Money mis en avant sur le bouton de réservation** : aligné sur les usages de paiement réels du marché congolais, plutôt qu'un focus carte bancaire par défaut.

## 6. Version finale

La version retenue est celle intégrant les éléments de marque ECAir (logo, couleurs bleu/or, slogan) tout en conservant la structure validée en itération 2 — jugée la plus cohérente avec le contexte de relance de confiance de la compagnie et les contraintes d'usage local (réseau, mobile-first, Mobile Money).

---

## Aperçu en ligne

Une fois ce dépôt publié sur GitHub avec GitHub Pages activé (Settings → Pages → Branch `main` → dossier `/root`), l'interface sera consultable à l'adresse :

```
https://<ton-nom-utilisateur>.github.io/<nom-du-repo>/
```

## Structure du dépôt

```
.
├── index.html   # Mockup de l'écran d'accueil FlyECAir
└── README.md    # Ce document
```
