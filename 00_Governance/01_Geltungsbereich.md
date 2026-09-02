# Geltungsbereich – GermanCrypto Custody AG

## 1. Zweck des Dokuments

Dieses Dokument grenzt den Geltungsbereich der Managementsysteme der
GermanCrypto Custody AG verbindlich ab. Es legt fest, welche
organisatorischen, physischen und technischen Bereiche erfasst werden,
welche Bereiche ausgeschlossen sind, und wie sich diese Grenzen zu den
Anforderungen der Verordnung (EU) 2022/2554 (DORA) verhalten.

Erfasst werden zwei Geltungsbereiche in einem Dokument:

- der Geltungsbereich des Informationssicherheits-Managementsystems (ISMS)
  nach ISO/IEC 27001:2022, Kapitel 4.3
- der Geltungsbereich des Business-Continuity-Managementsystems (BCMS)
  nach ISO/IEC 22301:2019, Kapitel 4.3

Die Zusammenführung ist bewusst gewählt. Beide Geltungsbereiche stützen
sich auf dieselben organisatorischen, physischen und technischen Grenzen.
Zwei getrennte Dokumente würden dieselben Festlegungen doppelt führen und
mit der Zeit auseinanderlaufen. Die Unterschiede zwischen beiden
Managementsystemen sind in den Abschnitten 4 und 5 ausdrücklich benannt.

## 2. Kontext der Organisation

Die GermanCrypto Custody AG ist ein regulierter Anbieter für die Verwahrung
digitaler Vermögenswerte mit Sitz in Frankfurt am Main. Das Institut ist
europaweit tätig, mit einer wesentlichen Konzentration des Kundengeschäfts
im deutschsprachigen und mitteleuropäischen Raum. Weitere Details zu
Organisation, Infrastruktur und Stakeholdern sind im Organisationsprofil
(`00_Organisationsprofil.md`) dokumentiert und werden hier nicht
dupliziert.

## 3. Gemeinsame Grenzen

Die folgenden Grenzen gelten für beide Managementsysteme.

### 3.1 Organisatorische Grenzen

Erfasst ist die gesamte GermanCrypto Custody AG, einschließlich Vorstand,
der Geschäftsbereiche (Custody Operations, Transaction Services, Client
Services, Treasury & Payments), der Compliance-Abteilung, des ISMS-Teams,
des BCM-Departments sowie der IT-Abteilung mit ihren Teilbereichen.

### 3.2 Physische Grenzen

- Primäres Rechenzentrum FDC1, Frankfurt am Main
- Sekundäres Rechenzentrum und Disaster-Recovery-Standort FDC2, Leverkusen
- Hauptsitz und Bürostandort Frankfurt am Main

### 3.3 Technische Grenzen

- Custody-Kernsysteme einschließlich der Hardware Security Module zur
  Erzeugung, Speicherung und Nutzung kryptographischer Schlüssel
- Virtualisierungsplattform (VMware-ESXi-Cluster) und SAN-basierte
  Storage-Infrastruktur an beiden Standorten
- Identitätssysteme: Active Directory, IAM und CIAM
- Mitarbeiter-Endgeräte sowie VPN- und Remote-Access-Infrastruktur

## 4. Geltungsbereich des ISMS (ISO/IEC 27001:2022, Kap. 4.3)

Das ISMS erstreckt sich auf den **Schutz von Informationswerten** innerhalb
der in Abschnitt 3 genannten Grenzen. Betrachtungsgegenstand sind
Informationen, die verarbeitenden Systeme und die zugehörigen Prozesse,
jeweils unter den Schutzzielen Vertraulichkeit, Integrität und
Verfügbarkeit.

Im Mittelpunkt stehen dabei die kryptographischen Schlüssel der Kunden, die
Transaktions- und Bestandsdaten sowie die Identitäts- und
Zugriffsinfrastruktur, über die der Zugang zu diesen Werten gesteuert wird.

## 5. Geltungsbereich des BCMS (ISO/IEC 22301:2019, Kap. 4.3)

Das BCMS erstreckt sich auf die **Aufrechterhaltung der Leistungserbringung**
innerhalb derselben Grenzen. Betrachtungsgegenstand sind hier nicht
Informationswerte, sondern Produkte, Dienstleistungen und die Aktivitäten,
die sie hervorbringen.

Erfasst sind die sieben Kernprozesse, die in der Business Impact Analysis
(`20_Business_Continuity/01_Business_Impact_Analysis.md`, Abschnitt 1.2)
identifiziert und begründet wurden:

