Initial Frontend Boilerplate
============================

![WORK IN PROGRESS](https://i1.sndcdn.com/artworks-000072976459-djwz6g-t200x200.jpg)

## Inhalt

1. [Grunt Tasks](#grunttasks)


## [Grunt Task Übersicht](id:grunttasks)

| Parameter      | Task(s)               |
|----------------|-----------------------|
| `default`      | -> `build`            |
| `build`        | vollständiger Build-Job (`copy-deps`, `copy-css`, `copy-js`)
| `copy-deps`    | kopiert Abhängigkeiten
| `build-css`    | kompiliert SASS, fügt Vendor-Präfixe hinzu und konkateniert/minimiert CSS
| `build-js`     | konkateniert/minimiert Javascripts
| `sync`         | startet BrowserSync und Watch
| `watch`        | startet Watch
| `update_json`  | aktualisiert Version und Name in _bower.json_ mit Daten aus _package.json_





