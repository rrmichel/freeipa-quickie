## FreeIPA

IPA = <u>I</u>dentity, <u>P</u>olicy, <u>A</u>udit

* Identität & Authentifizierung
* Ersatz für Active-Directory
* WebUI
* Open Source
  * Upstream Projekt für Red Hat
  * Red Hat Identity Management (IdM)


# Warum?
* zentrales Management
  * keine unschiedlichen Passwörter
  * Passwort Policiy
* Hochverfügbarkeit
* Web App Authentication
<!-- Note -->
Unterschiedliche Passwörter heißt irgendwann auch mal unsichere Passwörter.
HA durch Replicas, dadurch keine Downtime, dadurch Patching möglich. 


## Bestandteile
* LDAPv3
  * 389 Directory Server
* Single-Sign-On
  * MIT Kerberos
* Certification Authority / X.509
  * Dogtag PKI
* DNS
  * ISC Bind


## Features
* HBAC Regeln
* sudo Regeln
* RBAC Regeln
* Trust zw. Windows AD & FreeIPA
* Replicas


## Die Ba­sics

**Identität:** User, Gruppen, Hosts, Services

**Authentifizierung:** Passwörter, 2FA, SSO

**Autorisierung:** Identitäts bezogene Regeln

**Management:** How-to, WebUI

<!-- Note -->
Identities, Authentication, Authorisation


## Aufbau

![img](images/freeipa_aufbau.svg) <!-- .element: height="400px" -->


![img](images/freeipa_aufbau_trust.svg) <!-- .element: height="400px" -->


## Installation

**Server**
```bash
hostnamectl set-hostname $FQDN
yum install -y ipa-server ipa-server-dns
ipa-server-install -p $DM_PASS -a $ADMIN_PASS \
    -n $DOMAIN -r $REALM
```


**Client**
```bash
yum install -y ipa-client
ipa-client-install [--mkhomedir]
[authconfig --enablemkhomedir --update]
```


## WebUI

![img](images/freeipa_webui_1.png)


<!-- .slide: data-background-iframe="https://ipa-0.demo.example.com/ipa/ui/" data-background-interactive -->


## Ende

Fragen?

[info@b1-systems.de](mailto:info@b1-systems.de)