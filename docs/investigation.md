# Untersuchungsplan

## Ziel und Entscheidung

Eine angenehme Arbeitsumgebung für eigene RM2000-/RM2003-Spiele auf Apple Silicon.
Zuerst vorhandene freie Editoren bewerten, dann Portierung/Weiterentwicklung oder
gezielten Eigenbau empfehlen. Noch keine Festlegung auf Framework oder Fork.

1. R48 und EasyRPG Editor anhand gepinnter Quellen bauen/starten. Architektur,
   Abhängigkeiten, Lizenz, Entwicklungsstand und praktische Lücken festhalten.
2. Ein eigenes minimales Projekt erstellen: Karte/Tiles, Ereignis mit Bedingung,
   Dialog, Variablen, Transfer, Datenbankänderung, Kampf und Speichern/Laden.
   Im Editor erneut öffnen und in unserer Runtime ausführen. Inhaltserhaltung
   vor/nach Speichern prüfen, einschließlich Zeichencodierung und unbekannter Felder.
3. Wenn RM2003 bereitliegt, Version, PE-Metadaten, Imports, Ressourcenstruktur
   und SHA-256 inventarisieren. Originale unverändert lassen. CrossOver/VM nur
   als separaten Vergleich behandeln, nicht als native Portierung ausgeben.
4. Ultimate-Quellcode-Verfügbarkeit bei Originalquellen prüfen. Bedienfunktionen
   erfassen und priorisieren; Steam-Kompatibilität nicht voraussetzen.
5. Kurze Entscheidungsvorlage mit getesteten Ergebnissen und nächstem kleinen
   Prototyp vorlegen. Fehlende Windows-Dateien blockieren freie Editoren nicht.

## Optional: gezielte Binäranalyse

Ghidra kann unter macOS fremde CPU-Architekturen analysieren; eine Windows-x86-EXE
muss dafür nicht ausgeführt werden. Apple-Silicon-Einrichtung separat validieren.
Decompilation liefert angenäherten Pseudocode, keinen ursprünglichen, unmittelbar
als Mac-App kompilierbaren Quellcode. GUI-Framework, Imports und Laufzeitverhalten
bleiben zusätzliche Aufgaben.

Nur konkrete Fragen untersuchen, etwa die Kodierung eines Ereignisbefehls oder
Ressourcenfilters. Metadaten und kontrollierte Vorher/Nachher-Vergleiche eigener
Projekte zuerst nutzen. Ghidra-Projekte, Binärkopien und dekompilierte Ausgaben
unter `../Editor Reference Material/analysis/` speichern; im Git nur eigene
Analysewerkzeuge, Quellen/Hashes und sachliche Verhaltensbeschreibungen.
Das Setup führt noch keine Binäranalyse, Installation oder Decompilation aus.
