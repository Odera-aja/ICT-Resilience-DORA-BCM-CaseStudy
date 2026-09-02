# Minimum Viable Company (MVC) – GermanCrypto Custody AG

*Mitgeltendes Dokument zur `00_ICT_Business_Continuity_Policy.md`.*

## Zweck

Dieses Dokument definiert die Minimum Viable Company der GermanCrypto
Custody AG: die minimale Kombination aus Systemen, Personal, Dokumentation
und Drittparteien-Anbindungen, die auch im schwersten Krisenfall
aufrechterhalten werden muss, um finanzielle Insolvenz, regulatorische
Verstöße und irreversible Schäden für Kunden abzuwenden.

Es legt zugleich fest, **was im Krisenfall bewusst nicht aufrechterhalten
wird**, in welcher **Reihenfolge** der Wiederanlauf erfolgt und **wie lange**
das Institut im MVC-Zustand betrieben werden kann.

Die Definition basiert unmittelbar auf den Ergebnissen der Business Impact
Analysis (`01_Business_Impact_Analysis.md`) und deren Abhängigkeitsanalyse.

---

## 1. Begriff und normative Einordnung

### 1.1 Definition

Die Minimum Viable Company ist die kleinste Version der Organisation, die
noch funktionsfähig ist, Kunden bedient und ihre regulatorischen Pflichten
erfüllt, während alle übrigen Teile des Unternehmens ausgefallen sind oder
bewusst nicht betrieben werden.

Der Unterschied zum klassischen Disaster Recovery ist grundlegend: Disaster
Recovery fragt, wie ein einzelnes System innerhalb einer Zielzeit
zurückgeholt wird. Die MVC fragt, **welche Version des gesamten Unternehmens
zuerst wieder existieren muss**, damit das Institut überlebt, und was mit
allem anderen geschieht.

### 1.2 Verhältnis zu ISO/IEC 22301

Der Begriff „Minimum Viable Company" ist in keiner Norm definiert. Er ist
ein Praxisbegriff, der überwiegend von Beratungshäusern und Herstellern von
Backup- und Recovery-Lösungen geprägt wurde.

Sein normativer Vorläufer ist jedoch klar benennbar: ISO/IEC 22301 kennt das
**Minimum Business Continuity Objective (MBCO)**, definiert als das
Mindestniveau an Produkten und Dienstleistungen, das für eine Organisation
während einer Störung akzeptabel ist, um ihre Geschäftsziele zu erreichen.

Beide beantworten dieselbe Frage, unterscheiden sich aber in der Reichweite:

| | MBCO (ISO/IEC 22301) | MVC (Praxisbegriff) |
|---|---|---|
| Bezugsgröße | Leistungsniveau je Produkt oder Dienstleistung | Überlebensfähigkeit der Organisation als Ganzes |
| Fokus | Was muss geliefert werden? | Welcher Teil des Unternehmens muss existieren? |
| Reichweite | Primär Leistungserbringung | Zusätzlich Rechtsform, Zahlungsfähigkeit, Aufsichtsstatus, Entscheidungsfähigkeit |
| Normstatus | In der Norm definiert | Nicht normativ definiert |

Diese Policy verwendet den Begriff MVC, verankert ihn aber ausdrücklich im
MBCO nach ISO/IEC 22301. Die im Folgenden festgelegten MVC-Bestandteile
sind damit zugleich die Konkretisierung des MBCO für dieses Institut.

---

## 2. Abgrenzung des MVC-Umfangs

### 2.1 Dimensionen der Überlebensfähigkeit

Eine MVC, die ausschließlich Systeme auflistet, greift zu kurz. Für die
GermanCrypto Custody AG werden acht Dimensionen betrachtet:

| Dimension | Anforderung im MVC-Zustand | Getragen durch |
|---|---|---|
| **Zahlungsfähigkeit** | Laufende Verbindlichkeiten müssen bedient werden können, auch ohne laufende Transaktionserträge | Vorstand (CFO), Rücklagen |
| **Rechtsidentität** | Fortbestand der Gesellschaft, Handlungsfähigkeit der Organe | Vorstand |
| **Kundenvertrauen** | Kunden müssen erfahren, dass ihre Vermögenswerte unversehrt sind, auch wenn sie nicht darauf zugreifen können | Krisenstab, Unternehmenskommunikation |
| **Kernleistungskontinuität** | Verwahrung bleibt sicher, Transaktionsfähigkeit wird wiederhergestellt | Custody Operations, Transaction Services |
| **Personalfähigkeit** | Mindestbesetzung mit Vertretungsfähigkeit je kritischer Aufgabe | Abschnitt 3.3 |
| **Technologie- und Datenzugriff** | Wiederherstellung der MVC-Systeme in definierter Reihenfolge | Abschnitte 3.1 und 3.2 |
| **Aufsichtsstatus** | Meldepflichten nach DORA Art. 19 und MiCA werden ohne Unterbrechung erfüllt | Compliance-Abteilung, Meldewesen-Systeme |
| **Entscheidungsbefugnis** | Beschlussfähiges Gremium mit Mandat für Priorisierungsentscheidungen | Krisenstab |

Zwei dieser Dimensionen sind für einen Kryptoverwahrer besonders kritisch
und werden häufig unterschätzt: **Aufsichtsstatus**, weil eine verpasste
Meldefrist einen eigenständigen Verstoß erzeugt, und **Kundenvertrauen**,
weil Vertrauensverlust in dieser Branche innerhalb von Stunden zu
Abzugsverhalten führen kann.

### 2.2 Was bewusst nicht zur MVC gehört

Die eigentliche Entscheidung einer MVC-Definition liegt nicht in dem, was
aufrechterhalten wird, sondern in dem, was bewusst ruht. Folgende Prozesse
und Systeme werden im MVC-Zustand **nicht** betrieben. Die Entscheidung ist
vorab getroffen und vom Vorstand freigegeben, damit sie im Ereignisfall
nicht neu verhandelt werden muss:

| Nicht im MVC-Umfang | Auswirkung der Aussetzung | Begründung |
|---|---|---|
| Kunden-Onboarding und Identifikation | Kein Neugeschäft | Betrifft ausschließlich künftige Kundenbeziehungen. Bestehende Kundenvermögen sind nicht gefährdet. |
| Zahlungsverkehr und Fiat-Anbindung | Keine Ein- und Auszahlungen | Führt zu Geschäftsstillstand in diesem Segment, aber zu keinem irreversiblen Vermögensverlust. Kundengelder bleiben unversehrt. |
| Kundenzugriff und Reporting (Selbstbedienung) | Kunden können Bestände nicht selbst einsehen | Wird durch aktive Krisenkommunikation ersetzt. Vertrauensrisiko wird bewusst in Kauf genommen und über Dimension „Kundenvertrauen" gesteuert. |
| Softwareentwicklung | Keine Releases, kein Feature-Betrieb | Ohne Bezug zur Aufrechterhaltung des Betriebs. |
| Unternehmenswebsite und Marketing | Öffentliche Außendarstellung eingeschränkt | Bereits außerhalb des ISMS-Geltungsbereichs. Krisenkommunikation läuft über gesonderte Kanäle. |
| CRM- und HR-Randsysteme | Administrative Prozesse ruhen | Kein Beitrag zur Überlebensfähigkeit im Krisenzeitraum. |

Ausdrücklich festgehalten: Die Aussetzung dieser Prozesse ist **keine
Herabstufung ihrer Bedeutung im Normalbetrieb.** Sie ist eine
Priorisierungsentscheidung für einen eng begrenzten Ausnahmezustand.

---

## 3. Bestandteile der MVC

Die MVC-Systeme werden in zwei Schichten geführt. Diese Trennung ist keine
Systematik um ihrer selbst willen: Sie bestimmt unmittelbar die
Wiederanlaufreihenfolge in Abschnitt 4. Systeme der Schicht 0 ermöglichen
Wiederherstellung überhaupt erst und müssen deshalb vor allen
geschäftskritischen Systemen verfügbar sein.

