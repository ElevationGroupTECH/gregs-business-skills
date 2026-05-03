---
name: projekt-starten
description: Neues Projekt sauber aufsetzen — Struktur, Beschreibung, Protokoll, CLAUDE.md. Einfach drauf los reden, Claude macht den Rest.
---

# Projekt Starten

Dieser Skill richtet ein neues Projekt sauber ein — mit Projektbeschreibung, Protokolldatei, CLAUDE.md und ordentlicher Struktur. Basiert auf der Methodik aus „KI im Onlinebusiness Session 04" (Gregor Dorsch, 16.03.2026).

> **Teil eines Paares:** Dieser Skill startet Projekte sauber. Sein Partner `/projekt-review` (Alias `/review-project`) hält sie sauber — mit Hochglanz-Score, automatischen Fixes und ehrlichem Feedback. Zusammen bilden sie einen Kreislauf: Starten → Arbeiten → Review → Aufräumen → Weiterarbeiten.

---

## 🎯 Leitprinzip: Impact / Ressourcen (verbindlich für jedes hier gestartete Projekt)

**Bevor irgendetwas angelegt wird — dieses Entscheidungsprinzip ist der Kompass für alles, was im Skill folgt. Der Skill funktioniert eigenständig — alle nötigen Definitionen stehen hier drin.**

```
Wert = Impact (Auswirkung auf das Geschäftsziel) ÷ Ressourcen (Geld + Zeit + Emotionen)
```

### Drei Ressourcen-Dimensionen — bei jeder Aufgabenbewertung mitdenken

1. **💰 Geld** — Lizenzen, Tools, externe Dienstleister, Anschaffungen
2. **⏰ Zeit** — Gregor, Nadine, Team, Wartung, Übergabe, Lernkurve
3. **💚 Emotionen** — Nerv-Faktor, Frust, Energie. **Die am häufigsten unterschätzte Ressource.** Wenn Arbeit nervt oder ein Setup fragil und kompliziert ist, zerstört das mehr Wert, als jede Geld-Ersparnis je bringen kann.

### Impact-Hierarchie

- 🚀 **Riesen-Impact** (3-10× Wirkung): rein in den Plan, fast egal was es kostet
- ⚡ **Mittel + Low Hanging Fruit**: mitnehmen, wenn Claude es allein/automatisiert kann
- 🐭 **Homöopathisch** (<5%): lassen, auch wenn technisch elegant

### Zusatzfilter

- **Frau-Test:** Könnte Nadine das im Notfall ohne Gregor bedienen? → wenn nein, Komplexität reduzieren.
- **Compound-Effekte:** Manche Hebel multiplizieren sich (SEO × Content × Backlinks). Die zuerst.
- **Opportunitätskosten:** Was machen wir NICHT, wenn wir das machen?
- **Whole-System-Optimierung:** Wirkt das aufs ganze System, oder nur auf eine Komponente, die eh schon gut war?
- **Wer macht die Arbeit?** Gregor/Nadine = teuer. Claude = nachts kostenlos. Automatisiert > einmalig.

### Konsequenz für jedes neu angelegte Projekt

- Aufgabentabellen enthalten eine Spalte **„Aufwand"** (3-dimensionale Bewertung) zusätzlich zu den bestehenden Spalten
- Die CLAUDE.md jedes Projekts referenziert das Prinzip oben (oberster Filter-Abschnitt)
- Aufgaben-Priorisierung: Riesen-Impact > Compound-Effekt > Low-Hanging-Fruit > Rest
- Empfehlungen werden durch die CEO-Brille gefiltert, BEVOR sie ausgesprochen werden: „Was würde ein CEO denken, nicht ein Nerd?"

---

## Ablauf

### Phase 1: Projektordner bestimmen

1. **Frage nach dem Projektordner:**
   - Wurde ein Pfad als Argument übergeben? → Diesen verwenden
   - Sonst: „In welchem Ordner soll das Projekt leben? Gib mir den Pfad, oder sag mir, wo es thematisch hingehört (z.B. Marketing, Produkte, Kunden), dann schlage ich einen Platz in deiner Firmenstruktur vor."
   - Falls der Ordner noch nicht existiert: Anlegen (nach Bestätigung)

2. **In den Projektordner wechseln** und dort arbeiten.

---

### Phase 2: Projekt verstehen (Briefing)

Das ist der wichtigste Schritt. Der User wird typischerweise eine **Sprachnachricht** schicken — also unstrukturiert, wild durcheinander, mit Abschweifungen. Das ist normal und gewollt!

3. **Sage dem User:**
   > „Erklär mir das Projekt! Am besten einfach drauf los reden — wild durcheinander ist völlig okay. Ich sortiere das dann für dich. Erzähl mir:
   > - Was ist das für ein Projekt? (Buch, Kongress, Kurs, Workshop, Marketing-Kampagne, Software, ...)
   > - Für wen ist es? (Zielgruppe)
   > - Was ist das Ziel?
   > - Wer ist beteiligt? (Joint Venture, Team, Kunden...)
   > - Gibt es schon Vorarbeit? (Positionierung, Konzept, bestehende Dateien...)
   > - Gibt es Deadlines oder einen Zeitrahmen?
   > - Welche Tools/Plattformen werden verwendet?
   >
   > Wenn du schon Dateien hast (Positionierung, Konzept, Notizen), sag mir einfach wo die liegen — ich lese die mit ein."

4. **Wenn der User antwortet:** Alles aufnehmen, auch wenn es chaotisch ist. NICHT unterbrechen. Erst wenn er fertig ist, strukturiert zusammenfassen.

5. **Falls der User auf bestehende Dateien verweist** (z.B. eine Kongresspositionierung, ein Konzeptpapier): Diese einlesen und als Basis verwenden.

