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

## 1. Prozesslandschaft und Auswahl der Analysetiefe

Eine Business Impact Analysis ist nur so belastbar wie die Prozessliste, auf
der sie aufsetzt. Dieser Abschnitt dokumentiert daher, wie die Kernprozesse
der GermanCrypto Custody AG erhoben wurden und nach welchem Kriterium
entschieden wurde, welche davon in der Tiefe und welche nur grob bewertet
werden.

### 1.1 Vorgehen bei der Prozessidentifikation

Die Erhebung erfolgte in vier Schritten. Grundlage ist Schritt 1 der in
Abschnitt 2 beschriebenen Methodik.

**Schritt 1: Dokumentenanalyse.** Ausgewertet wurden das Organisationsprofil,
die Leistungsbeschreibungen gegenüber Privat- und institutionellen Kunden,
die Unterlagen zur Erlaubnis nach § 1 Abs. 1a Nr. 6 KWG sowie die
Melde- und Berichtspflichten aus DORA und MiCA. Ergebnis war eine Bruttoliste
aller wertschöpfenden und regulatorisch verpflichtenden Tätigkeiten.

**Schritt 2: Strukturierte Interviews mit den Prozessverantwortlichen.** Je
Bereich wurde ein Interview von 60 bis 90 Minuten geführt, geleitet vom
Crisis Manager. Die Interviews folgten einem einheitlichen Leitfaden mit vier
Kernfragen:

- Welche Leistung erbringt Ihr Bereich, und gegenüber wem?
- Was passiert konkret, wenn diese Leistung ausfällt, und ab wann wird es
  kritisch?
- Welche IT-Systeme und welche externen Partner benötigen Sie dafür
  zwingend?
- Wer bemerkt einen Ausfall zuerst, und über welchen Weg wird eskaliert?

Die vierte Frage dient bewusst der Gegenprobe: Prozesse, deren Ausfall
niemand kurzfristig bemerkt, sind selten kritisch, unabhängig davon, wie
wichtig sie im Interview eingeschätzt werden.

**Schritt 3: Konsolidierungsworkshop.** Die Einzelergebnisse wurden
zusammengeführt, Dubletten bereinigt und Kernprozesse von unterstützenden
Tätigkeiten abgegrenzt. Als Kernprozess gilt ein Prozess, der mindestens
eines der beiden folgenden Kriterien erfüllt:

1. Er erbringt unmittelbar die Leistung gegenüber dem Kunden, oder
2. seine Unterbrechung führt innerhalb von 24 Stunden zu einem
   regulatorischen Verstoß.

Tätigkeiten, die keines der beiden Kriterien erfüllen, etwa Marketing oder
Personalverwaltung, wurden bewusst nicht als Kernprozesse geführt. Sie
bleiben damit außerhalb der BIA, ohne dass ihre Bedeutung für den
Normalbetrieb bestritten wird.

**Schritt 4: Validierung durch den Vorstand.** Die konsolidierte Liste wurde
dem Vorstand vorgelegt und durch den Chief Risk Officer freigegeben. Diese
Freigabe ist erforderlich, weil die Prozessliste festlegt, welche Teile des
Unternehmens im Krisenfall Vorrang haben. Das ist eine unternehmerische
Entscheidung und keine rein methodische.

### 1.2 Identifizierte Kernprozesse

Aus diesem Vorgehen ergaben sich sieben Kernprozesse:

| # | Kernprozess | Prozessverantwortlicher Bereich | Erfülltes Kriterium |
|---|---|---|---|
| 1 | Verwahrung digitaler Vermögenswerte | Custody Operations | Kundenleistung |
| 2 | Transaktionsausführung | Transaction Services | Kundenleistung |
| 3 | Regulatorisches Meldewesen | Compliance-Abteilung | Regulatorisch |
| 4 | Interne IT-Sicherheit und Zugriffssteuerung | ISMS-Team mit IT-Betrieb | Beide |
| 5 | Kundenzugriff und Reporting | Client Services | Kundenleistung |
| 6 | Zahlungsverkehr und Fiat-Anbindung | Treasury & Payments | Kundenleistung |
| 7 | Kunden-Onboarding und Identifikation | Compliance-Abteilung | Regulatorisch |

Die Bereichsstruktur und die vollständige Zuordnung sind im Organisationsprofil
(`00_Governance/00_Organisationsprofil.md`, Abschnitt 5.5) dokumentiert.

### 1.3 Auswahl der Prozesse für die Tiefenanalyse

Eine vollständige Tiefenanalyse aller sieben Prozesse war im ersten
BIA-Zyklus nicht leistbar. Die Auswahl der drei tief analysierten Prozesse
erfolgte deshalb nicht nach gefühlter Wichtigkeit, sondern nach einem
inhaltlichen Kriterium: **Jede der im Institut auftretenden Schadensarten
sollte mindestens einmal vollständig durchgerechnet werden.**

Bei einem Krypto-Verwahrer lassen sich drei grundlegend verschiedene
Schadensarten unterscheiden, die sich in Verlauf, Umkehrbarkeit und
Adressat unterscheiden:

| Schadensart | Charakteristik | Repräsentiert durch |
|---|---|---|
| **Irreversibler Vermögensverlust** | Nicht rückholbar, kein Korrekturmechanismus, unmittelbarer Kundenschaden | Verwahrung digitaler Vermögenswerte |
| **Unmittelbarer Geschäftsstillstand** | Umkehrbar, aber mit sofortiger Wirkung auf Umsatz und Kundenvertrauen | Transaktionsausführung |
| **Regulatorischer Verstoß** | Eigenständiger Schaden, unabhängig vom auslösenden Ereignis, Adressat ist die Aufsicht | Regulatorisches Meldewesen |

Damit ist jede Auswirkungskategorie der in Abschnitt 2 definierten
Bewertungsskala mindestens einmal in voller Tiefe belegt. Die
Grobeinstufung der übrigen vier Prozesse in Abschnitt 4 lässt sich an
diesen drei Referenzfällen kalibrieren, statt frei geschätzt zu werden.

Die vollständige Tiefenanalyse der Prozesse 4 bis 7 erfolgt im nächsten
BIA-Reviewzyklus (siehe `00_ICT_Business_Continuity_Policy.md`, Abschnitt 4).

---

## 2. Methodik

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

Die Tiefenanalyse ist im ersten Zyklus auf drei Kernprozesse begrenzt. Die
Auswahl und ihre Begründung sind in Abschnitt 1.3 dokumentiert; die übrigen
Kernprozesse werden grob eingestuft und im nächsten BIA-Reviewzyklus
vollständig nachbewertet.

## 3. Tiefenanalyse der Kernprozesse

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

## 4. Grobeinstufung weiterer Kernprozesse

| Prozess | Grobe Kritikalität | Begründung |
|---|---|---|
| Interne IT-Sicherheit & Zugriffssteuerung | Kritisch | Unterstützt sämtliche anderen Prozesse; Ausfall führt zu vollständigem Zugriffsverlust unternehmensweit |
| Kundenzugriff/-Reporting | Hoch | Hohes Eskalationspotenzial für Vertrauensverlust und Bank-Run-Szenarien, ohne direkten Vermögensverlust |
| Zahlungsverkehr/Fiat-Anbindung | Hoch | Direkter Geschäftsstillstand für Ein-/Auszahlungen, jedoch kein irreversibler Vermögensverlust |
| Kunden-Onboarding & Identifikation | Mittel | Betrifft primär Neugeschäft; bestehende Kundenbeziehungen und -vermögen nicht unmittelbar gefährdet |

## 5. Abhängigkeitsanalyse und abgeleitete System-RTOs

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
