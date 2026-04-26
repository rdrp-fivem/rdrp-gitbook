---
description: >-
  Hier zeigen wir dir, wie du ganz einfach unser r1 auf deinem Server
  installieren kannst und so konfigurierst, dass deine Spieler ein neues
  Roleplay Erlebnis haben!
---

# Installation





#### Vorraussetzungen <a href="#vorraussetzungen" id="vorraussetzungen"></a>

Dein Server sollte folgende Inhalte bereits haben:

* visn\_are

***

#### Herunterladen <a href="#herunterladen" id="herunterladen"></a>

Die Dateien sollten für dich auf deinem Keymaster hinterlegt sein, lade dort die aktuellste Version herunter und lade Sie dann auf deinem Server. Achte darrauf, dass die Datei auf deinem Keymaster ein Bundle ist. Das Plugin sowie das System selbst sind darin enthalten.Sollte der Transfer auf deinen Keymaster nicht funktioniert haben, so melde dich mit deiner TebexID bei uns im Discord.

#### Anpassungen in "visn\_are" <a href="#anpassungen-in-visn_are" id="anpassungen-in-visn_are"></a>

1. actions.lua

```lua
        {
            name = "STARTSTOP_R1EKG",
            cooldown = 500,
            animation = _defaultAnimationData,
            hideOnSelf = false,
            exclusiveBodyParts = { "TORSO" },
            log = function(bodyPart, result)
                return TranslateText("LOG_STARTSTOP_R1EKG", TranslateText(bodyPart))
            end,
            condition = function(healthBuffer, bodyPart) return not healthBuffer.bodybag end,
            action = function(clientData, healthBuffer, bodyPart, callback)
                if not _isc3active then
                    TriggerEvent('toggler1EKG', clientData.source, TempAuthToken, bodyPart, true, healthBuffer)
                else
                    TriggerEvent('toggler1EKG', clientData.source, TempAuthToken, bodyPart, false, healthBuffer)
                end
                callback(true)
            end
        }
```

Füge in der `actions.lua` den Code aus dem Block hinzu, wichtig ist, dass der Code in der Spalte `[cpr] = {...}` hinzugefügt wird.

2. languages/de.json

```json
        "APPLY_START_R1EKG": "",
        "APPLY_STOP_R1EKG": "",
        "ACTION_START_R1EKG": "",
        "ACTION_STARTSTOP_R1EKG": "r1 wurde geöffnet",
        "LOG_STARTSTOP_R1EKG": "r1 wurde geöffnet",
        "STARTSTOP_R1EKG": "r1 öffnen",
        "STOP_R1EKG": "r1 ablegen",
        "SHOCK": "Kardioversion",
        "INJECT_SHOCK": "Kardioversion durchführen",
        "ACTION_INJECT_SHOCK": "Kardioversion wurde durchgeführt"
```



Füge den Code-Block inhalt an das untere Ende der `de.json` Datei. Achte hierbei auf korrekte "," Setzung, ein Fehlendes Komma kann zu massiven Fehlern führen.​



3. Einfügen des Plugins

​Fügt in `visn_are`, innerhalb des Ordners unsere `plugin_rdrp` - Ordner hinzu.

> All Set, damit habt ihr den Komplizierten Teil abgeschlossen!

​Fügt nur noch unser Script in einen Ordner ein und führt diesen beim Start eures Servers aus.

```
ensure rdrp_r3t​
```
