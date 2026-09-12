Arbeite in `dev/RPG-Maker-Editor-Lab/` im RPG-Maker-Workspace.
Lies AGENTS.md, README.md, VERSIONING.md und docs/references.md sowie
 docs/investigation.md. Ziel ist eine RM2000-/RM2003-kompatible Arbeitsumgebung
für eigene Spiele auf Apple Silicon, langfristig ein nativer Editor.

Prüfe zuerst die vorhandenen quelloffenen Ansätze R48 und EasyRPG Editor:
Quellstand/Lizenz, ARM64-Build, Bedienbarkeit, Karten-, Datenbank- und
Ereignisbearbeitung sowie verlustfreies Speichern. Erstelle eigene minimale
Testprojekte und prüfe sie mit der bestehenden Runtime im Nachbarrepository
RPG-RT-Apple-Silicon; dessen Dateien unverändert lassen.

Der gekaufte Windows-RM2003 liegt, sobald bereitgestellt, außerhalb von Git unter
`dev/Editor Reference Material/RPG Maker 2003/`. Ultimate dient als Bedienreferenz;
prüfe auch, ob dessen Quellcode verfügbar ist. Gezielte statische Analyse mit
Ghidra ist als privates Experiment sinnvoll, wenn sie konkrete offene Fragen
klärt; keine komplette Decompilation als Voraussetzung. Fremdbinärdateien und
Analyseprojekte bleiben extern. Fehlendes Referenzmaterial blockiert andere Arbeit nicht.

Dokumentiere kurz verifizierte Ergebnisse und empfehle eine Basis samt nächstem
kleinen Prototyp, bevor du eine große Neuimplementierung beginnst. Arbeite
selbstständig und committe geprüfte Schritte; niemals automatisch pushen oder
Releases veröffentlichen.
