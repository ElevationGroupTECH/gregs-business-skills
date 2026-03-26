[🇬🇧 English](README.md) | 🇩🇪 Deutsch

<p align="center">
  <img src="assets/claude-business-skills-hero.png" alt="Claude Business Skills" width="700">
</p>

# Claude Business Skills

**Die meisten nutzen Claude wie eine schicke Suchmaschine. Diese Skills machen daraus einen Projektmanager.**

Schon mal ein neues Projekt gestartet und 20 Minuten damit verbracht, Claude den Kontext zu erklären — nur um das in der nächsten Session nochmal zu machen? Oder einen Projektordner nach zwei Wochen geöffnet und keine Ahnung gehabt, wo du aufgehört hast?

Du kennst den Typ. 47 Dateien auf dem Desktop. "Entwurf_v3_FINAL_wirklich-final.docx". Ein Projektordner, der aussieht wie eine digitale Rumpelkammer.

Hier ist die Sache: **Claude ist nur so gut wie der Kontext, den du ihm gibst.** Gib ihm ein sauberes Projekt-Setup mit klarer Dokumentation, und es wird ein komplett anderes Werkzeug. Genau das machen diese Skills — in etwa 30 Sekunden.

---

## Was steckt drin?

### `/projekt-starten` — Projekte richtig aufsetzen

Verwandle ein chaotisches Brainstorming in ein sauber strukturiertes Projekt. Du redest, Claude organisiert:

- **Projektbeschreibung** mit allem was zählt (Ziele, Beteiligte, Zeitrahmen, Technik)
- **Protokoll** mit Phasen, Meilensteinen, Aufgaben-Tracking und Log-Einträgen
- **CLAUDE.md** damit Claude genau weiß, was es lesen soll und wie es sich im Projekt verhalten soll
- **Smarte Größenanpassung** — kleine Projekte bleiben flach, große bekommen Buchstaben-Prefix + nummerierte Unterordner
- **Verifikation** — drei gezielte Fragen, damit nichts verloren geht

**So funktioniert's:** Starte `/projekt-starten`, erzähl einfach drauflos (Sprachnachricht-Style — chaotisch, unstrukturiert, wild durcheinander), und schau zu wie Claude daraus in unter einer Minute eine saubere Projektstruktur macht.

