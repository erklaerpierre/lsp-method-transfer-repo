# LSP Method Transfer – ein Claude-Skill

Überträgt bestehende Methoden (Brainstorming, SCAMPER, Retrospektive, Stakeholder-Mapping, Design Thinking, Liberating Structures u. a.) in **LEGO® SERIOUS PLAY®** (LSP) und beschreibt die Adaption als Leitfaden für Facilitatoren: mit Bauaufgaben, Zeitplan, Reflexionsfragen und ehrlicher Kennzeichnung.

> Inoffizielles Community-Werkzeug. LEGO® und SERIOUS PLAY® sind Marken der LEGO Gruppe. Der Skill ersetzt keine Facilitator-Zertifizierung.

*English summary at the end of this file.*

## Was der Skill kann

| Du schreibst … | Der Skill liefert … |
|---|---|
| „Transferiere SCAMPER in LEGO® SERIOUS PLAY®“ | Vollständige Adaption: Kompatibilitätsanalyse, Phasen mit Bauaufgaben im Wortlaut, Zeitplan, Doku, Varianten |
| „Plane einen LSP-Workshop zum Thema Zusammenarbeit im Team (4 Stunden)“ | Workshopdesign mit Anwendungstechniken, Zeitplan, Material |
| „Formuliere Bauaufgaben für eine Stakeholder-Landschaft“ | Offene Challenge Questions mit Bauzeit und Folgefragen |
| „Wie kombiniere ich LSP mit Liberating Structures?“ | Konkrete Andockpunkte und Reihenfolge |
| „Transfer this method to LSP“ (Englisch) | Dieselbe Struktur auf Englisch |

Was ihn besonders macht:

- **Einheitliche Vorlage** für alle Adaptionen (Phase 0 bis n, Zeitübersicht, Kennzeichnung).
- **Kompatibilitätsprüfung**: Jedes Element der Originalmethode wird als „kompatibel“, „anpassen“ oder „nicht kompatibel“ eingestuft, mit Begründung.
- **Ehrliche Einstufung** der Dauer: Vollformat, Kompaktformat oder LSP-inspiriert. Kein „offizielles LSP“-Etikett.
- **Kennzeichnung** von `[Original]`, `[LSP-Kern]`, `[Adaption]` und `[Zu testen]`.
- **Selbstcheck** vor der Ausgabe (Etikette, Zeitrechnung, Stil).
- **Zweisprachig**: Deutsch (Standard) und Englisch.

## Inhalt

```
lsp-method-transfer/
├── SKILL.md                      Anweisungen und Ablauf
└── references/
    ├── lsp-kernprozess.md        Kernprozess, Etikette, Skill Building, 7 Anwendungstechniken
    ├── kompatibilitaet.md        Passung und Elementzuordnung
    ├── bauaufgaben.md            Challenge Questions formulieren
    ├── adaptions-vorlage.md      Einheitliche Gliederung
    ├── methodenkombinationen.md  LSP + Design Thinking, Liberating Structures, Lean, Agile, OKR, Effectuation
    ├── methodenkatalog.md        23 bereits ausgearbeitete Methoden (Kurzprofil)
    ├── qualitaetscheck.md        Checkliste vor der Ausgabe
    ├── beispiel-brainstorming.md Beispiel 1 (Kompaktformat, 75 Min)
    ├── beispiel-retrospektive.md Beispiel 2 (Kompaktformat, 90 Min)
    ├── glossar-de-en.md          Begriffe Deutsch/Englisch
    └── quellen.md                Quellen, Lizenz, Marken
```

## Installation

**Voraussetzung:** ein Claude-Konto mit Skills-Unterstützung. Welche Pläne und Einstellungen nötig sind, steht in der Anthropic-Hilfe unter „Use skills in Claude“ (support.claude.com). Die Menüführung ändert sich gelegentlich.

### In Claude (Web, Desktop)
1. ZIP-Datei `lsp-method-transfer.zip` aus dem [Release](../../releases) laden (oder aus Google Drive).
2. In den Einstellungen den Bereich für Skills öffnen und die ZIP-Datei hochladen.
3. Skill aktivieren und im Chat testen: „Transferiere Brainstorming in LEGO® SERIOUS PLAY®“.

Hochgeladene Skills sind zunächst privat. Auf Team- und Enterprise-Plänen können Organisations-Owner das Teilen innerhalb der Organisation freischalten.

