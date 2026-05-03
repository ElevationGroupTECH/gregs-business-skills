# Projekt-Review — Hochglanz-Check

Dieser Skill bringt ein gewachsenes Projekt zurück auf Hochglanz. Projekte wachsen über die Zeit wie ein Baum ohne Form — Dateien kommen dazu, Strukturen verwässern, Protokolle laufen auseinander, Müll sammelt sich an. Dieses Review schaut sich das Projekt aus der Adlerperspektive an, räumt selbstständig auf was offensichtlich ist, und schlägt alles Weitere als konkrete Aufgaben vor.

> **Teil eines Paares:** Dieser Skill hält Projekte sauber. Sein Partner `/projekt-starten` setzt sie sauber auf — mit Struktur, Beschreibung, Protokoll und CLAUDE.md. Zusammen bilden sie einen Kreislauf: Starten → Arbeiten → Review → Aufräumen → Weiterarbeiten.

Der Skill bezieht sich immer auf den Projektordner, in dem gerade gearbeitet wird. Der Maßstab ist die Projektstruktur aus `/projekt-starten`.

---

## Phase 0: Orientierung — Wo bin ich?

Bevor irgendwas passiert: **Sicherstellen, dass wir im richtigen Projektordner sind.**

1. **Aktuellen Ordner prüfen:**
   - Gibt es hier eine `CLAUDE.md`? Gibt es Projektdateien (01-Projektbeschreibung... oder A - Projektbeschreibung...)?
   - Wenn ja → Projekt erkannt, weiter mit Phase 1
   - Wenn nein → Nachfragen: "In welchem Projektordner soll ich das Review machen? Gib mir den Pfad oder sag mir, um welches Projekt es geht."

2. **Falls ein Argument übergeben wurde** (Pfad): Diesen verwenden.

3. **Projekt-Typ erkennen:**
   - Nummerierte Root-Dateien (01-, 02-...) → **Kleines Projekt** (flache Struktur)
   - Buchstaben-Prefix (A -, B -, C -...) + nummerierte Ordner → **Großes Projekt**
   - Keines von beiden → Notieren als Finding ("Projektstruktur entspricht keinem Standard-Schema")

---

## Phase 1: Bestandsaufnahme — Was haben wir hier?

Zuerst ein vollständiges Bild aufbauen, **bevor** irgendwas verändert wird.

### Ebene 1: CLAUDE.md

Die CLAUDE.md lesen und prüfen:

- **Existiert sie?** Wenn nicht → schwerwiegendes Finding
- **Ist sie kurz genug?** Die CLAUDE.md wird bei jedem Gesprächsstart geladen. Sie sollte knapp und präzise sein — Richtwert: unter 80 Zeilen. Alles was länger ist, verbraucht unnötig Kontext-Fenster.
- **Stimmt die Dateiübersicht?** Werden alle tatsächlich vorhandenen Projektdateien aufgelistet? Fehlen welche? Werden Dateien erwähnt, die gar nicht mehr existieren?
- **Stimmen die Regeln?** Wird auf die richtigen Dateien verwiesen? Sind Pfade korrekt?
- **Gibt es eine Projektreview-Regel?** (Nach 10 Aufgaben → Review)
- **Gibt es eine Context-Compact-Regel?** (Nach Compact → Projektbeschreibung + Protokoll neu lesen)
- **Ist sie aktuell?** Passt die Beschreibung noch zum tatsächlichen Stand des Projekts?

### Ebene 2: Projektdateien (Inhalt)

Alle Root-Dokumente lesen (01/02/03... oder A/B/C...) und prüfen:

**Projektbeschreibung (01 bzw. A):**
- Ist sie vollständig? (Titel, Übersicht, Beteiligte, Zielgruppe, Zeitrahmen, Dateistruktur)
- Ist sie aktuell? Passt sie noch zum tatsächlichen Projektverlauf?
- Gibt es Widersprüche zum tatsächlichen Stand?

