
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

### Métriques Spécifiques aux Bibliothèques
| Bibliothèque | Applications Affectées | Total CVE |
|--------------|-----------------------|-----------|
| stdlib | kube-prometheus-stack, trivy, velero, kyverno, policy-reporter, gitlab-agent | 22 |
| libssl3 | rabbitmq, trivy, keycloak, postgresql, backend-ddf | 6 |
| libgnutls30 | postgresql, rabbitmq, keycloak | 2 |
| libsystemd0 | postgresql, rabbitmq, keycloak | 2 |
| libudev1 | postgresql, rabbitmq, keycloak | 2 |
| openssl | postgresql, rabbitmq, keycloak | 4 |
| github.com/Azure/azure-sdk-for-go/sdk/azidentity | kube-prometheus-stack, trivy, kyverno | 1 |
| curl | rabbitmq, amazon-cloudwatch | 2 |
| libcrypto3 | trivy, backend-ddf | 2 |
| golang.org/x/net | velero, kyverno | 4 |
| glibc | amazon-cloudwatch | 1 |
| glibc-common | amazon-cloudwatch | 1 |
| glibc-langpack-en | amazon-cloudwatch | 1 |
| glibc-minimal-langpack | amazon-cloudwatch | 1 |
| libcrypt | amazon-cloudwatch | 1 |
| libcurl | amazon-cloudwatch | 2 |
| libnghttp2 | amazon-cloudwatch | 1 |
| openssl11-devel | amazon-cloudwatch | 1 |
| openssl11-libs | amazon-cloudwatch | 1 |
| github.com/hashicorp/go-retryablehttp | kyverno | 1 |
| libcurl4 | rabbitmq | 2 |
| busybox | trivy | 2 |
| busybox-binsh | trivy | 2 |
| ssl_client | trivy | 2 |
| github.com/hashicorp/go-getter | trivy | 1 |
| google.golang.org/grpc | velero | 2 |
| google.golang.org/protobuf | velero | 1 |

### Observations Clés
* velero est l'application la plus affectée avec un total de 51 CVE.
* rabbitmq a également un nombre significatif de CVE (18).
* trivy a également un nombre significatif de CVE (15).
* La majorité des CVE sont classées comme étant de haute gravité (26%), avec seulement une petite fraction étant critiques (5%).
* La bibliothèque stdlib est récurrente à travers plusieurs CVE et applications (applications, cves), indiquant des vulnérabilités communes dans cette bibliothèque.
* La bibliothèque libssl3 est récurrente à travers plusieurs CVE et applications (applications, cves), indiquant des vulnérabilités communes dans cette bibliothèque.
* La bibliothèque libgnutls30 est récurrente à travers plusieurs CVE et applications (applications, cves), indiquant des vulnérabilités communes dans cette bibliothèque.

## Liste Détaillée des CVE
### CVE Critiques

