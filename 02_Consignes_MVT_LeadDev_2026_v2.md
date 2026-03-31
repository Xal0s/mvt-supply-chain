# 02_Consignes_MVT_LeadDev_2026_v2.md
## Consignes officielles — MVT + Podcast + Soutenance (LeadDev M1/M2I)

### Objectif (clair)
Vous ne me vendez pas une “tendance”. Vous **argumentez** une décision LeadDev **avec des preuves** :
- hypothèses **falsifiables**,
- **sources primaires**,
- protocole de validation (mesure/expérimentation/analyse) **explicite**,
- limites et contre-arguments **assumés**,
- recommandation finale **actionnable**.

> On oublie l’ancienne logique “proto + démo”. **Aucune démonstration logicielle n’est attendue**.  
> Si vous faites des expérimentations (bench, tests, comparatifs), elles doivent être **documentées** et **reproductibles** (annexe).

### IA (autorisé, mais tracé)
L’IA est **autorisée**. Le copier-coller déguisé, non.
- Vous devez fournir une **annexe IA** avec :
  - vos **prompts** (copiés-collés),
  - les extraits utiles,
  - ce que vous avez **gardé / jeté**,
  - et **pourquoi** (qualité, cohérence, contraintes, risques).
- Sans annexe IA : la démarche est considérée **non démontrée**.

---

## 1) Livrables & Dates
### A. Pack MVT + Podcast (obligatoire)
- **À rendre : 20/06/2026 23:59**
- Contenu :
  - `MVT.pdf` (export du mémoire)
  - le podcast (fichier(s) audio) + `show_notes.md`
  - l’annexe IA `ai/ai_usage.md`
  - le dépôt Git accessible (lien + structure propre)

### B. Soutenance orale (obligatoire)
- **Date : 01/07/2026**
- **Durée : 30 minutes minimum — 40 minutes maximum**
  - Recommandation : 25–30 min exposé + 5–10 min questions (selon dynamique).
- Support de présentation attendu (PDF ou PPTX).

---

## 2) Podcast : format et durée (raisonnable et équitable)
Objectif : confronter vos hypothèses au réel (terrain/recherche) et alimenter votre MVT.

### Format possible 1 — 1 épisode unique
- **Durée recommandée : 18 à 25 minutes**
- 1 invité minimum (pro/chercheur en lien direct).

### Format possible 2 — Mini-série (si plusieurs intervenants)
Pour ne pas pénaliser les groupes qui interviewent plusieurs personnes :
- **2 à 3 épisodes max**
- **Durée recommandée par épisode : 8 à 12 minutes**
- Total recommandé : **20 à 30 minutes max** (toutes pistes confondues)

### Livrables podcast
- Audio : `.mp3` (128–192 kbps)
- `show_notes.md` contenant :
  - titre + invité(s) + date + durée
  - 5 takeaways
  - 3 timestamps
  - 5 liens (dont au moins 2 sources primaires si possible)
  - “Ce que ça change dans H1/H2/H3” (3 phrases)

### Exploitation obligatoire dans le MVT
- 3 citations courtes max, **analysées** (pas de name-dropping).
- Les points issus du podcast doivent impacter au moins **une** de ces choses :
  - hypothèses,
  - protocole de validation,
  - risques/contre-arguments,
  - recommandation finale.

---

## 3) Structure obligatoire du mémoire (MVT)
### 3.1 Page 1 — Synthèse (MAX 1 page)
Contenu minimum :
- Problématique (1 paragraphe).
- 3 hypothèses (H1/H2/H3) + ce que vous cherchez à prouver.
- Résultat (validée / infirmée / incertaine) + justification courte.
- Recommandation finale (décision LeadDev) : “Je ferais X / je ne ferais pas Y, parce que…”.

### 3.2 Table Hypothèses (obligatoire)
| Hypothèse | Indicateur mesurable | Protocole de validation | Résultat | Niveau de confiance |
|---|---|---|---|---|

Règles :
- Hypothèse = testable = réfutable.
- “Niveau de confiance” justifié (biais, limites, portée).

### 3.3 Table Claims → Sources (obligatoire)
| Claim (affirmation) | Source primaire | Pourquoi crédible | Limites / biais |
|---|---|---|---|

