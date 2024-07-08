
# CVE Report

08/07/2024
## Rapport sur les CVE pour le Cluster de Production

### Aperçu 
Ce rapport fournit une liste détaillée des vulnérabilités et expositions communes (CVE) présentes dans le cluster de production. Chaque entrée inclut l'identifiant CVE, l'application affectée, et les bibliothèques ou composants associés. Le rapport démontre que toutes les CVE répertoriées sont dues à des mises à jour non publiées par leurs mainteneurs respectifs. Nous utilisons un outil appelé Renovate pour être notifiés des mises à jour de composants disponibles sur notre cluster, garantissant que nous exécutons toujours la dernière version mise à disposition par le mainteneur.

### Métriques de Sévérité
| Type de CVE  | Nombre | Pourcentage du total |
|--------------|--------|----------------------|
| CVE Critiques | 7 | 5.0% |
| CVE Élevées  | 37 | 26.4% |
| CVE Moyennes  | 96 | 68.6% |
| CVE Basses  | 0 | 0.0% |
| CVE Inconnues  | 0 | 0.0% |

> **Note:** Le reste du rapport se concentre uniquement sur les CVE critiques et élevées afin de donner la priorité aux vulnérabilités qui présentent le plus grand risque pour la sécurité du système.

### Métriques Spécifiques aux Applications
| Application | CVE Critiques | CVE Élevées | CVE Moyennes | CVE Basses | Total CVE |
|-------------|---------------|-------------|--------------|-----------|-----------|
| velero | 4 | 16 | 31 | 0 | 51 |
| rabbitmq | 0 | 6 | 12 | 0 | 18 |
| trivy | 1 | 1 | 13 | 0 | 15 |
| keycloak | 0 | 4 | 10 | 0 | 14 |
| postgresql | 0 | 4 | 10 | 0 | 14 |
| amazon-cloudwatch | 0 | 6 | 6 | 0 | 12 |
| backend-ddf | 0 | 0 | 4 | 0 | 4 |
| kube-prometheus-stack | 1 | 0 | 3 | 0 | 4 |
| kyverno | 0 | 0 | 4 | 0 | 4 |
| policy-reporter | 1 | 0 | 2 | 0 | 3 |
| gitlab-agent | 0 | 0 | 1 | 0 | 1 |
| kube-system | 0 | 0 | 0 | 0 | 0 |

### Métriques Spécifiques aux Bibliothèques
| Bibliothèque | Applications Affectées | Total CVE |
|--------------|-----------------------|-----------|
| stdlib | kube-prometheus-stack, gitlab-agent, velero, kyverno, policy-reporter, trivy | 6 |
| libssl3 | postgresql, rabbitmq, backend-ddf, trivy, keycloak | 5 |
| libgnutls30 | postgresql, rabbitmq, keycloak | 3 |
| libsystemd0 | postgresql, rabbitmq, keycloak | 3 |
| libudev1 | postgresql, rabbitmq, keycloak | 3 |
| openssl | postgresql, rabbitmq, keycloak | 3 |
| github.com/Azure/azure-sdk-for-go/sdk/azidentity | kube-prometheus-stack, kyverno, trivy | 3 |
| curl | rabbitmq, amazon-cloudwatch | 2 |
| libcrypto3 | backend-ddf, trivy | 2 |
| golang.org/x/net | velero, kyverno | 2 |
| glibc | amazon-cloudwatch | 1 |
| glibc-common | amazon-cloudwatch | 1 |
| glibc-langpack-en | amazon-cloudwatch | 1 |
| glibc-minimal-langpack | amazon-cloudwatch | 1 |
| libcrypt | amazon-cloudwatch | 1 |
| libcurl | amazon-cloudwatch | 1 |
| libnghttp2 | amazon-cloudwatch | 1 |
| openssl11-devel | amazon-cloudwatch | 1 |
| openssl11-libs | amazon-cloudwatch | 1 |
| github.com/hashicorp/go-retryablehttp | kyverno | 1 |
| libcurl4 | rabbitmq | 1 |
| busybox | trivy | 1 |
| busybox-binsh | trivy | 1 |
| ssl_client | trivy | 1 |
| github.com/hashicorp/go-getter | trivy | 1 |
| google.golang.org/grpc | velero | 1 |
| google.golang.org/protobuf | velero | 1 |