> *Entstanden aus hunderten Stunden echtem Projektarbeiten mit Claude. Keine Theorie — so arbeiten wir wirklich jeden Tag bei [Teile Deine Botschaft](https://www.teiledeinebotschaft.de).*

### `/projekt-review` — Hochglanz-Check (Dein Projekt-Score)

Dein Projekt wächst seit Wochen. Dateien überall. Das Protokoll ist drei Updates hinterher. Die CLAUDE.md erwähnt noch Phase 1, obwohl du längst in Phase 3 steckst.

Dieser Skill macht ein umfassendes Review und gibt dir einen **Hochglanz-Score von 10**:

| Kategorie | Was geprüft wird |
|---|---|
| 🏗️ **Struktur** | CLAUDE.md, Dateibenennung, Ordner-Hierarchie |
| 📋 **Vollständigkeit** | Projektbeschreibung, Aufgaben, Meilensteine, Protokoll |
| 🔗 **Konsistenz** | Querverweise, URLs, Phasennamen, Status-Angaben |
| 🕐 **Aktualität** | Stimmen die Status? Ist das Protokoll aktuell? |
| 🧹 **Sauberkeit** | Temp-Dateien, verwaiste Dokumente, aufgeblähte Dateien |

**Was passiert:**
1. Komplette Bestandsaufnahme (liest alles, prüft alles)
2. Automatische Fixes (Sortierung, Log-Index, Dateiübersicht — das Offensichtliche)
3. Entscheidungstabelle (Dinge, die deinen Input brauchen)
4. Empfohlene Aufgaben mit Priorität und Score-Impact
5. Score-Prognose: "Wenn du das alles machst → 9.2 / 10"

**Die Score-Skala:**
```
0-1: 🤯  |  1-2: 🤬  |  2-3: 😱  |  3-4: 😫  |  4-5: 🥵
5-6: 🧐  |  6-7: 🤔  |  7-8: 😀  |  8-9: 🤩💪  |  9-10: 🏆🏆🏆
```

Score 9+ erreicht? Du bekommst eine Celebration. Hast du dir verdient.

---

## Besser zusammen

Diese zwei Skills sind ein Paar — wie Einatmen und Ausatmen.

```
   /projekt-starten                   /projekt-review
   ┌──────────────┐                   ┌──────────────┐
   │ SAUBER       │                   │ SAUBER       │
   │ STARTEN      │ ──→ Arbeiten ──→ │ HALTEN       │
   │              │                   │              │
   │ Struktur     │                   │ Score        │
   │ Beschreibung │                   │ Fixen        │
   │ Protokoll    │                   │ Polieren     │
   │ CLAUDE.md    │                   │ Feiern       │
   └──────────────┘                   └──────────────┘
          ↑                                  │
          └──────── Weiterarbeiten ←─────────┘
```

**`/projekt-starten`** legt ein sauberes Fundament. **`/projekt-review`** hält es sauber, während das Projekt wächst. Ohne Review verwildert jedes Projekt zum Dschungel. Ohne guten Start gibt's nichts, was sich zu reviewen lohnt. Zusammen bilden sie einen Kreislauf, der Claude über Wochen und Monate produktiv hält.

Installier beide. Dein zukünftiges Ich wird es dir danken.

---

## Installation

```bash
# Skill-Marketplace hinzufügen
/plugin marketplace add ElevationGroupTECH/claude-business-skills

# Skills installieren
/plugin install projekt-starten     # Deutsch
/plugin install project-kickoff     # English

/plugin install projekt-review      # Deutsch
/plugin install project-review      # English
```

Dann einfach `/projekt-starten` oder `/projekt-review` in einer beliebigen Claude-Code-Session starten.

---

## Sprachen

Jeder Skill ist auf **Deutsch** und **Englisch** verfügbar:

| Deutsch | English | Beschreibung |
|---|---|---|
| `/projekt-starten` | `/project-kickoff` | Neues Projekt mit sauberer Struktur aufsetzen |
| `/projekt-review` | `/project-review` | Bestehendes Projekt bewerten und auf Hochglanz bringen |

---

## Für wen ist das?

- **Coaches & Berater** die Kundenprojekte, Kurs-Launches oder Events managen
- **Marketer** die Kampagnen, Content-Kalender und Website-Projekte jonglieren
- **Solo-Unternehmer** die Struktur brauchen, aber keinen Projektmanager haben
- **Alle Claude-Code-Nutzer** die wollen, dass ihre KI sich tatsächlich erinnert, worum es geht

Wenn du jemals eine Claude-Konversation neu geöffnet und 10 Minuten damit verbracht hast, dein Projekt nochmal zu erklären — diese Skills lösen das. Dauerhaft.

---

## Die Philosophie

> Claude ist nur so gut wie der Kontext, den du ihm gibst.

Ein gut strukturiertes Projekt mit einer ordentlichen CLAUDE.md, versionierten Dokumenten und einem aktuellen Protokoll ist kein "nice to have." Es ist der Unterschied zwischen Claude als hilfreichem Teammitglied und Claude als verwirrtem Praktikanten, der zum fünften Mal dieselbe Frage stellt.

Diese Skills kodieren hunderte Stunden echte Projekt-Erfahrung mit Claude in wiederholbare, Ein-Befehl-Workflows.

---

## Beispiele

**Vor `/projekt-starten`:**
```
mein-projekt/
├── notizen.txt
├── ideen.docx
├── entwurf.docx
├── entwurf_v2.docx
├── entwurf_FINAL.docx
└── zeug/
```

**Nach `/projekt-starten`:**
```
mein-projekt/
├── CLAUDE.md
├── 01-Projektbeschreibung-Kundenportal-V01.md
├── 02-Protokoll-Kundenportal.md
└── xold/
```

**Vor `/projekt-review`:** Score 3.2 / 10 😫
**Nach `/projekt-review`:** Score 9.1 / 10 🏆🏆🏆

---

## Ein ehrliches Wort

Diese Skills sind keine Magie. Sie retten kein Projekt ohne klares Ziel, und sie ersetzen nicht das Nachdenken darüber, was du eigentlich baust. Was sie tun: Sie nehmen dir die Reibung beim Aufsetzen und Pflegen des langweiligen-aber-wichtigen Projekt-Gerüsts ab — damit du dich auf die Arbeit konzentrieren kannst, die wirklich zählt.

Das sind die Skills, die wir täglich nutzen. Praxiserprobt, nicht perfekt. Und komplett kostenlos.

---

## Mitmachen

Bug gefunden? Idee für einen neuen Skill? PRs und Issues sind willkommen.

Dieses Repo ist darauf ausgelegt zu wachsen — weitere Business-Skills werden mit der Zeit hinzugefügt.

---

## Lizenz

Apache 2.0 — nutzen, anpassen, teilen.

---

## Über uns

Gebaut von **[Teile Deine Botschaft](https://www.teiledeinebotschaft.de)** (TDB) — wir helfen Coaches, Beratern und Solo-Unternehmern, ihr Online-Business aufzubauen, ohne Technik-Experte werden zu müssen.

Diese Skills sind aus dutzenden echten Projekten mit Claude Code entstanden. Sie sind die Grundlage, wie wir jeden Tag arbeiten.

**Willst du tiefer einsteigen?**
- [Unsere Website](https://www.teiledeinebotschaft.de) — Online-Business ohne Technik-Kopfschmerzen
- [Termin buchen](https://www.teiledeinebotschaft.de/termin) — Kostenloses Erstgespräch
- [Kundenstimmen](https://www.teiledeinebotschaft.de/kundenstimmen) — Echte Stimmen, echte Ergebnisse

---

*Powered by Teile Deine Botschaft • Elevation Group G.N.D LTD*