Règles :
- “Source primaire” = paper, RFC/spec, doc officielle, repo officiel, standard, benchmark publié.
- Les secondaires sont autorisées **en appui**, jamais en base unique.

### 3.4 Contre-arguments (obligatoire)
- 3 objections sérieuses (pas des hommes de paille).
- Pour chaque objection :
  - réponse,
  - **ce qui vous ferait changer d’avis** (condition de falsification).

### 3.5 Conclusion opérationnelle
- Une décision (y compris “on ne déploie pas pour l’instant”).
- Un plan de suite : tests/prochaines étapes, risques à réduire, conditions de go/no-go.

---

## 4) Annexes de preuves (fortement recommandé)
Pas de démo imposée, mais vos preuves doivent être auditables.
Exemples acceptés :
- comparatifs chiffrés (perf/latence/coût/qualité),
- matrices de risques,
- tests de conformité,
- protocoles d’évaluation,
- retours terrain (podcast) + confrontation aux sources primaires.

Si vous fournissez du code/outillage de mesure :
- ajoutez une note “comment reproduire” (1 commande si possible).

---

## 5) Git : exigences minimales (traçabilité)
### 5.1 Commits
- Commits réguliers (pas 1 commit la veille).
- Messages lisibles.

### 5.2 Issues (minimum)
- Minimum : 10 issues par groupe (tâches, décisions, risques).
- Chaque issue a une conclusion (done / wontfix / blocked).

### 5.3 ADR (Architecture Decision Records) — courtes
- 1 décision = 1 ADR, **1 page max**.
- Minimum : 5 ADR.
- Format : Contexte / Décision / Alternatives / Conséquences.

### 5.4 Journal de veille (10 entrées datées)
Format imposé :
- Date
- Ce que j’ai lu (avec lien/source primaire)
- Ce que j’ai compris (résumé perso)
- Ce que ça change dans notre MVT (action/décision)

### 5.5 Annexe IA (obligatoire)
Fichier : `ai/ai_usage.md`
- Prompts (copiés-collés).
- Extraits utiles.
- **Décision** : gardé/jeté + pourquoi.
- Limites/risques : où l’IA peut vous induire en erreur.

---

## 6) Relecture pair-à-pair (obligatoire)
### Principe
Chaque groupe a un ou plusieurs “reviewers” (assignés). Les reviewers doivent faire des retours réguliers pour éviter le rendu “one shot”.

### Fréquence reviewers
- Les reviewers déposent des retours **tous les 15 du mois**, jusqu’au 01/07/2026 :
  - 15/02, 15/03, 15/04, 15/05, 15/06 (et éventuellement 15/07 si prolongation — non prévu ici)

### Fréquence PO (feedback intervenant)
- Feedback PO (moi) **15 jours avant** chaque journée de suivi :
  - **15/03/2026** (avant le 31/03)
  - **15/06/2026** (avant le 17/06)

### Format attendu d’une review (simple et utile)
À déposer dans le repo (ou dans le fichier de suivi prévu) :
- Résumé (5 lignes)
- 3 forces
- 3 problèmes bloquants (avec preuves)
- 5 suggestions actionnables (priorisées)
- Questions ouvertes (si besoin)
- “Risque principal si on rend comme ça”

---

## 7) Soutenance orale (01/07/2026) : attentes
- 30 à 40 minutes (respect strict).
- Slides : support, pas roman.
- Contenu attendu :
  - Problématique + contexte
  - Hypothèses + protocole
  - Ce que disent les sources primaires (et limites)
  - Ce que dit le podcast (et impact)
  - Contre-arguments + falsification
  - Décision LeadDev + plan de suite

---

## 8) Checkpoints (avec l’intervenant)
### 31/03/2026 — Checkpoint 1
À montrer :
- Sujet verrouillé + problématique.
- H1/H2/H3 formulées.
- 10 sources primaires shortlist.
- Plan podcast + contacts sollicités.
- Première version des tableaux (Hypothèses + Claims→Sources).

### 17/06/2026 — Checkpoint 2
À montrer :
- Podcast avancé (quasi final) + show notes.
- MVT quasi final + tableaux complets.
- Contre-arguments rédigés.
- Repo propre (issues, ADR, journal, annexe IA).
- Historique de reviews pair-à-pair à jour.

