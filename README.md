
# CVE Report

09/07/2024
## Rapport sur les CVE pour le Cluster de Production

### Aperçu 
Ce rapport fournit une liste détaillée des vulnérabilités et expositions communes (CVE) présentes dans le cluster de production. Chaque entrée inclut l'identifiant CVE, l'application affectée, et les bibliothèques ou composants associés. Le rapport démontre que toutes les CVE répertoriées sont dues à des mises à jour non publiées par leurs mainteneurs respectifs. Nous utilisons un outil appelé Renovate pour être notifiés des mises à jour de composants disponibles sur notre cluster, garantissant que nous exécutons toujours la dernière version mise à disposition par le mainteneur.

## Rapport sur les Ingress Kubernetes
| Namespace | Ingress Name | Host | Address | Type |
|-----------|--------------|------|---------|------|
| kps | blackbox-prometheus-blackbox-exporter | blackbox.h4ckm1n.org | 192.168.49.2 | Privé |
| kps | kps-prometheus | prometheus.h4ckm1n.org | 192.168.49.2 | Privé |

**Note : Seuls les points de terminaison publics sont sensibles, car les autres points de terminaison ne sont accessibles que via un VPN.**

### Endpoints Sensibles

#### Privés
- **Namespace:** kps
  - **Ingress Name:** blackbox-prometheus-blackbox-exporter
  - **Host:** blackbox.h4ckm1n.org
  - **Address:** 192.168.49.2
- **Namespace:** kps
  - **Ingress Name:** kps-prometheus
  - **Host:** prometheus.h4ckm1n.org
  - **Address:** 192.168.49.2

Il n'y a actuellement aucun point de terminaison public dans ce rapport.


### Métriques de Sévérité
| Type de CVE  | Nombre | Pourcentage du total |
|--------------|--------|----------------------|
| CVE Critiques | 6 | 6.5% |
| CVE Élevées  | 8 | 8.7% |
| CVE Moyennes  | 75 | 81.5% |
| CVE Basses  | 3 | 3.3% |
| CVE Inconnues  | 0 | 0.0% |

### Métriques Spécifiques aux namespaces
| Application | CVE Critiques | CVE Élevées | CVE Moyennes | CVE Basses | Total CVE |
|-------------|---------------|-------------|--------------|-----------|-----------|
| kube-system | 5 | 5 | 43 | 0 | 53 |
| kps | 0 | 2 | 22 | 3 | 27 |
| ingress-nginx | 1 | 1 | 9 | 0 | 11 |
| trivy-system | 0 | 0 | 1 | 0 | 1 |

### Métriques Spécifiques aux Bibliothèques
| Bibliothèque | namespaces Affectées | Total CVE |
|--------------|-----------------------|-----------|
| stdlib | ingress-nginx, kube-system, trivy-system | 9 |
| busybox | kps | 4 |
| busybox-binsh | kps | 4 |
| libcrypto3 | kps | 4 |
| libssl3 | kps | 4 |
| ssl_client | kps | 4 |
| libexpat | kps | 3 |
| golang.org/x/net | ingress-nginx, kube-system | 1 |
| google.golang.org/protobuf | ingress-nginx, kube-system | 1 |
| certifi | kps | 1 |
| idna | kps | 1 |
| requests | kps | 1 |
| urllib3 | kps | 1 |

### Observations Clés
* La majorité des CVE sont classées comme étant de gravité moyenne (82%), avec 7% critiques, 9% élevées, 82% moyennes, 3% basses, et 0% inconnues.
* kube-system est l'application la plus affectée avec un total de 53 CVE, incluant 5 critiques, 5 élevées, 43 moyennes et 0 basses.
* kps a également un nombre significatif de CVE (27), incluant 0 critiques, 2 élevées, 22 moyennes et 3 basses.
* ingress-nginx a également un nombre significatif de CVE (11), incluant 1 critiques, 1 élevées, 9 moyennes et 0 basses.
* La bibliothèque stdlib est récurrente à travers 9 CVE et 3 namespaces (ingress-nginx, kube-system, trivy-system), indiquant des vulnérabilités communes dans cette bibliothèque.
* La bibliothèque busybox est récurrente à travers 4 CVE et 1 namespaces (kps), indiquant des vulnérabilités communes dans cette bibliothèque.
* La bibliothèque busybox-binsh est récurrente à travers 4 CVE et 1 namespaces (kps), indiquant des vulnérabilités communes dans cette bibliothèque.

