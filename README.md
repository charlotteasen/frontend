Initial Frontend Boilerplate
============================

![WORK IN PROGRESS](https://i1.sndcdn.com/artworks-000072976459-djwz6g-t200x200.jpg)

## Inhalt

1. [Grunt Tasks](#grunttasks)
    1. [Task Übersicht](#grunttaskoverview)
2. [SASS Variablen](#sassvars)
3. [SASS Mixins](#sassmixins)
	1. [Media Query Shorthands](#mqshorthands)


## [Grunt Tasks](id:grunttasks)

### [Task Übersicht](id:grunttaskoverview)

| Parameter      | Task(s)               |
|----------------|-----------------------|
| `default`      | -> `build`
| `build`        | vollständiger Build-Job (`json_update`, `copy-deps`, `copy-css`, `copy-js`, `clean-temp`)
| `copy-deps`    | löscht existierende Abhängigkeiten, kopiert Abhängigkeiten neu aus *bower_components*
| `build-css`    | kompiliert SASS, fügt Vendor-Präfixe hinzu, kombiniert Media-Queries und konkateniert/minimiert CSS
| `build-js`     | konkateniert, linted und minimiert Javascripts
| `sync`         | startet BrowserSync und Watch
| `watch`        | startet Watch
| `update_json`  | aktualisiert Version und Name in _bower.json_ mit Daten aus _package.json_
| `clean-temp`   | löscht *assets-temp*


## SASS Variablen

### Media Query Breakpoints

| Variable     | Standardwert  | Beschreibung  |
|--------------|---------------|---------------|
| `$screen-xs` | 480px         | e<span style="color:#fe57a1">__X__</span>tra <span style="color:#fe57a1">__S__</span>mall screens / Smartphones
| `$screen-sm` | 768px         | <span style="color:#fe57a1">__SM__</span>all screens / Tablets
| `$screen-md` | 992px         | <span style="color:#fe57a1">__M__</span>e<span style="color:#fe57a1">__D__</span>ium screens / Desktops
| `$screen-lg` | 1200px        | <span style="color:#fe57a1">__L__</span>ar<span style="color:#fe57a1">__G__</span>e screens / Wide Desktops
| `$screen-xl` | 1600px        | e<span style="color:#fe57a1">__X__</span>tra <span style="color:#fe57a1">__L__</span>arge screens / Large Desktops

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

#### Beispiele

__SASS Input:__

    .first-box {
        width: 100px;
        @include mq-md-min {
            width: 150px;
        }
    }

    @include mq-lg {
        .second-box {
            width: 300px;
        }
    }

    @include mq-min( 1500px ) {
        .third-box {
            background: blue;
        }
    }


__CSS Output:__

    .first-box {
        width: 100px;
    }

    @media (min-width: 992px) {
        .first-box {
            width: 150px;
        }
    }

    @media (min-width: 1200px) and (max-width: 1599px) {
        .second-box {
            width: 300px;
        }
    }
    @media (min-width: 1500px) {
        .third-box {
            background: blue;
        }
    }

