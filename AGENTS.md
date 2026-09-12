# Arbeitsregeln

- Vor Beginn README.md, VERSIONING.md und Git-Zustand lesen.
- Aktive Entwicklung nur in diesem Repository. Runtime-Nachbarrepository,
  Archive, Patch-Archiv und Games Archive nur als Referenz lesen; keine Originale ändern.
- Externes Forschungsmaterial liegt in `../Editor Reference Material/`.
  Dort dürfen im beauftragten Rahmen Analyseausgaben und Arbeitskopien entstehen;
  bereitgestellte Originale erhalten. Fremde Windows-Programme nicht beiläufig ausführen.
- Keine proprietären Editorprogramme, DLLs, RTP, Spielressourcen oder extrahierten
  bzw. dekompilierten Fremdinhalte in dieses Repository übernehmen, auch nicht
  ignoriert. Hier eigene Werkzeuge, sachliche Erkenntnisse und Quellen dokumentieren.
- Quelloffene Abhängigkeiten dürfen unter build/upstream/ bezogen werden.
  Quelle, Commit/Version, Lizenz und Änderungen vor Integration dokumentieren.
- Eigene synthetische Testprojekte verwenden. Externe Spiele nur unverändert
  untersuchen; zusätzliche Spiele lädt der Nutzer. Keine Symlink-Umgehungen.
- Selbstständig in kleinen überprüfbaren Schritten arbeiten. Keine routinemäßigen
  Freigabeschleifen. Ergebnisse, Annahmen und offene Fragen klar unterscheiden.
- Originales Dateiformat, EasyRPG-Erweiterungen und Windows-Patches getrennt
  bewerten; keine volle Kompatibilität allein aus erfolgreichem Start ableiten.
- Relevante Tests/Builds ausführen und dokumentieren. Bei Dokumentationsänderungen
  genügen Inhaltsprüfung und Diff-Prüfung. Fremde Änderungen erhalten.
- Abgeschlossene Schritte selbstständig lokal committen, gezielt stagen.
  Vor JEDEM Commit `git status --short --branch`, den vollständigen
  `git diff --cached` einschließlich neuer Dateien sowie
  `git diff --cached --check` prüfen. Bei Änderung am Staging erneut prüfen.
  Anschließend Git-Zustand kontrollieren.
- Englische Conventional Commits: `type(scope): concise imperative summary`;
  Scope optional. Keine automatischen Pushes, Tags oder Release-Veröffentlichungen.
