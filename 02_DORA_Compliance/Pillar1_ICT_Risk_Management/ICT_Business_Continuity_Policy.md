# ICT Business Continuity Policy – GermanCrypto Custody AG

## 1. Zweck und regulatorischer Rahmen

Diese Policy legt das Rahmenwerk fest, mit dem die GermanCrypto Custody AG 
ihre operative Widerstandsfähigkeit (Resilienz) gegenüber Störungen und 
Krisenereignissen sicherstellt – einschließlich, aber nicht beschränkt 
auf Cyberangriffe, Naturkatastrophen, Stromausfälle und sonstige 
Betriebsunterbrechungen. Die Policy definiert, wie im Ernstfall reagiert 
wird, um finanzielle Insolvenz, regulatorische Verstöße, Reputations-
schäden sowie Schäden an Leib und Leben zu verhindern. Ein zentrales 
Element ist die Festlegung der Minimum Viable Company (MVC) – der 
minimalen Kombination kritischer Systeme, Prozesse und Ressourcen, die 
auch im schwersten Krisenfall aufrechterhalten werden müssen.

Regulatorische Compliance (insbesondere gegenüber DORA) ist dabei eine 
Konsequenz echter operativer Resilienz, nicht deren Selbstzweck. Diese 
Policy dient als übergeordnetes Rahmenwerk; die konkrete Umsetzung und 
regelmäßige Überprüfung ihrer Wirksamkeit erfolgt über den in Abschnitt 7 
definierten Testing- und Übungszyklus.

**Regulatorischer Rahmen:**
- **DORA Art. 11** (Verordnung (EU) 2022/2554) – verpflichtet 
  Finanzinstitute zu einer dedizierten ICT-Business-Continuity-Policy 
  mit Wiederanlaufplänen, Reaktionsstrategien und Kommunikationsplänen
- **ISO/IEC 22301** – internationaler Standard für 
  Business-Continuity-Management-Systeme (BCMS), unabhängig von, aber 
  eng verzahnt mit ISO/IEC 27001
- **BSI-Standard 200-4** – deutsche BCM-Methodik, eng an ISO 22301 
  angelehnt, mit ergänzenden nationalen Prüfungsanforderungen

## 2. BCM-Governance und Rollen

Dieser Abschnitt beschreibt die Governance-Struktur des BCM-Departments. 
Da Business Continuity Management breiter gefasst ist als reine 
Informationssicherheit – es umfasst neben ICT auch Personal, Gebäude 
und Lieferketten – wird BCM als eigenständiges Department geführt, 
getrennt vom ISMS-Team. Beide Bereiche arbeiten eng zusammen, 
insbesondere bei ICT-bezogenen Krisenereignissen.

Die Leitung des Departments obliegt dem Crisis Manager, der direkt an 
den Chief Risk Officer (CRO) berichtet. Der Crisis Manager leitet 
zugleich das IT Service Continuity Management (ITSCM)-Team, das für 
die technische Wiederherstellung von IT-Services im Krisenfall 
verantwortlich ist.

Im Ereignisfall tritt der Krisenstab zusammen – ein temporäres, 
funktionsübergreifendes Entscheidungsgremium, das ausschließlich im 
Krisenfall aktiviert wird und im Normalbetrieb nicht besteht. Der 
Krisenstab setzt sich zusammen aus je einem Vertreter bzw. einer 
Vertreterin des Vorstands, der Unternehmenskommunikation (PR), der 
IT-Abteilung sowie des internen Audit-Teams.

## 3. Business Impact Analysis (BIA): Methodik und Ergebnisse

### 3.1 Methodik

Die Business Impact Analysis wird gemäß DORA Art. 11 Abs. 5, ISO/IEC 
22301:2019 Kapitel 8.2.2 und BSI-Standard 200-4 durchgeführt und folgt 
einem sechsstufigen Vorgehen: (1) Identifikation der Geschäftsprozesse, 
(2) Definition von Auswirkungskategorien, (3) Bewertung der Auswirkung 
über mehrere Zeithorizonte, (4) Ableitung von RTO/RPO aus dem Maximum 
Tolerable Period of Disruption (MTPD), (5) Abhängigkeitsanalyse 
kritischer Ressourcen, (6) Konsolidierung zu Kritikalitätsstufen.