| CVE ID | Applications |
|--------|--------------|
| [CVE-2024-24790](#cve-2024-24790) | kube-prometheus-stack, policy-reporter, trivy, velero |
| [CVE-2023-24540](#cve-2023-24540) | velero |
### CVE Élevées

| CVE ID | Applications |
|--------|--------------|
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
### CVE Moyennes

| CVE ID | Applications |
|--------|--------------|
| [CVE-2024-2004](#cve-2024-2004) | amazon-cloudwatch, rabbitmq |
| [CVE-2024-2398](#cve-2024-2398) | amazon-cloudwatch |
| [CVE-2024-2511](#cve-2024-2511) | amazon-cloudwatch |
| [CVE-2024-4741](#cve-2024-4741) | backend-ddf, trivy |
| [CVE-2024-5535](#cve-2024-5535) | backend-ddf, trivy |
| [CVE-2024-24791](#cve-2024-24791) | gitlab-agent, kube-prometheus-stack, kyverno, policy-reporter, trivy, velero |
| [CVE-2024-28834](#cve-2024-28834) | keycloak, postgresql, rabbitmq |
| [CVE-2024-28835](#cve-2024-28835) | keycloak, postgresql, rabbitmq |
| [CVE-2023-5678](#cve-2023-5678) | keycloak, postgresql, rabbitmq |
| [CVE-2023-6129](#cve-2023-6129) | keycloak, postgresql, rabbitmq |
| [CVE-2023-6237](#cve-2023-6237) | keycloak, postgresql, rabbitmq |
| [CVE-2024-0727](#cve-2024-0727) | keycloak, postgresql, rabbitmq |
| [CVE-2024-35255](#cve-2024-35255) | kube-prometheus-stack, kyverno, trivy |
| [CVE-2024-24789](#cve-2024-24789) | kube-prometheus-stack, policy-reporter, trivy, velero |
| [CVE-2024-6104](#cve-2024-6104) | kyverno |
| [CVE-2023-45288](#cve-2023-45288) | kyverno, velero |
| [CVE-2023-42364](#cve-2023-42364) | trivy |
| [CVE-2023-42365](#cve-2023-42365) | trivy |
| [CVE-2023-29406](#cve-2023-29406) | velero |
| [CVE-2023-29409](#cve-2023-29409) | velero |
| [CVE-2023-39318](#cve-2023-39318) | velero |
| [CVE-2023-39319](#cve-2023-39319) | velero |
| [CVE-2023-39326](#cve-2023-39326) | velero |
| [CVE-2023-45284](#cve-2023-45284) | velero |
| [CVE-2023-45289](#cve-2023-45289) | velero |
| [CVE-2023-45290](#cve-2023-45290) | velero |
| [CVE-2024-24783](#cve-2024-24783) | velero |
| [CVE-2024-24784](#cve-2024-24784) | velero |
| [CVE-2024-24785](#cve-2024-24785) | velero |
| [CVE-2023-3978](#cve-2023-3978) | velero |
| [CVE-2023-44487](#cve-2023-44487) | velero |
| [CVE-2024-24786](#cve-2024-24786) | velero |
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
### CVE Moyennes
#### CVE-2024-2004
**Gravité:** MEDIUM (5.3)  
**Applications Affectées:** amazon-cloudwatch  
**Details:**
- curl (Versions: 8.3.0-1.amzn2.0.6)  
- Titre: curl: Usage of disabled protocol  
- Date de publication: 2024-03-27T08:15:41Z  
- Dernière modification: 2024-07-03T01:52:57Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-2004  
#### CVE-2024-2398
**Gravité:** MEDIUM (7.5)  
**Applications Affectées:** amazon-cloudwatch  
**Details:**
- curl (Versions: 8.3.0-1.amzn2.0.6)  
- Titre: curl: HTTP/2 push headers memory-leak  
- Date de publication: 2024-03-27T08:15:41Z  
- Dernière modification: 2024-07-03T01:53:12Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-2398  
#### CVE-2024-2004
**Gravité:** MEDIUM (5.3)  
**Applications Affectées:** amazon-cloudwatch  
**Details:**
- libcurl (Versions: 8.3.0-1.amzn2.0.6)  
- Titre: curl: Usage of disabled protocol  
- Date de publication: 2024-03-27T08:15:41Z  
- Dernière modification: 2024-07-03T01:52:57Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-2004  
#### CVE-2024-2398
**Gravité:** MEDIUM (7.5)  
**Applications Affectées:** amazon-cloudwatch  
**Details:**
- libcurl (Versions: 8.3.0-1.amzn2.0.6)  
- Titre: curl: HTTP/2 push headers memory-leak  
- Date de publication: 2024-03-27T08:15:41Z  
- Dernière modification: 2024-07-03T01:53:12Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-2398  
#### CVE-2024-2511
**Gravité:** MEDIUM (3.7)  
**Applications Affectées:** amazon-cloudwatch  
**Details:**
- openssl11-devel (Versions: 1:1.1.1g-12.amzn2.0.20)  
- Titre: openssl: Unbounded memory growth with session handling in TLSv1.3  
- Date de publication: 2024-04-08T14:15:07Z  
- Dernière modification: 2024-05-03T13:15:21Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-2511  
#### CVE-2024-2511
**Gravité:** MEDIUM (3.7)  
**Applications Affectées:** amazon-cloudwatch  
**Details:**
- openssl11-libs (Versions: 1:1.1.1g-12.amzn2.0.20)  
- Titre: openssl: Unbounded memory growth with session handling in TLSv1.3  
- Date de publication: 2024-04-08T14:15:07Z  
- Dernière modification: 2024-05-03T13:15:21Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-2511  
#### CVE-2024-4741
**Gravité:** MEDIUM (5.6)  
**Applications Affectées:** backend-ddf  
**Details:**
- libcrypto3 (Versions: 3.1.5-r0)  
- Titre: openssl: Use After Free with SSL_free_buffers  
- Date de publication:   
- Dernière modification:   
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-4741  
#### CVE-2024-5535
**Gravité:** MEDIUM (5.9)  
**Applications Affectées:** backend-ddf  
**Details:**
- libcrypto3 (Versions: 3.1.5-r0)  
- Titre: openssl: SSL_select_next_proto buffer overread  
- Date de publication: 2024-06-27T11:15:24Z  
- Dernière modification: 2024-07-03T02:09:04Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-5535  
#### CVE-2024-4741
**Gravité:** MEDIUM (5.6)  
**Applications Affectées:** backend-ddf  
**Details:**
- libssl3 (Versions: 3.1.5-r0)  
- Titre: openssl: Use After Free with SSL_free_buffers  
- Date de publication:   
- Dernière modification:   
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-4741  
#### CVE-2024-5535
**Gravité:** MEDIUM (5.9)  
**Applications Affectées:** backend-ddf  
**Details:**
- libssl3 (Versions: 3.1.5-r0)  
- Titre: openssl: SSL_select_next_proto buffer overread  
- Date de publication: 2024-06-27T11:15:24Z  
- Dernière modification: 2024-07-03T02:09:04Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-5535  
#### CVE-2024-24791
**Gravité:** MEDIUM (N/A)  
**Applications Affectées:** gitlab-agent  
**Details:**
- stdlib (Versions: 1.22.4)  
- Titre: net/http: Denial of service due to improper 100-continue handling in net/http  
- Date de publication: 2024-07-02T22:15:04Z  
- Dernière modification: 2024-07-03T12:53:24Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24791  
#### CVE-2024-28834
**Gravité:** MEDIUM (5.3)  
**Applications Affectées:** keycloak  
**Details:**
- libgnutls30 (Versions: 3.7.9-2+deb12u2)  
- Titre: gnutls: vulnerable to Minerva side-channel information leak  
- Date de publication: 2024-03-21T14:15:07Z  
- Dernière modification: 2024-06-10T17:16:24Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-28834  
#### CVE-2024-28835
**Gravité:** MEDIUM (5)  
**Applications Affectées:** keycloak  
**Details:**
- libgnutls30 (Versions: 3.7.9-2+deb12u2)  
- Titre: gnutls: potential crash during chain building/verification  
- Date de publication: 2024-03-21T06:15:45Z  
- Dernière modification: 2024-05-16T23:15:47Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-28835  
#### CVE-2023-5678
**Gravité:** MEDIUM (5.3)  
**Applications Affectées:** keycloak  
**Details:**
- libssl3 (Versions: 3.0.11-1~deb12u2)  
- Titre: openssl: Generating excessively long X9.42 DH keys or checking excessively long X9.42 DH keys or parameters may be very slow  
- Date de publication: 2023-11-06T16:15:42Z  
- Dernière modification: 2024-05-01T18:15:12Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-5678  
#### CVE-2023-6129
**Gravité:** MEDIUM (6.5)  
**Applications Affectées:** keycloak  
**Details:**
- libssl3 (Versions: 3.0.11-1~deb12u2)  
- Titre: mysql: openssl: POLY1305 MAC implementation corrupts vector registers on PowerPC  
- Date de publication: 2024-01-09T17:15:12Z  
- Dernière modification: 2024-05-03T13:15:21Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-6129  
#### CVE-2023-6237
**Gravité:** MEDIUM (5.9)  
**Applications Affectées:** keycloak  
**Details:**
- libssl3 (Versions: 3.0.11-1~deb12u2)  
- Titre: openssl: Excessive time spent checking invalid RSA public keys  
- Date de publication: 2024-04-25T07:15:45Z  
- Dernière modification: 2024-06-10T17:16:16Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-6237  
#### CVE-2024-0727
**Gravité:** MEDIUM (5.5)  
**Applications Affectées:** keycloak  
**Details:**
- libssl3 (Versions: 3.0.11-1~deb12u2)  
- Titre: openssl: denial of service via null dereference  
- Date de publication: 2024-01-26T09:15:07Z  
- Dernière modification: 2024-05-01T18:15:13Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-0727  
#### CVE-2023-5678
**Gravité:** MEDIUM (5.3)  
**Applications Affectées:** keycloak  
**Details:**
- openssl (Versions: 3.0.11-1~deb12u2)  
- Titre: openssl: Generating excessively long X9.42 DH keys or checking excessively long X9.42 DH keys or parameters may be very slow  
- Date de publication: 2023-11-06T16:15:42Z  
- Dernière modification: 2024-05-01T18:15:12Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-5678  
#### CVE-2023-6129
**Gravité:** MEDIUM (6.5)  
**Applications Affectées:** keycloak  
**Details:**
- openssl (Versions: 3.0.11-1~deb12u2)  
- Titre: mysql: openssl: POLY1305 MAC implementation corrupts vector registers on PowerPC  
- Date de publication: 2024-01-09T17:15:12Z  
- Dernière modification: 2024-05-03T13:15:21Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-6129  
#### CVE-2023-6237
**Gravité:** MEDIUM (5.9)  
**Applications Affectées:** keycloak  
**Details:**
- openssl (Versions: 3.0.11-1~deb12u2)  
- Titre: openssl: Excessive time spent checking invalid RSA public keys  
- Date de publication: 2024-04-25T07:15:45Z  
- Dernière modification: 2024-06-10T17:16:16Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-6237  
#### CVE-2024-0727
**Gravité:** MEDIUM (5.5)  
**Applications Affectées:** keycloak  
**Details:**
- openssl (Versions: 3.0.11-1~deb12u2)  
- Titre: openssl: denial of service via null dereference  
- Date de publication: 2024-01-26T09:15:07Z  
- Dernière modification: 2024-05-01T18:15:13Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-0727  
#### CVE-2024-35255
**Gravité:** MEDIUM (5.5)  
**Applications Affectées:** kube-prometheus-stack  
**Details:**
- github.com/Azure/azure-sdk-for-go/sdk/azidentity (Versions: v1.5.2)  
- Titre: Azure Identity Libraries and Microsoft Authentication Library Elevation of Privilege Vulnerability  
- Date de publication: 2024-06-11T17:16:03Z  
- Dernière modification: 2024-06-20T16:31:46Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-35255  
#### CVE-2024-24789
**Gravité:** MEDIUM (5.5)  
**Applications Affectées:** kube-prometheus-stack  
**Details:**
- stdlib (Versions: 1.22.3)  
- Titre: golang: archive/zip: Incorrect handling of certain ZIP files  
- Date de publication: 2024-06-05T16:15:10Z  
- Dernière modification: 2024-07-03T01:48:25Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24789  
#### CVE-2024-24791
**Gravité:** MEDIUM (N/A)  
**Applications Affectées:** kube-prometheus-stack  
**Details:**
- stdlib (Versions: 1.22.3)  
- Titre: net/http: Denial of service due to improper 100-continue handling in net/http  
- Date de publication: 2024-07-02T22:15:04Z  
- Dernière modification: 2024-07-03T12:53:24Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24791  
#### CVE-2024-35255
**Gravité:** MEDIUM (5.5)  
**Applications Affectées:** kyverno  
**Details:**
- github.com/Azure/azure-sdk-for-go/sdk/azidentity (Versions: v1.5.1)  
- Titre: Azure Identity Libraries and Microsoft Authentication Library Elevation of Privilege Vulnerability  
- Date de publication: 2024-06-11T17:16:03Z  
- Dernière modification: 2024-06-20T16:31:46Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-35255  
#### CVE-2024-6104
**Gravité:** MEDIUM (5.5)  
**Applications Affectées:** kyverno  
**Details:**
- github.com/hashicorp/go-retryablehttp (Versions: v0.7.5)  
- Titre: go-retryablehttp: url might write sensitive information to log file  
- Date de publication: 2024-06-24T17:15:11Z  
- Dernière modification: 2024-06-26T17:19:40Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-6104  
#### CVE-2023-45288
**Gravité:** MEDIUM (7.5)  
**Applications Affectées:** kyverno  
**Details:**
- golang.org/x/net (Versions: v0.22.0)  
- Titre: golang: net/http, x/net/http2: unlimited number of CONTINUATION frames causes DoS  
- Date de publication: 2024-04-04T21:15:16Z  
- Dernière modification: 2024-05-01T18:15:10Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45288  
#### CVE-2024-24791
**Gravité:** MEDIUM (N/A)  
**Applications Affectées:** kyverno  
**Details:**
- stdlib (Versions: 1.21.11)  
- Titre: net/http: Denial of service due to improper 100-continue handling in net/http  
- Date de publication: 2024-07-02T22:15:04Z  
- Dernière modification: 2024-07-03T12:53:24Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24791  
#### CVE-2024-24789
**Gravité:** MEDIUM (5.5)  
**Applications Affectées:** policy-reporter  
**Details:**
- stdlib (Versions: 1.22.3)  
- Titre: golang: archive/zip: Incorrect handling of certain ZIP files  
- Date de publication: 2024-06-05T16:15:10Z  
- Dernière modification: 2024-07-03T01:48:25Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24789  
#### CVE-2024-24791
**Gravité:** MEDIUM (N/A)  
**Applications Affectées:** policy-reporter  
**Details:**
- stdlib (Versions: 1.22.3)  
- Titre: net/http: Denial of service due to improper 100-continue handling in net/http  
- Date de publication: 2024-07-02T22:15:04Z  
- Dernière modification: 2024-07-03T12:53:24Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24791  
#### CVE-2024-28834
**Gravité:** MEDIUM (5.3)  
**Applications Affectées:** postgresql  
**Details:**
- libgnutls30 (Versions: 3.7.9-2+deb12u2)  
- Titre: gnutls: vulnerable to Minerva side-channel information leak  
- Date de publication: 2024-03-21T14:15:07Z  
- Dernière modification: 2024-06-10T17:16:24Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-28834  
#### CVE-2024-28835
**Gravité:** MEDIUM (5)  
**Applications Affectées:** postgresql  
**Details:**
- libgnutls30 (Versions: 3.7.9-2+deb12u2)  
- Titre: gnutls: potential crash during chain building/verification  
- Date de publication: 2024-03-21T06:15:45Z  
- Dernière modification: 2024-05-16T23:15:47Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-28835  
#### CVE-2023-5678
**Gravité:** MEDIUM (5.3)  
**Applications Affectées:** postgresql  
**Details:**
- libssl3 (Versions: 3.0.11-1~deb12u2)  
- Titre: openssl: Generating excessively long X9.42 DH keys or checking excessively long X9.42 DH keys or parameters may be very slow  
- Date de publication: 2023-11-06T16:15:42Z  
- Dernière modification: 2024-05-01T18:15:12Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-5678  
#### CVE-2023-6129
**Gravité:** MEDIUM (6.5)  
**Applications Affectées:** postgresql  
**Details:**
- libssl3 (Versions: 3.0.11-1~deb12u2)  
- Titre: mysql: openssl: POLY1305 MAC implementation corrupts vector registers on PowerPC  
- Date de publication: 2024-01-09T17:15:12Z  
- Dernière modification: 2024-05-03T13:15:21Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-6129  
#### CVE-2023-6237
**Gravité:** MEDIUM (5.9)  
**Applications Affectées:** postgresql  
**Details:**
- libssl3 (Versions: 3.0.11-1~deb12u2)  
- Titre: openssl: Excessive time spent checking invalid RSA public keys  
- Date de publication: 2024-04-25T07:15:45Z  
- Dernière modification: 2024-06-10T17:16:16Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-6237  
#### CVE-2024-0727
**Gravité:** MEDIUM (5.5)  
**Applications Affectées:** postgresql  
**Details:**
- libssl3 (Versions: 3.0.11-1~deb12u2)  
- Titre: openssl: denial of service via null dereference  
- Date de publication: 2024-01-26T09:15:07Z  
- Dernière modification: 2024-05-01T18:15:13Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-0727  
#### CVE-2023-5678
**Gravité:** MEDIUM (5.3)  
**Applications Affectées:** postgresql  
**Details:**
- openssl (Versions: 3.0.11-1~deb12u2)  
- Titre: openssl: Generating excessively long X9.42 DH keys or checking excessively long X9.42 DH keys or parameters may be very slow  
- Date de publication: 2023-11-06T16:15:42Z  
- Dernière modification: 2024-05-01T18:15:12Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-5678  
#### CVE-2023-6129
**Gravité:** MEDIUM (6.5)  
**Applications Affectées:** postgresql  
**Details:**
- openssl (Versions: 3.0.11-1~deb12u2)  
- Titre: mysql: openssl: POLY1305 MAC implementation corrupts vector registers on PowerPC  
- Date de publication: 2024-01-09T17:15:12Z  
- Dernière modification: 2024-05-03T13:15:21Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-6129  
#### CVE-2023-6237
**Gravité:** MEDIUM (5.9)  
**Applications Affectées:** postgresql  
**Details:**
- openssl (Versions: 3.0.11-1~deb12u2)  
- Titre: openssl: Excessive time spent checking invalid RSA public keys  
- Date de publication: 2024-04-25T07:15:45Z  
- Dernière modification: 2024-06-10T17:16:16Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-6237  
#### CVE-2024-0727
**Gravité:** MEDIUM (5.5)  
**Applications Affectées:** postgresql  
**Details:**
- openssl (Versions: 3.0.11-1~deb12u2)  
- Titre: openssl: denial of service via null dereference  
- Date de publication: 2024-01-26T09:15:07Z  
- Dernière modification: 2024-05-01T18:15:13Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-0727  
#### CVE-2024-2004
**Gravité:** MEDIUM (5.3)  
**Applications Affectées:** rabbitmq  
**Details:**
- curl (Versions: 7.88.1-10+deb12u5)  
- Titre: curl: Usage of disabled protocol  
- Date de publication: 2024-03-27T08:15:41Z  
- Dernière modification: 2024-07-03T01:52:57Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-2004  
#### CVE-2024-2004
**Gravité:** MEDIUM (5.3)  
**Applications Affectées:** rabbitmq  
**Details:**
- libcurl4 (Versions: 7.88.1-10+deb12u5)  
- Titre: curl: Usage of disabled protocol  
- Date de publication: 2024-03-27T08:15:41Z  
- Dernière modification: 2024-07-03T01:52:57Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-2004  
#### CVE-2024-28834
**Gravité:** MEDIUM (5.3)  
**Applications Affectées:** rabbitmq  
**Details:**
- libgnutls30 (Versions: 3.7.9-2+deb12u2)  
- Titre: gnutls: vulnerable to Minerva side-channel information leak  
- Date de publication: 2024-03-21T14:15:07Z  
- Dernière modification: 2024-06-10T17:16:24Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-28834  
#### CVE-2024-28835
**Gravité:** MEDIUM (5)  
**Applications Affectées:** rabbitmq  
**Details:**
- libgnutls30 (Versions: 3.7.9-2+deb12u2)  
- Titre: gnutls: potential crash during chain building/verification  
- Date de publication: 2024-03-21T06:15:45Z  
- Dernière modification: 2024-05-16T23:15:47Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-28835  
#### CVE-2023-5678
**Gravité:** MEDIUM (5.3)  
**Applications Affectées:** rabbitmq  
**Details:**
- libssl3 (Versions: 3.0.11-1~deb12u2)  
- Titre: openssl: Generating excessively long X9.42 DH keys or checking excessively long X9.42 DH keys or parameters may be very slow  
- Date de publication: 2023-11-06T16:15:42Z  
- Dernière modification: 2024-05-01T18:15:12Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-5678  
#### CVE-2023-6129
**Gravité:** MEDIUM (6.5)  
**Applications Affectées:** rabbitmq  
**Details:**
- libssl3 (Versions: 3.0.11-1~deb12u2)  
- Titre: mysql: openssl: POLY1305 MAC implementation corrupts vector registers on PowerPC  
- Date de publication: 2024-01-09T17:15:12Z  
- Dernière modification: 2024-05-03T13:15:21Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-6129  
#### CVE-2023-6237
**Gravité:** MEDIUM (5.9)  
**Applications Affectées:** rabbitmq  
**Details:**
- libssl3 (Versions: 3.0.11-1~deb12u2)  
- Titre: openssl: Excessive time spent checking invalid RSA public keys  
- Date de publication: 2024-04-25T07:15:45Z  
- Dernière modification: 2024-06-10T17:16:16Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-6237  
#### CVE-2024-0727
**Gravité:** MEDIUM (5.5)  
**Applications Affectées:** rabbitmq  
**Details:**
- libssl3 (Versions: 3.0.11-1~deb12u2)  
- Titre: openssl: denial of service via null dereference  
- Date de publication: 2024-01-26T09:15:07Z  
- Dernière modification: 2024-05-01T18:15:13Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-0727  
#### CVE-2023-5678
**Gravité:** MEDIUM (5.3)  
**Applications Affectées:** rabbitmq  
**Details:**
- openssl (Versions: 3.0.11-1~deb12u2)  
- Titre: openssl: Generating excessively long X9.42 DH keys or checking excessively long X9.42 DH keys or parameters may be very slow  
- Date de publication: 2023-11-06T16:15:42Z  
- Dernière modification: 2024-05-01T18:15:12Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-5678  
#### CVE-2023-6129
**Gravité:** MEDIUM (6.5)  
**Applications Affectées:** rabbitmq  
**Details:**
- openssl (Versions: 3.0.11-1~deb12u2)  
- Titre: mysql: openssl: POLY1305 MAC implementation corrupts vector registers on PowerPC  
- Date de publication: 2024-01-09T17:15:12Z  
- Dernière modification: 2024-05-03T13:15:21Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-6129  
#### CVE-2023-6237
**Gravité:** MEDIUM (5.9)  
**Applications Affectées:** rabbitmq  
**Details:**
- openssl (Versions: 3.0.11-1~deb12u2)  
- Titre: openssl: Excessive time spent checking invalid RSA public keys  
- Date de publication: 2024-04-25T07:15:45Z  
- Dernière modification: 2024-06-10T17:16:16Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-6237  
#### CVE-2024-0727
**Gravité:** MEDIUM (5.5)  
**Applications Affectées:** rabbitmq  
**Details:**
- openssl (Versions: 3.0.11-1~deb12u2)  
- Titre: openssl: denial of service via null dereference  
- Date de publication: 2024-01-26T09:15:07Z  
- Dernière modification: 2024-05-01T18:15:13Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-0727  
#### CVE-2023-42364
**Gravité:** MEDIUM (5.5)  
**Applications Affectées:** trivy  
**Details:**
- busybox (Versions: 1.36.1-r18)  
- Titre: busybox: use-after-free  
- Date de publication: 2023-11-27T23:15:07Z  
- Dernière modification: 2023-11-30T05:07:10Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-42364  
#### CVE-2023-42365
**Gravité:** MEDIUM (5.5)  
**Applications Affectées:** trivy  
**Details:**
- busybox (Versions: 1.36.1-r18)  
- Titre: busybox:  use-after-free  
- Date de publication: 2023-11-27T23:15:07Z  
- Dernière modification: 2023-11-30T05:08:08Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-42365  
#### CVE-2023-42364
**Gravité:** MEDIUM (5.5)  
**Applications Affectées:** trivy  
**Details:**
- busybox-binsh (Versions: 1.36.1-r18)  
- Titre: busybox: use-after-free  
- Date de publication: 2023-11-27T23:15:07Z  
- Dernière modification: 2023-11-30T05:07:10Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-42364  
#### CVE-2023-42365
**Gravité:** MEDIUM (5.5)  
**Applications Affectées:** trivy  
**Details:**
- busybox-binsh (Versions: 1.36.1-r18)  
- Titre: busybox:  use-after-free  
- Date de publication: 2023-11-27T23:15:07Z  
- Dernière modification: 2023-11-30T05:08:08Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-42365  
#### CVE-2024-4741
**Gravité:** MEDIUM (5.6)  
**Applications Affectées:** trivy  
**Details:**
- libcrypto3 (Versions: 3.1.5-r0)  
- Titre: openssl: Use After Free with SSL_free_buffers  
- Date de publication:   
- Dernière modification:   
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-4741  
#### CVE-2024-5535
**Gravité:** MEDIUM (5.9)  
**Applications Affectées:** trivy  
**Details:**
- libcrypto3 (Versions: 3.1.5-r0)  
- Titre: openssl: SSL_select_next_proto buffer overread  
- Date de publication: 2024-06-27T11:15:24Z  
- Dernière modification: 2024-07-03T02:09:04Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-5535  
#### CVE-2024-4741
**Gravité:** MEDIUM (5.6)  
**Applications Affectées:** trivy  
**Details:**
- libssl3 (Versions: 3.1.5-r0)  
- Titre: openssl: Use After Free with SSL_free_buffers  
- Date de publication:   
- Dernière modification:   
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-4741  
#### CVE-2024-5535
**Gravité:** MEDIUM (5.9)  
**Applications Affectées:** trivy  
**Details:**
- libssl3 (Versions: 3.1.5-r0)  
- Titre: openssl: SSL_select_next_proto buffer overread  
- Date de publication: 2024-06-27T11:15:24Z  
- Dernière modification: 2024-07-03T02:09:04Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-5535  
#### CVE-2023-42364
**Gravité:** MEDIUM (5.5)  
**Applications Affectées:** trivy  
**Details:**
- ssl_client (Versions: 1.36.1-r18)  
- Titre: busybox: use-after-free  
- Date de publication: 2023-11-27T23:15:07Z  
- Dernière modification: 2023-11-30T05:07:10Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-42364  
#### CVE-2023-42365
**Gravité:** MEDIUM (5.5)  
**Applications Affectées:** trivy  
**Details:**
- ssl_client (Versions: 1.36.1-r18)  
- Titre: busybox:  use-after-free  
- Date de publication: 2023-11-27T23:15:07Z  
- Dernière modification: 2023-11-30T05:08:08Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-42365  
#### CVE-2024-35255
**Gravité:** MEDIUM (5.5)  
**Applications Affectées:** trivy  
**Details:**
- github.com/Azure/azure-sdk-for-go/sdk/azidentity (Versions: v1.5.2)  
- Titre: Azure Identity Libraries and Microsoft Authentication Library Elevation of Privilege Vulnerability  
- Date de publication: 2024-06-11T17:16:03Z  
- Dernière modification: 2024-06-20T16:31:46Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-35255  
#### CVE-2024-24789
**Gravité:** MEDIUM (5.5)  
**Applications Affectées:** trivy  
**Details:**
- stdlib (Versions: 1.22.3)  
- Titre: golang: archive/zip: Incorrect handling of certain ZIP files  
- Date de publication: 2024-06-05T16:15:10Z  
- Dernière modification: 2024-07-03T01:48:25Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24789  
#### CVE-2024-24791
**Gravité:** MEDIUM (N/A)  
**Applications Affectées:** trivy  
**Details:**
- stdlib (Versions: 1.22.3)  
- Titre: net/http: Denial of service due to improper 100-continue handling in net/http  
- Date de publication: 2024-07-02T22:15:04Z  
- Dernière modification: 2024-07-03T12:53:24Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24791  
#### CVE-2023-29406
**Gravité:** MEDIUM (6.5)  
**Applications Affectées:** velero  
**Details:**
- stdlib (Versions: 1.19.8)  
- Titre: golang: net/http: insufficient sanitization of Host header  
- Date de publication: 2023-07-11T20:15:10Z  
- Dernière modification: 2023-11-25T11:15:14Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-29406  
#### CVE-2023-29409
**Gravité:** MEDIUM (5.3)  
**Applications Affectées:** velero  
**Details:**
- stdlib (Versions: 1.19.8)  
- Titre: golang: crypto/tls: slow verification of certificate chains containing large RSA keys  
- Date de publication: 2023-08-02T20:15:11Z  
- Dernière modification: 2023-11-25T11:15:14Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-29409  
#### CVE-2023-39318
**Gravité:** MEDIUM (6.1)  
**Applications Affectées:** velero  
**Details:**
- stdlib (Versions: 1.19.8)  
- Titre: golang: html/template: improper handling of HTML-like comments within script contexts  
- Date de publication: 2023-09-08T17:15:27Z  
- Dernière modification: 2023-11-25T11:15:17Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-39318  
#### CVE-2023-39319
**Gravité:** MEDIUM (6.1)  
**Applications Affectées:** velero  
**Details:**
- stdlib (Versions: 1.19.8)  
- Titre: golang: html/template: improper handling of special tags within script contexts  
- Date de publication: 2023-09-08T17:15:27Z  
- Dernière modification: 2023-11-25T11:15:17Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-39319  
#### CVE-2023-39326
**Gravité:** MEDIUM (5.3)  
**Applications Affectées:** velero  
**Details:**
- stdlib (Versions: 1.19.8)  
- Titre: golang: net/http/internal: Denial of Service (DoS) via Resource Consumption via HTTP requests  
- Date de publication: 2023-12-06T17:15:07Z  
- Dernière modification: 2024-01-20T04:15:07Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-39326  
#### CVE-2023-45284
**Gravité:** MEDIUM (5.3)  
**Applications Affectées:** velero  
**Details:**
- stdlib (Versions: 1.19.8)  
- Titre: On Windows, The IsLocal function does not correctly detect reserved de ...  
- Date de publication: 2023-11-09T17:15:08Z  
- Dernière modification: 2023-11-17T16:39:27Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45284  
#### CVE-2023-45289
**Gravité:** MEDIUM (5.3)  
**Applications Affectées:** velero  
**Details:**
- stdlib (Versions: 1.19.8)  
- Titre: golang: net/http/cookiejar: incorrect forwarding of sensitive headers and cookies on HTTP redirect  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:25Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45289  
#### CVE-2023-45290
**Gravité:** MEDIUM (5.3)  
**Applications Affectées:** velero  
**Details:**
- stdlib (Versions: 1.19.8)  
- Titre: golang: net/http: memory exhaustion in Request.ParseMultipartForm  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:26Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45290  
#### CVE-2024-24783
**Gravité:** MEDIUM (5.9)  
**Applications Affectées:** velero  
**Details:**
- stdlib (Versions: 1.19.8)  
- Titre: golang: crypto/x509: Verify panics on certificates with an unknown public key algorithm  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:29Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24783  
#### CVE-2024-24784
**Gravité:** MEDIUM (5.4)  
**Applications Affectées:** velero  
**Details:**
- stdlib (Versions: 1.19.8)  
- Titre: golang: net/mail: comments in display names are incorrectly handled  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:29Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24784  
#### CVE-2024-24785
**Gravité:** MEDIUM (6.5)  
**Applications Affectées:** velero  
**Details:**
- stdlib (Versions: 1.19.8)  
- Titre: golang: html/template: errors returned from MarshalJSON methods may break template escaping  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:29Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24785  
#### CVE-2024-24789
**Gravité:** MEDIUM (5.5)  
**Applications Affectées:** velero  
**Details:**
- stdlib (Versions: 1.19.8)  
- Titre: golang: archive/zip: Incorrect handling of certain ZIP files  
- Date de publication: 2024-06-05T16:15:10Z  
- Dernière modification: 2024-07-03T01:48:25Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24789  
#### CVE-2024-24791
**Gravité:** MEDIUM (N/A)  
**Applications Affectées:** velero  
**Details:**
- stdlib (Versions: 1.19.8)  
- Titre: net/http: Denial of service due to improper 100-continue handling in net/http  
- Date de publication: 2024-07-02T22:15:04Z  
- Dernière modification: 2024-07-03T12:53:24Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24791  
#### CVE-2023-3978
**Gravité:** MEDIUM (6.1)  
**Applications Affectées:** velero  
**Details:**
- golang.org/x/net (Versions: v0.7.0)  
- Titre: golang.org/x/net/html: Cross site scripting  
- Date de publication: 2023-08-02T20:15:12Z  
- Dernière modification: 2023-11-07T04:20:03Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-3978  
#### CVE-2023-44487
**Gravité:** MEDIUM (7.5)  
**Applications Affectées:** velero  
**Details:**
- golang.org/x/net (Versions: v0.7.0)  
- Titre: HTTP/2: Multiple HTTP/2 enabled web servers are vulnerable to a DDoS attack (Rapid Reset Attack)  
- Date de publication: 2023-10-10T14:15:10Z  
- Dernière modification: 2024-06-27T18:34:22Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-44487  
#### CVE-2023-45288
**Gravité:** MEDIUM (5.3)  
**Applications Affectées:** velero  
**Details:**
- golang.org/x/net (Versions: v0.7.0)  
- Titre: golang: net/http, x/net/http2: unlimited number of CONTINUATION frames causes DoS  
- Date de publication: 2024-04-04T21:15:16Z  
- Dernière modification: 2024-05-01T18:15:10Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45288  
#### CVE-2023-44487
**Gravité:** MEDIUM (7.5)  
**Applications Affectées:** velero  
**Details:**
- google.golang.org/grpc (Versions: v1.40.0)  
- Titre: HTTP/2: Multiple HTTP/2 enabled web servers are vulnerable to a DDoS attack (Rapid Reset Attack)  
- Date de publication: 2023-10-10T14:15:10Z  
- Dernière modification: 2024-06-27T18:34:22Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-44487  
#### CVE-2024-24786
**Gravité:** MEDIUM (5.9)  
**Applications Affectées:** velero  
**Details:**
- google.golang.org/protobuf (Versions: v1.27.1)  
- Titre: golang-protobuf: encoding/protojson, internal/encoding/json: infinite loop in protojson.Unmarshal when unmarshaling certain forms of invalid JSON  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-06-10T18:15:26Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24786  
#### CVE-2023-29406
**Gravité:** MEDIUM (6.5)  
**Applications Affectées:** velero  
**Details:**
- stdlib (Versions: 1.19.8)  
- Titre: golang: net/http: insufficient sanitization of Host header  
- Date de publication: 2023-07-11T20:15:10Z  
- Dernière modification: 2023-11-25T11:15:14Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-29406  
#### CVE-2023-29409
**Gravité:** MEDIUM (5.3)  
**Applications Affectées:** velero  
**Details:**
- stdlib (Versions: 1.19.8)  
- Titre: golang: crypto/tls: slow verification of certificate chains containing large RSA keys  
- Date de publication: 2023-08-02T20:15:11Z  
- Dernière modification: 2023-11-25T11:15:14Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-29409  
#### CVE-2023-39318
**Gravité:** MEDIUM (6.1)  
**Applications Affectées:** velero  
**Details:**
- stdlib (Versions: 1.19.8)  
- Titre: golang: html/template: improper handling of HTML-like comments within script contexts  
- Date de publication: 2023-09-08T17:15:27Z  
- Dernière modification: 2023-11-25T11:15:17Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-39318  
#### CVE-2023-39319
**Gravité:** MEDIUM (6.1)  
**Applications Affectées:** velero  
**Details:**
- stdlib (Versions: 1.19.8)  
- Titre: golang: html/template: improper handling of special tags within script contexts  
- Date de publication: 2023-09-08T17:15:27Z  
- Dernière modification: 2023-11-25T11:15:17Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-39319  
#### CVE-2023-39326
**Gravité:** MEDIUM (5.3)  
**Applications Affectées:** velero  
**Details:**
- stdlib (Versions: 1.19.8)  
- Titre: golang: net/http/internal: Denial of Service (DoS) via Resource Consumption via HTTP requests  
- Date de publication: 2023-12-06T17:15:07Z  
- Dernière modification: 2024-01-20T04:15:07Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-39326  
#### CVE-2023-45284
**Gravité:** MEDIUM (5.3)  
**Applications Affectées:** velero  
**Details:**
- stdlib (Versions: 1.19.8)  
- Titre: On Windows, The IsLocal function does not correctly detect reserved de ...  
- Date de publication: 2023-11-09T17:15:08Z  
- Dernière modification: 2023-11-17T16:39:27Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45284  
#### CVE-2023-45289
**Gravité:** MEDIUM (5.3)  
**Applications Affectées:** velero  
**Details:**
- stdlib (Versions: 1.19.8)  
- Titre: golang: net/http/cookiejar: incorrect forwarding of sensitive headers and cookies on HTTP redirect  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:25Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45289  
#### CVE-2023-45290
**Gravité:** MEDIUM (5.3)  
**Applications Affectées:** velero  
**Details:**
- stdlib (Versions: 1.19.8)  
- Titre: golang: net/http: memory exhaustion in Request.ParseMultipartForm  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:26Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45290  
#### CVE-2024-24783
**Gravité:** MEDIUM (5.9)  
**Applications Affectées:** velero  
**Details:**
- stdlib (Versions: 1.19.8)  
- Titre: golang: crypto/x509: Verify panics on certificates with an unknown public key algorithm  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:29Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24783  
#### CVE-2024-24784
**Gravité:** MEDIUM (5.4)  
**Applications Affectées:** velero  
**Details:**
- stdlib (Versions: 1.19.8)  
- Titre: golang: net/mail: comments in display names are incorrectly handled  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:29Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24784  
#### CVE-2024-24785
**Gravité:** MEDIUM (6.5)  
**Applications Affectées:** velero  
**Details:**
- stdlib (Versions: 1.19.8)  
- Titre: golang: html/template: errors returned from MarshalJSON methods may break template escaping  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:29Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24785  
#### CVE-2024-24789
**Gravité:** MEDIUM (5.5)  
**Applications Affectées:** velero  
**Details:**
- stdlib (Versions: 1.19.8)  
- Titre: golang: archive/zip: Incorrect handling of certain ZIP files  
- Date de publication: 2024-06-05T16:15:10Z  
- Dernière modification: 2024-07-03T01:48:25Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24789  
#### CVE-2024-24791
**Gravité:** MEDIUM (N/A)  
**Applications Affectées:** velero  
**Details:**
- stdlib (Versions: 1.19.8)  
- Titre: net/http: Denial of service due to improper 100-continue handling in net/http  
- Date de publication: 2024-07-02T22:15:04Z  
- Dernière modification: 2024-07-03T12:53:24Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24791  
