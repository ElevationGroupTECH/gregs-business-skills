---
name: text-wirkungsfilter
description: >
  Analysiert jeden Text auf emotionale WIRKUNG — Satz für Satz, mit 5-stufiger Farbskala. 
  Nutze diesen Skill wenn der User einen Text verbessern, verdichten, oder "auf den Punkt bringen" will.
  Auch nutzen bei: "Wirkungsfilter", "Text polieren", "Sätze bewerten", "was wirkt hier nicht",
  "zu lang", "langweilig", "den Text straffen", "emotionaler machen", "jeder Satz muss sitzen",
  "Filler raus", "Storytelling verbessern", "Skript optimieren", "Ad-Copy verbessern",
  "Newsletter kürzen", "Landing-Page-Text straffen". 
  Funktioniert mit jedem Text: Storytelling-Skripts, Sales Pages, Newsletter, Ads, Buchkapitel,
  Blogposts, Video-Skripts, Reden, Präsentationen.
---

# Wirkungsfilter

> Jeden Satz auf emotionale WIRKUNG bewerten. Schwaches eliminieren oder hochpolieren.
> Entwickelt bei TDB (Teile Deine Botschaft) — inspiriert von der Bindungsenergetik-Psychologie.

## Das Kernprinzip

Wirkung und Inhalt sind zwei verschiedene Dinge. Ein Satz kann inhaltlich perfekt sein und trotzdem null Wirkung haben. Ein anderer Satz sagt fast nichts — aber man fühlt ihn sofort.

**Im Zweifel: Wirkung > Inhalt.**

Das hier ist kein Lektorat. Kein Grammatik-Check. Kein "klingt das gut?". Der Wirkungsfilter stellt eine einzige Frage: **Erzeugt dieser Satz ein Gefühl?**

---

## Ablauf

Der Wirkungsfilter läuft KOMPLETT durch — keine Zwischenfragen, kein "soll ich?". Input rein → Output raus.

**Was rauskommt (in dieser Reihenfolge):**
1. HTML-Datei 1: Farbcodierte Analyse (zur Ansicht)
2. HTML-Datei 2: Polierte Version mit Markierungen (zur Ansicht)
3. **DER FERTIGE TEXT** — poliert, nur Stufe 4-5, copy-paste-ready (das ist das Hauptergebnis!)

### Schritt 1: Analyse

Gehe den Text **Satz für Satz** durch (bei langen Sätzen: Satzteil für Satzteil) und bewerte jeden auf der 5-Stufen-Skala:

| Stufe | CSS-Klasse | Farbe | Name | Was es bedeutet |
|-------|-----------|-------|------|-----------------|
| 5 | `w5` | Dunkelgrün (#14532d auf #dcfce7) | **Hammer** | Erzeugt sofort ein Gefühl. Man stoppt. Man fühlt es. |
| 4 | `w4` | Hellgrün (#365314 auf #ecfccb) | **Stark** | Trägt die Geschichte emotional. Gute Spannung. |
| 3 | `w3` | Orange (#78350f auf #fff7ed) | **Mittel** | Okay, aber austauschbar. Weder stark noch schwach. |
| 2 | `w2` | Rot (#9a3412 auf #fff1f2) | **Schwach** | Flach, generisch, erklärend. Keine Emotion. |
| 1 | `w1` | Durchgestrichen (#7f1d1d auf #fee2e2) | **Raus** | Füllsatz, Redundanz, Aufzählung ohne Gefühl. |

### Was macht einen Satz wirkungsstark?

Achte auf diese **Indikatoren für starke Wirkung** (Stufe 4-5):
- **Spezifität**: Uhrzeit, Ort, Wetter, sensorische Details ("Mittwochabend, Autobahn, Regen auf der Windschutzscheibe")
- **Rhythmus-Bruch**: Ein kurzer, punchiger Satz nach einer langen Passage
- **Show don't tell**: Konkrete Szene statt Erklärung
- **Kontrast & Überraschung**: Erwartung brechen
- **Verletzlichkeit**: Rohe Ehrlichkeit, die wehtut
- **Dreier-Gruppen**: "Nicht korrigieren. Nicht kontrollieren. Nicht überarbeiten."
- **Rhetorische Fragen**: "Aber wie willst du den bezahlen?"
- **Der Stopper**: Ein Satz bei dem man kurz innehalten MUSS

Und diese **Indikatoren für schwache Wirkung** (Stufe 1-2):
- Generische, abstrakte Aussagen ohne Bild
- Erklärende Füllsätze ("Das liegt daran, dass...")
- Aufzählungen ohne emotionale Aufladung
- Redundanz: Den gleichen Punkt nochmal anders sagen
- Relativierungen: "Und für generische Aufgaben passt das auch"
- Rationale Brücken: "Dann ging eine Tür auf. Ich verstand zum ersten Mal..."
- Zu viele abstrakte Nomen in einem Satz ("die Info, das Commitment, die Involviertheit")

### Schritt 2: HTML-Analyse ausgeben

Erstelle eine HTML-Datei mit farbcodierter Analyse. Nutze dieses Template:

```html
<!DOCTYPE html>
<html lang="de">
<head>
<meta charset="utf-8">
<title>Wirkungsfilter — [TITEL]</title>
<style>
  body { font-family: 'Inter', system-ui, sans-serif; max-width: 800px; margin: 40px auto; padding: 20px; background: #faf8f5; color: #3c3c3b; line-height: 1.8; font-size: 17px; }
  h1 { color: #91133B; font-size: 24px; }
  .subtitle { color: #888; font-size: 14px; margin-bottom: 30px; }
  .legend { display: flex; gap: 20px; margin-bottom: 30px; padding: 15px; background: white; border-radius: 12px; flex-wrap: wrap; border: 1px solid #eee; }
  .legend-item { display: flex; align-items: center; gap: 6px; font-size: 13px; }
  .dot { width: 14px; height: 14px; border-radius: 50%; flex-shrink: 0; }
  .w5 { color: #14532d; background: #dcfce7; padding: 1px 3px; border-radius: 3px; font-weight: 600; }
  .w4 { color: #365314; background: #ecfccb; padding: 1px 3px; border-radius: 3px; }
  .w3 { color: #78350f; background: #fff7ed; padding: 1px 3px; border-radius: 3px; }
  .w2 { color: #9a3412; background: #fff1f2; padding: 1px 3px; border-radius: 3px; }
  .w1 { color: #7f1d1d; background: #fee2e2; padding: 1px 3px; border-radius: 3px; text-decoration: line-through; }
  p { margin: 16px 0; }
  .note { font-size: 12px; color: #888; font-style: italic; margin-left: 6px; }
  .stats { background: white; padding: 20px; border-radius: 12px; margin-top: 40px; border: 1px solid #eee; }
  .stats table { width: 100%; border-collapse: collapse; }
  .stats td, .stats th { padding: 8px 12px; text-align: left; border-bottom: 1px solid #f0f0f0; font-size: 14px; }
  .bar { height: 16px; border-radius: 8px; display: inline-block; }
</style>
</head>
<body>
<h1>Wirkungsfilter — [TITEL]</h1>
<div class="subtitle">[UNTERTITEL]</div>
<!-- Legende und Sätze hier -->
<!-- Am Ende: Statistik-Tabelle mit Verteilung -->
</body>
</html>
```

Jeder Satz/Satzteil wird in `<span class="wN">` gewrapped. Bei schwachen Stellen eine `.note` mit kurzer Begründung hinzufügen (warum wirkt es nicht?).

Am Ende der HTML: Statistik-Tabelle mit Anzahl pro Stufe und Balkendiagramm.

### Schritt 3: Polieren (automatisch, KEIN Fragen!)

Direkt nach der Analyse — ohne Rückfrage — die polierte Version erstellen.

Erstelle eine zweite HTML-Datei mit drei Sektionen:
1. **Markierte Version**: Schwarz = behalten (4-5), Blau = neu geschrieben, Grau durchgestrichen = entfernt
2. **Vorher/Nachher-Tabelle**: Wörter, geschätzte Dauer, Stufe-1-2-Stellen
3. **Reiner Text**: Die polierte Version ohne Markierungen

### Polier-Regeln:
- Stufe 5: **NICHT ANFASSEN** — das ist Gold
- Stufe 4: Beibehalten
- Stufe 3: Nur behalten wenn nötig für Sinn/Kontext. Sonst: hochpolieren oder streichen
- Stufe 2: Streichen. Wenn der Sinn bricht → komplett neu schreiben auf Stufe 4-5
- Stufe 1: Sofort raus

Beim Hochpolieren: Nicht einfach umformulieren — den Satz so umbauen, dass er ein GEFÜHL erzeugt. Spezifischer machen, kürzer, überraschender, verletzlicher.

### Schritt 4: Fertigen Text liefern + abschließen

Das ist das HAUPTERGEBNIS. Den fertigen, polierten Text als reinen Text im Chat ausgeben — kein HTML, keine Markierungen, einfach der fertige Text zum Kopieren.

Dazu eine kurze Zusammenfassung:
- Wörter vorher → nachher (mit Prozent)
- Stellen gestrichen / neu geschrieben
- Die 3 stärksten Hammer-Sätze hervorheben

### Schritt 5: Am Ende nur EINE Frage

Nach dem fertigen Text:

> "Alles wirkungsoptimiert! Möchtest du die farbcodierte Wirkungsanalyse und die polierte Version sehen, ablegen oder löschen?"

Optionen:
- **Sehen:** HTML-Dateien im Browser öffnen
- **Ablegen:** HTML-Dateien im Projektordner speichern (unter `04-Assets/` oder ähnlich)
- **Löschen:** HTML-Dateien verwerfen — der fertige Text ist ja schon da

---

## Drei Einsatz-Modi

Der Wirkungsfilter wird unterschiedlich eingesetzt, je nachdem WER den Text geschrieben hat:

### Modus 1: Standalone (`/wirkungsfilter`)
Wenn der User explizit `/wirkungsfilter` aufruft oder einen bestehenden Text zur Optimierung gibt.
- Komplett durchziehen (Schritte 1-5)
- Am Ende die EINE Frage (sehen/ablegen/löschen)

### Modus 2: Automatisch (KI-generierte Texte)
Wenn Claude SELBST einen Text generiert hat — Newsletter, Ad-Copy, Social-Media-Posts, Sales-Page-Texte, E-Mail-Sequenzen, Funnel-Texte — dann den Wirkungsfilter AUTOMATISCH dranhängen. Kein Fragen, kein separater Aufruf nötig.
- Schritte 1-4 still im Hintergrund durchführen
- NUR den fertigen, wirkungsoptimierten Text ausgeben
- HTML-Dateien NICHT erstellen (spart Zeit)
- Kurze Notiz: "Wirkungsfilter angewendet: X Wörter → Y Wörter (-Z%)"

Gilt für alle Skills/Kontexte wo Claude Texte produziert:
- Newsletter schreiben
- Ad-Copy generieren
- Sales-Page-Texte
- E-Mail-Sequenzen
- Social-Media-Posts
- Funnel-Texte (Storytelling, Quiz, Diagnose)

### Modus 3: Buchkapitel (eigener Schritt)
Bei Büchern und langen Storytelling-Texten ist der Wirkungsfilter ein SEPARATER Schritt im Workflow — nicht automatisch.
- Erst den Text komplett schreiben lassen
- Dann explizit fragen: "Soll ich den Wirkungsfilter drüberlaufen lassen?"
- Bei "ja": Volle Analyse mit HTML-Dateien (Schritte 1-5)
- Feedback einholen: "Ist das gut? Besser? Was fehlt?"
- Iterieren bis es sitzt

Warum separat bei Büchern? Weil Buchkapitel länger sind, mehr Kontext haben, und der Autor (Gregor) die Wirkungs-Bewertung selbst reviewen will bevor gestrichen wird.

---

## Beispiele für Wirkung

**Stufe 5 (Hammer) — Sätze die STOPPEN:**
- "Das Einzige, worauf ich mich verlassen konnte, war ich."
- "Jetzt war ich Mädchen für alles."
- "Endlich keine Idioten mehr."
- "Werden sie nicht. Nicht so. Nicht allein."
- "Ich wusste nicht mal, wonach ich suchen sollte."
- "Es fühlte sich an, als wäre ich beschäftigt gehalten worden."

**Stufe 1 (Raus) — Sätze die NICHTS tun:**
- "Ich hatte mich schon überall effektiviert — Zeitmanagement-Kurse, Priorisierungs-Tools."
- "Vielleicht könnte man noch effizienter sein, vielleicht könnte man doch noch mehr arbeiten."
- "Und für wirklich generische Aufgaben, die man klar abwickeln kann, passt das auch."

---

## Dateien speichern (wenn gewünscht)

- Analyse: `[ordner]/wirkungs-analyse-[name].html`
- Polierte Version: `[ordner]/wirkungs-analyse-[name]-poliert.html`

Wenn kein Ordner angegeben: im aktuellen Projektordner unter `04-Assets/` oder dem nächstliegenden sinnvollen Ort.