### Observations Clés
* velero est l'application la plus affectée avec un total de 51 CVE.
* rabbitmq a également un nombre significatif de CVE (18).
* trivy a également un nombre significatif de CVE (15).
* La majorité des CVE sont classées comme étant de haute gravité (26%), avec seulement une petite fraction étant critiques (5%).
* La bibliothèque stdlib est récurrente à travers plusieurs CVE et applications (kube-prometheus-stack, gitlab-agent, velero, kyverno, policy-reporter, trivy), indiquant des vulnérabilités communes dans cette bibliothèque.
* La bibliothèque libssl3 est récurrente à travers plusieurs CVE et applications (postgresql, rabbitmq, backend-ddf, trivy, keycloak), indiquant des vulnérabilités communes dans cette bibliothèque.
* La bibliothèque libgnutls30 est récurrente à travers plusieurs CVE et applications (postgresql, rabbitmq, keycloak), indiquant des vulnérabilités communes dans cette bibliothèque.

## Liste Détaillée des CVE
### Sommaire

| CVE ID | Applications |
|--------|--------------|
| [CVE-2024-24790](#cve-2024-24790) | kube-prometheus-stack, policy-reporter, trivy, velero |
| [CVE-2023-24540](#cve-2023-24540) | velero |
| [CVE-2024-2961](#cve-2024-2961) | amazon-cloudwatch |
| [CVE-2023-29403](#cve-2023-29403) | velero |
| [CVE-2024-6257](#cve-2024-6257) | trivy |
| [CVE-2023-50387](#cve-2023-50387) | keycloak, postgresql, rabbitmq |
| [CVE-2023-50868](#cve-2023-50868) | keycloak, postgresql, rabbitmq |
| [CVE-2024-2398](#cve-2024-2398) | rabbitmq |
| [CVE-2023-39325](#cve-2023-39325) | velero |
| [CVE-2023-45283](#cve-2023-45283) | velero |
| [CVE-2023-45287](#cve-2023-45287) | velero |
| [CVE-2023-45288](#cve-2023-45288) | velero |
| [GHSA-m425-mq94-257g](#ghsa-m425-mq94-257g) | velero |
| [CVE-2023-24539](#cve-2023-24539) | velero |
| [CVE-2023-29400](#cve-2023-29400) | velero |
| [CVE-2024-28182](#cve-2024-28182) | amazon-cloudwatch |

### CVE Critiques
#### CVE-2024-24790
**Gravité:** CRITICAL (9.8)
**Applications Affectées:** kube-prometheus-stack
**Details:**
- stdlib (Versions: 1.22.3)
- Titre: golang: net/netip: Unexpected behavior from Is methods for IPv4-mapped IPv6 addresses
- Date de publication: 2024-06-05T16:15:10Z
- Dernière modification: 2024-06-18T17:59:12Z
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24790
#### CVE-2024-24790
**Gravité:** CRITICAL (9.8)
**Applications Affectées:** policy-reporter
**Details:**
- stdlib (Versions: 1.22.3)
- Titre: golang: net/netip: Unexpected behavior from Is methods for IPv4-mapped IPv6 addresses
- Date de publication: 2024-06-05T16:15:10Z
- Dernière modification: 2024-06-18T17:59:12Z
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24790
#### CVE-2024-24790
**Gravité:** CRITICAL (9.8)
**Applications Affectées:** trivy
**Details:**
- stdlib (Versions: 1.22.3)
- Titre: golang: net/netip: Unexpected behavior from Is methods for IPv4-mapped IPv6 addresses
- Date de publication: 2024-06-05T16:15:10Z
- Dernière modification: 2024-06-18T17:59:12Z
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24790
#### CVE-2023-24540
**Gravité:** CRITICAL (9.8)
**Applications Affectées:** velero
**Details:**
- stdlib (Versions: 1.19.8)
- Titre: golang: html/template: improper handling of JavaScript whitespace
- Date de publication: 2023-05-11T16:15:09Z
- Dernière modification: 2023-11-07T04:08:32Z
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-24540
#### CVE-2024-24790
**Gravité:** CRITICAL (9.8)
**Applications Affectées:** velero
**Details:**
- stdlib (Versions: 1.19.8)
- Titre: golang: net/netip: Unexpected behavior from Is methods for IPv4-mapped IPv6 addresses
- Date de publication: 2024-06-05T16:15:10Z
- Dernière modification: 2024-06-18T17:59:12Z
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24790
#### CVE-2023-24540
**Gravité:** CRITICAL (9.8)
**Applications Affectées:** velero
**Details:**
- stdlib (Versions: 1.19.8)
- Titre: golang: html/template: improper handling of JavaScript whitespace
- Date de publication: 2023-05-11T16:15:09Z
- Dernière modification: 2023-11-07T04:08:32Z
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-24540
#### CVE-2024-24790
**Gravité:** CRITICAL (9.8)
**Applications Affectées:** velero
**Details:**
- stdlib (Versions: 1.19.8)
- Titre: golang: net/netip: Unexpected behavior from Is methods for IPv4-mapped IPv6 addresses
- Date de publication: 2024-06-05T16:15:10Z
- Dernière modification: 2024-06-18T17:59:12Z
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24790

### CVE Élevées
#### CVE-2024-2961
**Gravité:** HIGH (8.8)
**Applications Affectées:** amazon-cloudwatch
**Details:**
- glibc (Versions: 2.26-63.amzn2.0.1)
- Titre: glibc: Out of bounds write in iconv may lead to remote code execution
- Date de publication: 2024-04-17T18:15:15Z
- Dernière modification: 2024-07-03T01:53:40Z
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-2961
#### CVE-2024-2961
**Gravité:** HIGH (8.8)
**Applications Affectées:** amazon-cloudwatch
**Details:**
- glibc-common (Versions: 2.26-63.amzn2.0.1)
- Titre: glibc: Out of bounds write in iconv may lead to remote code execution
- Date de publication: 2024-04-17T18:15:15Z
- Dernière modification: 2024-07-03T01:53:40Z
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-2961
#### CVE-2024-2961
**Gravité:** HIGH (8.8)
**Applications Affectées:** amazon-cloudwatch
**Details:**
- glibc-langpack-en (Versions: 2.26-63.amzn2.0.1)
- Titre: glibc: Out of bounds write in iconv may lead to remote code execution
- Date de publication: 2024-04-17T18:15:15Z
- Dernière modification: 2024-07-03T01:53:40Z
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-2961
#### CVE-2024-2961
**Gravité:** HIGH (8.8)
**Applications Affectées:** amazon-cloudwatch
**Details:**
- glibc-minimal-langpack (Versions: 2.26-63.amzn2.0.1)
- Titre: glibc: Out of bounds write in iconv may lead to remote code execution
- Date de publication: 2024-04-17T18:15:15Z
- Dernière modification: 2024-07-03T01:53:40Z
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-2961
#### CVE-2024-2961
**Gravité:** HIGH (8.8)
**Applications Affectées:** amazon-cloudwatch
**Details:**
- libcrypt (Versions: 2.26-63.amzn2.0.1)
- Titre: glibc: Out of bounds write in iconv may lead to remote code execution
- Date de publication: 2024-04-17T18:15:15Z
- Dernière modification: 2024-07-03T01:53:40Z
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-2961
#### CVE-2023-29403
**Gravité:** HIGH (7.8)
**Applications Affectées:** velero
**Details:**
- stdlib (Versions: 1.19.8)
- Titre: golang: runtime: unexpected behavior of setuid/setgid binaries
- Date de publication: 2023-06-08T21:15:16Z
- Dernière modification: 2023-11-25T11:15:14Z
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-29403
#### CVE-2023-29403
**Gravité:** HIGH (7.8)
**Applications Affectées:** velero
**Details:**
- stdlib (Versions: 1.19.8)
- Titre: golang: runtime: unexpected behavior of setuid/setgid binaries
- Date de publication: 2023-06-08T21:15:16Z
- Dernière modification: 2023-11-25T11:15:14Z
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-29403
#### CVE-2024-6257
**Gravité:** HIGH (7.7)
**Applications Affectées:** trivy
**Details:**
- github.com/hashicorp/go-getter (Versions: v1.7.4)
- Titre: hashicorp/go-getter: Arbitrary command execution through local git config file
- Date de publication: 2024-06-25T17:15:10Z
- Dernière modification: 2024-06-25T18:50:42Z
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-6257
#### CVE-2023-50387
**Gravité:** HIGH (7.5)
**Applications Affectées:** keycloak
**Details:**
- libsystemd0 (Versions: 252.22-1~deb12u1)
- Titre: bind9: KeyTrap - Extreme CPU consumption in DNSSEC validator
- Date de publication: 2024-02-14T16:15:45Z
- Dernière modification: 2024-06-10T17:16:15Z
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-50387
#### CVE-2023-50868
**Gravité:** HIGH (7.5)
**Applications Affectées:** keycloak
**Details:**
- libsystemd0 (Versions: 252.22-1~deb12u1)
- Titre: bind9: Preparing an NSEC3 closest encloser proof can exhaust CPU resources
- Date de publication: 2024-02-14T16:15:45Z
- Dernière modification: 2024-06-10T17:16:16Z
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-50868
#### CVE-2023-50387
**Gravité:** HIGH (7.5)
**Applications Affectées:** keycloak
**Details:**
- libudev1 (Versions: 252.22-1~deb12u1)
- Titre: bind9: KeyTrap - Extreme CPU consumption in DNSSEC validator
- Date de publication: 2024-02-14T16:15:45Z
- Dernière modification: 2024-06-10T17:16:15Z
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-50387
#### CVE-2023-50868
**Gravité:** HIGH (7.5)
**Applications Affectées:** keycloak
**Details:**
- libudev1 (Versions: 252.22-1~deb12u1)
- Titre: bind9: Preparing an NSEC3 closest encloser proof can exhaust CPU resources
- Date de publication: 2024-02-14T16:15:45Z
- Dernière modification: 2024-06-10T17:16:16Z
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-50868
#### CVE-2023-50387
**Gravité:** HIGH (7.5)
**Applications Affectées:** postgresql
**Details:**
- libsystemd0 (Versions: 252.22-1~deb12u1)
- Titre: bind9: KeyTrap - Extreme CPU consumption in DNSSEC validator
- Date de publication: 2024-02-14T16:15:45Z
- Dernière modification: 2024-06-10T17:16:15Z
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-50387
#### CVE-2023-50868
**Gravité:** HIGH (7.5)
**Applications Affectées:** postgresql
**Details:**
- libsystemd0 (Versions: 252.22-1~deb12u1)
- Titre: bind9: Preparing an NSEC3 closest encloser proof can exhaust CPU resources
- Date de publication: 2024-02-14T16:15:45Z
- Dernière modification: 2024-06-10T17:16:16Z
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-50868
#### CVE-2023-50387
**Gravité:** HIGH (7.5)
**Applications Affectées:** postgresql
**Details:**
- libudev1 (Versions: 252.22-1~deb12u1)
- Titre: bind9: KeyTrap - Extreme CPU consumption in DNSSEC validator
- Date de publication: 2024-02-14T16:15:45Z
- Dernière modification: 2024-06-10T17:16:15Z
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-50387
#### CVE-2023-50868
**Gravité:** HIGH (7.5)
**Applications Affectées:** postgresql
**Details:**
- libudev1 (Versions: 252.22-1~deb12u1)
- Titre: bind9: Preparing an NSEC3 closest encloser proof can exhaust CPU resources
- Date de publication: 2024-02-14T16:15:45Z
- Dernière modification: 2024-06-10T17:16:16Z
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-50868
#### CVE-2024-2398
**Gravité:** HIGH (7.5)
**Applications Affectées:** rabbitmq
**Details:**
- curl (Versions: 7.88.1-10+deb12u5)
- Titre: curl: HTTP/2 push headers memory-leak
- Date de publication: 2024-03-27T08:15:41Z
- Dernière modification: 2024-07-03T01:53:12Z
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-2398
#### CVE-2024-2398
**Gravité:** HIGH (7.5)
**Applications Affectées:** rabbitmq
**Details:**
- libcurl4 (Versions: 7.88.1-10+deb12u5)
- Titre: curl: HTTP/2 push headers memory-leak
- Date de publication: 2024-03-27T08:15:41Z
- Dernière modification: 2024-07-03T01:53:12Z
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-2398
#### CVE-2023-50387
**Gravité:** HIGH (7.5)
**Applications Affectées:** rabbitmq
**Details:**
- libsystemd0 (Versions: 252.22-1~deb12u1)
- Titre: bind9: KeyTrap - Extreme CPU consumption in DNSSEC validator
- Date de publication: 2024-02-14T16:15:45Z
- Dernière modification: 2024-06-10T17:16:15Z
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-50387
#### CVE-2023-50868
**Gravité:** HIGH (7.5)
**Applications Affectées:** rabbitmq
**Details:**
- libsystemd0 (Versions: 252.22-1~deb12u1)
- Titre: bind9: Preparing an NSEC3 closest encloser proof can exhaust CPU resources
- Date de publication: 2024-02-14T16:15:45Z
- Dernière modification: 2024-06-10T17:16:16Z
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-50868
#### CVE-2023-50387
**Gravité:** HIGH (7.5)
**Applications Affectées:** rabbitmq
**Details:**
- libudev1 (Versions: 252.22-1~deb12u1)
- Titre: bind9: KeyTrap - Extreme CPU consumption in DNSSEC validator
- Date de publication: 2024-02-14T16:15:45Z
- Dernière modification: 2024-06-10T17:16:15Z
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-50387
#### CVE-2023-50868
**Gravité:** HIGH (7.5)
**Applications Affectées:** rabbitmq
**Details:**
- libudev1 (Versions: 252.22-1~deb12u1)
- Titre: bind9: Preparing an NSEC3 closest encloser proof can exhaust CPU resources
- Date de publication: 2024-02-14T16:15:45Z
- Dernière modification: 2024-06-10T17:16:16Z
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-50868
#### CVE-2023-39325
**Gravité:** HIGH (7.5)
**Applications Affectées:** velero
**Details:**
- stdlib (Versions: 1.19.8)
- Titre: golang: net/http, x/net/http2: rapid stream resets can cause excessive work (CVE-2023-44487)
- Date de publication: 2023-10-11T22:15:09Z
- Dernière modification: 2024-04-28T04:15:09Z
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-39325
#### CVE-2023-45283
**Gravité:** HIGH (7.5)
**Applications Affectées:** velero
**Details:**
- stdlib (Versions: 1.19.8)
- Titre: The filepath package does not recognize paths with a \??\ prefix as sp ...
- Date de publication: 2023-11-09T17:15:08Z
- Dernière modification: 2023-12-14T10:15:07Z
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45283
#### CVE-2023-45287
**Gravité:** HIGH (7.5)
**Applications Affectées:** velero
**Details:**
- stdlib (Versions: 1.19.8)
- Titre: golang: crypto/tls: Timing Side Channel attack in RSA based TLS key exchanges.
- Date de publication: 2023-12-05T17:15:08Z
- Dernière modification: 2024-01-12T14:15:48Z
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45287
#### CVE-2023-45288
**Gravité:** HIGH (7.5)
**Applications Affectées:** velero
**Details:**
- stdlib (Versions: 1.19.8)
- Titre: golang: net/http, x/net/http2: unlimited number of CONTINUATION frames causes DoS
- Date de publication: 2024-04-04T21:15:16Z
- Dernière modification: 2024-05-01T18:15:10Z
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45288
#### CVE-2023-39325
**Gravité:** HIGH (7.5)
**Applications Affectées:** velero
**Details:**
- golang.org/x/net (Versions: v0.7.0)
- Titre: golang: net/http, x/net/http2: rapid stream resets can cause excessive work (CVE-2023-44487)
- Date de publication: 2023-10-11T22:15:09Z
- Dernière modification: 2024-04-28T04:15:09Z
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-39325
#### GHSA-m425-mq94-257g
**Gravité:** HIGH (7.5)
**Applications Affectées:** velero
**Details:**
- google.golang.org/grpc (Versions: v1.40.0)
- Titre: gRPC-Go HTTP/2 Rapid Reset vulnerability
- Date de publication: 
- Dernière modification: 
- Lien primaire: https://github.com/advisories/GHSA-m425-mq94-257g
#### CVE-2023-39325
**Gravité:** HIGH (7.5)
**Applications Affectées:** velero
**Details:**
- stdlib (Versions: 1.19.8)
- Titre: golang: net/http, x/net/http2: rapid stream resets can cause excessive work (CVE-2023-44487)
- Date de publication: 2023-10-11T22:15:09Z
- Dernière modification: 2024-04-28T04:15:09Z
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-39325
#### CVE-2023-45283
**Gravité:** HIGH (7.5)
**Applications Affectées:** velero
**Details:**
- stdlib (Versions: 1.19.8)
- Titre: The filepath package does not recognize paths with a \??\ prefix as sp ...
- Date de publication: 2023-11-09T17:15:08Z
- Dernière modification: 2023-12-14T10:15:07Z
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45283
#### CVE-2023-45287
**Gravité:** HIGH (7.5)
**Applications Affectées:** velero
**Details:**
- stdlib (Versions: 1.19.8)
- Titre: golang: crypto/tls: Timing Side Channel attack in RSA based TLS key exchanges.
- Date de publication: 2023-12-05T17:15:08Z
- Dernière modification: 2024-01-12T14:15:48Z
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45287
#### CVE-2023-45288
**Gravité:** HIGH (7.5)
**Applications Affectées:** velero
**Details:**
- stdlib (Versions: 1.19.8)
- Titre: golang: net/http, x/net/http2: unlimited number of CONTINUATION frames causes DoS
- Date de publication: 2024-04-04T21:15:16Z
- Dernière modification: 2024-05-01T18:15:10Z
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45288
#### CVE-2023-24539
**Gravité:** HIGH (7.3)
**Applications Affectées:** velero
**Details:**
- stdlib (Versions: 1.19.8)
- Titre: golang: html/template: improper sanitization of CSS values
- Date de publication: 2023-05-11T16:15:09Z
- Dernière modification: 2023-11-07T04:08:32Z
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-24539
#### CVE-2023-29400
**Gravité:** HIGH (7.3)
**Applications Affectées:** velero
**Details:**
- stdlib (Versions: 1.19.8)
- Titre: golang: html/template: improper handling of empty HTML attributes
- Date de publication: 2023-05-11T16:15:09Z
- Dernière modification: 2023-11-07T04:11:10Z
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-29400
#### CVE-2023-24539
**Gravité:** HIGH (7.3)
**Applications Affectées:** velero
**Details:**
- stdlib (Versions: 1.19.8)
- Titre: golang: html/template: improper sanitization of CSS values
- Date de publication: 2023-05-11T16:15:09Z
- Dernière modification: 2023-11-07T04:08:32Z
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-24539
#### CVE-2023-29400
**Gravité:** HIGH (7.3)
**Applications Affectées:** velero
**Details:**
- stdlib (Versions: 1.19.8)
- Titre: golang: html/template: improper handling of empty HTML attributes
- Date de publication: 2023-05-11T16:15:09Z
- Dernière modification: 2023-11-07T04:11:10Z
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-29400
#### CVE-2024-28182
**Gravité:** HIGH (5.3)
**Applications Affectées:** amazon-cloudwatch
**Details:**
- libnghttp2 (Versions: 1.41.0-1.amzn2.0.4)
- Titre: nghttp2: CONTINUATION frames DoS
- Date de publication: 2024-04-04T15:15:38Z
- Dernière modification: 2024-05-01T18:15:17Z
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-28182