**Aufgaben/Protokoll (02 bzw. B+C):**
- Sind die Aufgaben-Status aktuell? (Stimmt ✅/🔄/⬜ mit der Realität überein?)
- Sind die Aufgaben sauber nummeriert? (Durchgängige Nummerierung, keine Lücken, keine Doppelungen)
- Stimmt die Sortierung? (✅ oben → 🔄 → ⬜ → ⚙️ → ◆ unten)
- Sind die Phasen noch sinnvoll? Oder ist eine Phase so groß geworden, dass sie aufgeteilt werden sollte?
- Sind die Meilensteine noch sinnvoll und aktuell?
- **Log-Index:** Ist er vollständig? Stimmen die Log-Nummern? Sind alle Logs dort aufgeführt?
- **Protokoll-Verlauf:** Chronologisch korrekt (neueste oben)? Sind alle durchgeführten Arbeiten protokolliert?
- Gibt es Log-Einträge, die offensichtlich fehlen? (z.B. Dateien die existieren aber nirgends protokolliert sind)

**Entscheidungslog (falls vorhanden):**
- Ist der Index aktuell?
- Sind Entscheidungen mit Begründung dokumentiert?
- **Realitäts-Abgleich:** Für jede Entscheidung prüfen, ob sie noch den aktuellen Stand widerspiegelt. Entscheidungen dokumentieren den Moment, in dem sie getroffen wurden — aber wenn sich danach etwas geändert hat (z.B. ein Prefix wurde umbenannt, eine Phase umstrukturiert), muss die Entscheidung einen Nachtrag bekommen oder als überholt markiert werden. Sonst liest Claude eine alte Entscheidung und handelt danach, obwohl die Realität längst anders aussieht.

**Querverweis-Check (systematisch):**

Das ist einer der häufigsten Fehler in gewachsenen Projekten: Dieselbe Information steht an mehreren Stellen und läuft auseinander. Systematisch prüfen:

- **URLs:** Wenn eine URL in der Sitemap steht UND in der Aufgabenliste, müssen sie identisch sein. Jede URL die in mehr als einer Datei vorkommt → abgleichen.
- **Dateinamen und Pfade:** Verweise auf Dateien/Ordner in CLAUDE.md, Projektbeschreibung, Aufgaben → stimmen sie mit dem Dateisystem überein?
- **Phasennamen und Prefixe:** Werden in Aufgaben, Protokoll, Entscheidungslog und CLAUDE.md die gleichen Bezeichnungen verwendet?
- **Status-Angaben:** Wenn die Projektbeschreibung sagt "Phase 1a in Arbeit" und die CLAUDE.md dasselbe sagt — stimmt das noch mit der Aufgabenliste überein?
- **Personen und Rollen:** Werden Beteiligte überall gleich genannt?

Bei jedem Widerspruch: Die Quelle der Wahrheit identifizieren (meist die Aufgabendatei oder das Dateisystem) und alle anderen Stellen als Finding notieren.

---

### Ebene 3: Impact / Ressourcen-Klarheit (eigenständige strategische Prüfung)

> **Warum eigenständig?** Hochglanz-Hygiene (Struktur, Vollständigkeit, Konsistenz, Aktualität, Sauberkeit) sagt: „Das Projekt ist ordentlich gepflegt." Sie sagt **nicht**: „Das Projekt arbeitet an den richtigen Sachen."
>
> Ein Projekt kann Hochglanz-100% sein und trotzdem an homöopathischen Mikro-Optimierungen scheitern, während die Riesen-Hebel unangetastet liegen. Diese Dimension wird daher **separat bewertet** — als 0-2 Punkte zusätzlich zum Hochglanz-Score, weil sie eine **strategische Frage** ist, keine Hygiene-Frage.

**Das Prinzip kurz (für Claude-Instanzen ohne TDB-Kontext):**
> **Wert = Impact ÷ Ressourcen (Geld + Zeit + Emotionen)**
>
> Drei Ressourcen-Dimensionen, nicht zwei. Emotionen (Nerv-Faktor, Energie, Sicherheit) sind die am häufigsten unterschätzte Ressource.
> - 🚀 Riesen-Impact (3-10×): rein in den Plan
> - ⚡ Mittel + Low Hanging Fruit: mitnehmen, wenn KI/Claude allein/automatisiert
> - 🐭 Homöopathisch (<5%): lassen, auch wenn technisch elegant

**Was hier konkret geprüft wird:**

1. **Sind Aufgaben nach Impact priorisiert?**
   - Hat die Aufgabenliste eine **Impact-Spalte** (🚀 / ⚡ / 🐭 oder vergleichbar)?
   - Sind Riesen-Impact-Aufgaben in frühen Phasen, Homöopathisches in späten oder gar nicht?
   - Oder wird abgearbeitet, was leicht ist, statt was wirkt?

