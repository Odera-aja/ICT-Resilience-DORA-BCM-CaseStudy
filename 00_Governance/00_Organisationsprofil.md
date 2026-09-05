# Organisationsprofil – GermanCrypto Custody AG

## 1. Unternehmensübersicht

Die GermanCrypto Custody AG ist ein regulierter Anbieter für die Verwahrung 
digitaler Vermögenswerte mit Sitz in Frankfurt am Main. Das Institut ist 
europaweit tätig, mit einer wesentlichen Konzentration des Kundengeschäfts 
im deutschsprachigen und mitteleuropäischen Raum.

- Mitarbeiterzahl: ca. 2.500
- Verwahrtes Kundenvermögen (Assets under Custody, AuC): ca. 15 Mrd. EUR
- Geografische Tätigkeit: europaweit, mit regionalem Schwerpunkt
- Primäres Rechenzentrum: Frankfurt am Main (FDC1)
- Sekundäres Rechenzentrum / Disaster-Recovery-Standort: Leverkusen (FDC2)

## 2. Geschäftstätigkeit

Die GermanCrypto Custody AG bietet sowohl Privatkunden als auch 
institutionellen Kunden (u. a. Fonds und Family Offices) die sichere 
Verwahrung digitaler Vermögenswerte (Kryptowerte) an. Das Kerngeschäft 
umfasst die technische und rechtliche Verwahrung privater kryptographischer 
Schlüssel sowie die sichere Abwicklung von Transaktionen im Auftrag der 
Kunden. Die Kundenbasis ist europaweit verteilt, mit deutlichem regionalem 
Schwerpunkt im deutschsprachigen Raum.

## 3. Regulatorischer Status

Die Gesellschaft verfügt über eine Erlaubnis zum Kryptoverwahrgeschäft 
gemäß § 1 Abs. 1a Nr. 6 KWG, erteilt durch die Bundesanstalt für 
Finanzdienstleistungsaufsicht (BaFin), sowie über eine Zulassung als 
Crypto-Asset Service Provider (CASP) gemäß der EU-Verordnung über Märkte 
für Kryptowerte (MiCA). Die BaFin ist die zuständige nationale 
Aufsichtsbehörde sowohl für die KWG- als auch für die CASP-Zulassung. 
Als Finanzinstitut unterliegt die Gesellschaft zudem den Anforderungen 
der Verordnung (EU) 2022/2554 (DORA) zur digitalen operationalen 
Resilienz.

## 4. IT-Infrastruktur-Übersicht (High-Level)

Die IT-Infrastruktur der GermanCrypto Custody AG ist konsequent 
on-premise ausgerichtet, mit Ausnahme unkritischer Randsysteme.

- Primäres Rechenzentrum (FDC1) in Frankfurt am Main sowie sekundäres 
  Rechenzentrum (FDC2) in Leverkusen im Active-Passive-Betrieb
- Datenreplikation zwischen FDC1 und FDC2: synchron für kritische 
  Transaktions- und Custody-Daten, asynchron für alle übrigen Systeme
- Virtualisierungsplattform: VMware-ESXi-Cluster an beiden Standorten
- Storage: SAN-basierte Speicherinfrastruktur (Storage Area Network) mit 
  Replikation zwischen FDC1 und FDC2
- Hardware Security Module (HSM) an beiden Standorten zur sicheren 
  Erzeugung, Speicherung und Nutzung kryptographischer Schlüssel, um im 
  Falle eines Failovers die Signaturfähigkeit am sekundären Standort 
  sicherzustellen
- Cloud-Nutzung: ausschließlich für nicht-kritische Randsysteme 
  (z. B. Unternehmenswebsite); sämtliche Kernsysteme mit Kunden- und 
  Transaktionsdaten verbleiben strikt on-premise

## 5. Organisationsstruktur

- Mitarbeiterzahl: ca. 2.500
- Hauptsitz und zentraler Bürostandort: Frankfurt am Main

### 5.1 Vorstand

Geschäftsführung/Vorstand: Vorstandsvorsitzender (CEO), Chief Financial 
Officer (CFO), Chief Risk Officer (CRO), Chief Information Security 
Officer (CISO).

Der CISO berichtet direkt an den Gesamtvorstand und ist fachlich an den 
CRO angebunden, um sowohl Unabhängigkeit von der operativen IT als auch 
Einbettung in das unternehmensweite Risikomanagement sicherzustellen 
(in Anlehnung an ISO/IEC 27001:2022, Kapitel 5.3).

### 5.2 Geschäftsbereiche

Die wertschöpfenden Bereiche sind entlang der Kundenleistung geschnitten:

| Bereich | Aufgabe | Berichtslinie |
|---|---|---|
| **Custody Operations** | Betrieb der Verwahrlösung, Verwaltung und Absicherung der privaten kryptographischen Schlüssel, Betrieb der HSM-Prozesse | CEO |
| **Transaction Services** | Prüfung, Freigabe und Abwicklung von Kundentransaktionen, Anbindung an die Blockchain-Node-Infrastruktur | CEO |
| **Client Services** | Kundenbetreuung, Bestands- und Transaktionsreporting gegenüber Privat- und institutionellen Kunden | CEO |
| **Treasury & Payments** | Fiat-Anbindung, Ein- und Auszahlungsverkehr, Abstimmung mit Korrespondenzbanken | CFO |

### 5.3 Kontroll- und Steuerungsfunktionen

| Bereich | Aufgabe | Berichtslinie |
|---|---|---|
| **Compliance-Abteilung** | Aufsichtsrechtliche Compliance, Geldwäscheprävention, Kunden-Onboarding und Identifikation (KYC) sowie das regulatorische Meldewesen gegenüber BaFin und ESMA | CRO |
| **Recht und Datenschutz** | Rechtliche Beratung der Geschäftsbereiche sowie Wahrnehmung der Aufgaben des Datenschutzbeauftragten nach Art. 37 DSGVO. Im Krisenfall Mitglied des Krisenstabs | CRO |
| **ISMS-Team** | Betrieb des Informationssicherheits-Managementsystems. Besetzung: CISO sowie drei weitere Mitarbeitende | CISO |
| **BCM-Department** | Business Continuity Management als eigenständiges Department, geleitet vom Crisis Manager. Umfasst zugleich das IT Service Continuity Management (ITSCM). Aufbau und Aufgaben sind in der ICT Business Continuity Policy beschrieben | CRO |

### 5.4 IT-Abteilung

Die IT-Abteilung ist in folgende Teilbereiche organisiert: 
IT-Betrieb/Support, Softwareentwicklung (eigenes Dev-Team), 
ITIL-Prozessmanagement, Backup-Team, Firewall-Team, 
Virtualisierungs-Team (VM-Team).

### 5.5 Zuordnung der Kernprozesse zu Prozessverantwortlichen

Diese Zuordnung ist die organisatorische Grundlage der Business Impact 
Analysis. Prozessverantwortlich ist jeweils die Leitung des genannten 
Bereichs.

| Kernprozess | Verantwortlicher Bereich |
|---|---|
| Verwahrung digitaler Vermögenswerte | Custody Operations |
| Transaktionsausführung | Transaction Services |
| Regulatorisches Meldewesen | Compliance-Abteilung |
| Interne IT-Sicherheit und Zugriffssteuerung | ISMS-Team gemeinsam mit IT-Betrieb |
| Kundenzugriff und Reporting | Client Services |
| Zahlungsverkehr und Fiat-Anbindung | Treasury & Payments |
| Kunden-Onboarding und Identifikation | Compliance-Abteilung |

## 6. Stakeholder-Übersicht

**Kunden**
- Retail-Kunden (Privatpersonen)
- Institutionelle Kunden (u. a. Fonds, Family Offices)

**Aufsichtsbehörden und regulatorische Stakeholder**
- BaFin – nationale Aufsichtsbehörde für KWG- und CASP-Zulassung, 
  zuständige Behörde im Sinne von DORA Art. 46
- ESMA – europäische Wertpapier- und Marktaufsichtsbehörde, zuständig 
  für EU-weite Leitlinien unter MiCA
- BSI (Bundesamt für Sicherheit in der Informationstechnik) – aktuell 
  kein verpflichtendes Aufsichtsverhältnis; relevant als Herausgeber des 
  IT-Grundschutz-Standards (freiwillige methodische Referenz) sowie als 
  potenzieller Ansprechpartner im Falle einer künftigen 
  KRITIS-Einstufung

**Kritische Drittanbieter** (grobe Übersicht, Detailerfassung im 
Third-Party-Register unter DORA Pillar 4)
- Blockchain-Node-Infrastruktur-Anbieter
- HSM-Hersteller (Wartung/Support)
- ESXi-/Virtualisierungsanbieter
- Firewall-Anbieter
- Cloud-Anbieter (für die Unternehmenswebsite)
- ServiceNow (Ticketing und Governance-Workflows)
- Physisches Sicherheitsunternehmen (Zutrittskontrolle Rechenzentren)
- Wirtschaftsprüfer

**Interne Stakeholder**
- Vorstand
- ISMS-Team
- IT-Abteilung
- Compliance-Abteilung
