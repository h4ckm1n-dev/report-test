
# CVE Report

05/07/2024
## Rapport sur les CVE pour le Cluster de Production

### Aperçu 
Ce rapport fournit une liste détaillée des vulnérabilités et expositions communes (CVE) présentes dans le cluster de production. Chaque entrée inclut l'identifiant CVE, l'application affectée, et les bibliothèques ou composants associés. Le rapport démontre que toutes les CVE répertoriées sont dues à des mises à jour non publiées par leurs mainteneurs respectifs. Nous utilisons un outil appelé Renovate pour être notifiés des mises à jour de composants disponibles sur notre cluster, garantissant que nous exécutons toujours la dernière version mise à disposition par le mainteneur.

### Métriques de Sévérité
| Type de CVE  | Nombre | Pourcentage du total |
|--------------|--------|----------------------|
| CVE Critiques | 9 | 5.0% |
| CVE Élevées  | 57 | 31.7% |
| CVE Moyennes  | 104 | 57.8% |
| CVE Basses  | 2 | 1.1% |
| CVE Inconnues  | 8 | 4.4% |

> **Note:** Le reste du rapport se concentre uniquement sur les CVE critiques et élevées afin de donner la priorité aux vulnérabilités qui présentent le plus grand risque pour la sécurité du système.

### Métriques Spécifiques aux Applications
| Application | CVE Critiques | CVE Élevées | Total CVE |
|-------------|---------------|-------------|-----------|
| kyverno | 1 | 20 | 21 |
| velero | 4 | 16 | 20 |
| amazon-cloudwatch | 0 | 6 | 6 |
| rabbitmq | 0 | 6 | 6 |
| keycloak | 0 | 4 | 4 |
| postgresql | 0 | 4 | 4 |
| trivy | 1 | 1 | 2 |
| kube-prometheus-stack | 1 | 0 | 1 |
| kube-system | 1 | 0 | 1 |
| policy-reporter | 1 | 0 | 1 |
| backend-ddf | 0 | 0 | 0 |
| gitlab-agent | 0 | 0 | 0 |

### Métriques Spécifiques aux Bibliothèques
| Bibliothèque | Applications Affectées | Total CVE |
|--------------|-----------------------|-----------|
| stdlib | trivy, gitlab-agent, kyverno, kube-system, kube-prometheus-stack, velero, policy-reporter | 7 |
| libssl3 | trivy, postgresql, rabbitmq, keycloak, backend-ddf | 5 |
| libgnutls30 | kyverno, postgresql, rabbitmq, keycloak | 4 |
| libsystemd0 | postgresql, rabbitmq, keycloak | 3 |
| libudev1 | postgresql, rabbitmq, keycloak | 3 |
| openssl | postgresql, rabbitmq, keycloak | 3 |
| curl | amazon-cloudwatch, rabbitmq | 2 |
| libcrypto3 | backend-ddf, trivy | 2 |
| github.com/Azure/azure-sdk-for-go/sdk/azidentity | trivy, kube-prometheus-stack | 2 |
| golang.org/x/net | velero, kyverno | 2 |
| google.golang.org/protobuf | velero, kyverno | 2 |
| glibc | amazon-cloudwatch | 1 |
| glibc-common | amazon-cloudwatch | 1 |
| glibc-langpack-en | amazon-cloudwatch | 1 |
| glibc-minimal-langpack | amazon-cloudwatch | 1 |
| libcrypt | amazon-cloudwatch | 1 |
| libcurl | amazon-cloudwatch | 1 |
| libnghttp2 | amazon-cloudwatch | 1 |
| openssl11-devel | amazon-cloudwatch | 1 |
| openssl11-libs | amazon-cloudwatch | 1 |
| bsdutils | kyverno | 1 |
| libblkid1 | kyverno | 1 |
| libc-bin | kyverno | 1 |
| libc6 | kyverno | 1 |
| libcurl3-gnutls | kyverno | 1 |
| libmount1 | kyverno | 1 |
| libperl5.32 | kyverno | 1 |
| libsmartcols1 | kyverno | 1 |
| libssh2-1 | kyverno | 1 |
| libuuid1 | kyverno | 1 |
| mount | kyverno | 1 |
| perl | kyverno | 1 |
| perl-base | kyverno | 1 |
| perl-modules-5.32 | kyverno | 1 |
| tar | kyverno | 1 |
| util-linux | kyverno | 1 |
| libcurl4 | rabbitmq | 1 |
| busybox | trivy | 1 |
| busybox-binsh | trivy | 1 |
| ssl_client | trivy | 1 |
| github.com/hashicorp/go-getter | trivy | 1 |
| google.golang.org/grpc | velero | 1 |