2. **Sind Ressourcen mit drei Dimensionen geschätzt?**
   - Hat die Aufgabenliste eine **Aufwand-Spalte** mit Geld + Zeit + Emotionen (€/⏰/💚 oder vergleichbar)?
   - Werden Emotionen als Ressource explizit benannt? (Nerv-Faktor, Wartungs-Frust, Komplexitäts-Stress)
   - Oder nur in Stunden gerechnet — als ob die anderen zwei Dimensionen nicht existieren?

3. **Werden Hype-Argumente identifiziert und benannt?**
   - Gibt es im Entscheidungslog Einträge der Art „verworfen, weil kein konkretes Problem gelöst"?
   - Oder werden Aufgaben akzeptiert nur weil sie „Industriestandard" / „cool" / „sollte man" sind?
   - Achten auf Indikatoren in Protokoll und Entscheidungen: „löst kein konkretes Problem", „Frau-Test", „Compound", „Opportunitätskosten"

4. **Ist „nicht implementieren" eine sichtbare Option?**
   - Gibt es Aufgaben mit Status „verworfen" oder „bewusst nicht gemacht"?
   - Oder nur „offen", „in Arbeit", „erledigt"? (Das wäre verdächtig — heißt: niemand sagt nein.)

5. **Sind Compound-Effekte erkannt?**
   - Sind Aufgaben, die sich gegenseitig verstärken (z.B. SEO × Content × Backlinks bei einer Website), als zusammenhängende Hebel-Phase erkennbar?
   - Oder isoliert in der Liste verstreut, als wären sie unabhängig?

6. **Wer macht den Aufwand?**
   - Ist klar, welche Aufgaben Claude autonom kann, welche Zuarbeit brauchen, welche der Mensch entscheiden muss?
   - (z.B. „Wer"-Spalte oder „Claude"-Spalte mit ✅/⚠️/❌)
   - Sachen, die Claude allein kann, sollten **bevorzugt** werden, weil Mensch-Zeit teuer ist.

**Bewertung (max 2.0 Punkte):**

| Score | Bedeutung |
|---|---|
| **2.0 / 2.0** 🎯 | Aufgaben sind nach Impact priorisiert, Aufwand mit 3 Dimensionen, Anti-Pattern-Bewusstsein im Entscheidungslog, „nicht implementieren" sichtbar. Riesen-Hebel zuerst. |
| **1.5 / 2.0** 👍 | Impact erkannt und mehrheitlich berücksichtigt. Eine Dimension fehlt (oft: Emotionen werden nicht benannt). |
| **1.0 / 2.0** ⚠️ | Aufgaben gemischt — manche nach Impact, manche nach Bequemlichkeit. Prinzip nicht explizit verankert. |
| **0.5 / 2.0** 🚨 | Aufgabenliste ist eine To-do-Wand ohne Priorisierung. Wird abgearbeitet, was leicht ist. |
| **0 / 2.0** 🐭 | Reine Tool-/Feature-Sammlung ohne Impact-Bewusstsein. Optimierungsfalle aktiv. |

**Findings für diese Kategorie sind besonders wichtig.** Sie zeigen, ob das Projekt strategisch gesund ist — nicht nur ordentlich. Hochglanz-Score ohne Impact-Score ist wie ein gepflegter Garten ohne Ernte.

**Weitere Projektdateien:**
- Sind sie noch relevant? Oder überholt?
- Gibt es inhaltliche Doppelungen zwischen Dateien?
- Gibt es Widersprüche zwischen Dateien?
- Sind Dateinamen sprechend und korrekt versioniert (V01, V02...)?

### Ebene 3: Ordner und Dateistruktur

- **Alle Ordner auflisten** und kurz reinschauen (Dateiliste, nicht Inhalte lesen)
- **xold/ prüfen:**
  - Gibt es Dateien darin, die inhaltlich offensichtlich nichts mehr mit dem Projekt zu tun haben?
  - Gibt es Dateien, die identisch sind mit aktuellen Versionen (echte Duplikate)?
  - Gibt es extrem große Dateien, die nur Platz verschwenden?
  - NICHT pauschal nach Alter löschen! Ein Projekt kann monatelang ruhen — das Alter allein sagt nichts.
