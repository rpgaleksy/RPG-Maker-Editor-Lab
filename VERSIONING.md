# Versionierung

- Forschung und Repository-Setup haben noch keine Produktversion.
- Mit dem ersten ausführbaren eigenen Prototyp VERSION als einzige Versionsquelle
  einführen: `0.1.0-dev`. Upstream-Versionen separat festhalten.
- 0.MINOR.0 bezeichnet einen Funktionsmeilenstein, 0.MINOR.PATCH eine Korrektur.
  Inkompatible Änderungen in 0.x erhöhen Minor und werden erläutert.
  Nicht für jeden Commit oder Prüfbuild eine Version erhöhen.
- Ab erstem Funktionsstand CHANGELOG.md mit Unreleased pflegen.
  Builds anhand Version, Git-Commit und uncommittierter Änderungen zuordnen.
- Lokale Versionspflege und Commits autonom; Tags und Veröffentlichungen nur
  ausdrücklich beauftragt. Keine automatischen Pushes oder Releases.
- 1.0 erst nach ausdrücklich vereinbartem stabilen Funktionsumfang.
