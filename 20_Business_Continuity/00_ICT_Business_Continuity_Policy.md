# ICT Business Continuity Policy – GermanCrypto Custody AG

*Rahmendokument des Business-Continuity-Management-Systems. Analyse und
Ergebnisse sind in eigenständige mitgeltende Dokumente ausgelagert.*

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
regelmäßige Überprüfung ihrer Wirksamkeit erfolgt über den Testing- und Übungszyklus 
(`07_Testing_und_Uebungszyklus.md`, in Arbeit).

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

## 3. Mitgeltende Dokumente

Die inhaltliche Ausarbeitung erfolgt in eigenständigen Dokumenten, damit
Analyseergebnisse unabhängig vom Rahmenwerk fortgeschrieben und versioniert
werden können.

| Dokument | Inhalt | Stand |
|---|---|---|
| `01_Business_Impact_Analysis.md` | Methodik, Kritikalitätsbewertung der Kernprozesse, Abhängigkeitsanalyse, abgeleitete System-RTOs | ✅ fertig |
| `02_Minimum_Viable_Company.md` | Normative Einordnung, Viabilitätsdimensionen, Ausschlussumfang, kritische Systeme in zwei Schichten, Mindestbesetzung, Drittparteien, Notfalldokumentation, Wiederanlaufsequenz, Betriebsdauer | ✅ fertig |
| `03_Wiederanlaufstrategien.md` | Strategische Optionen zur Wiederherstellung der MVC-Systeme (ISO/IEC 22301 Kap. 8.3) | 🔜 geplant |
| `04_Wiederanlaufplaene.md` | Konkrete Pläne und Verfahren je System, Zuständigkeiten und Ablauf (ISO/IEC 22301 Kap. 8.4) | 🔜 geplant |
| `05_Backup_und_redundante_Kapazitaeten.md` | Backup-Richtlinien, Wiederherstellungsverfahren, redundante ICT-Kapazitäten (DORA Art. 12) | 🔜 geplant |
| `06_Krisenkommunikation.md` | Meldewege, Eskalation, interne und externe Kommunikation (DORA Art. 11 Abs. 2) | 🔜 geplant |
| `07_Testing_und_Uebungszyklus.md` | Testarten, Frequenz, Nachbereitung, Wirksamkeitsnachweis (ISO/IEC 22301 Kap. 8.5) | 🔜 geplant |
| `08_Review_und_Verbesserung.md` | Überprüfung der Wirksamkeit, Kennzahlen, Korrekturmaßnahmen (ISO/IEC 22301 Kap. 9 und 10) | 🔜 geplant |

Ergänzend außerhalb dieses Ordners: die BC-bezogene Risikobeurteilung nach
ISO/IEC 22301 Kap. 8.2 in `10_Risikomanagement/00_BC_Risikobeurteilung.md`.
Sie ergänzt die BIA um die Frage, wodurch eine Unterbrechung entstehen kann,
während die BIA deren Auswirkung bewertet.

## 4. Überprüfung und Fortschreibung

Diese Policy sowie die mitgeltenden Dokumente werden mindestens jährlich
sowie anlassbezogen nach wesentlichen Änderungen der Geschäftsprozesse, der
IT-Landschaft oder der regulatorischen Anforderungen überprüft. Die
Verantwortung liegt beim Crisis Manager als Leiter des BCM-Departments.

## Freigabe/Genehmigung

| Version | Datum | Autorisiert durch | Änderung |
|---|---|---|---|
| 1.0 | 31.07.2026 | CRO | Initiale Freigabe |
| 2.0 | 02.09.2026 | CRO | Aufteilung in Rahmendokument und mitgeltende Dokumente, Dokumentenlandschaft an DORA Art. 12 und ISO/IEC 22301 Kap. 8.3, 8.4, 9 und 10 angepasst |