- **Verwaiste Dateien:** Gibt es Dateien im Projektordner, die in keiner Projektdatei referenziert werden und keinem erkennbaren Zweck dienen?
- **Temporäre Dateien:** `.tmp`, `.bak`, Lock-Dateien, `node_modules` die nicht hingehören, etc.
- **Passt die Ordnerstruktur zum Projekt?** Sind die thematischen Ordner noch sinnvoll, oder hat sich das Projekt in eine andere Richtung entwickelt?
- **Gewachsene Dateien:** Gibt es einzelne Dateien, die unverhältnismäßig groß geworden sind (>300 Zeilen) und aufgeteilt werden sollten?

---

## Phase 2: Sofort-Reparaturen — Was ist offensichtlich?

Nach der Bestandsaufnahme: Alles was eindeutig falsch ist und risikolos korrigiert werden kann, **sofort selbst beheben**. Dazu gehören Dinge wie:

- **Sortierung reparieren:** Aufgaben in der richtigen Reihenfolge sortieren (✅ → 🔄 → ⬜ → ⚙️ → ◆)
- **Log-Index vervollständigen:** Fehlende Einträge im Log-Index nachtragen
- **CLAUDE.md Dateiübersicht aktualisieren:** Fehlende Dateien ergänzen, nicht mehr existierende entfernen
- **Nummerierungslücken schließen:** Aufgaben-Nummern korrigieren
- **Offensichtliche Tippfehler** in Projektdateien korrigieren
- **Temporäre Dateien** entfernen (.tmp, .bak, Lock-Dateien)
- **Leere oder nutzlose Dateien** nach xold/ verschieben
- **Chronologie reparieren:** Protokoll-Verlauf in richtige Reihenfolge bringen (neueste oben)

**NICHT selbst machen** (nur als Vorschlag):
- Dateien umbenennen die im Projekt referenziert werden (könnte Verweise brechen)
- Projektstruktur umbauen (von flach auf Unterordner oder umgekehrt)
- Phasen zusammenlegen oder aufteilen
- Inhalte umschreiben oder kürzen (außer CLAUDE.md wenn offensichtlich zu lang)
- Dateien aus xold/ löschen (immer als Vorschlag mit Begründung)
- Projekt splitten

---

## Phase 3: Review-Zusammenfassung

Den Review-Bericht direkt im Chat ausgeben. Struktur:

```
## Projekt-Review: [PROJEKTNAME]
📅 Datum: [DATUM]
📂 Ordner: [PFAD]
🔍 Typ: [Klein/Groß]

### Hochglanz-Score: [X.X] / 10  [EMOJI]

| Kategorie | Score | Details |
|---|---|---|
| 🏗️ **Struktur** | [X.X] / 2.0 | [1 Satz was gut/schlecht] |
| 📋 **Vollständigkeit** | [X.X] / 2.0 | [1 Satz was gut/schlecht] |
| 🔗 **Konsistenz** | [X.X] / 2.0 | [1 Satz was gut/schlecht] |
| 🕐 **Aktualität** | [X.X] / 2.0 | [1 Satz was gut/schlecht] |
| 🧹 **Sauberkeit** | [X.X] / 2.0 | [1 Satz was gut/schlecht] |
| | **[X.X] / 10** | |

### Impact-Score: [X.X] / 2.0  [EMOJI]

> **Strategische Zusatzdimension** — separat bewertet, weil Hygiene und Impact zwei verschiedene Fragen sind.
> Hochglanz-100% sagt: „ordentlich gepflegt". Impact-Score sagt: „arbeitet an den richtigen Sachen".

| Aspekt | Bewertung |
|---|---|
| 🎯 Aufgaben nach Impact priorisiert? | [✅/⚠️/❌] [Notiz] |
| 💰⏰💚 Aufwand mit 3 Dimensionen geschätzt? | [✅/⚠️/❌] [Notiz] |
| 🚫 Anti-Patterns identifiziert (kein Hype)? | [✅/⚠️/❌] [Notiz] |
| ❌ „Nicht implementieren" als Option sichtbar? | [✅/⚠️/❌] [Notiz] |
| 🔗 Compound-Effekte erkannt und gebündelt? | [✅/⚠️/❌] [Notiz] |
| 👤 „Wer macht den Aufwand?"-Klarheit? | [✅/⚠️/❌] [Notiz] |

**Impact-Summary** (1-2 Sätze): [Strategische Bewertung — arbeiten wir an den richtigen Sachen, oder polieren wir Sandkörner?]

**Die 5 Kategorien im Detail:**

**🏗️ Struktur** (max 2.0) — Das Skelett: Existiert die richtige Form?
- CLAUDE.md vorhanden, kurz genug (<80 Zeilen), Regeln korrekt?
- Projekt-Typ erkennbar (Buchstaben/Nummern)? Dateien richtig benannt?
- Ordner-Hierarchie sinnvoll? xold/ vorhanden?
- Dateiübersicht in CLAUDE.md stimmt mit Dateisystem überein?

**📋 Vollständigkeit** (max 2.0) — Das Fleisch: Sind alle Inhalte da?
- Projektbeschreibung vollständig (Titel, Beteiligte, Technik, Zeitrahmen)?
- Aufgaben mit Phasen, Meilensteinen, Nummerierung?
- Protokoll mit Log-Index und Log-Einträgen?
- Entscheidungslog vorhanden (bei großen Projekten)?
- Fehlen offensichtlich Dateien oder Inhalte?

**🔗 Konsistenz** (max 2.0) — Die Logik: Widerspricht sich nichts?
- URLs in Sitemap = URLs in Aufgabenliste?
- Phasennamen und Prefixe überall gleich?
- Dateiverweise in CLAUDE.md stimmen mit Dateisystem?
- Entscheidungen spiegeln den aktuellen Stand wider?
- Personen, Rollen, Status-Angaben überall identisch?

**🕐 Aktualität** (max 2.0) — Die Frische: Ist alles auf dem neuesten Stand?
- Aufgaben-Status stimmt mit Realität überein?
- Protokoll dokumentiert alle durchgeführten Arbeiten?
- Stand-Daten in Dokumenten aktuell?
- Aufgaben korrekt sortiert (✅ → 🔄 → ⬜ → ⚙️ → ◆)?
- CLAUDE.md beschreibt die aktuelle Phase?

**🧹 Sauberkeit** (max 2.0) — Die Hygiene: Liegt Müll rum?
- xold/ aufgeräumt? Keine riesigen, nutzlosen Dateien?
- Keine temporären Artefakte (.tmp, .bak, Logs, .DS_Store)?
- Keine verwaisten Dateien ohne Referenz?
- Keine gewachsenen Monster-Dateien (>300 Zeilen)?
- Keine KI-Artefakte (ChatGPT-Zitationen, Debug-Reste)?

**Gesamt-Skala:**
- 0–1: 🤯  |  1–2: 🤬  |  2–3: 😱  |  3–4: 😫  |  4–5: 🥵
- 5–6: 🧐  |  6–7: 🤔  |  7–8: 😀  |  8–9: 🤩💪  |  9–10: 🏆🏆🏆

> [REVIEW-SUMMARY — 1-3 Sätze, ehrlich und direkt]

Das Review-Summary ist das Herzstück der Bewertung. Es wird direkt unter dem Score angezeigt und soll in 1-3 Sätzen auf den Punkt bringen, wie es um das Projekt steht. Dabei gilt: SEI NICHT DIPLOMATISCH. Sag es wie es ist — ehrlich, menschlich, mit Charakter. Die Bewertung darf wehtun wenn es schlecht ist und darf begeistern wenn es gut ist.

Orientierung nach Score-Bereich (Beispiele, NICHT wörtlich übernehmen — eigene Worte finden!):

**0–2:** "Komplettausfall." / "Das ist kein Projekt, das ist ein Ordner mit Dateien drin." / "Hier fehlt alles. Wirklich alles." / "Puh... wo fängt man da an?" / "Was ist denn hier passiert?"

**2–4:** "Herrje." / "Da muss man jetzt ehrlich sein: Das ist ein ziemliches Durcheinander." / "Grundstruktur erkennbar — aber dann hört's auf." / "Bisschen mehr Mühe geben wäre nicht verkehrt gewesen." / "Stehts bemüht, würde man im Zeugnis schreiben."

**4–6:** "Arbeitsfähig, aber man merkt die Vernachlässigung." / "Das geht besser — und das weißt du auch." / "Solide Basis, aber drüber ist Staub gewachsen." / "Halbzeit: Kann man mit arbeiten, macht aber keinen Spaß."

**6–7:** "Schon ganz ordentlich, Struktur klar erkennbar." / "Man sieht, dass hier jemand mitdenkt." / "Ein paar Macken, aber grundsolide."

**7–8:** "Da ist richtig viel Schönes dabei!" / "Claude fühlt sich hier wohl — und das merkt man an der Arbeit." / "Gut gepflegt, nur ein paar Wachstumskratzer."

**8–9:** "Beeindruckend. So sieht ein Projekt aus, das jemand ernst nimmt." / "Top 5% — das hier ist eine Wonne für eine KI." / "Fast Hochglanz. Fast."

**9–10:** "Einfach wow." / "Top 1%. Ein Traum von Projektstruktur." / "Hier gibt es nichts zu tun. Herausragend." / "Wenn alle Projekte so aussehen würden..."

WICHTIG: Diese Beispiele sind nur Inspiration. Das Summary soll spezifisch auf das Projekt eingehen — was konkret gut oder schlecht ist. Nicht generisch labern, sondern benennen.

### ✅ Was ist gut
- [Punkte die in Ordnung sind — wichtig für die Einordnung!]

### 🔧 Sofort erledigt
- [Was wurde automatisch repariert, mit kurzer Begründung]

### ❓ Entscheidungen nötig

Manche Findings kann ich nicht selbst lösen — hier brauche ich eine Entscheidung. Jedes offene Thema wird klar dargestellt, damit es schnell entschieden werden kann:

| Nr | Thema | Option A | Option B | Empfehlung |
|---|---|---|---|---|
| 1 | [Kurzbeschreibung] | [Option A + was sich ändert] | [Option B + was sich ändert] | [Welche Option und warum] |

Für jede Entscheidung:
- **Was ist das Problem?** (1 Satz — was widerspricht sich oder ist unklar)
- **Welche Dateien sind betroffen?** (damit klar ist, was sich ändert)
- **Was empfehle ich?** (immer eine klare Empfehlung geben, nicht nur Optionen hinwerfen)
- **Was passiert wenn wir nichts tun?** (Konsequenz der Nicht-Entscheidung)

Nach jeder getroffenen Entscheidung: Sofort umsetzen und in den Entscheidungslog eintragen.

### 📋 Empfohlene Aufgaben — Der Weg zur 10/10
[Nummerierte Liste von konkreten Aufgaben, die KEINE Entscheidung brauchen — die kann ich direkt umsetzen. Priorisiert, mit Score-Impact:]

| Nr | Aufgabe | Priorität | Score-Impact | Begründung |
|---|---|---|---|---|
| 1 | ... | 🔴 Hoch | +0.5 | ... |
| 2 | ... | 🟡 Mittel | +0.3 | ... |
| 3 | ... | 🟢 Niedrig | +0.1 | ... |

> **Prognose:** Wenn alle Aufgaben erledigt + alle Entscheidungen getroffen → [neuer Score] / 10 [EMOJI]

### 💡 Strategische Überlegungen
- [Projekt splitten? Phasen neu definieren? Struktur umbauen?]
- [Dinge die man gelernt hat und festhalten sollte]
- [Richtung für die nächste Phase]
```