### In Claude Code
Ordner `lsp-method-transfer/` kopieren nach:
- persönlich: `~/.claude/skills/lsp-method-transfer/`
- im Projekt: `.claude/skills/lsp-method-transfer/`

### Aktualisieren
Neue ZIP-Version hochladen und die alte ersetzen. Bei Claude Code den Ordner überschreiben.

## Teilen

### Über GitHub
1. Neues Repository anlegen, z. B. `lsp-method-transfer`.
2. Diesen Ordner (README, LICENSE, `lsp-method-transfer/`) hineinkopieren und committen.
3. Unter **Releases** eine Version anlegen (z. B. `v0.1.0`) und `lsp-method-transfer.zip` als Datei anhängen. Die ZIP-Datei muss den Ordner `lsp-method-transfer/` auf oberster Ebene enthalten.
4. Link zum Release weitergeben.

### Über Google Drive
1. `lsp-method-transfer.zip` in einen Drive-Ordner legen.
2. Teilen: „Jeder mit dem Link“ (Betrachter genügt) oder gezielt per E-Mail.
3. Empfangende laden die ZIP-Datei herunter und installieren sie wie oben beschrieben. Nicht entpacken, wenn die Claude-Oberfläche eine ZIP-Datei verlangt.

### Hinweise zum Teilen
- Der Skill enthält **keine** Auszüge aus geschützten Büchern oder Workbooks. Prüfe vor jeder Erweiterung, dass das so bleibt.
- Lizenz und Marken: siehe unten.

## Beispielaufrufe

```
Transferiere die Methode „Pre-Mortem“ in LEGO® SERIOUS PLAY®. Gruppe: 8 Personen, 90 Minuten, LSP-erfahren.
```

```
Transferiere [Methodenbeschreibung einfügen] in LEGO® SERIOUS PLAY®. Gib nur die Kurzfassung (Methodenkarte).
```

```
Plane einen LEGO® SERIOUS PLAY® Workshop zum Thema „Zusammenarbeit zwischen Produkt und Entwicklung“, 1 Tag, 10 Personen.
```

```
Transfer the method “Impact Mapping” to LEGO® SERIOUS PLAY®. Write in English.
```

## Weiterentwickeln

Kurzfassung. Die ausführliche Anleitung steht in [docs/PFLEGE.md](docs/PFLEGE.md).

- Neue Methode erarbeitet? → als Eintrag in `references/methodenkatalog.md` aufnehmen.
- Neues Muster bewährt? → in `kompatibilitaet.md` oder `bauaufgaben.md` ergänzen.
- Erprobte Hypothese? → Kennzeichnung `[Zu testen]` in den Beispielen auf `[erprobt]` setzen und Erfahrung notieren.
- Immer nach `qualitaetscheck.md` prüfen.
- Änderung in `CHANGELOG.md` eintragen, Version hochzählen, Release mit neuer ZIP-Datei veröffentlichen.

## Lizenz und Marken

- **CC BY-SA 4.0** für den gesamten Inhalt (siehe `LICENSE.md`). Der Grund ist, dass `lsp-kernprozess.md` eine Bearbeitung des offenen LEGO®-Leitfadens (CC BY-SA 3.0) enthält. Keine Rechtsberatung.
- LEGO®, das LEGO Logo und SERIOUS PLAY® sind Marken der LEGO Gruppe. Dieses Projekt steht in keiner Verbindung zur LEGO Gruppe.
- Weitere Quellen: `lsp-method-transfer/references/quellen.md`.

---

## English summary

**LSP Method Transfer** is a Claude skill that adapts an existing method (brainstorming, SCAMPER, retrospectives, stakeholder mapping, design thinking, Liberating Structures, …) to **LEGO® SERIOUS PLAY®** (LSP) and writes it up as a facilitator guide: building challenges in full wording, timed phases, reflection questions, and honest labelling.

Highlights: one consistent template, a compatibility check per method element, honest format classification (full / compact / LSP-inspired), provenance tags (`[Original]`, `[LSP core]`, `[Adaptation]`, `[To test]`), and a quality checklist. Output language is German by default and English on request.

**Install:** upload `lsp-method-transfer.zip` in Claude’s skill settings, or copy the folder to `~/.claude/skills/` for Claude Code.
**Share:** attach the ZIP to a GitHub release or put it in a shared Google Drive folder.

*Unofficial community tool. LEGO® and SERIOUS PLAY® are trademarks of the LEGO Group. This project is not affiliated with, sponsored or endorsed by the LEGO Group. It does not replace facilitator certification.*
