# ICT Resilience Framework: GermanCrypto Custody AG

**Dieses Repository beantwortet eine einzige Frage: Welcher Teil eines regulierten Finanzinstituts muss im schwersten Krisenfall überleben, und wie kommt man nachvollziehbar zu dieser Antwort?**

Am Beispiel eines fiktiven, BaFin-regulierten Krypto-Verwahrers wird die vollständige Kette gezeigt, vom Organisationsprofil über die Business Impact Analysis bis zur Minimum Viable Company. Kein Ergebnis wird dabei behauptet: Jeder RTO, jede Kritikalitätsstufe und jedes überlebensnotwendige System ist aus der vorangegangenen Analyse abgeleitet. Regulatorischer Rahmen ist DORA, methodische Grundlage sind ISO/IEC 27001, ISO/IEC 22301 und BSI-Standard 200-4.

> ⚠️ Die **GermanCrypto Custody AG ist ein fiktives Unternehmen.** Sämtliche Zahlen, Systeme, Prozesse und Organisationsstrukturen sind erfunden. Dieses Repository ist ein persönliches Fach- und Lernprojekt und bildet keine reale Organisation ab.

---

## Worum es geht

Regulatorische Dokumentation wird selten am Stück gezeigt. Man findet Vorlagen, Checklisten und Normtexte, aber selten eine durchgehende Kette von der Organisationsbeschreibung über die Business Impact Analysis bis zu der Frage, welche Systeme ein Unternehmen im schwersten Krisenfall tatsächlich am Leben halten muss.

Genau diese Kette wird hier gebaut: für ein fiktives, aber realistisch modelliertes Finanzinstitut, das gleichzeitig unter KWG, MiCA und DORA fällt. Jedes Dokument baut nachvollziehbar auf dem vorherigen auf. Kein Ergebnis wird behauptet; jeder RTO, jede Kritikalitätsstufe und jedes MVC-System ist aus der vorangegangenen Analyse abgeleitet.

Der Schwerpunkt liegt auf der **Minimum Viable Company (MVC)**: der minimalen Kombination aus Systemen, Personal und Drittparteien, die auch im schwersten Krisenfall aufrechterhalten werden muss.

---

## Das Fallunternehmen

| | |
|---|---|
| **Unternehmen** | GermanCrypto Custody AG (fiktiv) |
| **Geschäftsmodell** | Verwahrung digitaler Vermögenswerte für Privat- und institutionelle Kunden |
| **Sitz** | Frankfurt am Main, europaweit tätig |
| **Größe** | ca. 2.500 Mitarbeitende, ca. 15 Mrd. EUR Assets under Custody |
| **Regulatorischer Status** | Erlaubnis zum Kryptoverwahrgeschäft nach § 1 Abs. 1a Nr. 6 KWG (BaFin), CASP-Zulassung nach MiCA, DORA-pflichtig |
| **Infrastruktur** | Zwei Rechenzentren im Active-Passive-Betrieb (Frankfurt / Leverkusen), konsequent on-premise, HSM an beiden Standorten |

Das Szenario ist bewusst so gewählt, dass sich Resilienzfragen zuspitzen: Bei einem Krypto-Verwahrer bedeutet der Verlust kryptographischer Schlüssel **irreversiblen** Vermögensverlust. Es gibt keine Rückbuchung und keine zentrale Instanz, die einen Fehler korrigiert.

---

## Aufbau des Repositorys

Die Ablage folgt **Fachdisziplinen, nicht Regelwerken.** Der Grund: DORA, ISO/IEC 27001 und ISO/IEC 22301 überlappen sich inhaltlich stark. Ein Dokument erfüllt meist gleichzeitig Anforderungen aus mehreren Quellen, eine Ablage nach Regelwerk würde dieselben Inhalte doppelt führen. Die regulatorische Nachvollziehbarkeit übernimmt deshalb das Compliance-Mapping.

