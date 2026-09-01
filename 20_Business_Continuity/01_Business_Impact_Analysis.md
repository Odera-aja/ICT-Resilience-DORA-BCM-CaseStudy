# Business Impact Analysis – GermanCrypto Custody AG

*Mitgeltendes Dokument zur `00_ICT_Business_Continuity_Policy.md`.*

## Zweck

Dieses Dokument dokumentiert die Business Impact Analysis (BIA) der
GermanCrypto Custody AG gemäß DORA Art. 11 Abs. 5, ISO/IEC 22301:2019
Kap. 8.2.2 und BSI-Standard 200-4. Es bewertet die Auswirkung von
Betriebsunterbrechungen auf die Kernprozesse, leitet daraus RTO und RPO ab
und ermittelt über eine Abhängigkeitsanalyse die Wiederanlaufzeiten der
unterstützenden Systeme.

Die Ergebnisse dieses Dokuments sind die unmittelbare Grundlage für die
Definition der Minimum Viable Company (`02_Minimum_Viable_Company.md`).

## 1. Methodik

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
BIA-Reviewzyklus (siehe `00_ICT_Business_Continuity_Policy.md`, Abschnitt 4) vollständig nachbewertet.

## 2. Tiefenanalyse der Kernprozesse

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

## 3. Grobeinstufung weiterer Kernprozesse

| Prozess | Grobe Kritikalität | Begründung |
|---|---|---|
| Interne IT-Sicherheit & Zugriffssteuerung | Kritisch | Unterstützt sämtliche anderen Prozesse; Ausfall führt zu vollständigem Zugriffsverlust unternehmensweit |
| Kundenzugriff/-Reporting | Hoch | Hohes Eskalationspotenzial für Vertrauensverlust und Bank-Run-Szenarien, ohne direkten Vermögensverlust |
| Zahlungsverkehr/Fiat-Anbindung | Hoch | Direkter Geschäftsstillstand für Ein-/Auszahlungen, jedoch kein irreversibler Vermögensverlust |
| Kunden-Onboarding & Identifikation | Mittel | Betrifft primär Neugeschäft; bestehende Kundenbeziehungen und -vermögen nicht unmittelbar gefährdet |

## 4. Abhängigkeitsanalyse und abgeleitete System-RTOs

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

## Freigabe/Genehmigung

| Version | Datum | Autorisiert durch | Änderung |
|---|---|---|---|
| 1.0 | 31.07.2026 | CRO | Initiale Freigabe |
