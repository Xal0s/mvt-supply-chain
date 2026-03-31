## Sujet — Sécurité supply chain : SBOM, SLSA, signature, provenance
### Angle LeadDev
Après un “npm install”, comment éviter la compromission bête et méchante ?
### Questions possibles
- Protocole minimal réaliste (SBOM + signature + policy) ?
- ROI : temps, incidents évités, conformité.
- Comment mesurer une réduction de risque ?
### Interview
- RSSI, AppSec, DevSecOps, CERT interne/prestataire.
### Sources primaires
- SLSA, Sigstore, CycloneDX/SPDX, docs officielles, advisories.

---

Problématique : 
- En quoi les outils et protocoles émergents permettent-ils de garantir l'intégrité et la traçabilité des dépendances logicielles dans les pipelines CI/CD sans dégrader la vélocité des équipes ?
- Comment automatiser la vérification de l'intégrité et de la provenance des dépendances sans bloquer la vélocité des cycles de déploiement (CI/CD) ?

Hypothese :
- [Parler SBOM (cyclone dx) + outils (dtrack)] 	Générer un SBOM (CycloneDX) + scanner avec DTrack n'ajoute pas plus de 2 min à un pipeline standard
- [SLSA (Exemple de Trivy piratage) + Sigstore/Cosign]	Sigstore/Cosign permet de détecter une image Docker altérée avant le déploiement, sans configuration manuelle par image 
- [depot local (Artifactory)] Un dépôt local (Artifactory) réduit la surface d'attaque supply chain sans dégrader les temps de build
- docker hardened image

Source :
- https://www.redhat.com/fr/topics/security/what-is-software-supply-chain-security
- https://blog.stephane-robert.info/
- https://slsa.dev/
- https://about.gitlab.com/blog/the-ultimate-guide-to-sboms/
- https://dependencytrack.org/
- https://cheatsheetseries.owasp.org/cheatsheets/Software_Supply_Chain_Security_Cheat_Sheet.html
- https://jfrog.com/fr/artifactory/#:~:text=Qu'est%2Dce%20qu'Artifactory&text=Artifactory%20sert%20de%20plaque%20tournante,sur%20vos%20processus%20de%20d%C3%A9veloppement.
- https://cyclonedx.org/
- https://trivy.dev/docs/latest/guide/
- https://www.sigstore.dev/
- https://www.cve.org/
- https://owasp.org/www-chapter-sofia/assets/presentations/202505%20-%20Scoring%20Vulnerabilities%20using%20CVSS%20by%20Martin%20Georgiev.pdf
- https://blog.stephane-robert.info/post/trivy-depot-github-vide/
- https://securitylabs.datadoghq.com/articles/shai-hulud-2.0-npm-worm/
- https://www.ibm.com/fr-fr/think/topics/log4j

Contact : 
- secret manager
- Stephane Robert : https://www.linkedin.com/in/stephanerobert1/