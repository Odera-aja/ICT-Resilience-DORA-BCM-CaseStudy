# Minimum Viable Company (MVC) – GermanCrypto Custody AG

*Mitgeltendes Dokument zur `00_ICT_Business_Continuity_Policy.md`.*

## Zweck

Die Minimum Viable Company beschreibt die minimale Kombination aus 
Systemen, Personal und Drittparteien-Anbindungen, die auch im 
schwersten Krisenfall aufrechterhalten werden muss, um finanzielle 
Insolvenz, regulatorische Verstöße und irreversible Schäden für 
Kunden abzuwenden. Die MVC-Definition basiert unmittelbar auf den 
Ergebnissen der Business Impact Analysis (Abschnitt 3) und deren 
Abhängigkeitsanalyse.

## 1. Kritische Systeme

Folgende Systeme sind gemäß Abhängigkeitsanalyse (`01_Business_Impact_Analysis.md`, Abschnitt 5) 
Bestandteil der MVC und müssen gemäß ihrem jeweiligen RTO 
wiederhergestellt werden:

- Hardware Security Module (HSM)
- Active Directory (interne Mitarbeiteridentitäten)
- IAM (interne Rechtevergabe)
- CIAM (Kundenauthentifizierung)
- Secure Gateways
- Custody-Ledger-Datenbank
- Meldewesen-Dokumentations-Datenbank

## 2. Mindestpersonalbesetzung

Um den Betrieb der MVC-Systeme im Krisenfall sicherzustellen, gelten 
folgende Mindestbesetzungen mit definierter Vertretungsfähigkeit 
(Bus-Factor-Prinzip):

| Bereich | Mindestbesetzung | Anmerkung |
|---|---|---|
| ITSCM-Team | 2 Personen | Mindestens zwei Personen müssen jede kritische Wiederherstellungsaufgabe eigenständig ausführen können |
| IT-Ops-Bereiche (Betrieb, Firewall, Virtualisierung, Backup) | 2 Personen je Bereich | Sicherstellung technischer Grundfunktionen |
| Krisenstab | Alle 4 definierten Rollen (Vorstand, PR, IT, Audit) | Funktionsübergreifende Entscheidungsfähigkeit erfordert vollständige Besetzung gemäß `00_ICT_Business_Continuity_Policy.md`, Abschnitt 2 |

## 3. Kritische Drittparteien

Die MVC ist zusätzlich von der Verfügbarkeit folgender kritischer 
Drittanbieter abhängig (Detailerfassung im Third-Party-Register unter 
DORA Pillar 4):

- HSM-Hersteller (Wartung/Support)
- Blockchain-Node-Infrastruktur-Anbieter

Diese Abhängigkeiten werden im Rahmen des Third-Party-Risikomanagements 
gesondert bewertet und sind nicht Gegenstand der internen 
BIA-Zeithorizont-Analyse.

## Freigabe/Genehmigung

| Version | Datum | Autorisiert durch | Änderung |
|---|---|---|---|
| 1.0 | 31.07.2026 | CRO | Initiale Freigabe |
