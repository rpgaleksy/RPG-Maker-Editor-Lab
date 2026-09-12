# Referenzen und vorläufige Bewertung

Stand: 2026-09-12. Quellen sind Einstiegspunkte, keine bereits geprüften Builds.
Vor einer Auswahl konkrete Revision, Build-Anforderungen und Lizenz erfassen.

| Gegenstand | Quelle | Relevanz und offene Prüfung |
| --- | --- | --- |
| R48 von 20kdc | https://github.com/20kdc/gabien-app-r48 | Quelloffener Java-Editor; README beschreibt Spieleentwicklung mit EasyRPG. ARM64-Java, native Bibliotheken, Bedienbarkeit und verlustfreies Speichern praktisch prüfen. |
| R48 Einführung | https://blog.easyrpg.org/2019/04/r48-an-alternative-editor-compatible-with-rpg-maker-2000-and-2003/ | EasyRPG-Einführung; alte Installationshinweise nicht ungeprüft übernehmen. |
| EasyRPG Editor | https://github.com/EasyRPG/Editor | Quelloffen, GPL-3.0; importiert RM2000/2003 über liblcf. Funktionsumfang und macOS-Build erst validieren. |
| Editor-Status | https://community.easyrpg.org/t/is-the-editor-still-work-in-progress/1635 | Entwickler bestätigt im April 2025 laufende Entwicklung; kein Nachweis vollständiger Einsatzreife. |
| liblcf | https://github.com/EasyRPG/liblcf | Kandidat für Lesen/Schreiben der LCF-Spieldaten; Roundtrip und unbekannte Felder separat untersuchen. |
| RPG Maker 2009 Ultimate | https://cherrytree.at/cms/projects/ultimate/ | Editor-Erweiterung durch Injektion, keine Spiel-Runtime. Letzte dort genannte Version 0.16.32 Beta, Entwicklung eingefroren. Referenz für Bedienkomfort. Öffentliche vollständige Quellcode-Verfügbarkeit bislang nicht nachgewiesen. |
| Ultimate-Changelog | https://cherrytree.at/cms/projects/ultimate/ultimate-changelog/ | Funktionsideen: Ereignisfarben, größere Ereignislisten, Werkzeuge, Ressourcen-Unterordner. |
| Ultimate + Steam | https://www.reddit.com/r/RPGMaker/comments/1n3mgz8 | Diskussion August 2025 mit Cherry zu Hängern und Build-Problemen. Kombination nicht als funktionierende Basis voraussetzen. |
| Offizieller RM2003 | https://store.steampowered.com/app/362870/RPG_Maker_2003/ | Windows-Editor; Nutzer besitzt Steam-Version und stellt Installation extern bereit. Genaue Version und SHA-256 lokal erfassen. |
| Maniacs | https://bingshan1024.github.io/steam2003_maniacs/ | Moderne Erweiterung für Steam-RM2003; Editorfunktionen und Runtime-Semantik getrennt prüfen. |
| EasyRPG Maniacs-Status | https://github.com/EasyRPG/Player/issues/1818 | Unvollständige Unterstützung; nicht jede zusätzliche Editorfunktion ist portabel. |
| Ghidra | https://github.com/NationalSecurityAgency/ghidra | Quelloffenes Analysewerkzeug mit macOS-Unterstützung; Disassembly, Decompilation, Skripting. Konkreten Release samt ARM64-Komponenten und JDK-Anforderungen vor Einrichtung prüfen. |

Keine Fremdpakete oder Quellcode-Kopien wurden mit dem Setup heruntergeladen.

## Vorhandene lokale Erkenntnisse

Runtime-README: `../RPG-RT-Apple-Silicon/README.md` relativ zum Repository-Root.
Dort dokumentierte Architektur, Patch-Kompatibilität und RTP-Validierung nutzen.
Der vorhandene Player ersetzt keinen Editor. Eigene Editor-Projekte früh gegen
unsere Runtime testen; EasyRPG-spezifisches UTF-8 nicht automatisch als mit dem
originalen Windows-Editor austauschbar betrachten.
