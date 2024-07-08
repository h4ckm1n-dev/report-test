
# CVE Report

08/07/2024
## Rapport sur les CVE pour le Cluster de Production

### Aperçu 
Ce rapport fournit une liste détaillée des vulnérabilités et expositions communes (CVE) présentes dans le cluster de production. Chaque entrée inclut l'identifiant CVE, l'application affectée, et les bibliothèques ou composants associés. Le rapport démontre que toutes les CVE répertoriées sont dues à des mises à jour non publiées par leurs mainteneurs respectifs. Nous utilisons un outil appelé Renovate pour être notifiés des mises à jour de composants disponibles sur notre cluster, garantissant que nous exécutons toujours la dernière version mise à disposition par le mainteneur.

## Kubernetes Ingress Report
Generated on: 2024-07-08 20:40:20.961105

| Namespace | Ingress Name | Host | Address | Type |
|-----------|--------------|------|---------|------|

**Note:** Only public endpoints are sensitive as other endpoints are only accessible behind a VPN.


### Métriques de Sévérité
| Type de CVE  | Nombre | Pourcentage du total |
|--------------|--------|----------------------|
| CVE Critiques | 6 | 9.2% |
| CVE Élevées  | 6 | 9.2% |
| CVE Moyennes  | 53 | 81.5% |
| CVE Basses  | 0 | 0.0% |
| CVE Inconnues  | 0 | 0.0% |

### Métriques Spécifiques aux Applications
| Application | CVE Critiques | CVE Élevées | CVE Moyennes | CVE Basses | Total CVE |
|-------------|---------------|-------------|--------------|-----------|-----------|
| kube-system | 5 | 5 | 43 | 0 | 53 |
| ingress-nginx | 1 | 1 | 9 | 0 | 11 |
| trivy-system | 0 | 0 | 1 | 0 | 1 |

### Métriques Spécifiques aux Bibliothèques
| Bibliothèque | Applications Affectées | Total CVE |
|--------------|-----------------------|-----------|
| stdlib | trivy-system, kube-system, ingress-nginx | 9 |
| golang.org/x/net | kube-system, ingress-nginx | 1 |
| google.golang.org/protobuf | kube-system, ingress-nginx | 1 |

### Observations Clés
* kube-system est l'application la plus affectée avec un total de 53 CVE.
* ingress-nginx a également un nombre significatif de CVE (11).
* trivy-system a également un nombre significatif de CVE (1).
* La majorité des CVE sont classées comme étant de haute gravité (9%), avec seulement une petite fraction étant critiques (9%).
* La bibliothèque stdlib est récurrente à travers plusieurs CVE et applications (cves, applications), indiquant des vulnérabilités communes dans cette bibliothèque.
* La bibliothèque golang.org/x/net est récurrente à travers plusieurs CVE et applications (cves, applications), indiquant des vulnérabilités communes dans cette bibliothèque.
* La bibliothèque google.golang.org/protobuf est récurrente à travers plusieurs CVE et applications (cves, applications), indiquant des vulnérabilités communes dans cette bibliothèque.

## Liste Détaillée des CVE
### CVE Critiques