```
00_Governance/                                 Kontext, Geltungsbereich, Rollen
    00_Organisationsprofil.md                  ✅ Unternehmen, Bereiche, Infrastruktur, Stakeholder
    01_Geltungsbereich.md                      ✅ ISMS (ISO 27001 Kap. 4.3) und BCMS (ISO 22301 Kap. 4.3)

10_Risikomanagement/                           Säule 1, Risikoseite
    00_BC_Risikobeurteilung.md                 🔜 Störungsszenarien, ISO 22301 Kap. 8.2

20_Business_Continuity/                        Säule 1, Schwerpunkt dieses Projekts
    00_ICT_Business_Continuity_Policy.md       ✅ Rahmenwerk, Governance, Rollen
    01_Business_Impact_Analysis.md             ✅ Prozesslandschaft, Kritikalität, System-RTOs
    02_Minimum_Viable_Company.md               ✅ Ausschlussumfang, Schichtung, Sequenz, Betriebsdauer
    03_Wiederanlaufstrategien.md               🔜 ISO 22301 Kap. 8.3
    04_Wiederanlaufplaene.md                   🔜 ISO 22301 Kap. 8.4
    05_Backup_und_redundante_Kapazitaeten.md   🔜 DORA Art. 12
    06_Krisenkommunikation.md                  🔜 DORA Art. 11 Abs. 2
    07_Testing_und_Uebungszyklus.md            🔜 ISO 22301 Kap. 8.5
    08_Review_und_Verbesserung.md              🔜 ISO 22301 Kap. 9 und 10

30_Third_Party_Risk/                           🔜 Säule 4, DORA Art. 28 bis 30
40_Incident_Management/                        🔜 Säule 2, DORA Art. 17 bis 23
50_Resilience_Testing/                         🔜 Säule 3, DORA Art. 24 bis 27

90_Compliance_Mapping/                         querschnittlich, kein eigener Arbeitsstrang
    DORA_ISO_Mapping.md                        ✅ Welches Dokument erfüllt welche Anforderung
```

**Warum die übrigen DORA-Säulen überhaupt auftauchen.** Die Minimum Viable Company benennt, welche Systeme überleben müssen. Vier Rückfragen darauf lassen sich innerhalb dieses Kapitels nicht beantworten, und genau dafür stehen die angrenzenden Ordner:

| Rückfrage | Beantwortet in |
|---|---|
| Überleben **wogegen**? Die BIA bewertet die Auswirkung eines Ausfalls, nicht dessen Ursache. | `10_Risikomanagement/` |
| Was, wenn eine **kritische Drittpartei** ausfällt? Die MVC hängt unter anderem am HSM-Hersteller und am Blockchain-Node-Anbieter. | `30_Third_Party_Risk/` |
| **Wodurch wird der MVC-Zustand ausgelöst**, und wer erkennt ihn? Die schärfste Zeitvorgabe des Instituts, 45 Minuten, stammt aus der Meldepflicht nach DORA Art. 19. | `40_Incident_Management/` |
| Woher ist bekannt, dass die MVC **tatsächlich funktioniert**? Eine ungetestete MVC ist eine Annahme, keine Fähigkeit. | `50_Resilience_Testing/` |

Säule 5 (Informations- und Erkenntnisaustausch, DORA Art. 45) trägt zu dieser Fragestellung nichts bei und ist deshalb als einzige vollständig ausgeklammert. Die Begründung steht im Compliance-Mapping.

Ordner ohne veröffentlichte Dokumente existieren im Repository noch nicht. Der jeweils aktuelle Stand ist der veröffentlichte Stand; unfertige Kapitel werden nicht vorab hochgeladen.

---

## Regulatorischer und methodischer Rahmen

| Rahmenwerk | Rolle in diesem Projekt |
|---|---|
| **Verordnung (EU) 2022/2554 (DORA)** | Regulatorischer Auftrag. Art. 11 für Business Continuity, Art. 12 für Backup und Wiederherstellung, Art. 19 für Meldepflichten, Art. 4 für den Verhältnismäßigkeitsgrundsatz |
| **ISO/IEC 27001:2022** | Managementsystem-Struktur. Kap. 4.3 (Geltungsbereich), Kap. 5.3 (Rollen und Verantwortlichkeiten) |
| **ISO/IEC 22301:2019** | BCM-Methodik. Führende BCM-Methodik. Kap. 4.3 (Geltungsbereich BCMS), Kap. 8.2 (Risikobeurteilung und BIA), Kap. 8.3 (Strategien), Kap. 8.4 (Pläne), Kap. 8.5 (Übungen), Kap. 9 und 10 (Bewertung und Verbesserung) |
| **BSI-Standard 200-4** | Deutsche BCM-Methodik als ergänzende nationale Referenz |
| **KWG / MiCA** | Bestimmen den aufsichtsrechtlichen Status des Fallunternehmens |

**Zum Verhältnis von ISO 27001 und DORA:** ISO/IEC 27001 ist ein freiwilliger, zertifizierbarer Managementsystem-Standard und liefert die Organisationsmaschinerie. DORA ist eine verpflichtende Verordnung und definiert die zu erreichenden Ergebnisse, ohne eine Organisationsform vorzugeben. Das ISMS ist damit das Vehikel, die DORA-Anforderungen sind das Ziel. Wie sich der bewusst eng gefasste ISO-Geltungsbereich zum weiten DORA-Anwendungsbereich verhält, ist im Geltungsbereichs-Dokument, Abschnitt 8, ausgeführt.

---

## Ausgewählte inhaltliche Entscheidungen

