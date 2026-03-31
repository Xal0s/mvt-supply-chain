# MVT - Synthèse

## Problématique : 

Les équipes de développement modernes s'appuient enormement sur des dépendances open source : un projet Node.js ou Python peut en embarquer plusieurs centaines, chacune maintenue par des tiers dont la chaîne de publication n'est ni vérifiée ni maîtrisée. Cette réalité crée des failles discrètes, illustrée par des incidents comme la compromission de xz-utils en 2024 ou l'attaque SolarWinds, où c'est le processus de build lui-même, et non le code métier, qui a été l'objet de la compromission. Face à ce risque, un ensemble d'outils et de protocoles émergents propose de rétablir la confiance dans les supply-chain : génération de SBOM pour inventorier les composants, frameworks comme SLSA pour certifier la provenance des artefacts, ou encore signature cryptographique avec Sigstore pour garantir l'intégrité de ce qui est déployé. Pourtant, leur adoption reste marginale dans les équipes produit, souvent freinée par la crainte d'alourdir les pipelines CI/CD et de sacrifier la vélocité sur l'autel de la sécurité. 
>*En quoi ces outils et protocoles permettent-ils de garantir l'intégrité et la traçabilité des dépendances logicielles dans les pipelines CI/CD, sans dégrader la vélocité des équipes ?*

## hypothèse :

| Hypothèse | Indicateur mesurable |
|---|---|
| Intégrer la génération d'un SBOM (CycloneDX) et son analyse via DependencyTrack dans un pipeline CI/CD permet de détecter des vulnérabilités connues sur les dépendances, sans dépasser 2 minutes de surcoût d'exécution. | delta temps pipeline (sec) + nombre de CVE identifiées par DTrack | 
| Signer et vérifier les images Docker avec Sigstore/Cosign permet de bloquer automatiquement le déploiement d'une image compromise ou non autorisée, sans configuration manuelle par image. | détection effective d'une image altérée (hash modifié) + temps de mise en place initiale | 
| Proxifier les dépendances via Artifactory réduit l'exposition aux attaques supply chain (dependency confusion, typosquatting) sans dégrader les temps de build par rapport à une résolution directe depuis internet. | nombre de dépendances exposées à des registres publics non contrôlés |  
| Remplacer une image Docker standard par une image durcies (distroless ou CIS-hardened) réduit significativement le nombre de CVE détectées au scan Trivy, sans alourdir le pipeline ni la maintenance des Dockerfiles. | nombre de CVE image standard vs image durcies + complexité diff Dockerfile | 


## Claims

| Claim (affirmation) | Source primaire | Pourquoi crédible | Limites / biais |
|---|---|---|---|
|*Un projet Node.js/Python peut embarquer plusieurs centaines de dépendances tierces* | https://www.sonatype.com/state-of-the-software-supply-chain/2024/optimization | Rapport annuel basé sur l'analyse de plus de 7 millions de projets open source et 1,5 trillion de requêtes Maven Central | Source provenant d'un editeur, peut être biaisé pour vendre son produit |
|*la compromission de xz-utils*| https://www.openwall.com/lists/oss-security/2024/03/29/4 | Freund est le découvreur de la faille, le rapport est la source de première main reprise par tous les médias | Analyse technique d'un seul individu, non auditée par un tiers à l'origine. Validée ensuite par la communauté |
|*L'attaque SolarWinds ciblait le processus de build* | https://www.cisa.gov/news-events/cybersecurity-advisories/aa20-352a | Publication officielle de la CISA (agence gouvernementale US de cybersécurité), co-signée FBI et NSA | document US-centré, mais largement documenté independement |