Auswirkungen werden auf einer Skala von 1 (vernachlässigbar) bis 5 
(kritisch/existenzbedrohend) über vier Zeithorizonte (1h, 4h, 24h, 
3 Tage) und fünf Kategorien bewertet: Finanzieller Schaden, 
Regulatorische/rechtliche Konsequenzen, Reputation, Kundenauswirkung, 
Schaden an Leib und Leben. Die Gesamteinstufung eines Zeitpunkts folgt 
dem Worst-Case-Prinzip: Der höchste Einzelwert über alle Kategorien 
bestimmt die Gesamtkritikalität.

Aus Kapazitätsgründen wird die vollständige BIA-Tiefenanalyse zunächst 
auf drei repräsentative Kernprozesse fokussiert. Die übrigen 
Kernprozesse werden grob eingestuft und im Rahmen des nächsten 
BIA-Reviewzyklus (siehe Abschnitt 8) vollständig nachbewertet.

### 3.2 Tiefenanalyse der Kernprozesse

| Prozess | RTO | RPO | Kritikalitätsverlauf (1h/4h/24h/3T) |
|---|---|---|---|
| Verwahrung digitaler Vermögenswerte | 2h | 2min | 4/4/5/5 |
| Transaktionsausführung | 1h | 30sek | 4/4/5/5 |
| Regulatorisches Meldewesen | 45min | 30min | 4/5/5/5 |

Bemerkenswert: Regulatorisches Meldewesen erreicht als einziger 
Prozess bereits nach 4 Stunden die maximale Kritikalitätsstufe erreicht,
begründet durch den Meta-Risiko-Charakter des Prozesses (eine 
verpasste Meldefrist nach DORA Art. 19 verschärft jeden zugrunde-
liegenden Incident zusätzlich um einen eigenständigen Compliance-
Verstoß) sowie die hohe Geschwindigkeit reputationsschädigender 
Verbreitung in der Kryptobranche.

### 3.3 Grobeinstufung weiterer Kernprozesse

| Prozess | Grobe Kritikalität | Begründung |
|---|---|---|
| Interne IT-Sicherheit & Zugriffssteuerung | Kritisch | Unterstützt sämtliche anderen Prozesse; Ausfall führt zu vollständigem Zugriffsverlust unternehmensweit |
| Kundenzugriff/-Reporting | Hoch | Hohes Eskalationspotenzial für Vertrauensverlust und Bank-Run-Szenarien, ohne direkten Vermögensverlust |
| Zahlungsverkehr/Fiat-Anbindung | Hoch | Direkter Geschäftsstillstand für Ein-/Auszahlungen, jedoch kein irreversibler Vermögensverlust |
| Kunden-Onboarding & Identifikation | Mittel | Betrifft primär Neugeschäft; bestehende Kundenbeziehungen und -vermögen nicht unmittelbar gefährdet |

### 3.4 Abhängigkeitsanalyse und abgeleitete System-RTOs

Aufbauend auf der Prozess-BIA wird für jedes unterstützende System 
ermittelt, von welchen Kernprozessen es abhängt. Der RTO eines Systems 
entspricht dabei stets dem strengsten (kürzesten) RTO aller abhängigen 
Prozesse, da ein System erst dann als wiederhergestellt gelten kann, 
wenn es alle seine Abhängigkeiten bedienen kann.

Ein zentraler Architekturgrundsatz liegt dieser Analyse zugrunde: 
interne Mitarbeiteridentitäten (verwaltet über Active Directory und 
IAM) und externe Kundenidentitäten (verwaltet über ein separates 
Customer Identity and Access Management, CIAM) werden strikt getrennt 
geführt. Diese Trennung verhindert, dass eine Kompromittierung der 
öffentlich erreichbaren Kundenlogin-Fläche einen Pfad zu internen 
Mitarbeiterkonten eröffnen könnte.

| System | Abhängige Kernprozesse | Abgeleiteter RTO |
|---|---|---|
| Hardware Security Module (HSM) | Verwahrung digitaler Vermögenswerte, Transaktionsausführung | 1h |
| Active Directory (interne Mitarbeiteridentitäten) | Verwahrung, Transaktionsausführung, Regulatorisches Meldewesen | 45min |
| IAM (interne Rechtevergabe) | Verwahrung, Transaktionsausführung, Regulatorisches Meldewesen | 45min |
| CIAM (Kundenauthentifizierung) | Verwahrung, Transaktionsausführung | 1h |
| Secure Gateways | Verwahrung, Transaktionsausführung, Regulatorisches Meldewesen | 45min |
| Custody-Ledger-Datenbank | Verwahrung, Transaktionsausführung | 1h |
| Meldewesen-Dokumentations-Datenbank | Regulatorisches Meldewesen | 45min |