### 3.1 Schicht 0: Control Plane

| System | Abgeleiteter RTO | Funktion im Wiederanlauf |
|---|---|---|
| Active Directory (interne Mitarbeiteridentitäten) | 45 min | Ohne interne Identitäten kann kein Wiederherstellungsschritt autorisiert werden |
| IAM (interne Rechtevergabe) | 45 min | Vergabe privilegierter Zugriffe für Wiederherstellungstätigkeiten |
| Secure Gateways | 45 min | Gesicherter Zugang der Wiederherstellungsteams zu den Zielsystemen |
| CIAM (Kundenauthentifizierung) | 1 h | Identitätssystem, wird aber für den Wiederanlauf selbst nicht benötigt und daher innerhalb der Schicht zuletzt wiederhergestellt |

Die Trennung interner und externer Identitäten (Abschnitt 3.4 der Business
Impact Analysis) wirkt sich hier unmittelbar aus: Weil CIAM architektonisch
von Active Directory getrennt ist, kann die interne Wiederherstellung
beginnen, ohne dass die öffentlich erreichbare Kundenlogin-Fläche
verfügbar oder vertrauenswürdig sein muss.

### 3.2 Schicht 1: Geschäftskritische Systeme

| System | Abgeleiteter RTO | Zugeordnete Dimension |
|---|---|---|
| Meldewesen-Dokumentations-Datenbank | 45 min | Aufsichtsstatus |
| Hardware Security Module (HSM) | 1 h | Kernleistungskontinuität, Verwahrung |
| Custody-Ledger-Datenbank | 1 h | Kernleistungskontinuität, Verwahrung und Transaktion |

Die Meldewesen-Datenbank ist das einzige geschäftskritische System mit
45-Minuten-RTO. Grund ist der in der Business Impact Analysis hergeleitete
Meta-Risiko-Charakter des regulatorischen Meldewesens.

### 3.3 Mindestpersonalbesetzung

Zur Sicherstellung des MVC-Betriebs gelten folgende Mindestbesetzungen mit
definierter Vertretungsfähigkeit (Bus-Factor-Prinzip):

| Bereich | Mindestbesetzung | Anmerkung |
|---|---|---|
| ITSCM-Team | 2 Personen | Mindestens zwei Personen müssen jede kritische Wiederherstellungsaufgabe eigenständig ausführen können |
| IT-Ops-Bereiche (Betrieb, Firewall, Virtualisierung, Backup) | 2 Personen je Bereich | Sicherstellung technischer Grundfunktionen |
| Compliance, Meldewesen | 2 Personen | Erfüllung der Meldepflichten unabhängig vom Ausfall Einzelner |
| Krisenstab | Alle 4 definierten Rollen (Vorstand, PR, IT, Audit) | Funktionsübergreifende Entscheidungsfähigkeit erfordert vollständige Besetzung |

### 3.4 Kritische Drittparteien

Die MVC ist zusätzlich von der Verfügbarkeit folgender kritischer
Drittanbieter abhängig (Detailerfassung im Third-Party-Register unter
`30_Third_Party_Risk/`, in Arbeit):

| Drittpartei | Abhängiges MVC-System |
|---|---|
| HSM-Hersteller (Wartung und Support) | Hardware Security Module |
| Blockchain-Node-Infrastruktur-Anbieter | Transaktionsausführung |

Diese Abhängigkeiten werden im Rahmen des Third-Party-Risikomanagements
gesondert bewertet und sind nicht Gegenstand der internen
BIA-Zeithorizont-Analyse.

### 3.5 Notfalldokumentation

Dokumentation ist ein eigenständiger MVC-Bestandteil, kein Anhang. Die
zentrale Prüffrage lautet: **Sind die Notfallunterlagen erreichbar, wenn
Active Directory kompromittiert ist?**

Folgende Unterlagen gehören zum MVC-Umfang:

- Wiederanlaufpläne je MVC-System, einschließlich der HSM-Wiederinbetriebnahme
- Kontaktliste des Krisenstabs sowie der kritischen Drittparteien, offline verfügbar
- Netzwerk- und Architekturdiagramme der MVC-Systeme
- Konfigurationsstände und Wiederherstellungsschlüssel
- Asset-Register der MVC-Systeme
- Zugangsdaten für die gesicherten Ausweichkommunikationskanäle

**Aufbewahrung:** Diese Unterlagen werden in einem isolierten,
unveränderlichen Ablageort außerhalb der Produktionsdomäne vorgehalten,
mit je einer Kopie an beiden Rechenzentrumsstandorten sowie einer
netzunabhängigen Offline-Kopie. Die Authentifizierung erfolgt unabhängig
von Active Directory, damit die Unterlagen auch bei kompromittierter
Identitätsinfrastruktur verfügbar bleiben.

---

## 4. Wiederanlaufsequenz

RTOs legen Zielzeiten fest, aber keine Reihenfolge. Bei mehreren Systemen
mit identischem RTO bestimmt erst die Sequenz, was tatsächlich zuerst
bearbeitet wird. Die Reihenfolge ist damit Bestandteil der MVC-Definition
und nicht Gegenstand einer Einzelfallentscheidung im Ereignis.

| Phase | Inhalt | Zielzeitpunkt | Begründung |
|---|---|---|---|
| **0** | Aktivierung des Krisenstabs, Herstellung gesicherter Ausweichkommunikation, Zugriff auf die Notfalldokumentation | unmittelbar | Ohne Entscheidungsgremium und Kommunikationsweg ist jede weitere Maßnahme unkoordiniert |
| **1** | Wiederherstellung der Control Plane: Active Directory, IAM, Secure Gateways | 45 min | Ohne interne Identitäten kann keine Wiederherstellung autorisiert und durchgeführt werden |
| **2** | Meldewesen-Dokumentations-Datenbank, Aufnahme der Meldetätigkeit gegenüber BaFin | 45 min | Meldefristen laufen unabhängig vom technischen Zustand weiter |
| **3** | Hardware Security Module, Custody-Ledger-Datenbank | 1 h | Wiederherstellung der Verwahr- und Signaturfähigkeit |
| **4** | CIAM, danach schrittweise Kundenzugriff | 1 h und später | Kundenauthentifizierung wird für den Wiederanlauf selbst nicht benötigt |
| **5** | Rückführung der nach Abschnitt 2.2 ausgesetzten Prozesse | nach Verlassen des MVC-Zustands | Rückkehr in den Normalbetrieb |

Bemerkenswert an dieser Reihenfolge: **Das regulatorische Meldewesen wird
vor der eigentlichen Kernleistung wiederhergestellt.** Das ist beabsichtigt.
Die Verwahrung der Vermögenswerte ist auch im Stillstand sicher, solange die
HSM unversehrt sind. Eine verpasste Meldefrist ist dagegen nicht
nachholbar und erzeugt einen zusätzlichen, eigenständigen Schaden.

---

## 5. Betriebsdauer im MVC-Zustand

Die MVC beschreibt einen Ausnahmezustand, keinen Dauerzustand. Wie lange
dieser Zustand tragfähig ist, wird in der verfügbaren Fachliteratur zu MVC
bislang nicht behandelt. Für dieses Institut wird die Frage deshalb
eigenständig beantwortet.

Die zulässige Betriebsdauer ergibt sich aus dem **kürzesten** der folgenden
vier Belastungshorizonte. Die Bewertung folgt damit demselben
Worst-Case-Prinzip wie die Kritikalitätseinstufung in der Business Impact
Analysis:

| Begrenzender Faktor | Horizont | Begründung |
|---|---|---|
| **Kundenvertrauen** | **3 Tage** | Kunden können weder auf Bestandsinformationen zugreifen noch Auszahlungen veranlassen. In der Kryptobranche verbreiten sich Zweifel an der Zahlungs- und Auskunftsfähigkeit eines Verwahrers besonders schnell. Ab etwa drei Tagen ist mit Abzugsverhalten in erheblichem Umfang zu rechnen. |
| **Personelle Belastbarkeit** | 5 bis 7 Tage | Die Mindestbesetzung von zwei Personen je kritischem Bereich lässt nur eingeschränkten Schichtbetrieb zu. Ab etwa fünf Tagen steigt die Fehlerwahrscheinlichkeit deutlich, ab sieben Tagen ist die Besetzung nicht mehr belastbar aufrechtzuerhalten. |
| **Finanzielle Tragfähigkeit** | mehrere Wochen | Transaktionsentgelte entfallen, laufende Verbindlichkeiten bestehen fort. Der Zeitraum ist deutlich länger als die übrigen Faktoren und daher nicht bestimmend. |
| **Aufsichtsrechtliche Duldung** | fortlaufend zu bewerten | Kein fester Horizont. Solange Meldepflichten erfüllt und die Aufsicht laufend informiert wird, besteht kein automatischer Endpunkt. Bei ausbleibender Rückkehr in den Normalbetrieb ist mit aufsichtlichen Maßnahmen zu rechnen. |

**Maßgeblich ist damit der Horizont von drei Tagen.** Er ist zugleich der
einzige Faktor, der sich nicht durch technische Maßnahmen verlängern lässt,
sondern ausschließlich durch Kommunikation.

**Daraus abgeleitete Eskalationspunkte:**

| Zeitpunkt | Auslöser | Maßnahme |
|---|---|---|
| ab Stunde 4 | MVC-Zustand hält an | Erste aktive Kundeninformation über den Krisenstab, unabhängig davon, ob neue Erkenntnisse vorliegen |
| ab Tag 2 | MVC-Zustand hält an | Verstärkung der Mindestbesetzung, Aktivierung zusätzlicher Vertretungen |
| ab Tag 3 | Vertrauenshorizont erreicht | Entscheidung des Vorstands über vorgezogene Teilwiederherstellung des Kundenzugriffs, auch mit eingeschränktem Funktionsumfang |
| ab Tag 5 | Personelle Belastungsgrenze | Entscheidung über externe Unterstützung oder kontrollierte Reduktion des Leistungsumfangs |

Der Kundenzugriff ist damit zwar nach Abschnitt 2.2 nicht Teil der MVC,
erhält über die Eskalationslogik aber einen definierten Zeitpunkt, ab dem
seine Wiederherstellung erzwungen wird. Genau an dieser Stelle wird
sichtbar, dass eine MVC ohne Zeitbetrachtung unvollständig bleibt: Ein
Ausschluss, der unbefristet gilt, ist in der Praxis nicht haltbar.

---

## 6. Weg in den MVC-Zustand: Clean-Room-Prinzip

Bei einem Cyberangriff kann nicht vorausgesetzt werden, dass vorhandene
Sicherungen frei von Schadcode sind. Eine Wiederherstellung direkt in die
Produktionsumgebung birgt daher das Risiko, die Ursache der Störung erneut
einzuspielen.

Der Wiederanlauf der MVC-Systeme erfolgt deshalb nach folgendem Grundsatz:

1. Wiederherstellung eines Sicherungsstandes in einer **isolierten
   Umgebung ohne Netzwerkverbindung zur Produktion**
2. Prüfung auf Schadcode und Validierung der Datenintegrität in dieser
   Umgebung
3. Freigabe durch den Krisenstab
4. Erst danach Überführung in die Produktion

Dieses Vorgehen verlängert den Wiederanlauf und ist bei der Bemessung der
RTOs zu berücksichtigen. Es ist gleichwohl nicht verzichtbar: Bei einem
Verwahrer digitaler Vermögenswerte würde eine Wiederherstellung
kompromittierter Systeme mit Zugriff auf die Signaturfähigkeit einen
irreversiblen Schaden ermöglichen.