1. Verwahrung digitaler Vermögenswerte
2. Transaktionsausführung
3. Regulatorisches Meldewesen
4. Interne IT-Sicherheit und Zugriffssteuerung
5. Kundenzugriff und Reporting
6. Zahlungsverkehr und Fiat-Anbindung
7. Kunden-Onboarding und Identifikation

Über die Systeme hinaus umfasst der BCMS-Geltungsbereich ausdrücklich auch
**Personal, Standorte und kritische Drittparteien**, soweit sie für die
Erbringung dieser Kernprozesse erforderlich sind. Dieser weitere Zuschnitt
ist der wesentliche Unterschied zum ISMS-Geltungsbereich: Ein Ausfall der
Mindestbesetzung oder eines kritischen Dienstleisters ist ein
BCMS-Sachverhalt, auch wenn dabei kein Informationswert betroffen ist.

## 6. Explizite Ausschlüsse

Ausgeschlossen sind das öffentliche Marketing-Portal (Unternehmenswebsite)
sowie angrenzende CRM- und HR-Randsysteme. Begründung: Diese Systeme haben
keinen Zugriff auf schützenswerte Kunden-, Transaktions- oder
Schlüsseldaten und tragen zu keinem der in Abschnitt 5 genannten
Kernprozesse bei.

Der Ausschluss betrifft ausschließlich die Geltungsbereiche nach ISO/IEC
27001 und ISO/IEC 22301. Er entbindet die betroffenen Systeme nicht von der
Betrachtung im Rahmen des DORA-Third-Party-Risikomanagements (siehe
Abschnitte 7 und 8).

Abzugrenzen davon ist der **Ausschluss aus dem MVC-Umfang**
(`20_Business_Continuity/02_Minimum_Viable_Company.md`, Abschnitt 2.2).
Dabei handelt es sich um Prozesse, die sehr wohl im BCMS-Geltungsbereich
liegen, im Krisenfall aber bewusst vorübergehend ruhen. Geltungsbereich und
Priorisierung im Ereignisfall sind zwei verschiedene Ebenen.

## 7. Schnittstellen zu Drittparteien und Cloud-Diensten

Obwohl die Unternehmenswebsite nicht im Geltungsbereich liegt, besteht eine
dokumentationspflichtige Schnittstelle zum externen Cloud-Anbieter, der sie
betreibt. Diese Schnittstelle wird im Rahmen des
Third-Party-Risikomanagements nach DORA erfasst (`30_Third_Party_Risk/`, in
Arbeit), unabhängig vom Scope-Status der Website selbst.

Gleiches gilt sinngemäß für weitere kritische Drittanbieter mit
Schnittstellen zu Scope-Systemen, unter anderem HSM-Hersteller,
Virtualisierungsanbieter, Firewall-Anbieter, ServiceNow und das physische
Sicherheitsunternehmen.

## 8. Anwendbarkeit von DORA im Verhältnis zu den Normgeltungsbereichen

Während die Geltungsbereiche nach ISO/IEC 27001 und ISO/IEC 22301 bewusst
eingegrenzt wurden, erfasst die Verordnung (EU) 2022/2554 (DORA)
grundsätzlich die gesamte ICT-Landschaft des Instituts, einschließlich der
unter Abschnitt 6 ausgeschlossenen Randsysteme.

DORA kennt kein Scoping-Konzept im Sinne von ISO/IEC 27001:2022, Kapitel
4.3. Stattdessen gilt der Verhältnismäßigkeitsgrundsatz nach DORA Art. 4,
wonach Art und Umfang der Maßnahmen risikobasiert auf das jeweilige System
anzuwenden sind.

Enge Normgeltungsbereiche und weiter DORA-Anwendungsbereich stehen somit
nicht im Widerspruch, sondern ergänzen sich: Kernsysteme werden vollständig
nach den Normen und nach DORA gesteuert, ausgeschlossene Randsysteme
unterliegen weiterhin einer risikobasierten Betrachtung im Rahmen des
DORA-Drittparteienmanagements.

## 9. Freigabe/Genehmigung

Dieses Dokument ist Grundlage aller nachfolgenden Dokumente des ISMS und
des BCMS. Der ISMS-Geltungsbereich wurde durch den Chief Information
Security Officer autorisiert, der BCMS-Geltungsbereich durch den Chief Risk
Officer als für das BCM-Department verantwortliches Vorstandsmitglied.

| Version | Datum | Autorisiert durch | Änderung |
|---|---|---|---|
| 1.0 | 27.07.2026 | CISO | Initiale Freigabe des ISMS-Geltungsbereichs |
| 2.0 | 02.09.2026 | CISO und CRO | Zusammenführung mit dem BCMS-Geltungsbereich nach ISO/IEC 22301 Kap. 4.3, Abgrenzung zwischen Geltungsbereich und MVC-Priorisierung |