Systeme mit Abhängigkeit zum Regulatorischen Meldewesen erben dessen 
strengeren RTO von 45 Minuten, auch wenn sie zusätzlich weniger 
zeitkritische Prozesse bedienen. Dies spiegelt den in Abschnitt 3.2 
beschriebenen Meta-Risiko-Charakter des Meldewesens wider.

## 4. Minimum Viable Company (MVC): Definition

Die Minimum Viable Company beschreibt die minimale Kombination aus 
Systemen, Personal und Drittparteien-Anbindungen, die auch im 
schwersten Krisenfall aufrechterhalten werden muss, um finanzielle 
Insolvenz, regulatorische Verstöße und irreversible Schäden für 
Kunden abzuwenden. Die MVC-Definition basiert unmittelbar auf den 
Ergebnissen der Business Impact Analysis (Abschnitt 3) und deren 
Abhängigkeitsanalyse.

### 4.1 Kritische Systeme

Folgende Systeme sind gemäß Abhängigkeitsanalyse (Abschnitt 3.4) 
Bestandteil der MVC und müssen gemäß ihrem jeweiligen RTO 
wiederhergestellt werden:

- Hardware Security Module (HSM)
- Active Directory (interne Mitarbeiteridentitäten)
- IAM (interne Rechtevergabe)
- CIAM (Kundenauthentifizierung)
- Secure Gateways
- Custody-Ledger-Datenbank
- Meldewesen-Dokumentations-Datenbank

### 4.2 Mindestpersonalbesetzung

Um den Betrieb der MVC-Systeme im Krisenfall sicherzustellen, gelten 
folgende Mindestbesetzungen mit definierter Vertretungsfähigkeit 
(Bus-Factor-Prinzip):

| Bereich | Mindestbesetzung | Anmerkung |
|---|---|---|
| ITSCM-Team | 2 Personen | Mindestens zwei Personen müssen jede kritische Wiederherstellungsaufgabe eigenständig ausführen können |
| IT-Ops-Bereiche (Betrieb, Firewall, Virtualisierung, Backup) | 2 Personen je Bereich | Sicherstellung technischer Grundfunktionen |
| Krisenstab | Alle 4 definierten Rollen (Vorstand, PR, IT, Audit) | Funktionsübergreifende Entscheidungsfähigkeit erfordert vollständige Besetzung gemäß Abschnitt 2 |

### 4.3 Kritische Drittparteien

Die MVC ist zusätzlich von der Verfügbarkeit folgender kritischer 
Drittanbieter abhängig (Detailerfassung im Third-Party-Register unter 
DORA Pillar 4):

- HSM-Hersteller (Wartung/Support)
- Blockchain-Node-Infrastruktur-Anbieter

Diese Abhängigkeiten werden im Rahmen des Third-Party-Risikomanagements 
gesondert bewertet und sind nicht Gegenstand der internen 
BIA-Zeithorizont-Analyse.

---

> 🔄 **Abschnitte 5 bis 8 befinden sich in Arbeit.** Vorgesehen sind:
> **5. Wiederanlaufstrategien**, **6. Notfall- und Wiederanlaufpläne inklusive
> Krisenkommunikation**, **7. Testing- und Übungszyklus** und
> **8. Review-Zyklus und kontinuierliche Verbesserung**. Auf die Abschnitte 7
> und 8 wird in Abschnitt 1 beziehungsweise 3.1 bereits verwiesen.

---

## 9. Freigabe/Genehmigung

Diese ICT Business Continuity Policy wurde durch den Chief Risk Officer (CRO)
der GermanCrypto Custody AG autorisiert. Die fachliche Verantwortung für
Pflege und Umsetzung liegt beim Crisis Manager als Leiter des BCM-Departments
(siehe Abschnitt 2).

| Version | Datum | Autorisiert durch | Änderung |
|---|---|---|---|
| 1.0 | 31.07.2026 | CRO | Initiale Freigabe |