6. **Optional: Übergabeprotokoll aus Planungs-Chat**

   Häufiger Fall: Der User hat das Projekt bereits in einem separaten Context-Fenster geplant und bringt ein Übergabeprotokoll mit (z.B. als eingefügten Text oder Datei). Das Übergabeprotokoll enthält typischerweise: Kontext, bereits Erledigtes, Zielzustand, nächste Schritte, Dateien & Referenzen.

   Wenn der User ein Übergabeprotokoll mitbringt:
   - Komplett einlesen und als **primäre Informationsquelle** verwenden
   - Mit der Projektbeschreibung (falls vorhanden) abgleichen — Übergabeprotokoll hat Vorrang bei Widersprüchen
   - Fehlende Infos aus dem Protokoll identifizieren und gezielt nachfragen
   - **Nicht nochmal alles abfragen**, was bereits im Übergabeprotokoll steht!

7. **Optional: Speak-Transkript als Quelle einbinden**

   Häufiger Fall: Das Projekt entsteht aus einer Sprach-Aufzeichnung in der Speak-App („Schau mal in meine Speak App", „da ist eine Aufnahme vom Joggen", „Transkript vom Gespräch mit X"). Der User erwartet, dass Claude das Transkript eigenständig holt und als Quellmaterial nutzt.

   Wenn der User auf ein Speak-Transkript verweist (oder es kontextuell klar ist):
   - Via `mcp__speak__speak_list_transcripts` (optional mit `search`-Filter) die passende Aufzeichnung finden
   - Mit `mcp__speak__speak_get_transcript` den Volltext ziehen
   - **Nicht nur referenzieren — tatsächlich in `04-Quellen/` (oder entsprechendem Unterordner) als strukturierte `.md`-Datei sichern:**
     - Namensschema: `YYYY-MM-DD-Speak-Transkript-[Kurztitel].md`
     - Aufbau: Frontmatter (ID, Datum, Sprecher), Zusammenfassung der Kernaussagen, Zitate-Block (fürs Marketing), Volltext-Referenz
   - Sprecher identifizieren (Gregor ist meist Speaker 1) und in der Zusammenfassung mit Namen belegen, soweit ableitbar
   - Als Quellmaterial in `A - Projektbeschreibung` und `D - Methodik` (oder passende Dokumente) referenzieren

   **Warum sichern statt nur referenzieren?** Transkript-IDs können sich ändern, die Speak-App kann offline sein, und das Projekt soll sich auch ohne Speak-Zugriff selbst erklären. Einmaliges Kopieren ins Projekt stabilisiert die Quelle.

---

### Phase 3: Rückfragen stellen

7. **Klärende Fragen stellen** — nur was wirklich fehlt oder unklar ist. Typische Lücken:
   - Projekttitel (falls nicht genannt)
   - Zielgruppe genauer
   - Beteiligte Personen und deren Rollen
   - Technische Plattform / Tools
   - Budget oder Ressourcen (nur wenn relevant)
   - Zugangsdaten (Backend, Frontend) — falls es ein digitales Projekt ist

   **Nicht zu viele Fragen auf einmal!** Maximal 3-5 Fragen, die wirklich nötig sind.

8. **Nach Meilensteinen fragen:**
   > „Gibt es klare Meilensteine oder Phasen? Ein Meilenstein ist ein messbares Ergebnis, das eine Phase abschließt — z.B. 'Manuskript fertig', 'Seite live', 'Kampagne gestartet'. Wenn du Phasen hast, definieren wir für jede einen Meilenstein."

   Meilensteine werden mit ◆ (Raute) dargestellt und in der Protokolldatei visualisiert:
   ```
   ◆ M1: Manuskript fertig              ✅ erledigt
   │
   ◆ M2: Cover + Layout abgenommen      🔄 in Arbeit
   │
   ◆ M3: Buch veröffentlicht            ⬜ offen
   ```

9. **Projektgröße bestimmen:**
   Frage den User (oder schätze selbst ein):
   > „Ist das eher ein kleines oder großes Projekt?"

   **Klein** = Workshop, einzelne Kampagne, überschaubarer Umfang, wenige Dateien erwartet
   **Groß** = Buch, Kongress, Kurs mit vielen Modulen, Software — viele Dateien aus verschiedenen Bereichen

   Im Zweifel: **Klein starten.** Man kann später immer Unterordner ergänzen.

---

### Phase 4: Projektstruktur anlegen

Wenn genug Infos vorhanden sind, folgende Dateien anlegen:

#### Pflichtdateien (immer):

##### Kleines Projekt: Nummerierte Dateien

```
[Projektordner]/
├── CLAUDE.md
├── 01-Projektbeschreibung-[NAME]-V01.md
├── 02-Protokoll-[NAME].md
├── 03-[Weitere-Datei]-V01.md
├── ...
└── xold/
```

##### Großes Projekt: Buchstaben-Prefix für Root-Dokumente + nummerierte Unterordner

Bei großen Projekten mit thematischen Unterordnern kollidieren nummerierte Root-Dateien (01-, 02-) mit nummerierten Ordnern. Daher: **Buchstaben-Prefix** für Root-Dokumente, Nummern für Unterordner.

```
[Projektordner]/
├── CLAUDE.md
├── A - Projektbeschreibung-[NAME]-V01.md    ← Immer lesen
├── B - Aufgaben-[NAME].md                   ← Immer lesen (Phasen, Aufgaben, Meilensteine, Specs)
├── C - Protokoll-[NAME].md                  ← Log-Index lesen (Logs bei Bedarf)
├── D - [Weitere-Datei].md                   ← z.B. Sitemap, Konzept
├── E - [Weitere-Datei].md                   ← z.B. Style-Guide
├── F - Entscheidungen-[NAME].md             ← Entscheidungslog (optional, empfohlen)
├── 01-[thematischer-ordner]/                ← z.B. Positionierung, Manuskript
├── 02-[thematischer-ordner]/                ← z.B. Bilder, Wettbewerb
├── ...
└── xold/
```

**Regel:** Die Buchstaben-Dateien (A, B, C...) sind die Dokumente, die Claude bei jedem Gesprächsstart liest. Nummern (01-, 02-...) sind für die Unterordner.

---

#### a) Projektbeschreibung (01 bzw. A)

   Inhalt:
   - Projekttitel
   - Kurzübersicht (Was? Für wen? Warum?)
   - Beteiligte (Personen, Rollen)
   - Projektart (Joint Venture, eigenes Projekt, Kundenprojekt...)
   - Zielgruppe
   - Format / Umfang
   - Plattform / Technik
   - Zeitrahmen / Deadlines
   - Dateistruktur (was liegt im Ordner)
   - Zugangsdaten (falls bekannt)
   - Nächste Schritte

#### b) Aufgaben & Protokoll

Bei **kleinen Projekten** ist alles in einer Datei (`02-Protokoll`). Bei **großen Projekten** wird in zwei Dateien getrennt:

##### Kleines Projekt: Eine Datei (02-Protokoll)

Enthält alles: Aufgaben-Tabellen, Meilensteine, Log-Index, Logs.

```
# Protokoll: [PROJEKTNAME]

> **Legende:**
> - 📄 = Seiten-Aufgabe (Erstellung/Überarbeitung einer Seite)
> - ⚙️ = Code-Review / Technische Aufgabe
> - ◆ = Meilenstein
> Ohne Icon = allgemeine Aufgabe

## Aufgaben nach Phasen

### Phase 1 — [PHASENNAME]

> Status: 🔄 In Arbeit

| Nr | Aufgabe | Claude | Impact | Aufwand | Braucht | Risiko | Rollback | Status |
|---|---|---|---|---|---|---|---|---|
| [PRE]-01 | 📄 Startseite erstellen | ✅ | 🔴 | 💰🟢 ⏰🟡 💚🟢 | — | 🟢 | — | ✅ Erledigt |
| [PRE]-02 | robots.txt konfigurieren | ✅ | 🟡 | 💰🟢 ⏰🟢 💚🟢 | — | 🟢 | Revert | ⬜ Offen |
| [PRE]-03 | ⚙️ Code-Review Phase 1 | ✅ | 🟡 | 💰🟢 ⏰🟡 💚🟢 | Gregor: Abnahme | 🟢 | — | ⬜ Offen |
| ◆ | **Meilenstein: [MESSBARES ERGEBNIS]** | | | | | | | ⬜ Offen |

## Meilensteine (Übersicht)

◆ M1: [Beschreibung]     ✅ erledigt
│
◆ M2: [Beschreibung]     🔄 in Arbeit

## Log-Index (Schnellübersicht)

| Log | Datum | Beschreibung |
|-----|-------|-------------|
| LOG-001 | [DATUM] | Projektstart — Setup, Struktur, CLAUDE.md |

## Protokoll-Verlauf (neueste oben!)

### LOG-001 — [DATUM] — Projektstart
- Projekt angelegt und strukturiert
```

##### Großes Projekt: Zwei getrennte Dateien (B + C)

Bei großen Projekten wachsen Aufgabenbeschreibungen und Logs unabhängig voneinander. Beides in einer Datei wird schnell unübersichtlich. Daher: **Aufgaben und Protokoll trennen.**

**`B - Aufgaben-[NAME].md`** — Was liegt vor uns? (Planung)

```
# Aufgaben — [PROJEKTNAME]

> Phasen, Aufgaben, Meilensteine und Detail-Specs.
> Für das Änderungsprotokoll (was wurde gemacht?) → siehe `C - Protokoll-[NAME].md`

## Aufgaben nach Phasen

### Phase 1 — [PHASENNAME]

> Status: 🔄 In Arbeit

| Nr | Aufgabe | Claude | Impact | Aufwand | Braucht | Risiko | Rollback | Status |
|---|---|---|---|---|---|---|---|---|
| [PRE]-01 | 📄 Startseite erstellen | ✅ | 🔴 | 💰🟢 ⏰🟡 💚🟢 | — | 🟢 | — | ✅ Erledigt |
| [PRE]-02 | ⚙️ Komplexe Komponente (→ siehe Aufgabenbeschreibung) | ✅ | 🔴 | 💰🟢 ⏰🔴 💚🟡 | — | 🟡 | Revert | ⬜ Offen |
| [PRE]-03 | ⚙️ Code-Review Phase 1 | ✅ | 🟡 | 💰🟢 ⏰🟡 💚🟢 | Gregor: Abnahme | 🟢 | — | ⬜ Offen |
| ◆ | **Meilenstein: [MESSBARES ERGEBNIS]** | | | | | | | ⬜ Offen |

## Aufgabenbeschreibungen

> Detail-Specs für komplexe Aufgaben, die mehr als eine Tabellenzeile brauchen.
> Nicht jede Aufgabe braucht das — nur die, wo Konzept, Architektur oder besondere Anforderungen dokumentiert werden müssen.

### [PRE]-02 — [Aufgabentitel]

**Was:** [Beschreibung]
**Wo:** [Einsatzort]
**Technische Architektur:** [Details]
**Umsetzungs-Schritte:** [1, 2, 3...]

## Meilensteine (Übersicht)

◆ M1: [Beschreibung]     ✅ erledigt
│
◆ M2: [Beschreibung]     🔄 in Arbeit
```

**`C - Protokoll-[NAME].md`** — Was wurde gemacht? (Verlauf)

```
# Protokoll — [PROJEKTNAME]

> Änderungsprotokoll. Was wurde wann gemacht?
> Für Aufgaben und Planung → siehe `B - Aufgaben-[NAME].md`

## Log-Index (Schnellübersicht)

> Neueste oben, älteste unten.

| Log | Datum | Beschreibung |
|-----|-------|-------------|
| LOG-001 | [DATUM] | Projektstart — Setup, Struktur, CLAUDE.md |

---

## Protokoll-Verlauf (neueste oben!)

### LOG-001 — [DATUM] — Projektstart
- Projekt angelegt und strukturiert
- Projektbeschreibung erstellt (V01)
- Aufgabendatei angelegt
- Protokolldatei angelegt
- CLAUDE.md konfiguriert
```

##### Regeln für beide Varianten

   **Bewertungsspalten für Aufgaben:**

   Jede Aufgabentabelle enthält neben Nr, Aufgabe und Status diese Bewertungsspalten:

   | Spalte | Bedeutung | Werte |
   |--------|-----------|-------|
   | Claude | Kann Claude die Aufgabe selbst durchführen? | ✅ = ja, selbständig \| ⚠️ = teilweise (braucht Zuarbeit) \| ❌ = nein (Mensch muss) \| — = nicht zutreffend |
   | Impact | Wie viel trägt die Aufgabe zur Zielerreichung bei? | 🔴 hoch \| 🟡 mittel \| 🟢 niedrig |
   | Aufwand | 3-dimensionale Ressourcen-Schätzung | 💰[Stufe] Geld / ⏰[Stufe] Zeit / 💚[Stufe] Emotion (jeweils 🟢 niedrig / 🟡 mittel / 🔴 hoch) |
   | Braucht | Wer muss was zuliefern / reviewen / freigeben? | Text (z.B. „Gregor: Review") oder „—" wenn selbständig |
   | Risiko | Wie hoch ist das Risiko, dass etwas kaputt geht? | 🔴 hoch \| 🟡 mittel \| 🟢 gering |
   | Rollback | Was tun, wenn etwas schiefgeht? | Kurzer Text oder „—" wenn risikolos |

   Diese Spalten helfen dem User zu entscheiden: Was kann Claude allein machen? Was braucht Aufmerksamkeit? Wo muss jemand handeln?
   Bei Meilenstein-Zeilen (◆) bleiben die Bewertungsspalten leer.

   **Aufgaben-Nummern:** Jede Phase hat ein 3–5-Buchstaben-Prefix (z.B. LIVE, STOLZ, GROW, INFRA, SCAN, DRILL, REACH).

   **Phasen-Benennung — WICHTIG:**
   - **Phasen-Überschriften** tragen den **vollen deutschen/englischen Namen zuerst**, dann den Prefix in Klammern.
     ✅ `### Phase 1 — Infrastruktur (INFRA)`
     ❌ `### Phase 1 — INFRA (Infrastruktur)`
   - **Aufgaben** tragen nur den Prefix als Nummer-Prefix: `INFRA-01`, `INFRA-02`, `SCAN-01`, `DRILL-01`, `REACH-01`
   - Der Prefix kann **technisch-beschreibend** (INFRA, SCAN, DRILL, REACH) ODER **positiv-motivierend** (LIVE, STOLZ, GROW, START, GLOW) sein — was auch immer zum Projekt passt.
   - Vermeide Prefixe wie ORDN, IMPL, PREP, wenn sie sich trocken anfühlen. Strategische/operative Projekte funktionieren oft besser mit klaren technischen Prefixen als mit erzwungen-motivierenden.

   **Seiten-Aufgaben** (📄): Wenn eine Aufgabe die Erstellung oder Überarbeitung einer Seite/eines Dokuments betrifft.
   **Code-Review** (⚙️): Nach JEDER Phase ein komplettes Review als Aufgabe einplanen.
   **Perspektivwechsel** (👁️): Am Ende des Projekts IMMER und bei größeren Projekten auch am Ende jeder Phase eine Perspektivwechsel-Aufgabe einplanen (→ siehe „Perspektivwechsel-Check" weiter unten).

   **Sortierung innerhalb einer Phase:** Aufgaben werden nach Status sortiert:
   1. ✅ Erledigt (oben)
   2. 🔄 In Arbeit / V1
   3. ⬜ Offen
   4. ⚙️ Code-Review / Review
   5. ◆ Meilenstein (immer letzte Zeile)

   **REGELN für den Protokoll-Verlauf:**
   - **UMGEKEHRT CHRONOLOGISCH:** Neueste Log-Einträge stehen OBEN, älteste UNTEN
   - **Log-Nummern:** Format `LOG-XXX` (z.B. LOG-001, LOG-002). Erleichtert Suchen und Referenzieren („siehe LOG-005").
   - **Log-Index pflegen:** Nach JEDEM neuen Log-Eintrag auch den Log-Index oben aktualisieren
   - **Zweck des Index:** Claude kann schnell im Index nachschauen, welcher Log relevant ist, ohne alle Detail-Einträge lesen zu müssen

#### c) Entscheidungslog (optional, bei größeren Projekten empfohlen)

Bei größeren Projekten ein Entscheidungslog anlegen. Dokumentiert das **Warum** hinter wichtigen Entscheidungen — damit man Monate später noch nachvollziehen kann, warum etwas so ist wie es ist.

**Dateiname:** `03-Entscheidungen-[NAME].md` (klein) oder `F - Entscheidungen-[NAME].md` (groß, nach A/B/C/D/E)

```
# Entscheidungen — [PROJEKTNAME]

> Dokumentation aller wesentlichen Entscheidungen.
> Neueste oben, älteste unten.

## Entscheidungs-Index

| Nr | Datum | Entscheidung |
|---|---|---|
| E-001 | [DATUM] | [Kurzbeschreibung] |

---

## Entscheidungen (neueste oben)

### E-001 — [DATUM] — [Titel]

**Entscheidung:** [Was wurde entschieden?]
**Begründung:** [Warum?]
**Auswirkung:** [Was ändert sich dadurch?]
```

**Wann anlegen?** Wenn beim Setup bereits Entscheidungen getroffen werden (Tech-Stack, Struktur, Plattform). Dem User vorschlagen: „Soll ich ein Entscheidungslog anlegen? Das hilft, wenn wir später nachschauen wollen, warum wir uns für X statt Y entschieden haben."

#### d) CLAUDE.md (im Projektordner)

   Inhalt:
   - Projektname und Einzeiler-Beschreibung
   - Beteiligte
   - Dateiübersicht (was liegt wo)
   - **Regel: Bei jedem Gesprächsstart** Projektbeschreibung UND Protokoll lesen
   - Kurze Zusammenfassung geben und nächste 2-3 To-dos vorschlagen
   - Nach jedem abgeschlossenen Schritt sofort Protokoll aktualisieren
   - Nach Context-Compact: Projektbeschreibung und Protokoll nochmal lesen
   - **Dateien NIEMALS löschen**, sondern in `xold/` verschieben
   - **Dateireferenzen immer aktuell halten:** Wenn eine Datei eine neue Version bekommt (z.B. V01 → V02), wird die CLAUDE.md sofort aktualisiert, damit alle Pfade/Referenzen auf die aktuelle Version zeigen. Alte Version → `xold/`.
   - Relevante Zugangsdaten (falls vorhanden)
   - **Projektreview-Regel:** Nach jeweils 10 abgeschlossenen Aufgaben ein Projektreview durchführen (siehe „Projektreview" unten)

#### e) `xold/` — Mülleimer-Ordner (immer anlegen)

#### Zusätzliche Dateien je nach Bedarf:

Weitere Dateien werden fortlaufend nummeriert (klein: `03-...`, `04-...` / groß: `C -`, `D -` etc.).
Z.B. Sitemap, Style-Guide, Methodik-Leitfaden, Teilnehmerliste, Marketing-Text, Ablaufplan...

---

### Strukturierung: Klein vs. Groß

#### Kleines Projekt (flache Struktur)

Alle Dateien liegen direkt im Projektordner. Keine Unterordner außer `xold/`. Nummerierung mit Ziffern.

```
[Projektordner]/
├── CLAUDE.md
├── 01-Projektbeschreibung-[NAME]-V01.md
├── 02-Protokoll-[NAME].md
├── 03-[Weitere-Datei]-V01.md
├── 04-[Weitere-Datei].md
├── ...
└── xold/
```

**Wann klein?** Workshop, einzelne Kampagne, überschaubarer Umfang. Wenn weniger als ~15 Dateien erwartet werden.

**Regel:** Erst erweitern wenn nötig. Neue Themen = neue nummerierte Datei. Erst wenn ein Bereich >5 Dateien hat, über einen Unterordner nachdenken.

#### Großes Projekt (Buchstaben + Unterordner)

Root-Dokumente mit **Buchstaben-Prefix** (A, B, C...), Unterordner mit **Nummern** (01-, 02-...). Aufgaben und Protokoll werden **getrennt** (B = Aufgaben/Planung, C = Protokoll/Verlauf).

```
[Projektordner]/
├── CLAUDE.md
├── A - Projektbeschreibung-[NAME]-V01.md
├── B - Aufgaben-[NAME].md                  ← Phasen, Aufgaben, Meilensteine, Specs
├── C - Protokoll-[NAME].md                 ← Log-Index + Logs
├── D - [z.B. Sitemap / Konzept].md
├── E - [z.B. Style-Guide].md
├── F - Entscheidungen-[NAME].md
├── 01-[thematischer-ordner]/
├── 02-[thematischer-ordner]/
├── ...
└── xold/
```

**Wann groß?** Buch (Manuskript, Freigaben, Cover, Marketing), Kongress (Positionierung, Experten, Bilder, Technik), Software (Anforderungen, Design, Docs).

**Warum Buchstaben?** Nummerierte Root-Dateien (01-, 02-) kollidieren visuell mit nummerierten Unterordnern (01-positionierung/, 02-wettbewerb/). Buchstaben machen sofort klar: „Das sind die Hauptdokumente, die ich immer lese."

**Typische Unterordner nach Projekttyp:**

| Projekttyp | Unterordner |
|-----------|-------------|
| Online-Kongress | 01-Positionierung, 02-Bilder, 03-Experten, 04-Technik, 05-Marketing |
| Buch | 01-Manuskript, 02-Freigaben, 03-Cover, 04-Marketing |
| Online-Kurs | 01-Curriculum, 02-Videos, 03-Materialien, 04-Technik |
| Marketing-Kampagne | 01-Strategie, 02-Content, 03-Ads, 04-Auswertung |
| Software / Website | 01-Anforderungen, 02-Design, 03-Dokumentation |

Unterordner dem User vorschlagen und bestätigen lassen. Nicht overengineeren!

---

### Optionale Patterns (wenn anwendbar)

Vier wiederkehrende Patterns, die nicht jedes Projekt braucht — aber oft genug auftauchen, um sie hier zu dokumentieren. Wenn eines passt: einbauen. Wenn nicht: weglassen.

#### Pattern A: Referenz-Projekt (wenn Projekt auf einem bestehenden aufbaut)

Häufig baut ein neues Projekt auf einem bereits laufenden auf — z.B. ein operatives Migrationsprojekt, das aus einem technischen Engineering-Projekt abgeleitet wird. Oder ein Marketing-Projekt, das auf einen Vorgänger-Kongress verweist.

**Wie integrieren:**

1. **In CLAUDE.md** einen Abschnitt „Referenz-Daten" oder „Referenz-Projekt" einfügen:
   ```
   ## Referenz-Daten
   - **[Name des Referenz-Projekts]:** `/pfad/zum/referenz-projekt/` — enthält [was] und [was].
   - **Relevante Dateien:** `[unterpfad]/xyz.md`
   ```

2. **In A - Projektbeschreibung** einen Abschnitt „Quellen / Zugangsdaten" hinzufügen, der die Referenzdateien aus dem anderen Projekt auflistet.

3. **Frage an den User:** „Dieses Projekt baut auf `[anderes Projekt]` auf. Soll ich wichtige Dateien direkt in dein neues Projekt kopieren (damit sie stabil bleiben, wenn das Quell-Projekt sich ändert), oder nur referenzieren?"

4. **Kopierte Dateien mit Datum im Namen markieren** (`2026-02-20-Domains-PHP7-Liste.txt`), damit später klar ist, von welchem Snapshot sie stammen.

**Wann nicht nötig:** Wenn das Projekt komplett eigenständig ist oder der User explizit sagt „frischer Start".

#### Pattern B: Session-Template (für wiederkehrende Arbeitssessions)

Manche Projekte bestehen aus vielen ähnlich strukturierten Arbeitssessions: Migrationstage, Aufnahmetage, Interview-Sessions, Produktionstermine, Kampagnenwellen. Statt jedes Mal bei Null anzufangen, ein **Session-Template** anlegen.

**Wie integrieren:**

1. Im thematisch passenden Unterordner (z.B. `04-Migrations-Logs/`, `03-Aufnahmen/`, `02-Produktionstage/`) eine Datei `Template-[Session-Typ].md` anlegen.

2. **Inhalt des Templates** (typischer Aufbau):
   ```
   # [Session-Typ] — [DATUM]

   **Erstellt:** [DATUM]
   **Owner:** [Person(en)]
   **Max-Kapazität:** [Anzahl] (falls relevant)

   ## Vorbereitung (Tag davor)
   - [ ] Checkpunkt 1
   - [ ] Checkpunkt 2

   ## Durchführung
   | Nr | Kunde/Item | ... | Status |
   |---|---|---|---|

   ## [Check]-Checkliste (pro Item)
   - [ ] Punkt 1
   - [ ] Punkt 2

   ## Nach der Session
   - [ ] Migrationsliste aktualisiert
   - [ ] Log-Eintrag in C geschrieben

   ## Learnings / Vorfälle
   [Leer lassen, während Session ausfüllen]
   ```

3. **In B - Aufgaben** eine Aufgabe einfügen, die auf das Template verweist: „Pro Session: Template kopieren und durchgehen."

4. **In CLAUDE.md** kurz erwähnen, dass dieses Template für wiederkehrende Sessions verwendet wird.

**Wann einbauen:** Wenn 3+ ähnlich strukturierte Sessions erwartet werden.
**Wann weglassen:** Einmalige Aktionen oder Sessions, die zu unterschiedlich sind, um ein Template zu rechtfertigen.

#### Pattern C: Meta-Verfahren-Dokument (bei generalisierungsfähigen Projekten)

Manchmal ist ein Projekt nicht nur ein Ergebnis, sondern zugleich ein **Blueprint für zukünftige, ähnliche Projekte**. Typische Fälle:
- Ein Freebie, das später gegen andere Themen ausgetauscht werden soll (ein Freebie aus 5, danach 10, 20)
- Ein Funnel-System, das auf beliebige Themen angewendet werden kann (→ siehe Quiz-Funnel-Fabrik)
- Ein Produktions-Workflow, den das Team mehrfach durchlaufen wird
- Ein Positionierungs-Verfahren, das für mehrere Produkte genutzt wird

In diesen Fällen lohnt sich ein **Meta-Verfahren-Dokument (Buchstabe G)**, das das generalisierbare Rahmenwerk beschreibt — so detailliert, dass das nächste Projekt mit einem einzigen Befehl aufgesetzt werden kann.

**Wie integrieren:**

1. **Nach F als zusätzliches Buchstaben-Dokument** `G - Meta-Verfahren-[NAME]-V01.md` anlegen.

2. **Inhaltliche Struktur** (Erstentwurf):
   - Warum dieses Dokument existiert (welche Wiederholung vermieden wird)
   - Das Rahmenwerk auf einen Blick (ASCII-Diagramm oder Flow)
   - Pro Stufe: Input, Schritte, Output, Vorlage (Prompt), Inspirationsquellen
   - Abschnitt „Anwendungs-Beispiele" — jedes neue Produkt, das dem Rahmen folgt, wird als Beispiel ergänzt

3. **In B - Aufgaben** eine eigene Phase **META** einplanen, die parallel zu den anderen Phasen läuft:
   ```
   ### Phase META — Meta-Verfahren dokumentieren (parallel durchgängig)
   | META-01 | Grundgerüst G - Meta-Verfahren-V01 | ... |
   | META-02 | Nach Phase 1: Schritte generalisieren | ... |
   | META-03 | Nach Phase 2: ... | ... |
   ◆ Meilenstein: G-Dokument wiederverwendbar
   ```

4. **Retrospektive Anwendung:** Wenn ein bestehendes Projekt im Nachhinein als Muster taugt (z.B. Quiz-Funnel-Fabrik), als separates Ticket vorschlagen, dort ein G-Dokument nachzuliefern.

**Wann einbauen:** Wenn der User Formulierungen verwendet wie „das könnte man öfter machen", „ist ein Blueprint", „das wäre wiederverwendbar", „als Vorlage für andere Produkte", „verallgemeinerbar".
**Wann weglassen:** Einmal-Projekte ohne Replikations-Absicht.

#### Pattern D: Multi-Channel-Projekt (4-6 Ausspielkanäle)

Viele TDB-Projekte sind **Multi-Channel-Produkte**: ein Kerninhalt, der über 4-6 verschiedene Kanäle ausgespielt wird — z.B. ein Freebie als PDF, Skill, E-Book, Video, Funnel UND Website. Typische Fälle:
- Freebies mit mehreren Ausspielwegen
- Launches (PR, Ads, Newsletter, Affiliate, Social, Event)
- Content-Serien (Blog, Video, Podcast, Newsletter, Social-Clips)
- Produkt-Releases mit mehreren Verkaufskanälen

**Wie integrieren:**

1. **Im Projektordner einen Unterordner `03-Ausspielkanaele/` anlegen** (oder projekt-passend `03-Distribution/`, `03-Kanaele/`).

2. **Pro Kanal einen nummerierten Sub-Unterordner** in der vom User gewünschten Priorisierungs-Reihenfolge:
   ```
   03-Ausspielkanaele/
   ├── 01-PDF-Freebie/          ← Priorität 1
   ├── 02-Claude-Skill/          ← Priorität 2
   ├── 03-Ebook-Buch/            ← Priorität 3
   ├── 04-Video-Miniserie/       ← Priorität 4
   ├── 05-Funnel-Lead-Gen/       ← Priorität 5
   └── 06-Website/               ← Priorität 6
   ```

3. **In B - Aufgaben** pro Kanal eine eigene Phase anlegen (Phasen-Kürzel je Kanal: PDF, SKILL, BOOK, VID, FUN, WEB, …). Jede Phase schließt mit einem Meilenstein ab (M3, M4, M5, …).

4. **In A - Projektbeschreibung** einen Abschnitt „Format & Umfang" mit **einem Block pro Kanal** (Titelseite, Umfang, Preis, Distribution).

5. **Beim Setup abfragen:**
   - „Welche Kanäle sollen wir bespielen?" (nicht weniger als 3 ist meist Multi-Channel sinnvoll)
   - „In welcher Priorisierungs-Reihenfolge?" (Kanal 1 wird zuerst produziert)
   - „Gibt es Kanäle, die später kommen können?" (nicht alle auf einmal)

6. **Begrifflich:** „Ausspielkanal" und „Distributionskanal" sind Synonyme. Projekt-intern das vom User bevorzugte Wort verwenden.

**Wann einbauen:** Wenn der User mehrere Ausspielformate nennt (z.B. „PDF und als Skill und vielleicht als Buch").
**Wann weglassen:** Bei Single-Channel-Projekten (ein Buch = nur das Buch).

---

### Phase 5: Verifikation (Drei-Fragen-Technik)

10. **Dem User das Ergebnis zeigen:**
    - Kurz zusammenfassen, was angelegt wurde
    - Dateistruktur auflisten

11. **Drei Fragen stellen:**
    > „Damit ich sicher bin, dass ich alles richtig verstanden habe, hier drei Fragen:"
    >
    > [Drei projektspezifische Fragen stellen, die zeigen, ob das Projekt korrekt verstanden wurde]

12. **Verbesserungsvorschläge machen:**
    > „Gibt es noch etwas, an das du denken solltest? Hier sind meine Vorschläge: [...]"

13. **Abschluss:**
    > „Das Projekt ist eingerichtet! Du kannst jetzt jederzeit in diesen Ordner kommen und weiterarbeiten. Ich lese dann automatisch die CLAUDE.md und weiß sofort, wo wir stehen."

---

## Perspektivwechsel-Check (Post-Publishing / Zielüberprüfung)

**Kernidee:** Raus aus der Ersteller-Rolle. Komplett andere Sicht einnehmen. Nicht mehr „toll was wir gemacht haben", sondern: **Würde die Zielgruppe das sofort haben wollen?**

**Wann einplanen?**
- **Am Ende des Projekts:** IMMER. Ist eine Pflicht-Aufgabe, nicht optional.
- **Am Ende jeder Phase** (bei größeren Projekten): Empfohlen, besonders wenn die Phase ein nach außen sichtbares Ergebnis hat (z.B. Seite live, Produkt veröffentlicht, Kampagne gestartet).

**Wie benennen?** Der Name passt sich dem Projekt an:
- Buch → „Post-Publishing"
- Website → „Post-Launch"
- Kurs → „Post-Release"
- Kampagne → „Post-Campaign"
- Allgemein → „Zielüberprüfung" oder „Qualitäts-Check"

**Was wird geprüft — die 5 Perspektivwechsel-Fragen:**

1. **Wow-Effekt:** Gibt es einen Moment, in dem die Zielgruppe denkt: „Das ist ja genial! Wer steckt dahinter?" — Wenn nicht, fehlt das Besondere. Gut genug ist nicht gut genug.

2. **Haben-Wollen:** Entsteht beim Anschauen ein sofortiges „Das will ich! Das muss ich haben!"? Oder eher ein „Interessant, mach ich irgendwann"? Der Unterschied ist alles.

3. **Emotionen:** Berührt es? Begeistert es? Macht es neugierig? Oder ist es nur korrekt und vollständig? Korrekt und vollständig bekommt jeder hin — emotionale Resonanz nicht.

4. **Zielerreichung:** Ist das Ziel dieser Phase / dieses Projekts (wie in der Projektbeschreibung definiert) tatsächlich erfüllt? Nicht „fast", nicht „im Prinzip" — wirklich erfüllt?

5. **Kundensicht:** Die gesamte Customer Journey aus Sicht der Zielgruppe durchspielen. Vom ersten Kontakt bis zur gewünschten Aktion. Wo stolpert man? Wo verliert man die Lust? Wo fehlt Info?

**Wie in die Aufgabenliste einbauen:**

```
| [PRE]-XX | 👁️ Perspektivwechsel: [Projektspezifischer Name] | ✅ | 🔴 | 💰🟢 ⏰🟡 💚🟡 | Gregor: Review | 🟢 | — | ⬜ Offen |
```

Bei größeren Projekten als eigene Mini-Phase (Beispiel):

```
### Phase 1b — POST (Post-Publishing Qualitätskontrolle)

> Methodik: Raus aus der Ersteller-Rolle. Von außen drauf schauen wie ein Kunde.

| Nr | Aufgabe | Claude | Impact | Aufwand | Braucht | Risiko | Rollback | Status |
|---|---|---|---|---|---|---|---|---|
| POST-01 | 👁️ Customer Journey durchspielen (Sicht: [Zielgruppe]) | ✅ | 🔴 | 💰🟢 ⏰🟡 💚🟡 | Gregor: Review | 🟢 | — | ⬜ Offen |
| POST-02 | 👁️ Wow-Effekt-Check: Gibt es ein Element das begeistert? | ✅ | 🔴 | 💰🟢 ⏰🟢 💚🟢 | Gregor: Review | 🟢 | — | ⬜ Offen |
| POST-03 | 👁️ Alle Links/CTAs prüfen | ✅ | 🟡 | 💰🟢 ⏰🟢 💚🟢 | — | 🟢 | — | ⬜ Offen |
| POST-04 | 👁️ „Wer ist das?"-Check: Absender klar? Funnel logisch? | ✅ | 🟡 | 💰🟢 ⏰🟢 💚🟢 | Gregor: Review | 🟢 | — | ⬜ Offen |
| POST-05 | 🔧 Alle Findings fixen | ✅ | 🔴 | 💰🟢 ⏰🟡 💚🟡 | — | 🟡 | Revert | ⬜ Offen |
| ◆ | **Meilenstein: Zielüberprüfung bestanden — kein Kunde stolpert** | | | | | | | ⬜ Offen |
```

**Ergebnis:** Konkrete Findings + Fixes. Kein Bericht um des Berichts willen, sondern: besser machen.

---

## Projektreview (bei größeren Projekten)

**Wann?** Nach jeweils **10 abgeschlossenen Aufgaben** ein komplettes Projektreview durchführen. Die CLAUDE.md soll diese Regel enthalten.

**Was wird geprüft:**

1. **Protokoll aktuell?** Stimmen alle Status-Angaben? Sind alle Logs eingetragen?
2. **Doppelungen?** Gibt es Informationen, die an mehreren Stellen gepflegt werden und auseinanderlaufen könnten?
3. **Struktur passend?** Hat sich das Projekt so entwickelt, dass Ordner/Dateien nicht mehr passen? Müssen Dateien verschoben, zusammengefasst oder aufgeteilt werden?
4. **Dokumentation vollständig?** Weiß man noch, wo man hinlangen muss? Sind alle Entscheidungen dokumentiert?
5. **Aufgeräumt?** Gibt es veraltete Dateien, die nach `xold/` gehören? Stale Locks, temporäre Dateien?
6. **CLAUDE.md aktuell?** Stimmen Pfade, Dateiübersicht, Regeln noch?

**Ergebnis:** Log-Eintrag mit Befund + ggf. Aufräumarbeiten.

---

## Selbstverbesserung

**WICHTIG:** Nachdem der Skill durchgelaufen ist und das Projekt aufgesetzt wurde, aktiv prüfen:

> „Bevor wir loslegen — ich habe beim Einrichten ein paar Dinge bemerkt, die den `/projekt-starten` Skill verbessern könnten:
> - [Konkrete Beobachtungen: Was hat gut funktioniert? Was war umständlich? Was fehlte?]
> - [Vorschläge für Verbesserungen oder Individualisierungen]
>
> Soll ich diese Verbesserungen in den Skill einarbeiten?"

**Worauf achten:**
- Neue Projekttypen, die der Skill noch nicht kennt (z.B. neue Unterordner-Vorschläge)
- Schritte, die überflüssig waren oder gefehlt haben
- Fragen, die der Skill hätte stellen sollen aber nicht gestellt hat
- Strukturen, die sich im Projektverlauf als unpraktisch erwiesen haben
- Patterns, die projektspezifisch waren aber eigentlich generell nützlich wären

**Auch während des Projektverlaufs:** Wenn in späteren Chats auffällt, dass die Projektstruktur Schwächen hat oder der Skill etwas besser hätte machen können → dem User vorschlagen, den Skill zu aktualisieren.

---

## Wichtige Regeln

- **Klein starten:** Im Zweifel flache Struktur. Unterordner ergänzen wenn nötig.
- **Versionierung:** Neue Version = neue Nummer (V01, V02, ...), nie überschreiben
- **Versionierte Dateien:** Bei neuer Version (z.B. V02) wird die ältere Version (V01) sofort nach `xold/` verschoben. Im Hauptordner liegt immer nur die aktuelle Version. So bleibt der Ordner übersichtlich.
- **xold-Ordner:** Altes hierhin verschieben statt löschen
- **Sprache:** Deutsch (Standard) oder Englisch (wenn das Projekt es verlangt — z.B. internationales Team oder kundenseitig englischer Content). In der CLAUDE.md pro Projekt festlegen.
- **Dateien nach außen:** Immer nur PDF, nie DOCX
- **Diktierfehler:** User nutzt häufig Diktierfunktion — Domains, E-Mail-Adressen, Fachbegriffe immer gegenchecken
- **Nicht overengineeren:** Nur anlegen was gebraucht wird. Lieber schlank starten und bei Bedarf erweitern.
