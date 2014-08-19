Initial Frontend Boilerplate
============================

![WORK IN PROGRESS](https://i1.sndcdn.com/artworks-000072976459-djwz6g-t200x200.jpg)

## Inhalt

1. [Grunt Tasks](#grunttasks)
2. [SASS Variablen](#sassvars)
3. [SASS Mixins](#sassmixins)
	1. [Media Query Shorthands](#mqshorthands)


## [Grunt Task Übersicht](id:grunttasks)

| Parameter      | Task(s)               |
|----------------|-----------------------|
| `default`      | -> `build`
| `build`        | vollständiger Build-Job (`copy-deps`, `copy-css`, `copy-js`)
| `copy-deps`    | kopiert Abhängigkeiten
| `build-css`    | kompiliert SASS, fügt Vendor-Präfixe hinzu und konkateniert/minimiert CSS
| `build-js`     | konkateniert/minimiert Javascripts
| `sync`         | startet BrowserSync und Watch
| `watch`        | startet Watch
| `update_json`  | aktualisiert Version und Name in _bower.json_ mit Daten aus _package.json_


## SASS Variablen

### Media Query Breakpoints

| Variable     | Standardwert  | Beschreibung  |
|--------------|---------------|---------------|
| `$screen-xs` | 480px         | e<span style="color:#fe57a1">__x__</span>tra <span style="color:#fe57a1">__s__</span>mall screens / Smartphones
| `$screen-sm` | 768px         | <span style="color:#fe57a1">__sm__</span>all screens / Tablets
| `$screen-md` | 992px         | <span style="color:#fe57a1">__m__</span>e<span style="color:#fe57a1">__d__</span>ium screens / Desktops
| `$screen-lg` | 1200px        | <span style="color:#fe57a1">__l__</span>ar<span style="color:#fe57a1">__g__</span>e screens / Wide Desktops
| `$screen-xl` | 1600px        | e<span style="color:#fe57a1">__x__</span>tra <span style="color:#fe57a1">__l__</span>arge screen / Large Desktops

## SASS Mixins

### [Media Query Shorthands](id:mqshorthands)

| Mixin                      | adressiertes Medium |
|----------------------------|---------------------|
| `mq-min( $min )`           | mindestens `$min` breit
| `mq-min-max( $min, $max )` | zwischen `$min` und `$max` breit
| `mq-max( $max )`           | maximal `$max` breit
| `mq-xs`                    | nur XS
| `mq-sm-min`                | SM und größer
| `mq-sm`                    | nur SM
| `mq-sm-max`                | SM und kleiner
| `mq-md-min`                | MD und größer
| `mq-md`                    | nur MD
| `mq-md-max`                | MD und kleiner
| `mq-lg-min`                | LG und größer
| `mq-lg`                    | nur LG
| `mq-lg-max`                | LG und kleiner
| `mq-xl`                    | nur XL

(siehe auch *[SASS Variablen: Media Query Breakpoints](#mqbreakpoints)*)
