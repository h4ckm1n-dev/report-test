
# CVE Report

22/08/2024
## Rapport sur les CVE pour le Cluster de Production

### Aperçu 
Ce rapport fournit une liste détaillée des vulnérabilités et expositions communes (CVE) présentes dans le cluster de production. Chaque entrée inclut l'identifiant CVE, l'application affectée, et les bibliothèques ou composants associés. Le rapport démontre que toutes les CVE répertoriées sont dues à des mises à jour non publiées par leurs mainteneurs respectifs. Nous utilisons un outil appelé Renovate pour être notifiés des mises à jour de composants disponibles sur notre cluster, garantissant que nous exécutons toujours la dernière version mise à disposition par le mainteneur.

## Kubernetes Ingress Report
| Namespace | Ingress Name | Host | Address | Type |
|-----------|--------------|------|---------|------|
| prom-stack | kps-prometheus | prometheus.h4ckm1n.org | None | Private |
| prom-stack | prom-stack-grafana | grafana.h4ckm1n.org | None | Private |

**Note:** Only public endpoints are sensitive as other endpoints are only accessible behind a VPN.


### Métriques de Sévérité
| Type de CVE  | Nombre | Pourcentage du total |
|--------------|--------|----------------------|
| CVE Critiques | 6 | 9.8% |
| CVE Élevées  | 18 | 29.5% |
| CVE Moyennes  | 36 | 59.0% |
| CVE Basses  | 1 | 1.6% |
| CVE Inconnues  | 0 | 0.0% |

### Métriques Spécifiques aux Applications
| Application | CVE Critiques | CVE Élevées | CVE Moyennes | CVE Basses | Total CVE |
|-------------|---------------|-------------|--------------|-----------|-----------|
| kube-system | 3 | 16 | 20 | 0 | 39 |
| trivy | 2 | 1 | 13 | 1 | 17 |
| prom-stack | 1 | 1 | 3 | 0 | 5 |

### Métriques Spécifiques aux Bibliothèques
| Bibliothèque | Applications Affectées | Total CVE |
|--------------|-----------------------|-----------|
| stdlib | kube-system, trivy, prom-stack | 30 |
| golang.org/x/net | kube-system, prom-stack | 5 |
| google.golang.org/grpc | kube-system, trivy | 3 |
| busybox | trivy | 2 |
| busybox-binsh | trivy | 2 |
| libcrypto3 | trivy | 2 |
| libssl3 | trivy | 2 |
| ssl_client | trivy | 2 |
| golang.org/x/crypto | kube-system | 1 |
| google.golang.org/protobuf | kube-system | 1 |
| github.com/Azure/azure-sdk-for-go/sdk/azidentity | trivy | 1 |
| github.com/docker/docker | trivy | 1 |
| github.com/hashicorp/go-getter | trivy | 1 |

### Observations Clés
* kube-system est l'application la plus affectée avec un total de 39 CVE.
* trivy a également un nombre significatif de CVE (17).
* prom-stack a également un nombre significatif de CVE (5).
* La majorité des CVE sont classées comme étant de haute gravité (30%), avec seulement une petite fraction étant critiques (10%).
* La bibliothèque stdlib est récurrente à travers plusieurs CVE et applications (applications, cves), indiquant des vulnérabilités communes dans cette bibliothèque.
* La bibliothèque golang.org/x/net est récurrente à travers plusieurs CVE et applications (applications, cves), indiquant des vulnérabilités communes dans cette bibliothèque.
* La bibliothèque google.golang.org/grpc est récurrente à travers plusieurs CVE et applications (applications, cves), indiquant des vulnérabilités communes dans cette bibliothèque.

## Liste Détaillée des CVE
### CVE Critiques