| CVE ID | Applications |
|--------|--------------|
| [CVE-2024-24790](#cve-2024-24790) | ingress-nginx, kube-system |
### CVE Élevées

| CVE ID | Applications |
|--------|--------------|
| [CVE-2023-45288](#cve-2023-45288) | ingress-nginx, kube-system |
### CVE Moyennes

| CVE ID | Applications |
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
### CVE Critiques
#### CVE-2024-24790
**Gravité:** CRITICAL (9.8)  
**Applications Affectées:** ingress-nginx  
**Details:**
- stdlib (Versions: 1.21.6)  
- Titre: golang: net/netip: Unexpected behavior from Is methods for IPv4-mapped IPv6 addresses  
- Date de publication: 2024-06-05T16:15:10Z  
- Dernière modification: 2024-06-18T17:59:12Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24790  
#### CVE-2024-24790
**Gravité:** CRITICAL (9.8)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/netip: Unexpected behavior from Is methods for IPv4-mapped IPv6 addresses  
- Date de publication: 2024-06-05T16:15:10Z  
- Dernière modification: 2024-06-18T17:59:12Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24790  
#### CVE-2024-24790
**Gravité:** CRITICAL (9.8)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/netip: Unexpected behavior from Is methods for IPv4-mapped IPv6 addresses  
- Date de publication: 2024-06-05T16:15:10Z  
- Dernière modification: 2024-06-18T17:59:12Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24790  
#### CVE-2024-24790
**Gravité:** CRITICAL (9.8)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/netip: Unexpected behavior from Is methods for IPv4-mapped IPv6 addresses  
- Date de publication: 2024-06-05T16:15:10Z  
- Dernière modification: 2024-06-18T17:59:12Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24790  
#### CVE-2024-24790
**Gravité:** CRITICAL (9.8)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/netip: Unexpected behavior from Is methods for IPv4-mapped IPv6 addresses  
- Date de publication: 2024-06-05T16:15:10Z  
- Dernière modification: 2024-06-18T17:59:12Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24790  
#### CVE-2024-24790
**Gravité:** CRITICAL (9.8)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/netip: Unexpected behavior from Is methods for IPv4-mapped IPv6 addresses  
- Date de publication: 2024-06-05T16:15:10Z  
- Dernière modification: 2024-06-18T17:59:12Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24790  
### CVE Élevées
#### CVE-2023-45288
**Gravité:** HIGH (7.5)  
**Applications Affectées:** ingress-nginx  
**Details:**
- stdlib (Versions: 1.21.6)  
- Titre: golang: net/http, x/net/http2: unlimited number of CONTINUATION frames causes DoS  
- Date de publication: 2024-04-04T21:15:16Z  
- Dernière modification: 2024-05-01T18:15:10Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45288  
#### CVE-2023-45288
**Gravité:** HIGH (7.5)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/http, x/net/http2: unlimited number of CONTINUATION frames causes DoS  
- Date de publication: 2024-04-04T21:15:16Z  
- Dernière modification: 2024-05-01T18:15:10Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45288  
#### CVE-2023-45288
**Gravité:** HIGH (5.3)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/http, x/net/http2: unlimited number of CONTINUATION frames causes DoS  
- Date de publication: 2024-04-04T21:15:16Z  
- Dernière modification: 2024-05-01T18:15:10Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45288  
#### CVE-2023-45288
**Gravité:** HIGH (5.3)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/http, x/net/http2: unlimited number of CONTINUATION frames causes DoS  
- Date de publication: 2024-04-04T21:15:16Z  
- Dernière modification: 2024-05-01T18:15:10Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45288  
#### CVE-2023-45288
**Gravité:** HIGH (5.3)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/http, x/net/http2: unlimited number of CONTINUATION frames causes DoS  
- Date de publication: 2024-04-04T21:15:16Z  
- Dernière modification: 2024-05-01T18:15:10Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45288  
#### CVE-2023-45288
**Gravité:** HIGH (5.3)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/http, x/net/http2: unlimited number of CONTINUATION frames causes DoS  
- Date de publication: 2024-04-04T21:15:16Z  
- Dernière modification: 2024-05-01T18:15:10Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45288  
### CVE Moyennes
#### CVE-2023-45288
**Gravité:** MEDIUM (7.5)  
**Applications Affectées:** ingress-nginx  
**Details:**
- golang.org/x/net (Versions: v0.21.0)  
- Titre: golang: net/http, x/net/http2: unlimited number of CONTINUATION frames causes DoS  
- Date de publication: 2024-04-04T21:15:16Z  
- Dernière modification: 2024-05-01T18:15:10Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45288  
#### CVE-2024-24786
**Gravité:** MEDIUM (5.9)  
**Applications Affectées:** ingress-nginx  
**Details:**
- google.golang.org/protobuf (Versions: v1.32.0)  
- Titre: golang-protobuf: encoding/protojson, internal/encoding/json: infinite loop in protojson.Unmarshal when unmarshaling certain forms of invalid JSON  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-06-10T18:15:26Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24786  
#### CVE-2023-45289
**Gravité:** MEDIUM (5.3)  
**Applications Affectées:** ingress-nginx  
**Details:**
- stdlib (Versions: 1.21.6)  
- Titre: golang: net/http/cookiejar: incorrect forwarding of sensitive headers and cookies on HTTP redirect  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:25Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45289  
#### CVE-2023-45290
**Gravité:** MEDIUM (5.3)  
**Applications Affectées:** ingress-nginx  
**Details:**
- stdlib (Versions: 1.21.6)  
- Titre: golang: net/http: memory exhaustion in Request.ParseMultipartForm  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:26Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45290  
#### CVE-2024-24783
**Gravité:** MEDIUM (5.9)  
**Applications Affectées:** ingress-nginx  
**Details:**
- stdlib (Versions: 1.21.6)  
- Titre: golang: crypto/x509: Verify panics on certificates with an unknown public key algorithm  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:29Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24783  
#### CVE-2024-24784
**Gravité:** MEDIUM (5.4)  
**Applications Affectées:** ingress-nginx  
**Details:**
- stdlib (Versions: 1.21.6)  
- Titre: golang: net/mail: comments in display names are incorrectly handled  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:29Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24784  
#### CVE-2024-24785
**Gravité:** MEDIUM (6.5)  
**Applications Affectées:** ingress-nginx  
**Details:**
- stdlib (Versions: 1.21.6)  
- Titre: golang: html/template: errors returned from MarshalJSON methods may break template escaping  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:29Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24785  
#### CVE-2024-24789
**Gravité:** MEDIUM (5.5)  
**Applications Affectées:** ingress-nginx  
**Details:**
- stdlib (Versions: 1.21.6)  
- Titre: golang: archive/zip: Incorrect handling of certain ZIP files  
- Date de publication: 2024-06-05T16:15:10Z  
- Dernière modification: 2024-07-03T01:48:25Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24789  
#### CVE-2024-24791
**Gravité:** MEDIUM (N/A)  
**Applications Affectées:** ingress-nginx  
**Details:**
- stdlib (Versions: 1.21.6)  
- Titre: net/http: Denial of service due to improper 100-continue handling in net/http  
- Date de publication: 2024-07-02T22:15:04Z  
- Dernière modification: 2024-07-03T12:53:24Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24791  
#### CVE-2023-45288
**Gravité:** MEDIUM (7.5)  
**Applications Affectées:** kube-system  
**Details:**
- golang.org/x/net (Versions: v0.17.0)  
- Titre: golang: net/http, x/net/http2: unlimited number of CONTINUATION frames causes DoS  
- Date de publication: 2024-04-04T21:15:16Z  
- Dernière modification: 2024-05-01T18:15:10Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45288  
#### CVE-2024-24786
**Gravité:** MEDIUM (5.9)  
**Applications Affectées:** kube-system  
**Details:**
- google.golang.org/protobuf (Versions: v1.31.0)  
- Titre: golang-protobuf: encoding/protojson, internal/encoding/json: infinite loop in protojson.Unmarshal when unmarshaling certain forms of invalid JSON  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-06-10T18:15:26Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24786  
#### CVE-2023-45289
**Gravité:** MEDIUM (5.3)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/http/cookiejar: incorrect forwarding of sensitive headers and cookies on HTTP redirect  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:25Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45289  
#### CVE-2023-45290
**Gravité:** MEDIUM (5.3)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/http: memory exhaustion in Request.ParseMultipartForm  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:26Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45290  
#### CVE-2024-24783
**Gravité:** MEDIUM (5.9)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: crypto/x509: Verify panics on certificates with an unknown public key algorithm  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:29Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24783  
#### CVE-2024-24784
**Gravité:** MEDIUM (5.4)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/mail: comments in display names are incorrectly handled  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:29Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24784  
#### CVE-2024-24785
**Gravité:** MEDIUM (6.5)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: html/template: errors returned from MarshalJSON methods may break template escaping  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:29Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24785  
#### CVE-2024-24789
**Gravité:** MEDIUM (5.5)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: archive/zip: Incorrect handling of certain ZIP files  
- Date de publication: 2024-06-05T16:15:10Z  
- Dernière modification: 2024-07-03T01:48:25Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24789  
#### CVE-2024-24791
**Gravité:** MEDIUM (N/A)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: net/http: Denial of service due to improper 100-continue handling in net/http  
- Date de publication: 2024-07-02T22:15:04Z  
- Dernière modification: 2024-07-03T12:53:24Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24791  
#### CVE-2023-45288
**Gravité:** MEDIUM (7.5)  
**Applications Affectées:** kube-system  
**Details:**
- golang.org/x/net (Versions: v0.17.0)  
- Titre: golang: net/http, x/net/http2: unlimited number of CONTINUATION frames causes DoS  
- Date de publication: 2024-04-04T21:15:16Z  
- Dernière modification: 2024-05-01T18:15:10Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45288  
#### CVE-2024-24786
**Gravité:** MEDIUM (5.9)  
**Applications Affectées:** kube-system  
**Details:**
- google.golang.org/protobuf (Versions: v1.31.0)  
- Titre: golang-protobuf: encoding/protojson, internal/encoding/json: infinite loop in protojson.Unmarshal when unmarshaling certain forms of invalid JSON  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-06-10T18:15:26Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24786  
#### CVE-2023-45289
**Gravité:** MEDIUM (5.3)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/http/cookiejar: incorrect forwarding of sensitive headers and cookies on HTTP redirect  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:25Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45289  
#### CVE-2023-45290
**Gravité:** MEDIUM (5.3)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/http: memory exhaustion in Request.ParseMultipartForm  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:26Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45290  
#### CVE-2024-24783
**Gravité:** MEDIUM (5.9)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: crypto/x509: Verify panics on certificates with an unknown public key algorithm  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:29Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24783  
#### CVE-2024-24784
**Gravité:** MEDIUM (5.4)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/mail: comments in display names are incorrectly handled  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:29Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24784  
#### CVE-2024-24785
**Gravité:** MEDIUM (6.5)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: html/template: errors returned from MarshalJSON methods may break template escaping  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:29Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24785  
#### CVE-2024-24789
**Gravité:** MEDIUM (5.5)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: archive/zip: Incorrect handling of certain ZIP files  
- Date de publication: 2024-06-05T16:15:10Z  
- Dernière modification: 2024-07-03T01:48:25Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24789  
#### CVE-2024-24791
**Gravité:** MEDIUM (N/A)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: net/http: Denial of service due to improper 100-continue handling in net/http  
- Date de publication: 2024-07-02T22:15:04Z  
- Dernière modification: 2024-07-03T12:53:24Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24791  
#### CVE-2023-45288
**Gravité:** MEDIUM (7.5)  
**Applications Affectées:** kube-system  
**Details:**
- golang.org/x/net (Versions: v0.17.0)  
- Titre: golang: net/http, x/net/http2: unlimited number of CONTINUATION frames causes DoS  
- Date de publication: 2024-04-04T21:15:16Z  
- Dernière modification: 2024-05-01T18:15:10Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45288  
#### CVE-2024-24786
**Gravité:** MEDIUM (5.9)  
**Applications Affectées:** kube-system  
**Details:**
- google.golang.org/protobuf (Versions: v1.31.0)  
- Titre: golang-protobuf: encoding/protojson, internal/encoding/json: infinite loop in protojson.Unmarshal when unmarshaling certain forms of invalid JSON  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-06-10T18:15:26Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24786  
#### CVE-2023-45289
**Gravité:** MEDIUM (5.3)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/http/cookiejar: incorrect forwarding of sensitive headers and cookies on HTTP redirect  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:25Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45289  
#### CVE-2023-45290
**Gravité:** MEDIUM (5.3)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/http: memory exhaustion in Request.ParseMultipartForm  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:26Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45290  
#### CVE-2024-24783
**Gravité:** MEDIUM (5.9)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: crypto/x509: Verify panics on certificates with an unknown public key algorithm  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:29Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24783  
#### CVE-2024-24784
**Gravité:** MEDIUM (5.4)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/mail: comments in display names are incorrectly handled  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:29Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24784  
#### CVE-2024-24785
**Gravité:** MEDIUM (6.5)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: html/template: errors returned from MarshalJSON methods may break template escaping  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:29Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24785  
#### CVE-2024-24789
**Gravité:** MEDIUM (5.5)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: archive/zip: Incorrect handling of certain ZIP files  
- Date de publication: 2024-06-05T16:15:10Z  
- Dernière modification: 2024-07-03T01:48:25Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24789  
#### CVE-2024-24791
**Gravité:** MEDIUM (N/A)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: net/http: Denial of service due to improper 100-continue handling in net/http  
- Date de publication: 2024-07-02T22:15:04Z  
- Dernière modification: 2024-07-03T12:53:24Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24791  
#### CVE-2023-45288
**Gravité:** MEDIUM (7.5)  
**Applications Affectées:** kube-system  
**Details:**
- golang.org/x/net (Versions: v0.17.0)  
- Titre: golang: net/http, x/net/http2: unlimited number of CONTINUATION frames causes DoS  
- Date de publication: 2024-04-04T21:15:16Z  
- Dernière modification: 2024-05-01T18:15:10Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45288  
#### CVE-2024-24786
**Gravité:** MEDIUM (5.9)  
**Applications Affectées:** kube-system  
**Details:**
- google.golang.org/protobuf (Versions: v1.31.0)  
- Titre: golang-protobuf: encoding/protojson, internal/encoding/json: infinite loop in protojson.Unmarshal when unmarshaling certain forms of invalid JSON  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-06-10T18:15:26Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24786  
#### CVE-2023-45289
**Gravité:** MEDIUM (5.3)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/http/cookiejar: incorrect forwarding of sensitive headers and cookies on HTTP redirect  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:25Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45289  
#### CVE-2023-45290
**Gravité:** MEDIUM (5.3)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/http: memory exhaustion in Request.ParseMultipartForm  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:26Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45290  
#### CVE-2024-24783
**Gravité:** MEDIUM (5.9)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: crypto/x509: Verify panics on certificates with an unknown public key algorithm  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:29Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24783  
#### CVE-2024-24784
**Gravité:** MEDIUM (5.4)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/mail: comments in display names are incorrectly handled  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:29Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24784  
#### CVE-2024-24785
**Gravité:** MEDIUM (6.5)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: html/template: errors returned from MarshalJSON methods may break template escaping  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:29Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24785  
#### CVE-2024-24789
**Gravité:** MEDIUM (5.5)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: archive/zip: Incorrect handling of certain ZIP files  
- Date de publication: 2024-06-05T16:15:10Z  
- Dernière modification: 2024-07-03T01:48:25Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24789  
#### CVE-2024-24791
**Gravité:** MEDIUM (N/A)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: net/http: Denial of service due to improper 100-continue handling in net/http  
- Date de publication: 2024-07-02T22:15:04Z  
- Dernière modification: 2024-07-03T12:53:24Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24791  
#### CVE-2023-45289
**Gravité:** MEDIUM (5.3)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/http/cookiejar: incorrect forwarding of sensitive headers and cookies on HTTP redirect  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:25Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45289  
#### CVE-2023-45290
**Gravité:** MEDIUM (5.3)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/http: memory exhaustion in Request.ParseMultipartForm  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:26Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45290  
#### CVE-2024-24783
**Gravité:** MEDIUM (5.9)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: crypto/x509: Verify panics on certificates with an unknown public key algorithm  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:29Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24783  
#### CVE-2024-24784
**Gravité:** MEDIUM (5.4)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: net/mail: comments in display names are incorrectly handled  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:29Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24784  
#### CVE-2024-24785
**Gravité:** MEDIUM (6.5)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: html/template: errors returned from MarshalJSON methods may break template escaping  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:29Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24785  
#### CVE-2024-24789
**Gravité:** MEDIUM (5.5)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: golang: archive/zip: Incorrect handling of certain ZIP files  
- Date de publication: 2024-06-05T16:15:10Z  
- Dernière modification: 2024-07-03T01:48:25Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24789  
#### CVE-2024-24791
**Gravité:** MEDIUM (N/A)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20.13)  
- Titre: net/http: Denial of service due to improper 100-continue handling in net/http  
- Date de publication: 2024-07-02T22:15:04Z  
- Dernière modification: 2024-07-03T12:53:24Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24791  
#### CVE-2024-24791
**Gravité:** MEDIUM (N/A)  
**Applications Affectées:** trivy-system  
**Details:**
- stdlib (Versions: 1.22.4)  
- Titre: net/http: Denial of service due to improper 100-continue handling in net/http  
- Date de publication: 2024-07-02T22:15:04Z  
- Dernière modification: 2024-07-03T12:53:24Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24791  
