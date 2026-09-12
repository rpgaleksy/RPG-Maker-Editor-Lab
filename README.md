# RPG Maker Editor Lab

Forschung und Prototypen für einen RM2000-/RM2003-kompatiblen Editor auf
Apple Silicon. Noch kein Editor implementiert und keine Basis ausgewählt.
Eine native Lösung ist das langfristige Ziel; ein Windows-Editor über CrossOver
oder VM kann als Vergleich und vorläufiges Arbeitswerkzeug dienen.

## Einstieg

Zuerst [AGENTS.md](AGENTS.md), [VERSIONING.md](VERSIONING.md),
[Referenzen](docs/references.md) und [Untersuchungsplan](docs/investigation.md) lesen.
Der kompakte [Startprompt](docs/next-task-prompt.md) übergibt an eine neue Aufgabe.

## Workspace

- `../RPG-RT-Apple-Silicon/`: bestehende native EasyRPG-Runtime, nur Referenz
  und Testziel. Eigener Entwicklungsstand und eigenes Git-Repository.
- `../Editor Reference Material/RPG Maker 2003/`: vom Nutzer bereitgestellte
  Steam-Installation; bitte den vollständigen Installationsordner ablegen,
  einschließlich Unterordnern, nicht nur die Editor-EXE.
- `../Editor Reference Material/RPG Maker 2009 Ultimate/`: externe Originalpakete.
- `../Editor Reference Material/analysis/`: lokale Kopien, Ghidra-Projekte und
  aus Binärdateien erzeugte Analyseausgaben; außerhalb dieses Repositories.
- `../Add-ons and Patches/`: vorhandene Patch-Forschung, zunächst nur lesen.
- `../../archive/`: historische Referenzen, nur lesen.
- `../../games_archive/`: bestehende Spiele und RTP, unverändert extern belassen.

## Struktur

`docs/` enthält Quellen und Entscheidungen; `src/` spätere eigene Prototypen,
`tools/` eigene Analyse-/Buildwerkzeuge, `tests/` selbst erstellte Testfälle.
`build/`, `dist/`, `test-output/` sind ignorierte generierte Arbeitsverzeichnisse.
Quelloffene Abhängigkeiten später unter `build/upstream/` beziehen und pinnen.
Windows-Editoren, RTP und Spielressourcen gehören auch nicht in ignorierte Ordner.

Setup-Prüfung: Inhalte und Links prüfen, `git diff --cached --check`.
Es gibt derzeit keine Builds oder automatisierten Tests.
