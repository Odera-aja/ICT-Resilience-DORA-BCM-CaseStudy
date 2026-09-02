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

**Erhebungsgrundlage:** Die BIA wurde im ersten Halbjahr 2026 durchgeführt.
Grundlage sind sieben strukturierte Interviews mit den
Prozessverantwortlichen sowie ein Konsolidierungsworkshop, ergänzt um die
Auswertung der in Abschnitt 1.1 genannten Unterlagen. Die Ergebnisse wurden
dem Vorstand vorgelegt und durch den Chief Risk Officer freigegeben.

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

Die Business Impact Analysis folgt einem sechsstufigen Vorgehen:
(1) Identifikation der Geschäftsprozesse, (2) Definition von
Auswirkungskategorien, (3) Bewertung der Auswirkung über mehrere
Zeithorizonte, (4) Ableitung von MTPD, RTO und RPO, (5) Abhängigkeitsanalyse
kritischer Ressourcen, (6) Konsolidierung zu Kritikalitätsstufen.

### 2.1 Auswirkungskategorien

Bewertet wird über fünf Kategorien: finanzieller Schaden,
regulatorische und rechtliche Konsequenzen, Reputation, Kundenauswirkung
sowie Schaden an Leib und Leben.

### 2.2 Bewertungsskala

| Stufe | Bezeichnung | Bedeutung |
|---|---|---|
| **1** | vernachlässigbar | Kein nach außen spürbarer Schaden, Ausgleich im Regelbetrieb möglich |
| **2** | gering | Interner Mehraufwand, keine Außenwirkung gegenüber Kunden oder Aufsicht |
| **3** | spürbar | Außenwirkung gegenüber einzelnen Kunden oder der Aufsicht, vollständig umkehrbar |
| **4** | schwerwiegend | Erheblicher finanzieller oder reputativer Schaden, aufsichtliche Aufmerksamkeit, Umkehrbarkeit nur mit Aufwand |
| **5** | kritisch, existenzbedrohend | Fortbestand des Instituts oder der Erlaubnis nach § 1 Abs. 1a Nr. 6 KWG gefährdet, oder irreversible Kundenschäden |

Die Bewertung erfolgt über vier Zeithorizonte: 1 Stunde, 4 Stunden,
24 Stunden und 3 Tage. Die Gesamteinstufung eines Zeitpunkts folgt dem
**Worst-Case-Prinzip**: Der höchste Einzelwert über alle fünf Kategorien
bestimmt die Gesamtkritikalität.

### 2.3 Ableitung von MTPD, RTO und RPO

Der **Maximum Tolerable Period of Disruption (MTPD)** ist der Zeitpunkt, ab
dem ein Prozessausfall die Kritikalitätsstufe 5 erreicht, also den Fortbestand
des Instituts oder die Erlaubnis gefährdet. Er wird unmittelbar aus dem
Kritikalitätsverlauf abgelesen und nicht gesondert geschätzt.

Der **RTO** wird deutlich unterhalb des MTPD festgelegt. Der Abstand ist
Sicherheitsmarge: Der MTPD markiert die Bruchstelle, der RTO das
Wiederanlaufziel. Ein RTO auf Höhe des MTPD ließe keinen Spielraum für
Verzögerungen im Wiederanlauf.

Der **RPO** wird aus der Frage abgeleitet, wie viel Datenverlust der Prozess
fachlich verträgt. Er hängt an der Änderungsrate der verarbeiteten Daten
und ist deshalb unabhängig vom RTO zu bestimmen.

### 2.4 Analysetiefe

Die Tiefenanalyse ist im ersten Zyklus auf drei Kernprozesse begrenzt. Die
Auswahl und ihre Begründung sind in Abschnitt 1.3 dokumentiert; die übrigen
Kernprozesse werden grob eingestuft und im nächsten BIA-Reviewzyklus
vollständig nachbewertet.

---

## 3. Tiefenanalyse der Kernprozesse

| Prozess | Kritikalitätsverlauf (1h/4h/24h/3T) | MTPD | RTO | RPO |
|---|---|---|---|---|
| Verwahrung digitaler Vermögenswerte | 4/4/5/5 | 24 h | 2 h | 2 min |
| Transaktionsausführung | 4/4/5/5 | 24 h | 1 h | 30 sek |
| Regulatorisches Meldewesen | 4/5/5/5 | 4 h | 45 min | 30 min |

### 3.1 Regulatorisches Meldewesen als Meta-Risiko

