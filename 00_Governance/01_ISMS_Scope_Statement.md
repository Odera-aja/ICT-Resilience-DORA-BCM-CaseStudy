# ISMS Scope Statement – GermanCrypto Custody AG

## 1. Zweck des Dokuments

Dieses Dokument dient dazu, den Geltungsbereich (Scope) des Informations-
sicherheits-Managementsystems (ISMS) der GermanCrypto Custody AG gemäß 
ISO/IEC 27001:2022, Kapitel 4.3, verbindlich abzugrenzen und zu 
dokumentieren. Es legt fest, welche organisatorischen, physischen und 
technischen Bereiche vom ISMS erfasst werden, welche Bereiche explizit 
ausgeschlossen sind, und wie sich der Geltungsbereich zu den 
Anforderungen der Verordnung (EU) 2022/2554 (DORA) verhält.

## 2. Kontext der Organisation

Die GermanCrypto Custody AG ist ein regulierter Anbieter für die 
Verwahrung digitaler Vermögenswerte mit Sitz in Frankfurt am Main. Das 
Institut ist europaweit tätig, mit einer wesentlichen Konzentration des 
Kundengeschäfts im deutschsprachigen und mitteleuropäischen Raum. Weitere 
Details zu Organisation, Infrastruktur und Stakeholdern sind im 
Organisationsprofil (`00_Governance/00_Organisationsprofil.md`) 
dokumentiert und werden an dieser Stelle nicht dupliziert.

## 3. Geltungsbereich (Scope) — positiv definiert

### Organisatorische Grenzen
Der Geltungsbereich des ISMS umfasst die gesamte GermanCrypto Custody AG, 
einschließlich Vorstand, IT-Abteilung (IT-Betrieb, Softwareentwicklung, 
ITIL, Backup-Team, Firewall-Team, Virtualisierungs-Team), ISMS-Team und 
Compliance-Abteilung.

### Physische Grenzen
- Primäres Rechenzentrum FDC1, Frankfurt am Main
- Sekundäres Rechenzentrum / Disaster-Recovery-Standort FDC2, Leverkusen
- Hauptsitz und Bürostandort Frankfurt am Main

### Technische und systemische Grenzen
- Custody-Kernsysteme (einschließlich der Hardware Security Module zur 
  Erzeugung, Speicherung und Nutzung kryptographischer Schlüssel für 
  Kundentransaktionen)
- Virtualisierungsplattform (VMware-ESXi-Cluster) und SAN-basierte 
  Storage-Infrastruktur an beiden Standorten
- Mitarbeiter-Endgeräte sowie VPN- und Remote-Access-Infrastruktur zur 
  Anbindung von Homeoffice-Arbeitsplätzen

## 4. Explizite Ausschlüsse

Vom Geltungsbereich des ISMS ausgeschlossen sind das öffentliche 
Marketing-Portal (Unternehmenswebsite) sowie angrenzende CRM- und 
HR-Randsysteme. Die Begründung für diesen Ausschluss liegt darin, dass 
diese Systeme keinen Zugriff auf schützenswerte Kunden-, Transaktions- 
oder Schlüsseldaten haben und somit kein signifikantes 
Informationssicherheitsrisiko im Sinne des ISMS-Geltungsbereichs 
darstellen. Der Ausschluss betrifft ausschließlich den ISO-27001-Scope; 
er entbindet die betroffenen Systeme nicht von der Betrachtung im Rahmen 
des DORA-Third-Party-Risikomanagements (siehe Abschnitt 5 und 6).

## 5. Schnittstellen zu Drittparteien und Cloud-Diensten

Obwohl die Unternehmenswebsite nicht im Geltungsbereich des ISMS liegt, 
besteht eine dokumentationspflichtige Schnittstelle zum externen 
Cloud-Anbieter, der die Website betreibt. Diese Schnittstelle wird im 
Rahmen des Third-Party-Risikomanagements nach DORA Pillar 4 
(`02_DORA_Compliance/Pillar4_Third_Party_Risk/`) erfasst, unabhängig vom 
ISO-Scope-Status der Website selbst. Gleiches gilt sinngemäß für weitere 
kritische Drittanbieter mit Schnittstellen zu Scope-Systemen (u. a. 
HSM-Hersteller, ESXi-/Virtualisierungsanbieter, Firewall-Anbieter, 
ServiceNow, physisches Sicherheitsunternehmen), die im Third-Party-
Register separat geführt werden.

## 6. Anwendbarkeit von DORA im Verhältnis zum ISO-Scope

Während der ISO-27001-Geltungsbereich bewusst eingegrenzt wurde, erfasst 
die Verordnung (EU) 2022/2554 (DORA) grundsätzlich die gesamte 
ICT-Landschaft des Instituts, einschließlich der unter Abschnitt 4 
ausgeschlossenen Randsysteme. DORA kennt kein Scoping-Konzept im Sinne 
von ISO/IEC 27001:2022, Kapitel 4.3; stattdessen gilt der 
Verhältnismäßigkeitsgrundsatz (DORA Art. 4), wonach Art und Umfang der 
Maßnahmen risikobasiert auf das jeweilige System anzuwenden sind. Der 
enge ISO-Scope und der weite DORA-Anwendungsbereich stehen somit nicht 
im Widerspruch, sondern ergänzen sich: Kernsysteme werden vollständig 
nach ISO 27001 und DORA gesteuert, ausgeschlossene Randsysteme unterliegen 
weiterhin einer risikobasierten Betrachtung im Rahmen des 
DORA-Drittparteienmanagements.

## 7. Freigabe/Genehmigung

Dieses ISMS Scope Statement wurde durch den Chief Information Security 
Officer (CISO) der GermanCrypto Custody AG autorisiert und ist 
Grundlage für alle nachfolgenden ISMS-Dokumente.

| Version | Datum | Autorisiert durch | Änderung |
|---|---|---|---|
| 1.0 | 27.07.2026 | CISO | Initiale Freigabe |
