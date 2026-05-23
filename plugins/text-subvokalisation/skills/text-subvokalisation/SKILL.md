---
name: text-subvokalisation
description: >
  Optimiert alle Nicht-Fließtext-Elemente für schnelle visuelle Erfassung: Buttons, Überschriften,
  Aufzählungen, Labels, Menüpunkte, Tabs, CTAs, Betreffzeilen, Bildunterschriften.
  Nutze diesen Skill wenn der User UI-Texte, Buttons, Menüs, Listen, Überschriften oder andere
  visuell angeordnete Texte schreibt oder optimiert. Auch nutzen bei: "Subvokalisationssperre",
  "Button-Text", "Überschrift kürzen", "Label optimieren", "zu lang für einen Button",
  "Aufzählung vereinheitlichen", "UI-Text", "CTA-Text", "Betreffzeile",
  "die Texte sehen ungleich aus", "passt nicht in eine Zeile".
  Wird AUTOMATISCH angewendet wenn Claude selbst UI-Elemente, Buttons, Listen oder
  Überschriften generiert — kein separater Aufruf nötig.
---

# Subvokalisationssperre

> Visuelle Texte (alles außer Fließtext) für schnelle Mustererkennung optimieren.
> Entwickelt bei TDB, validiert mit 26 Quiz-Fragen + allen Quiz-Funnel-Elementen.

## Warum das wichtig ist

Das Gehirn verarbeitet **grafisch angeordnete Texte** anders als Fließtext. Bei Fließtext liest der Mensch innerlich vor (Subvokalisierung) — langsam, aber tief. Bei visuellen Elementen wie Buttons und Überschriften greift eine schnelle **Mustererkennung**: Das Auge scannt die ersten 1-2 Wörter und "erkennt" den Inhalt.

Schlecht strukturierter Text in solchen Elementen **bricht die Mustererkennung** — das Gehirn fällt in den langsamen Subvokalisierungs-Modus zurück. Das fühlt sich "zäh" an und killt die Wirkung.

## Gilt für

Überschriften, Aufzählungen, Listen, Buttons, Bildunterschriften, Tabs, Menüpunkte, Labels, Slogans, Betreffzeilen, CTAs, Infografik-Texte — alles was NICHT Fließtext ist.

**Gilt NICHT für:** Fließtext in Absätzen, Kapiteln, E-Mail-Body (dort ist lineares Lesen eingestellt).

---

## Die 5 Regeln

### Regel 1: Einzeiligkeit ist King (70-80% Wichtigkeit)

Texte in Buttons, Aufzählungspunkten und Überschriften so kurz, dass sie in **eine Zeile** passen.

| Schlecht | Gut |
|---|---|
| Solo-Unternehmer/in | Solopreneur |
| Kleines Team (2-5 Personen) | Kleines Team |
| Ich arbeite viel, aber es läuft | Läuft — viel, aber im Griff |

### Regel 2: Kontrollierter Umbruch

Wenn eine Zeile nicht reicht: **bewussten** Zeilenumbruch setzen, nicht dem Layout überlassen.

- Bei zentriertem Text: Beide Zeilen etwa gleich lang, untere minimal länger (Pyramiden-Effekt)
- Dreizeilig nur in Ausnahmefällen

### Regel 3: Information-First (Keyword vorne)

Das **Schlüsselwort** kommt als ERSTES Wort. Einleitungen sind Information-Killer — das Auge scannt nur die ersten 1-2 Wörter.

| Schlecht | Gut | Warum |
|---|---|---|
| Wie würdest du dein Arbeitspensum beschreiben? | Dein Arbeitspensum? | "Wie würdest du" = null Info |
| Fühlt sich zäh an, obwohl es nicht viel ist | **Zäh** — obwohl nicht viel | "Zäh" sofort sichtbar |

**Fett-Formatierung** auf das Keyword verstärkt den Effekt. In einer Gruppe von 4 Antworten scannt das Auge dann nur: **Läuft / Zu viel / Am Limit / Zäh**.

### Regel 4: Zahlen als Zahlen (nicht als Wort)

Zahlen IMMER als Ziffer schreiben, NICHT ausgeschrieben. Das Auge erkennt Ziffern in <50 ms, Wörter brauchen Subvokalisierung.