Das regulatorische Meldewesen erreicht als einziger Prozess bereits nach
vier Stunden die maximale Kritikalitätsstufe und hat damit den mit Abstand
kürzesten MTPD. Zwei Gründe:

Erstens der **Meta-Risiko-Charakter** des Prozesses. Eine verpasste
Meldefrist nach DORA Art. 19 verschärft jeden zugrundeliegenden Vorfall um
einen eigenständigen Compliance-Verstoß. Der Schaden entsteht also
zusätzlich zum ursprünglichen Ereignis und ist nicht nachholbar.

Zweitens die hohe Geschwindigkeit, mit der sich reputationsschädigende
Informationen in der Kryptobranche verbreiten.

### 3.2 Warum die Verwahrung einen längeren RTO hat als die Transaktionsausführung

Beide Prozesse haben denselben Kritikalitätsverlauf und denselben MTPD von
24 Stunden, aber unterschiedliche RTOs. Das ist beabsichtigt und beruht auf
einer Eigenschaft des Verwahrgeschäfts:

**Die Verwahrung ist im Stillstand sicher.** Solange die Hardware Security
Module unversehrt sind, führt ein Ausfall der Verwahrfunktion nicht zu einem
Vermögensverlust, sondern zu einer Nichtverfügbarkeit. Das Schlüsselmaterial
bleibt geschützt, gerade weil kein Zugriff möglich ist.

Die **Transaktionsausführung** dagegen erzeugt fortlaufend Umsatz und ist die
für den Kunden unmittelbar sichtbare Leistung. Jede Minute Ausfall bedeutet
entgangene Entgelte und wahrnehmbaren Leistungsausfall.

Die Kritikalität ab 24 Stunden ist bei beiden gleich hoch. Der frühere
Wiederanlauf der Transaktionsausführung ergibt sich aus der laufenden
Schadensakkumulation, nicht aus einem höheren Endschaden.

---

## 4. Grobeinstufung weiterer Kernprozesse

| Prozess | Grobe Kritikalität | Begründung |
|---|---|---|
| Interne IT-Sicherheit und Zugriffssteuerung | Kritisch | Querschnittsprozess. Unterstützt sämtliche anderen Prozesse; ein Ausfall führt zu vollständigem Zugriffsverlust unternehmensweit |
| Kundenzugriff und Reporting | Hoch | Hohes Eskalationspotenzial für Vertrauensverlust und Abzugsverhalten, ohne direkten Vermögensverlust |
| Zahlungsverkehr und Fiat-Anbindung | Hoch | Direkter Geschäftsstillstand für Ein- und Auszahlungen, jedoch kein irreversibler Vermögensverlust |
| Kunden-Onboarding und Identifikation | Mittel | Betrifft primär Neugeschäft; bestehende Kundenbeziehungen und Kundenvermögen sind nicht unmittelbar gefährdet |

**Sonderstellung der internen IT-Sicherheit.** Dieser Prozess setzt keine
eigene Zeitvorgabe, sondern **erbt** sie von den Prozessen, die er
ermöglicht. Er wird deshalb in der Abhängigkeitsanalyse in Abschnitt 5 als
abhängiger Prozess der Identitäts- und Zugangssysteme geführt, ohne einen
eigenen RTO zu definieren. Ein Querschnittsprozess kann nicht später
wiederhergestellt sein als der zeitkritischste Prozess, den er trägt.

---

## 5. Abhängigkeitsanalyse und abgeleitete System-RTOs

Aufbauend auf der Prozess-BIA wird für jedes unterstützende System
ermittelt, von welchen Kernprozessen es abhängt.

### 5.1 Vererbungsregeln

**Der RTO vererbt sich streng.** Der RTO eines Systems entspricht stets dem
kürzesten RTO aller abhängigen Prozesse, da ein System erst dann als
wiederhergestellt gilt, wenn es alle seine Abhängigkeiten bedienen kann.

**Der RPO vererbt sich nicht mechanisch.** Er richtet sich nach der
Änderungsrate der Daten, die das jeweilige System selbst führt. Eine
mechanische Übernahme des strengsten Prozess-RPO würde für Systeme mit
selten veränderlichen Konfigurationsdaten Anforderungen erzeugen, die weder
fachlich begründet noch wirtschaftlich vertretbar wären. Der RPO wird
deshalb je System eigenständig bestimmt.

### 5.2 Architekturgrundsatz