**Das regulatorische Meldewesen als Meta-Risiko.** Es ist der einzige Kernprozess, der bereits nach vier Stunden die maximale Kritikalitätsstufe erreicht. Begründung: Eine verpasste Meldefrist nach DORA Art. 19 verschärft jeden zugrundeliegenden Incident um einen eigenständigen Compliance-Verstoß. Der daraus abgeleitete RTO von 45 Minuten wird konsequent auf alle abhängigen Systeme vererbt.

**Strikte Trennung interner und externer Identitäten.** Mitarbeiteridentitäten (Active Directory, IAM) und Kundenidentitäten (CIAM) werden getrennt geführt, damit eine Kompromittierung der öffentlich erreichbaren Kundenlogin-Fläche keinen Pfad zu internen Konten eröffnet.

**Enger ISO-Scope, weiter DORA-Anwendungsbereich.** Der Geltungsbereich der Managementsysteme schließt Randsysteme bewusst aus. DORA kennt kein Scoping-Konzept, sondern den Verhältnismäßigkeitsgrundsatz. Beide Rahmen widersprechen sich daher nicht, sondern greifen ineinander.

**Die MVC als Ausschluss-Entscheidung.** Das Kapitel legt nicht nur fest, welche Systeme überleben müssen, sondern welche Prozesse im Krisenfall bewusst ruhen, in welcher Reihenfolge wiederangelaufen wird und wie lange der MVC-Zustand tragfähig ist. Der begrenzende Faktor ist dabei nicht die Technik, sondern das Kundenvertrauen.

**Offengelegte Analysetiefe.** Die BIA-Tiefenanalyse umfasst drei repräsentative Kernprozesse; die übrigen sind grob eingestuft und für den nächsten Reviewzyklus vorgemerkt. Diese Begrenzung wird im Dokument benannt statt kaschiert.

**Bewusste Auslassungen.** DORA Säule 5 (Informationsaustausch) sowie ISO 27001 Kap. 9 und 10 (Audit, Managementbewertung) werden nicht bearbeitet. Die Begründung steht im Compliance-Mapping.

---

## Methodik und Quellen

Die Dokumente stützen sich auf unterschiedliche Quellenarten, und diese Unterscheidung ist bewusst:

**Normativ abgesichert** sind Aufbau des Managementsystems, Scoping, BIA-Methodik und die Ableitung von RTO/RPO aus dem Maximum Tolerable Period of Disruption. Grundlage sind ISO/IEC 27001:2022, ISO/IEC 22301:2019, BSI-Standard 200-4 und der Verordnungstext von DORA.

**Nicht normativ abgesichert** ist der Kern des MVC-Konzepts. Weder ISO/IEC 22301 noch DORA definieren eine "Minimum Viable Company" als eigenständige Methodik. Das Thema wird derzeit überwiegend **herstellerseitig** vorangetrieben, insbesondere von den Anbietern, die im **Gartner Magic Quadrant für Backup and Data Protection Platforms** als Leaders geführt werden (unter anderem Veeam, Rubrik, Commvault und Cohesity). Deren Fachbeiträge, Referenzmodelle und Recovery-Konzepte bilden derzeit die belastbarste verfügbare Quellenlage zu MVC.

Für die MVC-Definition in diesem Projekt wurde daher bewusst auf dieses Herstellermaterial zurückgegriffen und mit der normativ abgesicherten BIA verknüpft. Wo Aussagen aus Herstellerquellen stammen, ist das kenntlich gemacht. Deren Perspektive ist fachlich fundiert, aber nicht neutral.

> 📌 **Hinweis zum Stand der Quellenarbeit:** Die konkreten Einzelnachweise zu den herangezogenen Herstellerquellen werden ergänzt, sobald die Recherche abgeschlossen ist.

---

## Warum dieses Projekt

Ich arbeite seit mehreren Jahren im Cybersecurity- und GRC-Umfeld eines DAX-Konzerns, unter anderem in der Koordination von Disaster-Recovery-Tests über mehrere europäische Märkte. Vieles davon ist operative Arbeit an bestehenden Prozessen. Dieses Repository ist der Versuch, denselben Themenkomplex einmal **von Grund auf und durchgehend** selbst aufzubauen: von der Organisationsbeschreibung bis zur Frage, was ein Unternehmen im schwersten Fall am Leben hält.

Rückmeldungen, Kritik und Hinweise auf methodische Schwächen sind ausdrücklich willkommen.

---

## Autor

**Odera Anthony Anene**, Cybersecurity & GRC Consultant
CompTIA Security+ (SY0-701) · SC-900 · AZ-900 · Infosys Certified GRC Associate
[LinkedIn](https://www.linkedin.com/in/odera-anthony)