## Liste Détaillée des CVE
### CVE Critiques

| CVE ID | namespaces |
|--------|--------------|
| [CVE-2024-24790](#cve-2024-24790) | ingress-nginx, kube-system |
### CVE Élevées

| CVE ID | namespaces |
|--------|--------------|
| [CVE-2023-45288](#cve-2023-45288) | ingress-nginx, kube-system |
| [CVE-2023-52425](#cve-2023-52425) | kps |
| [CVE-2024-28757](#cve-2024-28757) | kps |
### CVE Moyennes

| CVE ID | namespaces |
|--------|--------------|
| [CVE-2023-45288](#cve-2023-45288) | ingress-nginx, kube-system |
| [CVE-2024-24786](#cve-2024-24786) | ingress-nginx, kube-system |
| [CVE-2023-45289](#cve-2023-45289) | ingress-nginx, kube-system |
| [CVE-2023-45290](#cve-2023-45290) | ingress-nginx, kube-system |
| [CVE-2024-24783](#cve-2024-24783) | ingress-nginx, kube-system |
| [CVE-2024-24784](#cve-2024-24784) | ingress-nginx, kube-system |
| [CVE-2024-24785](#cve-2024-24785) | ingress-nginx, kube-system |
| [CVE-2024-24789](#cve-2024-24789) | ingress-nginx, kube-system |
| [CVE-2024-24791](#cve-2024-24791) | ingress-nginx, kube-system, trivy-system |
| [CVE-2023-42363](#cve-2023-42363) | kps |
| [CVE-2023-42364](#cve-2023-42364) | kps |
| [CVE-2023-42365](#cve-2023-42365) | kps |
| [CVE-2023-42366](#cve-2023-42366) | kps |
| [CVE-2024-4603](#cve-2024-4603) | kps |
| [CVE-2024-4741](#cve-2024-4741) | kps |
| [CVE-2024-5535](#cve-2024-5535) | kps |
| [CVE-2023-52426](#cve-2023-52426) | kps |
| [CVE-2024-3651](#cve-2024-3651) | kps |
| [CVE-2024-35195](#cve-2024-35195) | kps |
| [CVE-2024-37891](#cve-2024-37891) | kps |
### CVE Basses

| CVE ID | namespaces |
|--------|--------------|
| [CVE-2024-2511](#cve-2024-2511) | kps |
| [CVE-2024-39689](#cve-2024-39689) | kps |
### CVE Critiques
#### CVE-2024-24790
**Gravité:** CRITICAL (9.8)  
**namespaces Affectées:** ingress-nginx  
**Details:**
- stdlib (Versions: 1.21.6)  
- Titre: golang: net/netip: Unexpected behavior from Is methods for IPv4-mapped IPv6 addresses  
- Date de publication: 2024-06-05T16:15:10Z  
- Dernière modification: 2024-06-18T17:59:12Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24790  
#### CVE-2024-24790
**Gravité:** CRITICAL (9.8)  
**namespaces Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/netip: Unexpected behavior from Is methods for IPv4-mapped IPv6 addresses  
- Date de publication: 2024-06-05T16:15:10Z  
- Dernière modification: 2024-06-18T17:59:12Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24790  
#### CVE-2024-24790
**Gravité:** CRITICAL (9.8)  
**namespaces Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/netip: Unexpected behavior from Is methods for IPv4-mapped IPv6 addresses  
- Date de publication: 2024-06-05T16:15:10Z  
- Dernière modification: 2024-06-18T17:59:12Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24790  
#### CVE-2024-24790
**Gravité:** CRITICAL (9.8)  
**namespaces Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/netip: Unexpected behavior from Is methods for IPv4-mapped IPv6 addresses  
- Date de publication: 2024-06-05T16:15:10Z  
- Dernière modification: 2024-06-18T17:59:12Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24790  
#### CVE-2024-24790
**Gravité:** CRITICAL (9.8)  
**namespaces Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/netip: Unexpected behavior from Is methods for IPv4-mapped IPv6 addresses  
- Date de publication: 2024-06-05T16:15:10Z  
- Dernière modification: 2024-06-18T17:59:12Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24790  
#### CVE-2024-24790
**Gravité:** CRITICAL (9.8)  
**namespaces Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/netip: Unexpected behavior from Is methods for IPv4-mapped IPv6 addresses  
- Date de publication: 2024-06-05T16:15:10Z  
- Dernière modification: 2024-06-18T17:59:12Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24790  
### CVE Élevées
#### CVE-2023-45288
**Gravité:** HIGH (7.5)  
**namespaces Affectées:** ingress-nginx  
**Details:**
- stdlib (Versions: 1.21.6)  
- Titre: golang: net/http, x/net/http2: unlimited number of CONTINUATION frames causes DoS  
- Date de publication: 2024-04-04T21:15:16Z  
- Dernière modification: 2024-05-01T18:15:10Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45288  
#### CVE-2023-52425
**Gravité:** HIGH (7.5)  
**namespaces Affectées:** kps  
**Details:**
- libexpat (Versions: 2.5.0-r2)  
- Titre: expat: parsing large tokens can trigger a denial of service  
- Date de publication: 2024-02-04T20:15:46Z  
- Dernière modification: 2024-06-14T13:15:49Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-52425  
#### CVE-2024-28757
**Gravité:** HIGH (7.5)  
**namespaces Affectées:** kps  
**Details:**
- libexpat (Versions: 2.5.0-r2)  
- Titre: expat: XML Entity Expansion  
- Date de publication: 2024-03-10T05:15:06Z  
- Dernière modification: 2024-05-01T19:15:22Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-28757  
#### CVE-2023-45288
**Gravité:** HIGH (7.5)  
**namespaces Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/http, x/net/http2: unlimited number of CONTINUATION frames causes DoS  
- Date de publication: 2024-04-04T21:15:16Z  
- Dernière modification: 2024-05-01T18:15:10Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45288  
#### CVE-2023-45288
**Gravité:** HIGH (5.3)  
**namespaces Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/http, x/net/http2: unlimited number of CONTINUATION frames causes DoS  
- Date de publication: 2024-04-04T21:15:16Z  
- Dernière modification: 2024-05-01T18:15:10Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45288  
#### CVE-2023-45288
**Gravité:** HIGH (5.3)  
**namespaces Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/http, x/net/http2: unlimited number of CONTINUATION frames causes DoS  
- Date de publication: 2024-04-04T21:15:16Z  
- Dernière modification: 2024-05-01T18:15:10Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45288  
#### CVE-2023-45288
**Gravité:** HIGH (5.3)  
**namespaces Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/http, x/net/http2: unlimited number of CONTINUATION frames causes DoS  
- Date de publication: 2024-04-04T21:15:16Z  
- Dernière modification: 2024-05-01T18:15:10Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45288  
#### CVE-2023-45288
**Gravité:** HIGH (5.3)  
**namespaces Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/http, x/net/http2: unlimited number of CONTINUATION frames causes DoS  
- Date de publication: 2024-04-04T21:15:16Z  
- Dernière modification: 2024-05-01T18:15:10Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45288  
### CVE Moyennes
#### CVE-2023-45288
**Gravité:** MEDIUM (7.5)  
**namespaces Affectées:** ingress-nginx  
**Details:**
- golang.org/x/net (Versions: v0.21.0)  
- Titre: golang: net/http, x/net/http2: unlimited number of CONTINUATION frames causes DoS  
- Date de publication: 2024-04-04T21:15:16Z  
- Dernière modification: 2024-05-01T18:15:10Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45288  
#### CVE-2024-24786
**Gravité:** MEDIUM (5.9)  
**namespaces Affectées:** ingress-nginx  
**Details:**
- google.golang.org/protobuf (Versions: v1.32.0)  
- Titre: golang-protobuf: encoding/protojson, internal/encoding/json: infinite loop in protojson.Unmarshal when unmarshaling certain forms of invalid JSON  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-06-10T18:15:26Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24786  
#### CVE-2023-45289
**Gravité:** MEDIUM (5.3)  
**namespaces Affectées:** ingress-nginx  
**Details:**
- stdlib (Versions: 1.21.6)  
- Titre: golang: net/http/cookiejar: incorrect forwarding of sensitive headers and cookies on HTTP redirect  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:25Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45289  
#### CVE-2023-45290
**Gravité:** MEDIUM (5.3)  
**namespaces Affectées:** ingress-nginx  
**Details:**
- stdlib (Versions: 1.21.6)  
- Titre: golang: net/http: memory exhaustion in Request.ParseMultipartForm  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:26Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45290  
#### CVE-2024-24783
**Gravité:** MEDIUM (5.9)  
**namespaces Affectées:** ingress-nginx  
**Details:**
- stdlib (Versions: 1.21.6)  
- Titre: golang: crypto/x509: Verify panics on certificates with an unknown public key algorithm  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:29Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24783  
#### CVE-2024-24784
**Gravité:** MEDIUM (5.4)  
**namespaces Affectées:** ingress-nginx  
**Details:**
- stdlib (Versions: 1.21.6)  
- Titre: golang: net/mail: comments in display names are incorrectly handled  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:29Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24784  
#### CVE-2024-24785
**Gravité:** MEDIUM (6.5)  
**namespaces Affectées:** ingress-nginx  
**Details:**
- stdlib (Versions: 1.21.6)  
- Titre: golang: html/template: errors returned from MarshalJSON methods may break template escaping  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:29Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24785  
#### CVE-2024-24789
**Gravité:** MEDIUM (5.5)  
**namespaces Affectées:** ingress-nginx  
**Details:**
- stdlib (Versions: 1.21.6)  
- Titre: golang: archive/zip: Incorrect handling of certain ZIP files  
- Date de publication: 2024-06-05T16:15:10Z  
- Dernière modification: 2024-07-03T01:48:25Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24789  
#### CVE-2024-24791
**Gravité:** MEDIUM (N/A)  
**namespaces Affectées:** ingress-nginx  
**Details:**
- stdlib (Versions: 1.21.6)  
- Titre: net/http: Denial of service due to improper 100-continue handling in net/http  
- Date de publication: 2024-07-02T22:15:04Z  
- Dernière modification: 2024-07-03T12:53:24Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24791  
#### CVE-2023-42363
**Gravité:** MEDIUM (5.5)  
**namespaces Affectées:** kps  
**Details:**
- busybox (Versions: 1.36.1-r15)  
- Titre: busybox: use-after-free in awk  
- Date de publication: 2023-11-27T22:15:07Z  
- Dernière modification: 2023-11-30T05:06:49Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-42363  
#### CVE-2023-42364
**Gravité:** MEDIUM (5.5)  
**namespaces Affectées:** kps  
**Details:**
- busybox (Versions: 1.36.1-r15)  
- Titre: busybox: use-after-free  
- Date de publication: 2023-11-27T23:15:07Z  
- Dernière modification: 2023-11-30T05:07:10Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-42364  
#### CVE-2023-42365
**Gravité:** MEDIUM (5.5)  
**namespaces Affectées:** kps  
**Details:**
- busybox (Versions: 1.36.1-r15)  
- Titre: busybox:  use-after-free  
- Date de publication: 2023-11-27T23:15:07Z  
- Dernière modification: 2023-11-30T05:08:08Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-42365  
#### CVE-2023-42366
**Gravité:** MEDIUM (5.5)  
**namespaces Affectées:** kps  
**Details:**
- busybox (Versions: 1.36.1-r15)  
- Titre: busybox: A heap-buffer-overflow  
- Date de publication: 2023-11-27T23:15:07Z  
- Dernière modification: 2023-11-30T05:08:23Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-42366  
#### CVE-2023-42363
**Gravité:** MEDIUM (5.5)  
**namespaces Affectées:** kps  
**Details:**
- busybox-binsh (Versions: 1.36.1-r15)  
- Titre: busybox: use-after-free in awk  
- Date de publication: 2023-11-27T22:15:07Z  
- Dernière modification: 2023-11-30T05:06:49Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-42363  
#### CVE-2023-42364
**Gravité:** MEDIUM (5.5)  
**namespaces Affectées:** kps  
**Details:**
- busybox-binsh (Versions: 1.36.1-r15)  
- Titre: busybox: use-after-free  
- Date de publication: 2023-11-27T23:15:07Z  
- Dernière modification: 2023-11-30T05:07:10Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-42364  
#### CVE-2023-42365
**Gravité:** MEDIUM (5.5)  
**namespaces Affectées:** kps  
**Details:**
- busybox-binsh (Versions: 1.36.1-r15)  
- Titre: busybox:  use-after-free  
- Date de publication: 2023-11-27T23:15:07Z  
- Dernière modification: 2023-11-30T05:08:08Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-42365  
#### CVE-2023-42366
**Gravité:** MEDIUM (5.5)  
**namespaces Affectées:** kps  
**Details:**
- busybox-binsh (Versions: 1.36.1-r15)  
- Titre: busybox: A heap-buffer-overflow  
- Date de publication: 2023-11-27T23:15:07Z  
- Dernière modification: 2023-11-30T05:08:23Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-42366  
#### CVE-2024-4603
**Gravité:** MEDIUM (5.3)  
**namespaces Affectées:** kps  
**Details:**
- libcrypto3 (Versions: 3.1.4-r5)  
- Titre: openssl: Excessive time spent checking DSA keys and parameters  
- Date de publication: 2024-05-16T16:15:10Z  
- Dernière modification: 2024-06-21T19:15:30Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-4603  
#### CVE-2024-4741
**Gravité:** MEDIUM (5.6)  
**namespaces Affectées:** kps  
**Details:**
- libcrypto3 (Versions: 3.1.4-r5)  
- Titre: openssl: Use After Free with SSL_free_buffers  
- Date de publication:   
- Dernière modification:   
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-4741  
#### CVE-2024-5535
**Gravité:** MEDIUM (5.9)  
**namespaces Affectées:** kps  
**Details:**
- libcrypto3 (Versions: 3.1.4-r5)  
- Titre: openssl: SSL_select_next_proto buffer overread  
- Date de publication: 2024-06-27T11:15:24Z  
- Dernière modification: 2024-07-03T02:09:04Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-5535  
#### CVE-2023-52426
**Gravité:** MEDIUM (5.5)  
**namespaces Affectées:** kps  
**Details:**
- libexpat (Versions: 2.5.0-r2)  
- Titre: expat: recursive XML entity expansion vulnerability  
- Date de publication: 2024-02-04T20:15:46Z  
- Dernière modification: 2024-03-07T17:15:11Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-52426  
#### CVE-2024-4603
**Gravité:** MEDIUM (5.3)  
**namespaces Affectées:** kps  
**Details:**
- libssl3 (Versions: 3.1.4-r5)  
- Titre: openssl: Excessive time spent checking DSA keys and parameters  
- Date de publication: 2024-05-16T16:15:10Z  
- Dernière modification: 2024-06-21T19:15:30Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-4603  
#### CVE-2024-4741
**Gravité:** MEDIUM (5.6)  
**namespaces Affectées:** kps  
**Details:**
- libssl3 (Versions: 3.1.4-r5)  
- Titre: openssl: Use After Free with SSL_free_buffers  
- Date de publication:   
- Dernière modification:   
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-4741  
#### CVE-2024-5535
**Gravité:** MEDIUM (5.9)  
**namespaces Affectées:** kps  
**Details:**
- libssl3 (Versions: 3.1.4-r5)  
- Titre: openssl: SSL_select_next_proto buffer overread  
- Date de publication: 2024-06-27T11:15:24Z  
- Dernière modification: 2024-07-03T02:09:04Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-5535  
#### CVE-2023-42363
**Gravité:** MEDIUM (5.5)  
**namespaces Affectées:** kps  
**Details:**
- ssl_client (Versions: 1.36.1-r15)  
- Titre: busybox: use-after-free in awk  
- Date de publication: 2023-11-27T22:15:07Z  
- Dernière modification: 2023-11-30T05:06:49Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-42363  
#### CVE-2023-42364
**Gravité:** MEDIUM (5.5)  
**namespaces Affectées:** kps  
**Details:**
- ssl_client (Versions: 1.36.1-r15)  
- Titre: busybox: use-after-free  
- Date de publication: 2023-11-27T23:15:07Z  
- Dernière modification: 2023-11-30T05:07:10Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-42364  
#### CVE-2023-42365
**Gravité:** MEDIUM (5.5)  
**namespaces Affectées:** kps  
**Details:**
- ssl_client (Versions: 1.36.1-r15)  
- Titre: busybox:  use-after-free  
- Date de publication: 2023-11-27T23:15:07Z  
- Dernière modification: 2023-11-30T05:08:08Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-42365  
#### CVE-2023-42366
**Gravité:** MEDIUM (5.5)  
**namespaces Affectées:** kps  
**Details:**
- ssl_client (Versions: 1.36.1-r15)  
- Titre: busybox: A heap-buffer-overflow  
- Date de publication: 2023-11-27T23:15:07Z  
- Dernière modification: 2023-11-30T05:08:23Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-42366  
#### CVE-2024-3651
**Gravité:** MEDIUM (6.2)  
**namespaces Affectées:** kps  
**Details:**
- idna (Versions: 3.6)  
- Titre: python-idna: potential DoS via resource consumption via specially crafted inputs to idna.encode()  
- Date de publication: 2024-07-07T18:15:09Z  
- Dernière modification: 2024-07-07T18:15:09Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-3651  
#### CVE-2024-35195
**Gravité:** MEDIUM (5.6)  
**namespaces Affectées:** kps  
**Details:**
- requests (Versions: 2.31.0)  
- Titre: requests: subsequent requests to the same host ignore cert verification  
- Date de publication: 2024-05-20T21:15:09Z  
- Dernière modification: 2024-06-10T17:16:29Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-35195  
#### CVE-2024-37891
**Gravité:** MEDIUM (4.4)  
**namespaces Affectées:** kps  
**Details:**
- urllib3 (Versions: 1.26.18)  
- Titre: urllib3: proxy-authorization request header is not stripped during cross-origin redirects  
- Date de publication: 2024-06-17T20:15:13Z  
- Dernière modification: 2024-06-20T12:44:22Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-37891  
#### CVE-2023-45288
**Gravité:** MEDIUM (7.5)  
**namespaces Affectées:** kube-system  
**Details:**
- golang.org/x/net (Versions: v0.17.0)  
- Titre: golang: net/http, x/net/http2: unlimited number of CONTINUATION frames causes DoS  
- Date de publication: 2024-04-04T21:15:16Z  
- Dernière modification: 2024-05-01T18:15:10Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45288  
#### CVE-2024-24786
**Gravité:** MEDIUM (5.9)  
**namespaces Affectées:** kube-system  
**Details:**
- google.golang.org/protobuf (Versions: v1.31.0)  
- Titre: golang-protobuf: encoding/protojson, internal/encoding/json: infinite loop in protojson.Unmarshal when unmarshaling certain forms of invalid JSON  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-06-10T18:15:26Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24786  
#### CVE-2023-45289
**Gravité:** MEDIUM (5.3)  
**namespaces Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/http/cookiejar: incorrect forwarding of sensitive headers and cookies on HTTP redirect  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:25Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45289  
#### CVE-2023-45290
**Gravité:** MEDIUM (5.3)  
**namespaces Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/http: memory exhaustion in Request.ParseMultipartForm  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:26Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45290  
#### CVE-2024-24783
**Gravité:** MEDIUM (5.9)  
**namespaces Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: crypto/x509: Verify panics on certificates with an unknown public key algorithm  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:29Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24783  
#### CVE-2024-24784
**Gravité:** MEDIUM (5.4)  
**namespaces Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/mail: comments in display names are incorrectly handled  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:29Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24784  
#### CVE-2024-24785
**Gravité:** MEDIUM (6.5)  
**namespaces Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: html/template: errors returned from MarshalJSON methods may break template escaping  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:29Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24785  
#### CVE-2024-24789
**Gravité:** MEDIUM (5.5)  
**namespaces Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: archive/zip: Incorrect handling of certain ZIP files  
- Date de publication: 2024-06-05T16:15:10Z  
- Dernière modification: 2024-07-03T01:48:25Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24789  
#### CVE-2024-24791
**Gravité:** MEDIUM (N/A)  
**namespaces Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: net/http: Denial of service due to improper 100-continue handling in net/http  
- Date de publication: 2024-07-02T22:15:04Z  
- Dernière modification: 2024-07-03T12:53:24Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24791  
#### CVE-2023-45288
**Gravité:** MEDIUM (7.5)  
**namespaces Affectées:** kube-system  
**Details:**
- golang.org/x/net (Versions: v0.17.0)  
- Titre: golang: net/http, x/net/http2: unlimited number of CONTINUATION frames causes DoS  
- Date de publication: 2024-04-04T21:15:16Z  
- Dernière modification: 2024-05-01T18:15:10Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45288  
#### CVE-2024-24786
**Gravité:** MEDIUM (5.9)  
**namespaces Affectées:** kube-system  
**Details:**
- google.golang.org/protobuf (Versions: v1.31.0)  
- Titre: golang-protobuf: encoding/protojson, internal/encoding/json: infinite loop in protojson.Unmarshal when unmarshaling certain forms of invalid JSON  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-06-10T18:15:26Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24786  
#### CVE-2023-45289
**Gravité:** MEDIUM (5.3)  
**namespaces Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/http/cookiejar: incorrect forwarding of sensitive headers and cookies on HTTP redirect  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:25Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45289  
#### CVE-2023-45290
**Gravité:** MEDIUM (5.3)  
**namespaces Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/http: memory exhaustion in Request.ParseMultipartForm  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:26Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45290  
#### CVE-2024-24783
**Gravité:** MEDIUM (5.9)  
**namespaces Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: crypto/x509: Verify panics on certificates with an unknown public key algorithm  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:29Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24783  
#### CVE-2024-24784
**Gravité:** MEDIUM (5.4)  
**namespaces Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/mail: comments in display names are incorrectly handled  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:29Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24784  
#### CVE-2024-24785
**Gravité:** MEDIUM (6.5)  
**namespaces Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: html/template: errors returned from MarshalJSON methods may break template escaping  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:29Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24785  
#### CVE-2024-24789
**Gravité:** MEDIUM (5.5)  
**namespaces Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: archive/zip: Incorrect handling of certain ZIP files  
- Date de publication: 2024-06-05T16:15:10Z  
- Dernière modification: 2024-07-03T01:48:25Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24789  
#### CVE-2024-24791
**Gravité:** MEDIUM (N/A)  
**namespaces Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: net/http: Denial of service due to improper 100-continue handling in net/http  
- Date de publication: 2024-07-02T22:15:04Z  
- Dernière modification: 2024-07-03T12:53:24Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24791  
#### CVE-2023-45288
**Gravité:** MEDIUM (7.5)  
**namespaces Affectées:** kube-system  
**Details:**
- golang.org/x/net (Versions: v0.17.0)  
- Titre: golang: net/http, x/net/http2: unlimited number of CONTINUATION frames causes DoS  
- Date de publication: 2024-04-04T21:15:16Z  
- Dernière modification: 2024-05-01T18:15:10Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45288  
#### CVE-2024-24786
**Gravité:** MEDIUM (5.9)  
**namespaces Affectées:** kube-system  
**Details:**
- google.golang.org/protobuf (Versions: v1.31.0)  
- Titre: golang-protobuf: encoding/protojson, internal/encoding/json: infinite loop in protojson.Unmarshal when unmarshaling certain forms of invalid JSON  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-06-10T18:15:26Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24786  
#### CVE-2023-45289
**Gravité:** MEDIUM (5.3)  
**namespaces Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/http/cookiejar: incorrect forwarding of sensitive headers and cookies on HTTP redirect  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:25Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45289  
#### CVE-2023-45290
**Gravité:** MEDIUM (5.3)  
**namespaces Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/http: memory exhaustion in Request.ParseMultipartForm  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:26Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45290  
#### CVE-2024-24783
**Gravité:** MEDIUM (5.9)  
**namespaces Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: crypto/x509: Verify panics on certificates with an unknown public key algorithm  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:29Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24783  
#### CVE-2024-24784
**Gravité:** MEDIUM (5.4)  
**namespaces Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/mail: comments in display names are incorrectly handled  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:29Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24784  
#### CVE-2024-24785
**Gravité:** MEDIUM (6.5)  
**namespaces Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: html/template: errors returned from MarshalJSON methods may break template escaping  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:29Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24785  
#### CVE-2024-24789
**Gravité:** MEDIUM (5.5)  
**namespaces Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: archive/zip: Incorrect handling of certain ZIP files  
- Date de publication: 2024-06-05T16:15:10Z  
- Dernière modification: 2024-07-03T01:48:25Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24789  
#### CVE-2024-24791
**Gravité:** MEDIUM (N/A)  
**namespaces Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: net/http: Denial of service due to improper 100-continue handling in net/http  
- Date de publication: 2024-07-02T22:15:04Z  
- Dernière modification: 2024-07-03T12:53:24Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24791  
#### CVE-2023-45288
**Gravité:** MEDIUM (7.5)  
**namespaces Affectées:** kube-system  
**Details:**
- golang.org/x/net (Versions: v0.17.0)  
- Titre: golang: net/http, x/net/http2: unlimited number of CONTINUATION frames causes DoS  
- Date de publication: 2024-04-04T21:15:16Z  
- Dernière modification: 2024-05-01T18:15:10Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45288  
#### CVE-2024-24786
**Gravité:** MEDIUM (5.9)  
**namespaces Affectées:** kube-system  
**Details:**
- google.golang.org/protobuf (Versions: v1.31.0)  
- Titre: golang-protobuf: encoding/protojson, internal/encoding/json: infinite loop in protojson.Unmarshal when unmarshaling certain forms of invalid JSON  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-06-10T18:15:26Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24786  
#### CVE-2023-45289
**Gravité:** MEDIUM (5.3)  
**namespaces Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/http/cookiejar: incorrect forwarding of sensitive headers and cookies on HTTP redirect  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:25Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45289  
#### CVE-2023-45290
**Gravité:** MEDIUM (5.3)  
**namespaces Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/http: memory exhaustion in Request.ParseMultipartForm  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:26Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45290  
#### CVE-2024-24783
**Gravité:** MEDIUM (5.9)  
**namespaces Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: crypto/x509: Verify panics on certificates with an unknown public key algorithm  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:29Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24783  
#### CVE-2024-24784
**Gravité:** MEDIUM (5.4)  
**namespaces Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/mail: comments in display names are incorrectly handled  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:29Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24784  
#### CVE-2024-24785
**Gravité:** MEDIUM (6.5)  
**namespaces Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: html/template: errors returned from MarshalJSON methods may break template escaping  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:29Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24785  
#### CVE-2024-24789
**Gravité:** MEDIUM (5.5)  
**namespaces Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: archive/zip: Incorrect handling of certain ZIP files  
- Date de publication: 2024-06-05T16:15:10Z  
- Dernière modification: 2024-07-03T01:48:25Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24789  
#### CVE-2024-24791
**Gravité:** MEDIUM (N/A)  
**namespaces Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: net/http: Denial of service due to improper 100-continue handling in net/http  
- Date de publication: 2024-07-02T22:15:04Z  
- Dernière modification: 2024-07-03T12:53:24Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24791  
#### CVE-2023-45289
**Gravité:** MEDIUM (5.3)  
**namespaces Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/http/cookiejar: incorrect forwarding of sensitive headers and cookies on HTTP redirect  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:25Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45289  
#### CVE-2023-45290
**Gravité:** MEDIUM (5.3)  
**namespaces Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/http: memory exhaustion in Request.ParseMultipartForm  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:26Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45290  
#### CVE-2024-24783
**Gravité:** MEDIUM (5.9)  
**namespaces Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: crypto/x509: Verify panics on certificates with an unknown public key algorithm  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:29Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24783  
#### CVE-2024-24784
**Gravité:** MEDIUM (5.4)  
**namespaces Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/mail: comments in display names are incorrectly handled  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:29Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24784  
#### CVE-2024-24785
**Gravité:** MEDIUM (6.5)  
**namespaces Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: html/template: errors returned from MarshalJSON methods may break template escaping  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:29Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24785  
#### CVE-2024-24789
**Gravité:** MEDIUM (5.5)  
**namespaces Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: archive/zip: Incorrect handling of certain ZIP files  
- Date de publication: 2024-06-05T16:15:10Z  
- Dernière modification: 2024-07-03T01:48:25Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24789  
#### CVE-2024-24791
**Gravité:** MEDIUM (N/A)  
**namespaces Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: net/http: Denial of service due to improper 100-continue handling in net/http  
- Date de publication: 2024-07-02T22:15:04Z  
- Dernière modification: 2024-07-03T12:53:24Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24791  
#### CVE-2024-24791
**Gravité:** MEDIUM (N/A)  
**namespaces Affectées:** trivy-system  
**Details:**
- stdlib (Versions: 1.22.4)  
- Titre: net/http: Denial of service due to improper 100-continue handling in net/http  
- Date de publication: 2024-07-02T22:15:04Z  
- Dernière modification: 2024-07-03T12:53:24Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24791  
### CVE Basses
#### CVE-2024-2511
**Gravité:** LOW (3.7)  
**namespaces Affectées:** kps  
**Details:**
- libcrypto3 (Versions: 3.1.4-r5)  
- Titre: openssl: Unbounded memory growth with session handling in TLSv1.3  
- Date de publication: 2024-04-08T14:15:07Z  
- Dernière modification: 2024-05-03T13:15:21Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-2511  
#### CVE-2024-2511
**Gravité:** LOW (3.7)  
**namespaces Affectées:** kps  
**Details:**
- libssl3 (Versions: 3.1.4-r5)  
- Titre: openssl: Unbounded memory growth with session handling in TLSv1.3  
- Date de publication: 2024-04-08T14:15:07Z  
- Dernière modification: 2024-05-03T13:15:21Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-2511  
#### CVE-2024-39689
**Gravité:** LOW (3.7)  
**namespaces Affectées:** kps  
**Details:**
- certifi (Versions: 2024.2.2)  
- Titre: python-certifi: Remove root certificates from `GLOBALTRUST` from the root store  
- Date de publication: 2024-07-05T19:15:10Z  
- Dernière modification: 2024-07-05T19:15:10Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-39689  
