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
.claude-plugin/marketplace.json  Marketplace-Eintrag für Claude Code
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

Es gibt zwei Wege, je nach Werkzeug. Beide nutzen dieselben Dateien.

### A. Claude im Web und in der Desktop-App

**Voraussetzung:** Einstellungen → Fähigkeiten (Capabilities) → „Code execution and file creation“ aktivieren. Auf Team/Enterprise schaltet der Owner „Skills“ unter Organisationseinstellungen → Plugins & Skills → Policy frei.

1. `lsp-method-transfer.zip` aus dem [neuesten Release](https://github.com/erklaerpierre/lsp-method-transfer-repo/releases/latest) laden (oder aus Google Drive). Nicht entpacken. Die ZIP-Datei enthält den Ordner `lsp-method-transfer/` auf oberster Ebene.
2. In Claude: **Customize → Skills → „+“ → „+ Create skill“ → „Upload a skill“**, ZIP-Datei wählen. (Bezeichnungen können in der deutschen Oberfläche abweichen und sich ändern.)
3. Skill in der Liste einschalten und testen: „Transferiere Brainstorming in LEGO® SERIOUS PLAY®“.

Hochgeladene Skills sind zunächst privat. Auf Team/Enterprise können sie über das Drei-Punkte-Menü des Skills mit Personen geteilt werden; Empfangende sehen den Skill ausgegraut, bis sie ihn aktivieren.

### B. Claude Code

**Empfohlen: als Plugin über das Repository (aktualisiert sich automatisch).**

```
/plugin marketplace add erklaerpierre/lsp-method-transfer-repo
/plugin install lsp-method-transfer@lsp-tools
```

Danach unter `/plugin` → **Marketplaces** → `lsp-tools` → **Enable auto-update** wählen. Der Skill heißt dann `/lsp-method-transfer:lsp-method-transfer`; Claude lädt ihn auch von selbst, wenn die Aufgabe passt.

**Alternative ohne Plugin:** Ordner `lsp-method-transfer/` kopieren nach `~/.claude/skills/lsp-method-transfer/` (persönlich) oder `.claude/skills/lsp-method-transfer/` (nur dieses Projekt). Dann Name ohne Präfix: `/lsp-method-transfer`.

**Wenn du in Claude Code mit demselben Konto angemeldet bist** und den Skill in Claude (Web/Desktop) hochgeladen hast, erscheint er dort automatisch unter „claude.ai sync“ (Claude Code ab v2.1.273, nicht bei Anmeldung per API-Schlüssel). Nutze nur einen der drei Wege, sonst hast du den Skill doppelt.

### Aktualisieren

| Wo | Wie |
|---|---|
| Claude Code (Plugin) | automatisch mit „Enable auto-update“; manuell: `/plugin marketplace update lsp-tools` |
| Claude Code (kopierter Ordner) | Ordner überschreiben oder `git pull` bei Symlink auf einen Klon |
| Claude Web/Desktop | neue ZIP-Datei hochladen (alte Version vorher entfernen). Kein Auto-Update aus GitHub |
| Claude Web/Desktop, geteilt (Team/Enterprise) | Original ändern; Empfangende bekommen die neue Version bei der nächsten Nutzung |

## Teilen

### Über GitHub
1. Repository: `erklaerpierre/lsp-method-transfer-repo` (öffentlich).
2. Ein Versions-Tag (z. B. `v0.2.1`) baut die ZIP-Datei automatisch und hängt sie an ein Release (GitHub Action).
3. Link zum Release weitergeben: https://github.com/erklaerpierre/lsp-method-transfer-repo/releases/latest
4. Claude-Code-Nutzende können das Repository direkt als Marketplace hinzufügen (siehe oben).

### Über Google Drive
1. `lsp-method-transfer.zip` in einen Drive-Ordner legen.
2. Teilen: „Jeder mit dem Link“ (Betrachter genügt) oder gezielt per E-Mail.
3. Empfangende laden die ZIP-Datei herunter und installieren sie wie unter „Installation A“ beschrieben. Nicht entpacken.

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

**Install:** Claude web/desktop: Customize → Skills → + → Create skill → Upload a skill (ZIP from the latest release). Claude Code: `/plugin marketplace add erklaerpierre/lsp-method-transfer-repo`, then `/plugin install lsp-method-transfer@lsp-tools` and enable auto-update.
**Share:** attach the ZIP to a GitHub release or put it in a shared Google Drive folder.

*Unofficial community tool. LEGO® and SERIOUS PLAY® are trademarks of the LEGO Group. This project is not affiliated with, sponsored or endorsed by the LEGO Group. It does not replace facilitator certification.*
