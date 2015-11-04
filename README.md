# Beets Genres

## TLDR;
1. Dieses Repo clonen
2. *genres.txt* bereinigen
3. evtl. genres-tree.yaml sinnvoll bearbeiten
4. Zurück auf GitHub pushen
5. Profit

#### Aktueller Status
Der Import neuer Musik wird von Beetwerk bzw. Beets erledigt.
Dabei wird neu importierte Musik nach Genre/Albumartist/Album sortiert.
Wie jeder weiß, der unsere Datenbank schonmal gesehen hat: *Es ist eine Katastrophe!*

#### Warum ist es so?
Die Zuordnung der Genres erledigt Beets über lastgenre. Ein Plugin, welches Genres für verschiedene Alben auf last.fm sucht. Leider ist da auch viel Mist mit dabei der dafür sorgt, dass unsere Datenbank inzwischen echt unübersichtlich geworden ist.

#### Ziel dieser Aktion
So wenig Genres wie möglich, so viele Genres wie nötig

#### Ich will helfen!
Gerne! In diesem Repo befinden sich 2 Dateien.
* genres.txt: Beinhaltet eine Whitelist der Genres, welche wir in unserer Datenbank haben möchten. Aktuell enthält sie **alle** Genres, welche es auf Wikipedia gibt (ca. **1526**)
* genres-tree.yaml: Stellt ein Mapping verschiedener Genres da. Ein kleines Beispiel: *"punk blues"* ist eine Unterkategorie von *"blues rock"* welches wiederum eine Unterkategorie des Genres *"blues"* ist.

#### Was muss gemacht werden?
Erstes Ziel: Die genres.txt auf die relevantesten Genres kürzen. Anschließend werden alle Unterkategorien welche nicht in dieser Whitelist enthalten sind auf die nächst höhere Kategorie "gemappt". Nehmen wir wieder Blues als Beispiel:

Ein Song mit dem Genre "blues rock" wird hochgeladen. Unsere genres.txt enthält jedoch nur "country blues" und "piano blues". Da "blues rock" ein Untergenre von "country blues" ist, wird das Genre des neu hochgeladenen Songs nun auf "country blues" geändert. So entsteht eine saubere Datenbank mit einer angenehmen Anzahl und sinnvollen Genres.