| CVE ID | Applications |
|--------|--------------|
| [CVE-2024-41110](#cve-2024-41110) | trivy |
| [CVE-2023-24538](#cve-2023-24538) | kube-system |
| [CVE-2023-24540](#cve-2023-24540) | kube-system |
| [CVE-2024-24790](#cve-2024-24790) | kube-system, prom-stack, trivy |
### CVE Élevées

| CVE ID | Applications |
|--------|--------------|
| [CVE-2024-6257](#cve-2024-6257) | trivy |
| [CVE-2023-29403](#cve-2023-29403) | kube-system |
| [CVE-2022-41723](#cve-2022-41723) | kube-system |
| [CVE-2023-39325](#cve-2023-39325) | kube-system |
| [GHSA-m425-mq94-257g](#ghsa-m425-mq94-257g) | kube-system |
| [CVE-2022-41722](#cve-2022-41722) | kube-system |
| [CVE-2022-41724](#cve-2022-41724) | kube-system |
| [CVE-2022-41725](#cve-2022-41725) | kube-system |
| [CVE-2023-24534](#cve-2023-24534) | kube-system |
| [CVE-2023-24536](#cve-2023-24536) | kube-system |
| [CVE-2023-24537](#cve-2023-24537) | kube-system |
| [CVE-2023-45283](#cve-2023-45283) | kube-system |
| [CVE-2023-45288](#cve-2023-45288) | kube-system, prom-stack |
| [CVE-2023-24539](#cve-2023-24539) | kube-system |
| [CVE-2023-29400](#cve-2023-29400) | kube-system |
### CVE Moyennes

| CVE ID | Applications |
|--------|--------------|
| [CVE-2023-48795](#cve-2023-48795) | kube-system |
| [CVE-2023-3978](#cve-2023-3978) | kube-system |
| [CVE-2023-44487](#cve-2023-44487) | kube-system |
| [CVE-2023-45288](#cve-2023-45288) | kube-system, prom-stack |
| [CVE-2024-24786](#cve-2024-24786) | kube-system |
| [CVE-2023-24532](#cve-2023-24532) | kube-system |
| [CVE-2023-29406](#cve-2023-29406) | kube-system |
| [CVE-2023-29409](#cve-2023-29409) | kube-system |
| [CVE-2023-39318](#cve-2023-39318) | kube-system |
| [CVE-2023-39319](#cve-2023-39319) | kube-system |
| [CVE-2023-39326](#cve-2023-39326) | kube-system |
| [CVE-2023-45284](#cve-2023-45284) | kube-system |
| [CVE-2023-45289](#cve-2023-45289) | kube-system |
| [CVE-2023-45290](#cve-2023-45290) | kube-system |
| [CVE-2024-24783](#cve-2024-24783) | kube-system |
| [CVE-2024-24784](#cve-2024-24784) | kube-system |
| [CVE-2024-24785](#cve-2024-24785) | kube-system |
| [CVE-2024-24789](#cve-2024-24789) | kube-system, prom-stack, trivy |
| [CVE-2024-24791](#cve-2024-24791) | kube-system, prom-stack, trivy |
| [CVE-2023-42364](#cve-2023-42364) | trivy |
| [CVE-2023-42365](#cve-2023-42365) | trivy |
| [CVE-2024-4741](#cve-2024-4741) | trivy |
| [CVE-2024-5535](#cve-2024-5535) | trivy |
| [CVE-2024-35255](#cve-2024-35255) | trivy |
### CVE Basses

| CVE ID | Applications |
|--------|--------------|
| [GHSA-xr7q-jx4m-x55m](#ghsa-xr7q-jx4m-x55m) | trivy |
### CVE Critiques
#### CVE-2024-41110
**Gravité:** CRITICAL (9.9)  
**Applications Affectées:** trivy  
**Details:**
- github.com/docker/docker (Versions: v26.1.3+incompatible)  
- Titre: moby: Authz zero length regression  
- Date de publication: 2024-07-24T17:15:11Z  
- Dernière modification: 2024-07-30T20:15:04Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-41110  
#### CVE-2023-24538
**Gravité:** CRITICAL (9.8)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20)  
- Titre: golang: html/template: backticks not treated as string delimiters  
- Date de publication: 2023-04-06T16:15:07Z  
- Dernière modification: 2023-11-25T11:15:14Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-24538  
#### CVE-2023-24540
**Gravité:** CRITICAL (9.8)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20)  
- Titre: golang: html/template: improper handling of JavaScript whitespace  
- Date de publication: 2023-05-11T16:15:09Z  
- Dernière modification: 2023-11-07T04:08:32Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-24540  
#### CVE-2024-24790
**Gravité:** CRITICAL (9.8)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20)  
- Titre: golang: net/netip: Unexpected behavior from Is methods for IPv4-mapped IPv6 addresses  
- Date de publication: 2024-06-05T16:15:10Z  
- Dernière modification: 2024-06-18T17:59:12Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24790  
#### CVE-2024-24790
**Gravité:** CRITICAL (9.8)  
**Applications Affectées:** prom-stack  
**Details:**
- stdlib (Versions: 1.21.8)  
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
### CVE Élevées
#### CVE-2024-6257
**Gravité:** HIGH (8.5)  
**Applications Affectées:** trivy  
**Details:**
- github.com/hashicorp/go-getter (Versions: v1.7.4)  
- Titre: hashicorp/go-getter: Arbitrary command execution through local git config file  
- Date de publication: 2024-06-25T17:15:10Z  
- Dernière modification: 2024-06-25T18:50:42Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-6257  
#### CVE-2023-29403
**Gravité:** HIGH (7.8)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20)  
- Titre: golang: runtime: unexpected behavior of setuid/setgid binaries  
- Date de publication: 2023-06-08T21:15:16Z  
- Dernière modification: 2023-11-25T11:15:14Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-29403  
#### CVE-2022-41723
**Gravité:** HIGH (7.5)  
**Applications Affectées:** kube-system  
**Details:**
- golang.org/x/net (Versions: v0.4.0)  
- Titre: golang.org/x/net/http2: avoid quadratic complexity in HPACK decoding  
- Date de publication: 2023-02-28T18:15:09Z  
- Dernière modification: 2023-11-25T11:15:10Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2022-41723  
#### CVE-2023-39325
**Gravité:** HIGH (7.5)  
**Applications Affectées:** kube-system  
**Details:**
- golang.org/x/net (Versions: v0.4.0)  
- Titre: golang: net/http, x/net/http2: rapid stream resets can cause excessive work (CVE-2023-44487)  
- Date de publication: 2023-10-11T22:15:09Z  
- Dernière modification: 2024-04-28T04:15:09Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-39325  
#### GHSA-m425-mq94-257g
**Gravité:** HIGH (7.5)  
**Applications Affectées:** kube-system  
**Details:**
- google.golang.org/grpc (Versions: v1.52.3)  
- Titre: gRPC-Go HTTP/2 Rapid Reset vulnerability  
- Date de publication:   
- Dernière modification:   
- Lien primaire: https://github.com/advisories/GHSA-m425-mq94-257g  
#### CVE-2022-41722
**Gravité:** HIGH (7.5)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20)  
- Titre: golang: path/filepath: path-filepath filepath.Clean path traversal  
- Date de publication: 2023-02-28T18:15:09Z  
- Dernière modification: 2023-11-07T03:52:55Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2022-41722  
#### CVE-2022-41723
**Gravité:** HIGH (7.5)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20)  
- Titre: golang.org/x/net/http2: avoid quadratic complexity in HPACK decoding  
- Date de publication: 2023-02-28T18:15:09Z  
- Dernière modification: 2023-11-25T11:15:10Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2022-41723  
#### CVE-2022-41724
**Gravité:** HIGH (7.5)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20)  
- Titre: golang: crypto/tls: large handshake records may cause panics  
- Date de publication: 2023-02-28T18:15:10Z  
- Dernière modification: 2023-11-25T11:15:10Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2022-41724  
#### CVE-2022-41725
**Gravité:** HIGH (7.5)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20)  
- Titre: golang: net/http, mime/multipart: denial of service from excessive resource consumption  
- Date de publication: 2023-02-28T18:15:10Z  
- Dernière modification: 2023-11-25T11:15:10Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2022-41725  
#### CVE-2023-24534
**Gravité:** HIGH (7.5)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20)  
- Titre: golang: net/http, net/textproto: denial of service from excessive memory allocation  
- Date de publication: 2023-04-06T16:15:07Z  
- Dernière modification: 2023-11-25T11:15:14Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-24534  
#### CVE-2023-24536
**Gravité:** HIGH (7.5)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20)  
- Titre: golang: net/http, net/textproto, mime/multipart: denial of service from excessive resource consumption  
- Date de publication: 2023-04-06T16:15:07Z  
- Dernière modification: 2023-11-25T11:15:14Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-24536  
#### CVE-2023-24537
**Gravité:** HIGH (7.5)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20)  
- Titre: golang: go/parser: Infinite loop in parsing  
- Date de publication: 2023-04-06T16:15:07Z  
- Dernière modification: 2023-11-25T11:15:14Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-24537  
#### CVE-2023-39325
**Gravité:** HIGH (7.5)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20)  
- Titre: golang: net/http, x/net/http2: rapid stream resets can cause excessive work (CVE-2023-44487)  
- Date de publication: 2023-10-11T22:15:09Z  
- Dernière modification: 2024-04-28T04:15:09Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-39325  
#### CVE-2023-45283
**Gravité:** HIGH (7.5)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20)  
- Titre: The filepath package does not recognize paths with a \??\ prefix as sp ...  
- Date de publication: 2023-11-09T17:15:08Z  
- Dernière modification: 2023-12-14T10:15:07Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45283  
#### CVE-2023-45288
**Gravité:** HIGH (7.5)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20)  
- Titre: golang: net/http, x/net/http2: unlimited number of CONTINUATION frames causes DoS  
- Date de publication: 2024-04-04T21:15:16Z  
- Dernière modification: 2024-05-01T18:15:10Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45288  
#### CVE-2023-45288
**Gravité:** HIGH (7.5)  
**Applications Affectées:** prom-stack  
**Details:**
- stdlib (Versions: 1.21.8)  
- Titre: golang: net/http, x/net/http2: unlimited number of CONTINUATION frames causes DoS  
- Date de publication: 2024-04-04T21:15:16Z  
- Dernière modification: 2024-05-01T18:15:10Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45288  
#### CVE-2023-24539
**Gravité:** HIGH (7.3)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20)  
- Titre: golang: html/template: improper sanitization of CSS values  
- Date de publication: 2023-05-11T16:15:09Z  
- Dernière modification: 2023-11-07T04:08:32Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-24539  
#### CVE-2023-29400
**Gravité:** HIGH (7.3)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20)  
- Titre: golang: html/template: improper handling of empty HTML attributes  
- Date de publication: 2023-05-11T16:15:09Z  
- Dernière modification: 2023-11-07T04:11:10Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-29400  
### CVE Moyennes
#### CVE-2023-48795
**Gravité:** MEDIUM (5.9)  
**Applications Affectées:** kube-system  
**Details:**
- golang.org/x/crypto (Versions: v0.0.0-20221010152910-d6f0a8c073c2)  
- Titre: ssh: Prefix truncation attack on Binary Packet Protocol (BPP)  
- Date de publication: 2023-12-18T16:15:10Z  
- Dernière modification: 2024-05-01T18:15:10Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-48795  
#### CVE-2023-3978
**Gravité:** MEDIUM (6.1)  
**Applications Affectées:** kube-system  
**Details:**
- golang.org/x/net (Versions: v0.4.0)  
- Titre: golang.org/x/net/html: Cross site scripting  
- Date de publication: 2023-08-02T20:15:12Z  
- Dernière modification: 2023-11-07T04:20:03Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-3978  
#### CVE-2023-44487
**Gravité:** MEDIUM (7.5)  
**Applications Affectées:** kube-system  
**Details:**
- golang.org/x/net (Versions: v0.4.0)  
- Titre: HTTP/2: Multiple HTTP/2 enabled web servers are vulnerable to a DDoS attack (Rapid Reset Attack)  
- Date de publication: 2023-10-10T14:15:10Z  
- Dernière modification: 2024-08-14T19:57:18Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-44487  
#### CVE-2023-45288
**Gravité:** MEDIUM (7.5)  
**Applications Affectées:** kube-system  
**Details:**
- golang.org/x/net (Versions: v0.4.0)  
- Titre: golang: net/http, x/net/http2: unlimited number of CONTINUATION frames causes DoS  
- Date de publication: 2024-04-04T21:15:16Z  
- Dernière modification: 2024-05-01T18:15:10Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45288  
#### CVE-2023-44487
**Gravité:** MEDIUM (7.5)  
**Applications Affectées:** kube-system  
**Details:**
- google.golang.org/grpc (Versions: v1.52.3)  
- Titre: HTTP/2: Multiple HTTP/2 enabled web servers are vulnerable to a DDoS attack (Rapid Reset Attack)  
- Date de publication: 2023-10-10T14:15:10Z  
- Dernière modification: 2024-08-14T19:57:18Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-44487  
#### CVE-2024-24786
**Gravité:** MEDIUM (5.9)  
**Applications Affectées:** kube-system  
**Details:**
- google.golang.org/protobuf (Versions: v1.28.1)  
- Titre: golang-protobuf: encoding/protojson, internal/encoding/json: infinite loop in protojson.Unmarshal when unmarshaling certain forms of invalid JSON  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-06-10T18:15:26Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24786  
#### CVE-2023-24532
**Gravité:** MEDIUM (5.3)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20)  
- Titre: golang: crypto/internal/nistec: specific unreduced P-256 scalars produce incorrect results  
- Date de publication: 2023-03-08T20:15:09Z  
- Dernière modification: 2023-11-07T04:08:30Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-24532  
#### CVE-2023-29406
**Gravité:** MEDIUM (6.5)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20)  
- Titre: golang: net/http: insufficient sanitization of Host header  
- Date de publication: 2023-07-11T20:15:10Z  
- Dernière modification: 2023-11-25T11:15:14Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-29406  
#### CVE-2023-29409
**Gravité:** MEDIUM (5.3)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20)  
- Titre: golang: crypto/tls: slow verification of certificate chains containing large RSA keys  
- Date de publication: 2023-08-02T20:15:11Z  
- Dernière modification: 2023-11-25T11:15:14Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-29409  
#### CVE-2023-39318
**Gravité:** MEDIUM (6.1)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20)  
- Titre: golang: html/template: improper handling of HTML-like comments within script contexts  
- Date de publication: 2023-09-08T17:15:27Z  
- Dernière modification: 2023-11-25T11:15:17Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-39318  
#### CVE-2023-39319
**Gravité:** MEDIUM (6.1)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20)  
- Titre: golang: html/template: improper handling of special tags within script contexts  
- Date de publication: 2023-09-08T17:15:27Z  
- Dernière modification: 2023-11-25T11:15:17Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-39319  
#### CVE-2023-39326
**Gravité:** MEDIUM (5.3)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20)  
- Titre: golang: net/http/internal: Denial of Service (DoS) via Resource Consumption via HTTP requests  
- Date de publication: 2023-12-06T17:15:07Z  
- Dernière modification: 2024-01-20T04:15:07Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-39326  
#### CVE-2023-45284
**Gravité:** MEDIUM (5.3)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20)  
- Titre: On Windows, The IsLocal function does not correctly detect reserved de ...  
- Date de publication: 2023-11-09T17:15:08Z  
- Dernière modification: 2023-11-17T16:39:27Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45284  
#### CVE-2023-45289
**Gravité:** MEDIUM (5.3)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20)  
- Titre: golang: net/http/cookiejar: incorrect forwarding of sensitive headers and cookies on HTTP redirect  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:25Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45289  
#### CVE-2023-45290
**Gravité:** MEDIUM (5.3)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20)  
- Titre: golang: net/http: memory exhaustion in Request.ParseMultipartForm  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:26Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45290  
#### CVE-2024-24783
**Gravité:** MEDIUM (5.9)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20)  
- Titre: golang: crypto/x509: Verify panics on certificates with an unknown public key algorithm  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:29Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24783  
#### CVE-2024-24784
**Gravité:** MEDIUM (7.5)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20)  
- Titre: golang: net/mail: comments in display names are incorrectly handled  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-08-05T21:35:04Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24784  
#### CVE-2024-24785
**Gravité:** MEDIUM (6.5)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20)  
- Titre: golang: html/template: errors returned from MarshalJSON methods may break template escaping  
- Date de publication: 2024-03-05T23:15:07Z  
- Dernière modification: 2024-05-01T17:15:29Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24785  
#### CVE-2024-24789
**Gravité:** MEDIUM (5.5)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20)  
- Titre: golang: archive/zip: Incorrect handling of certain ZIP files  
- Date de publication: 2024-06-05T16:15:10Z  
- Dernière modification: 2024-07-03T01:48:25Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24789  
#### CVE-2024-24791
**Gravité:** MEDIUM (5.9)  
**Applications Affectées:** kube-system  
**Details:**
- stdlib (Versions: 1.20)  
- Titre: net/http: Denial of service due to improper 100-continue handling in net/http  
- Date de publication: 2024-07-02T22:15:04Z  
- Dernière modification: 2024-07-08T14:17:39Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24791  
#### CVE-2023-45288
**Gravité:** MEDIUM (7.5)  
**Applications Affectées:** prom-stack  
**Details:**
- golang.org/x/net (Versions: v0.22.0)  
- Titre: golang: net/http, x/net/http2: unlimited number of CONTINUATION frames causes DoS  
- Date de publication: 2024-04-04T21:15:16Z  
- Dernière modification: 2024-05-01T18:15:10Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-45288  
#### CVE-2024-24789
**Gravité:** MEDIUM (5.5)  
**Applications Affectées:** prom-stack  
**Details:**
- stdlib (Versions: 1.21.8)  
- Titre: golang: archive/zip: Incorrect handling of certain ZIP files  
- Date de publication: 2024-06-05T16:15:10Z  
- Dernière modification: 2024-07-03T01:48:25Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24789  
#### CVE-2024-24791
**Gravité:** MEDIUM (7.5)  
**Applications Affectées:** prom-stack  
**Details:**
- stdlib (Versions: 1.21.8)  
- Titre: net/http: Denial of service due to improper 100-continue handling in net/http  
- Date de publication: 2024-07-02T22:15:04Z  
- Dernière modification: 2024-07-08T14:17:39Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24791  
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
- Titre: busybox: use-after-free  
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
- Titre: busybox: use-after-free  
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
- Dernière modification: 2024-07-12T14:15:16Z  
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
- Dernière modification: 2024-07-12T14:15:16Z  
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
- Titre: busybox: use-after-free  
- Date de publication: 2023-11-27T23:15:07Z  
- Dernière modification: 2023-11-30T05:08:08Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2023-42365  
#### CVE-2024-35255
**Gravité:** MEDIUM (5.5)  
**Applications Affectées:** trivy  
**Details:**
- github.com/Azure/azure-sdk-for-go/sdk/azidentity (Versions: v1.5.2)  
- Titre: azure-identity: Azure Identity Libraries Elevation of Privilege Vulnerability in github.com/Azure/azure-sdk-for-go/sdk/azidentity  
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
**Gravité:** MEDIUM (5.9)  
**Applications Affectées:** trivy  
**Details:**
- stdlib (Versions: 1.22.3)  
- Titre: net/http: Denial of service due to improper 100-continue handling in net/http  
- Date de publication: 2024-07-02T22:15:04Z  
- Dernière modification: 2024-07-08T14:17:39Z  
- Lien primaire: https://avd.aquasec.com/nvd/cve-2024-24791  
### CVE Basses
#### GHSA-xr7q-jx4m-x55m
**Gravité:** LOW (N/A)  
**Applications Affectées:** trivy  
**Details:**
- google.golang.org/grpc (Versions: v1.64.0)  
- Titre: Private tokens could appear in logs if context containing gRPC metadata is logged in github.com/grpc/grpc-go  
- Date de publication:   
- Dernière modification:   
- Lien primaire: https://github.com/advisories/GHSA-xr7q-jx4m-x55m  