Die konkrete technische Ausgestaltung wird in
`03_Wiederanlaufstrategien.md` beschrieben (in Arbeit).

---

## 7. Quellen und Einordnung

Der Begriff MVC ist nicht normativ definiert. Die inhaltliche Ausgestaltung
dieses Dokuments stützt sich daher auf drei Quellenarten mit
unterschiedlicher Interessenlage. Diese Unterscheidung wird bewusst
offengelegt.

**Normativ**

- ISO/IEC 22301:2019, Minimum Business Continuity Objective, Business Impact Analysis (Kap. 8.2.2), Strategien (Kap. 8.3)
- Verordnung (EU) 2022/2554 (DORA), insbesondere Art. 11 und Art. 12
- BSI-Standard 200-4

**Beratungsseitig, nicht herstellergebunden**

- PwC, Global Centre for Crisis and Resilience: Whitepaper *The Survival Core: Your Minimum Viable Company for Enterprise Resilience* sowie Podcast *Emerge Stronger Through Disruption*, Folge 35, „Minimum Viable Company (MVC) Explained"
  https://www.pwc.com/gx/en/issues/crisis-solutions/minimum-viable-company.html
- DCR Partners: *The Minimum Viable Company*, Rahmenwerk mit acht Dimensionen der Überlebensfähigkeit, entwickelt im Kontext der Operational-Resilience-Anforderungen von FCA und PRA
  https://www.dcrpartners.co.uk/the-minimum-viable-company

**Herstellerseitig**

Die Anbieter sind Leaders im Gartner Magic Quadrant for Backup and Data
Protection Platforms 2025 (Rubrik, Veeam, Commvault, Cohesity, Dell,
Druva). Ihr Material ist fachlich fundiert, aber nicht neutral, da es
zugleich der Positionierung eigener Produkte dient.

- Veeam: *Cyber Resilience Through Minimum Viable Business (MVB/MVC)*, Herkunft der Aussage, dass MVC primär eine Priorisierungsfrage ist
  https://www.veeam.com/blog/minimum-viable-business-and-company-cyber-resilience.html
- Cohesity: *Minimum Viable Company: Recover faster when systems go dark*, Herkunft der Schichtung in Control Plane und Business Services sowie der Behandlung von Dokumentation als eigenständigem Bestandteil
  https://www.cohesity.com/blogs/minimum-viable-company/
- Commvault: *Minimum Viable Company: Restoring What Matters Most* sowie die Produktkategorie Cleanroom Recovery
  https://www.commvault.com/resources/whitepaper/minimum-viable-company-restoring-what-matters-most
- Semperis: *Minimum Viable Company: Cyber Resilience Beyond the Breach*, Herkunft des Arguments, dass die Identitätswiederherstellung dem Wiederanlauf der Geschäftssysteme vorausgehen muss
  https://www.semperis.com/blog/minimum-viable-company-cyber-resilience-beyond-the-breach/

**Eigenständiger Beitrag dieses Dokuments**

Abschnitt 5 (Betriebsdauer im MVC-Zustand) ist nicht aus den genannten
Quellen abgeleitet. Keine der ausgewerteten Veröffentlichungen behandelt
die Frage, wie lange ein MVC-Zustand tragfähig ist. Die dort dargestellte
Herleitung über konkurrierende Belastungshorizonte und die daraus
abgeleiteten Eskalationspunkte sind eine eigene Ausarbeitung für dieses
Fallunternehmen.

---

## Freigabe/Genehmigung

| Version | Datum | Autorisiert durch | Änderung |
|---|---|---|---|
| 1.0 | 31.07.2026 | CRO | Initiale Freigabe |
| 2.0 | 02.09.2026 | CRO | Normative Einordnung (MBCO), Viabilitätsdimensionen, expliziter Ausschlussumfang, Schichtung der Systeme, Wiederanlaufsequenz, Betriebsdauer und Eskalationspunkte, Notfalldokumentation, Clean-Room-Prinzip, Quellenverzeichnis |