**Prioritäten:**
- 🔴 **Hoch:** Beeinträchtigt die Arbeit direkt (z.B. CLAUDE.md fehlt, Protokoll veraltet, Widersprüche)
- 🟡 **Mittel:** Sollte bald gemacht werden (z.B. xold aufräumen, Doppelungen beseitigen, Phasen überdenken)
- 🟢 **Niedrig:** Nice-to-have (z.B. Entscheidungslog nachrüsten, Dateinamen vereinheitlichen)

---

## Phase 4: Nächste Schritte

Nach der Zusammenfassung:

1. **Fragen ob Aufgaben umgesetzt werden sollen:**
   > "Das sind die Punkte, die ich gefunden habe. Soll ich die Aufgaben jetzt direkt angehen? Oder willst du erst einzelne besprechen?"

2. **Bei Zustimmung:** Aufgaben der Reihe nach abarbeiten, bei größeren Eingriffen (Struktur-Umbau, Projekt-Split) vorher Rücksprache halten.

3. **Protokoll aktualisieren:** Am Ende einen Log-Eintrag schreiben:
   ```
   ### LOG-XXX — [DATUM] — Projekt-Review (Hochglanz)
   - Review durchgeführt: [Anzahl] Findings, davon [X] sofort behoben
   - Sofort erledigt: [Aufzählung]
   - Empfohlene Aufgaben: [Aufzählung oder Verweis auf Review-Ausgabe]
   - Hochglanz-Score: [vorher] → [nachher]
   ```

