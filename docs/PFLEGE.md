# Skill pflegen und aktuell halten

Kurzfassung: **Das GitHub-Repository ist die einzige Quelle der Wahrheit.** Du änderst dort Markdown-Dateien. Ein Versions-Tag baut die ZIP-Datei automatisch. Claude Code holt sich Änderungen selbst (Plugin mit Auto-Update); Claude Web/Desktop und Google Drive bekommen die neue ZIP-Datei von Hand.

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

**B. Lokal oder mit Claude Code.** Repository klonen (`git clone https://github.com/erklaerpierre/lsp-method-transfer-repo.git`), Datei in einem Editor ändern oder Claude bitten („Ergänze im Skill ein Muster für …“). Danach `git commit` und `git push`.

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
5. Verteilung nach dem Release:
   - **Claude Code (Plugin):** nichts tun. Wer „Enable auto-update“ eingeschaltet hat, bekommt die Änderung beim nächsten Start; sonst `/plugin marketplace update lsp-tools`.
   - **Claude Web/Desktop:** ZIP aus dem Release laden, alte Version im Skill-Bereich entfernen, neue hochladen.
   - **Google Drive:** Datei im Ordner → Rechtsklick → „Versionen verwalten“ → „Neue Version hochladen“. Der Freigabelink bleibt gleich.

Version hochzählen: Neue Inhalte → 0.x.0, Korrekturen → 0.x.y, grundlegende Umstellung → 1.0.0. In `.claude-plugin/marketplace.json` steht bewusst **keine** `version`: Claude Code erkennt Änderungen dann an jedem neuen Commit. Würde dort eine Version stehen, kämen Updates nur nach Hochzählen an.

## 4. Selbst immer aktuell bleiben

| Werkzeug | Automatisch? | Einrichtung (einmalig) |
|---|---|---|
| Claude Code | **Ja** | `/plugin marketplace add erklaerpierre/lsp-method-transfer-repo`, `/plugin install lsp-method-transfer@lsp-tools`, dann in `/plugin` → Marketplaces → `lsp-tools` → „Enable auto-update“ |
| Claude Code, Entwicklung | Sofort | Klon des Repos als Marketplace-Verzeichnis hinzufügen: `/plugin marketplace add ~/lsp-method-transfer-repo`. Änderungen gelten nach Neustart oder `/reload-plugins`, ohne Version hochzuzählen |
| Claude Web/Desktop | **Nein** (nur manuell) | Neue ZIP hochladen. Für persönliche Uploads gibt es keine Aktualisierung aus GitHub |

Gut zu wissen:
- Claude Code übernimmt Skills aus deinem Claude-Konto (Anzeige „claude.ai sync“), nicht umgekehrt. Der Abgleich ist einseitig: Was du in Web/Desktop hochlädst, erscheint in Claude Code, aber Claude Code kann nichts nach Web/Desktop schreiben.
- Wenn du in Web/Desktop immer die aktuelle Version willst, ist der kürzeste Weg: nach jedem Release die ZIP hochladen (ca. eine Minute). In Claude Code brauchst du dann nur eines von beidem, Plugin oder Sync, nicht beides.
- Team/Enterprise: Ein Owner kann ein privates oder internes GitHub-Repository über Organisationseinstellungen → Plugins & Skills als Marketplace synchronisieren. Das gilt nur für Organisationen, nicht für einen persönlichen Account, und das Repository muss auf github.com privat sein.

## 5. Qualität sichern

Vor jedem Release:
- 2 bis 3 echte Testläufe mit Methoden aus deiner Praxis (z. B. Pre-Mortem, Impact Mapping, eine Methode aus dem Katalog erneut)
- Ausgabe gegen `references/qualitaetscheck.md` prüfen
- Zeitplan nachrechnen (Phasensumme = Gesamtdauer)
- Warum-Fragen kontrollieren: umgewandelt und mit `[Umformuliert]` gekennzeichnet?

## 6. Rechtliches beim Erweitern

- Keine längeren Textpassagen aus Büchern oder Workbooks übernehmen. Paraphrasieren und die Quelle nennen.
- Neue Quellen in `references/quellen.md` eintragen.
- Marken und Lizenz bleiben im Repository: `LICENSE.md`, Markenhinweis im README.