| Schlecht | Gut |
|---|---|
| Drei Säulen der Zeitmaschine | 3 Säulen der Zeitmaschine |
| Zwei Stunden, zwei Themen | 2 Stunden · 2 Themen |
| Faustregel — 3× gleicher Prompt = ein Skill | Faustregel — 3x gleicher Prozess = 1 Skill |
| Sieben Sessions | 7 Sessions |

**Ausnahme:** Wenn die Zahl Teil eines feststehenden Begriffs ist und so im Sprachgebrauch zwingend gehört (z. B. „Eins-zu-Eins-Gespräch" als Eigenname). In Listen, Bullets, Headlines, Buttons aber **immer** Ziffer.

### Regel 5: Visuelle Gleichheit unter Geschwistern

Alle Elemente einer Gruppe haben die **gleiche Textstruktur**:
- Gleiche Zeilenanzahl
- Gleiches Formatierungsmuster (Keyword fett → Erklärung normal)
- **Horizontal > Vertikal**: Elemente nebeneinander MÜSSEN gleich sein

| Schlecht (ungleich) | Gut (gleich) |
|---|---|
| ✅ Läuft | ✅ **Läuft** — im Griff |
| ❌ Viel Arbeit, trotzdem komme ich nicht hinterher | ✅ **Zu viel** — nicht hinterher |
| ✅ Am Limit | ✅ **Am Limit** — mehr geht nicht |
| ❌ Fühlt sich zäh an, obwohl es nicht so viel ist | ✅ **Zäh** — obwohl nicht viel |

---

## Ablauf

### Als Standalone (`/subvokalisationssperre`):
1. User gibt Texte (Buttons, Liste, Überschriften etc.)
2. Alle 5 Regeln anwenden
3. Optimierte Version ausgeben mit Erklärung pro Änderung
4. Vorher/Nachher-Vergleich zeigen

### Automatisch (wenn Claude selbst generiert):
Immer wenn Claude UI-Elemente, Buttons, Listen, Quiz-Fragen, Tab-Labels, Menüpunkte, CTAs oder Überschriften generiert — automatisch alle 5 Regeln anwenden. Kein separater Aufruf, keine Rückfrage. Einfach direkt richtig machen.

Gilt besonders für:
- Quiz-Fragen und Antwort-Optionen
- Button-Texte und CTAs
- Navigations-Menüs
- E-Mail-Betreffzeilen
- Aufzählungen in Sales Pages
- Slide-Überschriften
- Dashboard-Labels

---

## Qualitäts-Check

- [ ] Passt jedes Element in eine Zeile?
- [ ] Steht das Keyword am Anfang?
- [ ] Sind alle Zahlen als Ziffern (nicht ausgeschrieben)?
- [ ] Sind alle Geschwister-Elemente visuell gleich?
- [ ] Keine unkontrollierten Umbrüche?

---

## 🔄 Selbstverbesserung — nach jedem Durchlauf

Dieser Skill verbessert sich selbst. **Nach jedem vollständigen Durchlauf** kurz innehalten und ehrlich reflektieren:

- **Was lief gut?** Was ging glatt und schnell — was unbedingt so behalten?
- **Was lief schlecht?** Wo bin ich hängengeblieben, was hat nicht geklappt, wo gab es Reibung, Fehler oder Unklarheit?
- **Warum?** Was war die Ursache — fehlende Info, unklarer Schritt, technisches Problem?
- **Wie beim nächsten Mal besser?** Was hätte ich gebraucht, um es schneller, sauberer und fehlerfrei zu machen?

**Dann handeln:**
- **Kleine, klare Verbesserungen** (Tippfehler, fehlender Hinweis, schärfere Formulierung, neuer Sonderfall) → sofort selbst in diesen Skill eintragen und unten im Änderungslog vermerken.
- **Größere Änderungen** (anderer Ablauf, neue Schritte, struktureller Umbau) → dem Nutzer vorschlagen und auf Freigabe warten, bevor sie eingebaut werden.

So wird der Skill mit jedem Einsatz schärfer. Lieber eine kleine Verbesserung zu viel als eine zu wenig.

### Änderungslog

| Datum | Was verbessert | Auslöser |
|-------|----------------|----------|
| 23.05.2026 | Neue Regel 4: Zahlen als Zahlen (nicht ausgeschrieben). Qualitätscheck ergänzt. | Folien Session 05: „zwei Stunden, zwei Themen" → „2 Stunden · 2 Themen". Feedback Gregor. |