### Observations Clés
* kyverno est l'application la plus affectée avec un total de 21 CVE.
* velero a également un nombre significatif de CVE (20).
* amazon-cloudwatch a également un nombre significatif de CVE (6).
* La majorité des CVE sont classées comme étant de haute gravité (32%), avec seulement une petite fraction étant critiques (5%).
* La bibliothèque stdlib est récurrente à travers plusieurs CVE et applications (trivy, gitlab-agent, kyverno, kube-system, kube-prometheus-stack, velero, policy-reporter), indiquant des vulnérabilités communes dans cette bibliothèque.
* La bibliothèque libssl3 est récurrente à travers plusieurs CVE et applications (trivy, postgresql, rabbitmq, keycloak, backend-ddf), indiquant des vulnérabilités communes dans cette bibliothèque.
* La bibliothèque libgnutls30 est récurrente à travers plusieurs CVE et applications (kyverno, postgresql, rabbitmq, keycloak), indiquant des vulnérabilités communes dans cette bibliothèque.

## Liste Détaillée des CVE
### Sommaire

| CVE ID | Applications |
|--------|--------------|
| [CVE-2024-24790](#cve-2024-24790) | trivy, kube-system, kube-prometheus-stack, velero, policy-reporter, kyverno |
| [CVE-2023-24540](#cve-2023-24540) | velero |
| [CVE-2024-2961](#cve-2024-2961) | amazon-cloudwatch, kyverno |
| [CVE-2024-28085](#cve-2024-28085) | kyverno |
| [CVE-2023-47038](#cve-2023-47038) | kyverno |
| [CVE-2023-29403](#cve-2023-29403) | velero |
| [CVE-2024-6257](#cve-2024-6257) | trivy |
| [CVE-2024-33599](#cve-2024-33599) | kyverno |
| [CVE-2023-50387](#cve-2023-50387) | postgresql, rabbitmq, keycloak |
| [CVE-2023-50868](#cve-2023-50868) | postgresql, rabbitmq, keycloak |
| [CVE-2024-2398](#cve-2024-2398) | rabbitmq, kyverno |
| [CVE-2024-0553](#cve-2024-0553) | kyverno |
| [CVE-2024-0567](#cve-2024-0567) | kyverno |
| [CVE-2020-22218](#cve-2020-22218) | kyverno |
| [CVE-2023-39325](#cve-2023-39325) | velero |
| [CVE-2023-45283](#cve-2023-45283) | velero |
| [CVE-2023-45287](#cve-2023-45287) | velero |
| [CVE-2023-45288](#cve-2023-45288) | velero, kyverno |
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
- Date de publication: 2024-06-05T16:15:10Z)
- Dernière modification: 2024-06-18T17:59:12Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24790
#### CVE-2024-24790
**Gravité:** CRITICAL (9.8)
**Applications Affectées:** kube-system
**Details:**
- stdlib (Versions: 1.22.3)
- Titre: golang: net/netip: Unexpected behavior from Is methods for IPv4-mapped IPv6 addresses
- Date de publication: 2024-06-05T16:15:10Z)
- Dernière modification: 2024-06-18T17:59:12Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24790
#### CVE-2024-24790
**Gravité:** CRITICAL (9.8)
**Applications Affectées:** kyverno
**Details:**
- stdlib (Versions: 1.20.12)
- Titre: golang: net/netip: Unexpected behavior from Is methods for IPv4-mapped IPv6 addresses
- Date de publication: 2024-06-05T16:15:10Z)
- Dernière modification: 2024-06-18T17:59:12Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24790
#### CVE-2024-24790
**Gravité:** CRITICAL (9.8)
**Applications Affectées:** policy-reporter
**Details:**
- stdlib (Versions: 1.22.3)
- Titre: golang: net/netip: Unexpected behavior from Is methods for IPv4-mapped IPv6 addresses
- Date de publication: 2024-06-05T16:15:10Z)
- Dernière modification: 2024-06-18T17:59:12Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24790
#### CVE-2024-24790
**Gravité:** CRITICAL (9.8)
**Applications Affectées:** trivy
**Details:**
- stdlib (Versions: 1.22.3)
- Titre: golang: net/netip: Unexpected behavior from Is methods for IPv4-mapped IPv6 addresses
- Date de publication: 2024-06-05T16:15:10Z)
- Dernière modification: 2024-06-18T17:59:12Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24790
#### CVE-2023-24540
**Gravité:** CRITICAL (9.8)
**Applications Affectées:** velero
**Details:**
- stdlib (Versions: 1.19.8)
- Titre: golang: html/template: improper handling of JavaScript whitespace
- Date de publication: 2023-05-11T16:15:09Z)
- Dernière modification: 2023-11-07T04:08:32Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-24540
#### CVE-2024-24790
**Gravité:** CRITICAL (9.8)
**Applications Affectées:** velero
**Details:**
- stdlib (Versions: 1.19.8)
- Titre: golang: net/netip: Unexpected behavior from Is methods for IPv4-mapped IPv6 addresses
- Date de publication: 2024-06-05T16:15:10Z)
- Dernière modification: 2024-06-18T17:59:12Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24790
#### CVE-2023-24540
**Gravité:** CRITICAL (9.8)
**Applications Affectées:** velero
**Details:**
- stdlib (Versions: 1.19.8)
- Titre: golang: html/template: improper handling of JavaScript whitespace
- Date de publication: 2023-05-11T16:15:09Z)
- Dernière modification: 2023-11-07T04:08:32Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-24540
#### CVE-2024-24790
**Gravité:** CRITICAL (9.8)
**Applications Affectées:** velero
**Details:**
- stdlib (Versions: 1.19.8)
- Titre: golang: net/netip: Unexpected behavior from Is methods for IPv4-mapped IPv6 addresses
- Date de publication: 2024-06-05T16:15:10Z)
- Dernière modification: 2024-06-18T17:59:12Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24790

### CVE Élevées
#### CVE-2024-2961
**Gravité:** HIGH (8.8)
**Applications Affectées:** amazon-cloudwatch
**Details:**
- glibc (Versions: 2.26-63.amzn2.0.1)
- Titre: glibc: Out of bounds write in iconv may lead to remote code execution
- Date de publication: 2024-04-17T18:15:15Z)
- Dernière modification: 2024-07-03T01:53:40Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-2961
#### CVE-2024-2961
**Gravité:** HIGH (8.8)
**Applications Affectées:** amazon-cloudwatch
**Details:**
- glibc-common (Versions: 2.26-63.amzn2.0.1)
- Titre: glibc: Out of bounds write in iconv may lead to remote code execution
- Date de publication: 2024-04-17T18:15:15Z)
- Dernière modification: 2024-07-03T01:53:40Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-2961
#### CVE-2024-2961
**Gravité:** HIGH (8.8)
**Applications Affectées:** amazon-cloudwatch
**Details:**
- glibc-langpack-en (Versions: 2.26-63.amzn2.0.1)
- Titre: glibc: Out of bounds write in iconv may lead to remote code execution
- Date de publication: 2024-04-17T18:15:15Z)
- Dernière modification: 2024-07-03T01:53:40Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-2961
#### CVE-2024-2961
**Gravité:** HIGH (8.8)
**Applications Affectées:** amazon-cloudwatch
**Details:**
- glibc-minimal-langpack (Versions: 2.26-63.amzn2.0.1)
- Titre: glibc: Out of bounds write in iconv may lead to remote code execution
- Date de publication: 2024-04-17T18:15:15Z)
- Dernière modification: 2024-07-03T01:53:40Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-2961
#### CVE-2024-2961
**Gravité:** HIGH (8.8)
**Applications Affectées:** amazon-cloudwatch
**Details:**
- libcrypt (Versions: 2.26-63.amzn2.0.1)
- Titre: glibc: Out of bounds write in iconv may lead to remote code execution
- Date de publication: 2024-04-17T18:15:15Z)
- Dernière modification: 2024-07-03T01:53:40Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-2961
#### CVE-2024-2961
**Gravité:** HIGH (8.8)
**Applications Affectées:** kyverno
**Details:**
- libc-bin (Versions: 2.31-13+deb11u7)
- Titre: glibc: Out of bounds write in iconv may lead to remote code execution
- Date de publication: 2024-04-17T18:15:15Z)
- Dernière modification: 2024-07-03T01:53:40Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-2961
#### CVE-2024-2961
**Gravité:** HIGH (8.8)
**Applications Affectées:** kyverno
**Details:**
- libc6 (Versions: 2.31-13+deb11u7)
- Titre: glibc: Out of bounds write in iconv may lead to remote code execution
- Date de publication: 2024-04-17T18:15:15Z)
- Dernière modification: 2024-07-03T01:53:40Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-2961
#### CVE-2024-28085
**Gravité:** HIGH (8.4)
**Applications Affectées:** kyverno
**Details:**
- bsdutils (Versions: 1:2.36.1-8+deb11u1)
- Titre: util-linux: CVE-2024-28085: wall: escape sequence injection
- Date de publication: 2024-03-27T19:15:48Z)
- Dernière modification: 2024-06-10T17:16:24Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-28085
#### CVE-2024-28085
**Gravité:** HIGH (8.4)
**Applications Affectées:** kyverno
**Details:**
- libblkid1 (Versions: 2.36.1-8+deb11u1)
- Titre: util-linux: CVE-2024-28085: wall: escape sequence injection
- Date de publication: 2024-03-27T19:15:48Z)
- Dernière modification: 2024-06-10T17:16:24Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-28085
#### CVE-2024-28085
**Gravité:** HIGH (8.4)
**Applications Affectées:** kyverno
**Details:**
- libmount1 (Versions: 2.36.1-8+deb11u1)
- Titre: util-linux: CVE-2024-28085: wall: escape sequence injection
- Date de publication: 2024-03-27T19:15:48Z)
- Dernière modification: 2024-06-10T17:16:24Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-28085
#### CVE-2024-28085
**Gravité:** HIGH (8.4)
**Applications Affectées:** kyverno
**Details:**
- libsmartcols1 (Versions: 2.36.1-8+deb11u1)
- Titre: util-linux: CVE-2024-28085: wall: escape sequence injection
- Date de publication: 2024-03-27T19:15:48Z)
- Dernière modification: 2024-06-10T17:16:24Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-28085
#### CVE-2024-28085
**Gravité:** HIGH (8.4)
**Applications Affectées:** kyverno
**Details:**
- libuuid1 (Versions: 2.36.1-8+deb11u1)
- Titre: util-linux: CVE-2024-28085: wall: escape sequence injection
- Date de publication: 2024-03-27T19:15:48Z)
- Dernière modification: 2024-06-10T17:16:24Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-28085
#### CVE-2024-28085
**Gravité:** HIGH (8.4)
**Applications Affectées:** kyverno
**Details:**
- mount (Versions: 2.36.1-8+deb11u1)
- Titre: util-linux: CVE-2024-28085: wall: escape sequence injection
- Date de publication: 2024-03-27T19:15:48Z)
- Dernière modification: 2024-06-10T17:16:24Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-28085
#### CVE-2024-28085
**Gravité:** HIGH (8.4)
**Applications Affectées:** kyverno
**Details:**
- util-linux (Versions: 2.36.1-8+deb11u1)
- Titre: util-linux: CVE-2024-28085: wall: escape sequence injection
- Date de publication: 2024-03-27T19:15:48Z)
- Dernière modification: 2024-06-10T17:16:24Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-28085
#### CVE-2023-47038
**Gravité:** HIGH (7.8)
**Applications Affectées:** kyverno
**Details:**
- libperl5.32 (Versions: 5.32.1-4+deb11u2)
- Titre: perl: Write past buffer end via illegal user-defined Unicode property
- Date de publication: 2023-12-18T14:15:08Z)
- Dernière modification: 2024-05-30T14:15:09Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-47038
#### CVE-2023-47038
**Gravité:** HIGH (7.8)
**Applications Affectées:** kyverno
**Details:**
- perl (Versions: 5.32.1-4+deb11u2)
- Titre: perl: Write past buffer end via illegal user-defined Unicode property
- Date de publication: 2023-12-18T14:15:08Z)
- Dernière modification: 2024-05-30T14:15:09Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-47038
#### CVE-2023-47038
**Gravité:** HIGH (7.8)
**Applications Affectées:** kyverno
**Details:**
- perl-base (Versions: 5.32.1-4+deb11u2)
- Titre: perl: Write past buffer end via illegal user-defined Unicode property
- Date de publication: 2023-12-18T14:15:08Z)
- Dernière modification: 2024-05-30T14:15:09Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-47038
#### CVE-2023-47038
**Gravité:** HIGH (7.8)
**Applications Affectées:** kyverno
**Details:**
- perl-modules-5.32 (Versions: 5.32.1-4+deb11u2)
- Titre: perl: Write past buffer end via illegal user-defined Unicode property
- Date de publication: 2023-12-18T14:15:08Z)
- Dernière modification: 2024-05-30T14:15:09Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-47038
#### CVE-2023-29403
**Gravité:** HIGH (7.8)
**Applications Affectées:** velero
**Details:**
- stdlib (Versions: 1.19.8)
- Titre: golang: runtime: unexpected behavior of setuid/setgid binaries
- Date de publication: 2023-06-08T21:15:16Z)
- Dernière modification: 2023-11-25T11:15:14Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-29403
#### CVE-2023-29403
**Gravité:** HIGH (7.8)
**Applications Affectées:** velero
**Details:**
- stdlib (Versions: 1.19.8)
- Titre: golang: runtime: unexpected behavior of setuid/setgid binaries
- Date de publication: 2023-06-08T21:15:16Z)
- Dernière modification: 2023-11-25T11:15:14Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-29403
#### CVE-2024-6257
**Gravité:** HIGH (7.7)
**Applications Affectées:** trivy
**Details:**
- github.com/hashicorp/go-getter (Versions: v1.7.4)
- Titre: hashicorp/go-getter: Arbitrary command execution through local git config file
- Date de publication: 2024-06-25T17:15:10Z)
- Dernière modification: 2024-06-25T18:50:42Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-6257
#### CVE-2024-33599
**Gravité:** HIGH (7.6)
**Applications Affectées:** kyverno
**Details:**
- libc-bin (Versions: 2.31-13+deb11u7)
- Titre: glibc: stack-based buffer overflow in netgroup cache
- Date de publication: 2024-05-06T20:15:11Z)
- Dernière modification: 2024-06-30T15:15:09Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-33599
#### CVE-2024-33599
**Gravité:** HIGH (7.6)
**Applications Affectées:** kyverno
**Details:**
- libc6 (Versions: 2.31-13+deb11u7)
- Titre: glibc: stack-based buffer overflow in netgroup cache
- Date de publication: 2024-05-06T20:15:11Z)
- Dernière modification: 2024-06-30T15:15:09Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-33599
#### CVE-2023-50387
**Gravité:** HIGH (7.5)
**Applications Affectées:** keycloak
**Details:**
- libsystemd0 (Versions: 252.22-1~deb12u1)
- Titre: bind9: KeyTrap - Extreme CPU consumption in DNSSEC validator
- Date de publication: 2024-02-14T16:15:45Z)
- Dernière modification: 2024-06-10T17:16:15Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-50387
#### CVE-2023-50868
**Gravité:** HIGH (7.5)
**Applications Affectées:** keycloak
**Details:**
- libsystemd0 (Versions: 252.22-1~deb12u1)
- Titre: bind9: Preparing an NSEC3 closest encloser proof can exhaust CPU resources
- Date de publication: 2024-02-14T16:15:45Z)
- Dernière modification: 2024-06-10T17:16:16Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-50868
#### CVE-2023-50387
**Gravité:** HIGH (7.5)
**Applications Affectées:** keycloak
**Details:**
- libudev1 (Versions: 252.22-1~deb12u1)
- Titre: bind9: KeyTrap - Extreme CPU consumption in DNSSEC validator
- Date de publication: 2024-02-14T16:15:45Z)
- Dernière modification: 2024-06-10T17:16:15Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-50387
#### CVE-2023-50868
**Gravité:** HIGH (7.5)
**Applications Affectées:** keycloak
**Details:**
- libudev1 (Versions: 252.22-1~deb12u1)
- Titre: bind9: Preparing an NSEC3 closest encloser proof can exhaust CPU resources
- Date de publication: 2024-02-14T16:15:45Z)
- Dernière modification: 2024-06-10T17:16:16Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-50868
#### CVE-2024-2398
**Gravité:** HIGH (7.5)
**Applications Affectées:** kyverno
**Details:**
- libcurl3-gnutls (Versions: 7.74.0-1.3+deb11u11)
- Titre: curl: HTTP/2 push headers memory-leak
- Date de publication: 2024-03-27T08:15:41Z)
- Dernière modification: 2024-07-03T01:53:12Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-2398
#### CVE-2024-0553
**Gravité:** HIGH (7.5)
**Applications Affectées:** kyverno
**Details:**
- libgnutls30 (Versions: 3.7.1-5+deb11u3)
- Titre: gnutls: incomplete fix for CVE-2023-5981
- Date de publication: 2024-01-16T12:15:45Z)
- Dernière modification: 2024-06-27T12:15:17Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-0553
#### CVE-2024-0567
**Gravité:** HIGH (7.5)
**Applications Affectées:** kyverno
**Details:**
- libgnutls30 (Versions: 3.7.1-5+deb11u3)
- Titre: gnutls: rejects certificate chain with distributed trust
- Date de publication: 2024-01-16T14:15:48Z)
- Dernière modification: 2024-06-27T12:15:17Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-0567
#### CVE-2020-22218
**Gravité:** HIGH (7.5)
**Applications Affectées:** kyverno
**Details:**
- libssh2-1 (Versions: 1.9.0-2)
- Titre: libssh2: use-of-uninitialized-value in _libssh2_transport_read
- Date de publication: 2023-08-22T19:16:19Z)
- Dernière modification: 2023-10-06T15:15:12Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2020-22218
#### CVE-2023-50387
**Gravité:** HIGH (7.5)
**Applications Affectées:** postgresql
**Details:**
- libsystemd0 (Versions: 252.22-1~deb12u1)
- Titre: bind9: KeyTrap - Extreme CPU consumption in DNSSEC validator
- Date de publication: 2024-02-14T16:15:45Z)
- Dernière modification: 2024-06-10T17:16:15Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-50387
#### CVE-2023-50868
**Gravité:** HIGH (7.5)
**Applications Affectées:** postgresql
**Details:**
- libsystemd0 (Versions: 252.22-1~deb12u1)
- Titre: bind9: Preparing an NSEC3 closest encloser proof can exhaust CPU resources
- Date de publication: 2024-02-14T16:15:45Z)
- Dernière modification: 2024-06-10T17:16:16Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-50868
#### CVE-2023-50387
**Gravité:** HIGH (7.5)
**Applications Affectées:** postgresql
**Details:**
- libudev1 (Versions: 252.22-1~deb12u1)
- Titre: bind9: KeyTrap - Extreme CPU consumption in DNSSEC validator
- Date de publication: 2024-02-14T16:15:45Z)
- Dernière modification: 2024-06-10T17:16:15Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-50387
#### CVE-2023-50868
**Gravité:** HIGH (7.5)
**Applications Affectées:** postgresql
**Details:**
- libudev1 (Versions: 252.22-1~deb12u1)
- Titre: bind9: Preparing an NSEC3 closest encloser proof can exhaust CPU resources
- Date de publication: 2024-02-14T16:15:45Z)
- Dernière modification: 2024-06-10T17:16:16Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-50868
#### CVE-2024-2398
**Gravité:** HIGH (7.5)
**Applications Affectées:** rabbitmq
**Details:**
- curl (Versions: 7.88.1-10+deb12u5)
- Titre: curl: HTTP/2 push headers memory-leak
- Date de publication: 2024-03-27T08:15:41Z)
- Dernière modification: 2024-07-03T01:53:12Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-2398
#### CVE-2024-2398
**Gravité:** HIGH (7.5)
**Applications Affectées:** rabbitmq
**Details:**
- libcurl4 (Versions: 7.88.1-10+deb12u5)
- Titre: curl: HTTP/2 push headers memory-leak
- Date de publication: 2024-03-27T08:15:41Z)
- Dernière modification: 2024-07-03T01:53:12Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-2398
#### CVE-2023-50387
**Gravité:** HIGH (7.5)
**Applications Affectées:** rabbitmq
**Details:**
- libsystemd0 (Versions: 252.22-1~deb12u1)
- Titre: bind9: KeyTrap - Extreme CPU consumption in DNSSEC validator
- Date de publication: 2024-02-14T16:15:45Z)
- Dernière modification: 2024-06-10T17:16:15Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-50387
#### CVE-2023-50868
**Gravité:** HIGH (7.5)
**Applications Affectées:** rabbitmq
**Details:**
- libsystemd0 (Versions: 252.22-1~deb12u1)
- Titre: bind9: Preparing an NSEC3 closest encloser proof can exhaust CPU resources
- Date de publication: 2024-02-14T16:15:45Z)
- Dernière modification: 2024-06-10T17:16:16Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-50868
#### CVE-2023-50387
**Gravité:** HIGH (7.5)
**Applications Affectées:** rabbitmq
**Details:**
- libudev1 (Versions: 252.22-1~deb12u1)
- Titre: bind9: KeyTrap - Extreme CPU consumption in DNSSEC validator
- Date de publication: 2024-02-14T16:15:45Z)
- Dernière modification: 2024-06-10T17:16:15Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-50387
#### CVE-2023-50868
**Gravité:** HIGH (7.5)
**Applications Affectées:** rabbitmq
**Details:**
- libudev1 (Versions: 252.22-1~deb12u1)
- Titre: bind9: Preparing an NSEC3 closest encloser proof can exhaust CPU resources
- Date de publication: 2024-02-14T16:15:45Z)
- Dernière modification: 2024-06-10T17:16:16Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-50868
#### CVE-2023-39325
**Gravité:** HIGH (7.5)
**Applications Affectées:** velero
**Details:**
- stdlib (Versions: 1.19.8)
- Titre: golang: net/http, x/net/http2: rapid stream resets can cause excessive work (CVE-2023-44487)
- Date de publication: 2023-10-11T22:15:09Z)
- Dernière modification: 2024-04-28T04:15:09Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-39325
#### CVE-2023-45283
**Gravité:** HIGH (7.5)
**Applications Affectées:** velero
**Details:**
- stdlib (Versions: 1.19.8)
- Titre: The filepath package does not recognize paths with a \??\ prefix as sp ...
- Date de publication: 2023-11-09T17:15:08Z)
- Dernière modification: 2023-12-14T10:15:07Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45283
#### CVE-2023-45287
**Gravité:** HIGH (7.5)
**Applications Affectées:** velero
**Details:**
- stdlib (Versions: 1.19.8)
- Titre: golang: crypto/tls: Timing Side Channel attack in RSA based TLS key exchanges.
- Date de publication: 2023-12-05T17:15:08Z)
- Dernière modification: 2024-01-12T14:15:48Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45287
#### CVE-2023-45288
**Gravité:** HIGH (7.5)
**Applications Affectées:** velero
**Details:**
- stdlib (Versions: 1.19.8)
- Titre: golang: net/http, x/net/http2: unlimited number of CONTINUATION frames causes DoS
- Date de publication: 2024-04-04T21:15:16Z)
- Dernière modification: 2024-05-01T18:15:10Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45288
#### CVE-2023-39325
**Gravité:** HIGH (7.5)
**Applications Affectées:** velero
**Details:**
- golang.org/x/net (Versions: v0.7.0)
- Titre: golang: net/http, x/net/http2: rapid stream resets can cause excessive work (CVE-2023-44487)
- Date de publication: 2023-10-11T22:15:09Z)
- Dernière modification: 2024-04-28T04:15:09Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-39325
#### GHSA-m425-mq94-257g
**Gravité:** HIGH (7.5)
**Applications Affectées:** velero
**Details:**
- google.golang.org/grpc (Versions: v1.40.0)
- Titre: gRPC-Go HTTP/2 Rapid Reset vulnerability
- Date de publication: )
- Dernière modification: )
- Lien primaire: https://github.com/advisories/GHSA-m425-mq94-257g
#### CVE-2023-39325
**Gravité:** HIGH (7.5)
**Applications Affectées:** velero
**Details:**
- stdlib (Versions: 1.19.8)
- Titre: golang: net/http, x/net/http2: rapid stream resets can cause excessive work (CVE-2023-44487)
- Date de publication: 2023-10-11T22:15:09Z)
- Dernière modification: 2024-04-28T04:15:09Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-39325
#### CVE-2023-45283
**Gravité:** HIGH (7.5)
**Applications Affectées:** velero
**Details:**
- stdlib (Versions: 1.19.8)
- Titre: The filepath package does not recognize paths with a \??\ prefix as sp ...
- Date de publication: 2023-11-09T17:15:08Z)
- Dernière modification: 2023-12-14T10:15:07Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45283
#### CVE-2023-45287
**Gravité:** HIGH (7.5)
**Applications Affectées:** velero
**Details:**
- stdlib (Versions: 1.19.8)
- Titre: golang: crypto/tls: Timing Side Channel attack in RSA based TLS key exchanges.
- Date de publication: 2023-12-05T17:15:08Z)
- Dernière modification: 2024-01-12T14:15:48Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45287
#### CVE-2023-45288
**Gravité:** HIGH (7.5)
**Applications Affectées:** velero
**Details:**
- stdlib (Versions: 1.19.8)
- Titre: golang: net/http, x/net/http2: unlimited number of CONTINUATION frames causes DoS
- Date de publication: 2024-04-04T21:15:16Z)
- Dernière modification: 2024-05-01T18:15:10Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45288
#### CVE-2023-24539
**Gravité:** HIGH (7.3)
**Applications Affectées:** velero
**Details:**
- stdlib (Versions: 1.19.8)
- Titre: golang: html/template: improper sanitization of CSS values
- Date de publication: 2023-05-11T16:15:09Z)
- Dernière modification: 2023-11-07T04:08:32Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-24539
#### CVE-2023-29400
**Gravité:** HIGH (7.3)
**Applications Affectées:** velero
**Details:**
- stdlib (Versions: 1.19.8)
- Titre: golang: html/template: improper handling of empty HTML attributes
- Date de publication: 2023-05-11T16:15:09Z)
- Dernière modification: 2023-11-07T04:11:10Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-29400
#### CVE-2023-24539
**Gravité:** HIGH (7.3)
**Applications Affectées:** velero
**Details:**
- stdlib (Versions: 1.19.8)
- Titre: golang: html/template: improper sanitization of CSS values
- Date de publication: 2023-05-11T16:15:09Z)
- Dernière modification: 2023-11-07T04:08:32Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-24539
#### CVE-2023-29400
**Gravité:** HIGH (7.3)
**Applications Affectées:** velero
**Details:**
- stdlib (Versions: 1.19.8)
- Titre: golang: html/template: improper handling of empty HTML attributes
- Date de publication: 2023-05-11T16:15:09Z)
- Dernière modification: 2023-11-07T04:11:10Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-29400
#### CVE-2024-28182
**Gravité:** HIGH (5.3)
**Applications Affectées:** amazon-cloudwatch
**Details:**
- libnghttp2 (Versions: 1.41.0-1.amzn2.0.4)
- Titre: nghttp2: CONTINUATION frames DoS
- Date de publication: 2024-04-04T15:15:38Z)
- Dernière modification: 2024-05-01T18:15:17Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-28182
#### CVE-2023-45288
**Gravité:** HIGH (5.3)
**Applications Affectées:** kyverno
**Details:**
- stdlib (Versions: 1.20.12)
- Titre: golang: net/http, x/net/http2: unlimited number of CONTINUATION frames causes DoS
- Date de publication: 2024-04-04T21:15:16Z)
- Dernière modification: 2024-05-01T18:15:10Z)
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45288
