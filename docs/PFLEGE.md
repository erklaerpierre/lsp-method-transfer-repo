# Skill pflegen und aktuell halten

Kurzfassung: **Das GitHub-Repository ist die einzige Quelle der Wahrheit.** Du änderst dort Markdown-Dateien. Ein Versions-Tag baut die ZIP-Datei automatisch. Google Drive und Claude bekommen danach die neue ZIP-Datei.

## 1. Wo ändere ich was?

| Ich will … | Datei in `lsp-method-transfer/` |
|---|---|
| Ablauf, Betriebsarten, Wording, Kennzeichnung ändern | `SKILL.md` |
| Aufbau jeder Adaption ändern | `references/adaptions-vorlage.md` |
| Regeln zur Passung oder Anpassung ergänzen | `references/kompatibilitaet.md` |
| Bauaufgaben-Muster, Warum-Umwandlungen ergänzen | `references/bauaufgaben.md` |
| Kernprozess, Etikette, Anwendungstechniken anpassen | `references/lsp-kernprozess.md` |
| Kombinationen mit anderen Methoden ergänzen | `references/methodenkombinationen.md` |
| Eine neue Methode im Katalog aufnehmen | `references/methodenkatalog.md` |
| Ein weiteres Beispiel als Zielzustand hinzufügen | neue Datei `references/beispiel-<name>.md`, in `SKILL.md` verlinken |
| Prüfregeln vor der Ausgabe ändern | `references/qualitaetscheck.md` |
| Begriffe Deutsch/Englisch pflegen | `references/glossar-de-en.md` |

Faustregel: `SKILL.md` bleibt kurz (Ablauf und Regeln). Wissen, Tabellen und Beispiele gehören in `references/`. Claude lädt Referenzen nur bei Bedarf.

## 2. Drei Wege, Änderungen zu machen

**A. Direkt auf GitHub (am einfachsten).** Datei öffnen → Stift-Symbol → ändern → „Commit changes“.

**B. Lokal oder mit Claude Code.** Repository klonen, Datei in einem Editor ändern oder Claude bitten („Ergänze im Skill ein Muster für …“). Danach `git commit` und `git push`.

**C. Aus der Praxis heraus.** Nach einem Workshop notierst du, was nicht gepasst hat. Dann ergänzt du:
- `[Zu testen]` → `[erprobt]` mit einem Satz Erfahrung (Gruppe, Dauer, Ergebnis)
- eine neue Stolperstelle in „Praxis-Tipps“ des Beispiels oder in `kompatibilitaet.md`
- die Methode im Katalog

## 3. Neue Version veröffentlichen

1. Änderung machen, `CHANGELOG.md` ergänzen (Datum, Stichpunkte).
2. Prüfen: Beispielaufruf im Chat testen und `references/qualitaetscheck.md` durchgehen.
3. Auf GitHub ein Release mit Tag anlegen (z. B. `v0.2.1`) oder per Terminal:
   ```
   git tag v0.2.1
   git push origin v0.2.1
   ```
4. Die GitHub-Action (`.github/workflows/release.yml`) prüft den Skill, baut `lsp-method-transfer.zip` und hängt sie an das Release.
5. ZIP herunterladen und verteilen:
   - **Google Drive:** Datei im Ordner → Rechtsklick → „Versionen verwalten“ → „Neue Version hochladen“. Der Freigabelink bleibt gleich.
   - **Claude (Web, Desktop):** alte Version im Skill-Bereich entfernen oder ersetzen, neue ZIP hochladen.
   - **Claude Code:** siehe Abschnitt 4.

Version hochzählen: Neue Inhalte → 0.x.0, Korrekturen → 0.x.y, grundlegende Umstellung → 1.0.0.

## 4. Claude Code: automatisch aktuell

Wenn du den Skill in Claude Code nutzt, klone das Repository direkt dorthin:

```
git clone https://github.com/<dein-konto>/lsp-method-transfer.git ~/lsp-method-transfer-repo
ln -s ~/lsp-method-transfer-repo/lsp-method-transfer ~/.claude/skills/lsp-method-transfer
```

Aktualisieren: `git -C ~/lsp-method-transfer-repo pull`. Änderungen an Dateien gelten sofort, ohne neues Hochladen.

## 5. Was Empfangende tun müssen

Skills in Claude (Web, Desktop) aktualisieren sich nicht von selbst. Empfangende laden die neue ZIP-Datei hoch. Sag in der Release-Notiz, was sich ändert. Wer in einer Team- oder Enterprise-Organisation ist, kann den Skill dort teilen lassen; Aktualisierungen laufen dann über die Organisation.

## 6. Qualität sichern

Vor jedem Release:
- 2 bis 3 echte Testläufe mit Methoden aus deiner Praxis (z. B. Pre-Mortem, Impact Mapping, eine Methode aus dem Katalog erneut)
- Ausgabe gegen `references/qualitaetscheck.md` prüfen
- Zeitplan nachrechnen (Phasensumme = Gesamtdauer)
- Warum-Fragen kontrollieren: umgewandelt und mit `[Umformuliert]` gekennzeichnet?

## 7. Rechtliches beim Erweitern

- Keine längeren Textpassagen aus Büchern oder Workbooks übernehmen. Paraphrasieren und die Quelle nennen.
- Neue Quellen in `references/quellen.md` eintragen.
- Marken und Lizenz bleiben im Repository: `LICENSE.md`, Markenhinweis im README.