Ein zentraler Architekturgrundsatz liegt dieser Analyse zugrunde: interne
Mitarbeiteridentitäten (verwaltet über Active Directory und IAM) und externe
Kundenidentitäten (verwaltet über ein separates Customer Identity and Access
Management, CIAM) werden strikt getrennt geführt. Diese Trennung verhindert,
dass eine Kompromittierung der öffentlich erreichbaren Kundenlogin-Fläche
einen Pfad zu internen Mitarbeiterkonten eröffnen könnte.

### 5.3 Systeme der tief analysierten Prozesse

| System | Abhängige Kernprozesse | RTO | RPO | Begründung des RPO |
|---|---|---|---|---|
| Hardware Security Module (HSM) | Verwahrung, Transaktionsausführung, interne IT-Sicherheit | 1 h | kein Datenverlust zulässig | Schlüsselmaterial ist nicht rekonstruierbar. Ein Verlust ist irreversibel, unabhängig vom Zeitpunkt |
| Active Directory (interne Mitarbeiteridentitäten) | Verwahrung, Transaktionsausführung, Meldewesen, interne IT-Sicherheit | 45 min | 24 h | Verzeichnisdaten ändern sich selten; Änderungen sind aus dem Personalprozess rekonstruierbar |
| IAM (interne Rechtevergabe) | Verwahrung, Transaktionsausführung, Meldewesen, interne IT-Sicherheit | 45 min | 24 h | Rechteänderungen sind dokumentiert und nachvollziehbar wiederherstellbar |
| Secure Gateways | Verwahrung, Transaktionsausführung, Meldewesen, interne IT-Sicherheit | 45 min | 24 h | Reine Konfigurationsdaten ohne laufende Transaktionsinhalte |
| CIAM (Kundenauthentifizierung) | Verwahrung, Transaktionsausführung | 1 h | 24 h | Kundenstammdaten ändern sich selten; kein Bezug zu Transaktionsständen |
| Custody-Ledger-Datenbank | Verwahrung, Transaktionsausführung | 1 h | **30 sek** | Führt die Transaktions- und Bestandsdaten selbst. Erbt damit den strengsten fachlichen RPO |
| Meldewesen-Dokumentations-Datenbank | Regulatorisches Meldewesen | 45 min | 30 min | Meldeinhalte sind aus den Quellsystemen nachbildbar, jedoch mit Aufwand |

Systeme mit Abhängigkeit zum regulatorischen Meldewesen erben dessen
strengeren RTO von 45 Minuten, auch wenn sie zusätzlich weniger
zeitkritische Prozesse bedienen. Dies spiegelt den in Abschnitt 3.1
beschriebenen Meta-Risiko-Charakter des Meldewesens wider.

**Die Custody-Ledger-Datenbank ist das einzige System mit einem RPO im
Sekundenbereich.** Sie ist damit auch das System mit den höchsten
Anforderungen an die Replikation zwischen den beiden Rechenzentren. Die
synchrone Replikation für Transaktions- und Custody-Daten, die im
Organisationsprofil beschrieben ist, ist genau hierdurch begründet.

### 5.4 Noch nicht analysierte Systeme

Die Prozesse 5 bis 7 (Kundenzugriff und Reporting, Zahlungsverkehr und
Fiat-Anbindung, Kunden-Onboarding und Identifikation) wurden im ersten
Zyklus nur grob eingestuft. Die sie tragenden Systeme, insbesondere das
Kundenportal, die Anbindung an die Korrespondenzbanken und die
KYC-Plattform, sind daher in Abschnitt 5.3 noch nicht mit abgeleiteten
Zeitvorgaben enthalten. Ihre Aufnahme erfolgt im nächsten BIA-Reviewzyklus.

Diese Lücke wirkt sich **nicht auf die Minimum Viable Company aus**: Alle
drei Prozesse gehören nach `02_Minimum_Viable_Company.md`, Abschnitt 2.2,
ausdrücklich nicht zum MVC-Umfang und ruhen im Krisenfall bewusst. Ihre
Zeitvorgaben werden erst für den Rückweg in den Normalbetrieb relevant.

---

## Freigabe/Genehmigung

| Version | Datum | Autorisiert durch | Änderung |
|---|---|---|---|
| 1.0 | 31.07.2026 | CRO | Initiale Freigabe |
| 2.0 | 02.09.2026 | CRO | Prozesslandschaft und Erhebungsvorgehen ergänzt, Begründung der Analysetiefe, Bewertungsskala vollständig definiert, MTPD ausgewiesen, RPO je System hergeleitet, Querschnittsprozess interne IT-Sicherheit in die Abhängigkeitsanalyse aufgenommen, noch nicht analysierte Systeme benannt |
