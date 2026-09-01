# Compliance-Mapping – GermanCrypto Custody AG

Dieses Dokument bildet ab, welches Dokument dieses Repositorys welche
Anforderung aus DORA, ISO/IEC 27001:2022, ISO/IEC 22301:2019 und
BSI-Standard 200-4 abdeckt.

**Warum diese Tabelle existiert:** Die Ordnerstruktur ist nach
Fachdisziplinen aufgebaut, nicht nach Regelwerken. Das ist bewusst so, weil
sich die Rahmenwerke inhaltlich überlappen: Ein Dokument erfüllt in der
Regel gleichzeitig Anforderungen aus mehreren Quellen. Eine Ablage nach
Regelwerk würde dieselben Inhalte mehrfach führen. Die
Nachvollziehbarkeit übernimmt stattdessen dieses Mapping.

---

## Abdeckung nach Dokument

| Dokument | DORA | ISO/IEC 27001:2022 | ISO/IEC 22301:2019 | Stand |
|---|---|---|---|---|
| `00_Governance/00_Organisationsprofil.md` | Art. 5 (Governance und Organisation), Kontextgrundlage für Art. 6 | Kap. 4.1, 4.2 (Kontext, interessierte Parteien), 5.3 (Rollen) | Kap. 4.1, 4.2 | ✅ |
| `00_Governance/01_BCMS_Scope_Statement.md` | Art. 11 Abs. 1 (Geltungsbereich der BC-Policy) | – | **Kap. 4.3** (Geltungsbereich BCMS) | 🔜 |
| `00_Governance/02_ISMS_Scope_Statement.md` | Art. 4 (Verhältnismäßigkeit), Abgrenzung zum DORA-Anwendungsbereich | **Kap. 4.3** (Geltungsbereich ISMS) | – | ✅ |
| `10_Risikomanagement/` | Art. 6 bis 10 (ICT-Risikomanagementrahmen) | Kap. 6.1.2, 6.1.3, 8.2, 8.3, Anhang A | – | 🔜 |
| `20_Business_Continuity/00_ICT_Business_Continuity_Policy.md` | **Art. 11** (ICT Business Continuity Policy) | Kap. 5.2 (Politik) | Kap. 5.2, 8.1 | ✅ |
| `20_Business_Continuity/01_Business_Impact_Analysis.md` | **Art. 11 Abs. 5** | – | **Kap. 8.2.2** (BIA) | ✅ |
| `20_Business_Continuity/02_Minimum_Viable_Company.md` | Art. 11 Abs. 2 und 4 | – | Kap. 8.2.2, 8.3 | ✅ |
| `20_Business_Continuity/03_Wiederanlaufstrategien.md` | Art. 11, **Art. 12** (Backup und Wiederherstellung) | Anhang A 5.29, 5.30 | **Kap. 8.3** | 🔜 |
| `20_Business_Continuity/04_Testing_und_Uebungszyklus.md` | Art. 11 Abs. 6 | – | **Kap. 8.5** (Übungsprogramm) | 🔜 |
| `20_Business_Continuity/05_Notfall_und_Krisenkommunikation.md` | Art. 11 Abs. 2, **Art. 14** (Kommunikation) | – | Kap. 8.4.3 | 🔜 |
| `30_Third_Party_Risk/` | **Art. 28 bis 30** (ICT-Drittparteienrisiko) | Anhang A 5.19 bis 5.23 | Kap. 8.2.3 | 🔜 |
| `40_Incident_Management/` | **Art. 17 bis 23** (Vorfallbehandlung und Meldung) | Anhang A 5.24 bis 5.28 | – | 🔜 |
| `50_Resilience_Testing/` | **Art. 24 bis 27** (Resilienztests, TLPT) | Kap. 9.1 | – | 🔜 |

Fett markiert ist jeweils die Anforderung, für die das Dokument den primären
Nachweis erbringt. Die übrigen Angaben sind unterstützende Bezüge.

---

## Nicht bearbeitete Bereiche

| Bereich | Begründung |
|---|---|
| DORA Säule 5, Informations- und Erkenntnisaustausch (Art. 45) | Bewusst ausgeklammert. Die Anforderung ist als Kann-Bestimmung ausgestaltet und trägt für den Schwerpunkt dieser Fallstudie, die operative Wiederherstellungsfähigkeit, nichts bei. |
| ISO/IEC 27001, Kap. 9 und 10 (Internes Audit, Managementbewertung, Verbesserung) | Bewusst ausgeklammert. Für ein fiktives Unternehmen ohne reale Auditbefunde wären diese Dokumente reine Formalie ohne inhaltlichen Erkenntniswert. |

---

## Methodischer Hinweis

Die Zuordnungen beruhen auf dem Verordnungstext von DORA sowie den
Normtexten von ISO/IEC 27001:2022 und ISO/IEC 22301:2019. Sie sind eine
fachliche Einschätzung im Rahmen einer Fallstudie und ersetzen keine
Prüfung durch eine akkreditierte Stelle.

| Version | Datum | Autorisiert durch | Änderung |
|---|---|---|---|
| 1.0 | 01.09.2026 | CISO | Initiale Fassung |
