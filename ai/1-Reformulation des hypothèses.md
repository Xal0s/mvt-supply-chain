# Reformulation des hypothèses

### Prompt envoyé
```
Poux tu reformuler nos hypothèses :

| Hypothèse | Indicateur mesurable | Protocole de validation | Résultat | Niveau de confiance |
|---|---|---|---|---|
| [SBOM (CycloneDX) + DependencyTrack] Générer un SBOM (CycloneDX) et le scanner avec DependencyTrack n'ajoute pas plus de 2 minutes à un pipeline standard | | | | |
| [SLSA + Sigstore/Cosign] Sigstore/Cosign permet de détecter une image Docker altérée avant le déploiement, sans configuration manuelle par image | | | | |
| [Dépôt local Artifactory] Un dépôt local (Artifactory) réduit la surface d'attaque supply chain sans dégrader les temps de build | | | | |
| [Docker Hardened Images] Utiliser des images Docker durcies réduit significativement le nombre de CVE détectées | | | | |
```

### Réponse obtenue (extrait utile)
```
H1 — SBOM + DependencyTrack
Intégrer la génération d'un SBOM (CycloneDX) et son analyse via DependencyTrack
dans un pipeline CI/CD permet de détecter des vulnérabilités connues sur les
dépendances, sans dépasser 2 minutes de surcoût d'exécution.
Indicateur : delta temps pipeline + nombre de CVE identifiées par DTrack.

H2 — Sigstore/Cosign
Signer et vérifier les images Docker avec Sigstore/Cosign permet de bloquer
automatiquement le déploiement d'une image compromise ou non autorisée,
sans configuration manuelle par image.
Indicateur : détection effective d'une image altérée (hash modifié) + temps de mise en place initiale.

H3 — Dépôt local Artifactory
Proxifier les dépendances via Artifactory réduit l'exposition aux attaques supply chain
(dependency confusion, typosquatting) sans dégrader les temps de build par rapport
à une résolution directe depuis internet.
Indicateur : nombre de dépendances exposées à des registres publics non contrôlés + delta temps de build.

H4 — Docker Hardened Images
Remplacer une image Docker standard par une image durcies (distroless ou CIS-hardened)
réduit significativement le nombre de CVE détectées au scan Trivy, sans alourdir
le pipeline ni la maintenance des Dockerfiles.
Indicateur : nombre de CVE (Trivy) image standard vs image durcies + complexité diff Dockerfile + temps de build.
```

### Ce qu'on a gardé
- Les 4 hypothèses et leurs indicateurs

### Ce qu'on a jeté
- L'indicateur de temps pour H3 : pas pertinent

### Pourquoi
On a gardé les 4 hypothèses séparées car chacune couvre un mécanisme différent.

### Limites / risques identifiés
- L'IA a d'abord voulu fusionner SBOM et Sigstore/Cosign en une seule hypothèse
- Certains indicateurs proposés étaient à retravailler