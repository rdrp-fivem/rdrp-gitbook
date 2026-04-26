---
description: >-
  Hier zeigen wir dir, wie du ganz einfach unser Airways System auf deinem
  Server installieren kannst und so konfigurierst, dass deine Spieler ein neues
  Roleplay Erlebnis haben!
---

# Installation

#### Vorraussetzungen <a href="#vorraussetzungen" id="vorraussetzungen"></a>

Dein Server sollte folgende Inhalte bereits haben:

* visn\_are
* [visn\_are:plugin\_airway](https://discord.com/channels/766006715535458324/1370478846238785627)

***

#### Anpassungen in "visn\_are" <a href="#anpassungen-in-visn_are" id="anpassungen-in-visn_are"></a>

1. actions.lua

```lua
["respiratory"] = {

    {
            name = "PLACE_ET_TUBE",
            cooldown = 5000,
            animation = _defaultAnimationData,
            requiredItem = { name = "et_tube", count = 1 },
            log = function(bodyPart, result)
                return TranslateText("LOG_ET_TUBE_APPLIED")
            end,
            condition = function(healthBuffer, bodyPart)
                return not healthBuffer.bodybag and not healthBuffer.airwayType
            end,
            action = function(clientData, healthBuffer, bodyPart, callback)
                --TriggerServerEvent("plugin_airway:applyAirway", clientData.targetId or clientData.source, "et_tube")
                
                TriggerEvent('rdrp:startintubate', clientData.targetId or clientData.source)
                
                callback(true)
            end
        },

}
```

Ändere in der `actions.lua` den Code aus dem Block,&#x20;

​Fügt nur noch unser Script in einen Ordner ein und führt diesen beim Start eures Servers aus.

```
ensure rdrp_airways
```