4. **Wenn alle Aufgaben erledigt sind → Neuen Score berechnen und Hochglanz-Abschluss feiern!**

   Den Score neu berechnen. Wenn er jetzt bei 9+ liegt:

   ```
   ---

   ## 🏆🏆🏆 HOCHGLANZ ERREICHT!

   **Score: [X.X] / 10** (vorher: [alter Score])

   [HIER KOMMT DIE CELEBRATION — siehe unten]

   Dieses Projekt ist jetzt bereit für die nächsten 100 Aufgaben.
   Viel Spaß beim Weiterarbeiten! 🚀
   ```

   Die Celebration soll lustig, bildlich und motivierend sein. Kreativ sein! Hier ein paar Richtungen als Inspiration (NICHT abschreiben, eigene Varianten erfinden!):

   - **Duft-Metaphern:** "Dieses Projekt duftet jetzt nach frischer Frühlingsbrise und frisch gemähtem Rasen. Vorher roch es eher nach... naja, sagen wir: nach einer WG-Küche am Sonntagmorgen."
   - **Hotel-Metaphern:** "Willkommen zurück im 5-Sterne-Projekthotel. Die Handtücher sind gefaltet, die Kissen aufgeschüttelt, eine kleine Schokolade liegt auf dem Protokoll."
   - **Zahnarzt-Metaphern:** "So fühlt sich ein Projekt nach der Prophylaxe an. Alles blitzt, alles glänzt, und man fragt sich: Warum hab ich das nicht schon vor drei Monaten gemacht?"
   - **Auto-Metaphern:** "Frisch durch die Waschanlage. Lack poliert, Innenraum gesaugt, der Tannenbaum-Duftspender baumelt am Rückspiegel der CLAUDE.md."
   - **Kochen:** "Mise en place. Alles an seinem Platz, die Messer geschärft, die Zutaten vorbereitet. Jetzt kann gekocht werden."
   - **Marie-Kondo:** "Marie Kondo wäre stolz. Jede Datei funzt joy. Der xold-Ordner atmet auf."
   - **KI-Perspektive:** "Wenn ich ein Herz hätte, würde es jetzt schneller schlagen. Dieses Projekt ist wie ein aufgeräumtes Wohnzimmer mit Kamin, einer Tasse Tee und einem guten Buch. Ich WILL hier arbeiten."

   WICHTIG: Immer projektspezifisch! Beziehe dich auf konkrete Sachen die aufgeräumt wurden. "Die Buch-URL zeigt jetzt überall auf /buecher/ statt auf drei verschiedene Pfade" ist besser als "Alles ist aufgeräumt."

   Wenn der Score unter 9 bleibt, trotzdem den Fortschritt feiern:
   > "Von [alter Score] auf [neuer Score] — das ist ein spürbarer Unterschied! [1-2 konkrete Verbesserungen benennen]. Für die volle 10 fehlt noch [was], aber das Projekt ist jetzt deutlich arbeitsfähiger."

---

## Wichtige Grundsätze

- **Adlerperspektive, nicht Ameisenperspektive:** Nicht in Code oder Ausführungsdateien eintauchen. Nur den Projekt-Rahmen prüfen (CLAUDE.md, Projektdateien, Struktur).
- **Erst verstehen, dann handeln:** Komplett lesen bevor irgendwas verändert wird.
- **Konservativ bei Löschungen:** Lieber einmal zu viel nach xold/ verschieben als einmal zu viel löschen. Bei echtem Löschen (xold bereinigen) immer vorschlagen, nie selbst machen.
- **Das Ziel ist Hochglanz:** Nach dem Review soll das Projekt sich anfühlen wie frisch aufgesetzt — Claude arbeitet gerne darin, alles ist an seinem Platz, nichts widersprüchlich, nichts überfällig.
- **Kein Overengineering:** Nicht unnötig Dateien oder Strukturen hinzufügen. Das Projekt soll schlank bleiben, nicht aufgebläht werden.
