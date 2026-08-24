---
description: >-
  Hier zeigen wir dir, wie du ganz einfach unser rdrp_rueckwarnsystem auf deinem
  Server installieren kannst und so konfigurierst, dass deine Spieler ein neues
  Roleplay Erlebnis haben!
---

# Installation

#### Vorraussetzungen <a href="#vorraussetzungen" id="vorraussetzungen"></a>

Dein Server sollte folgende Inhalte bereits haben:

* Keine

***

### Anpassungen in&#x20;

1. config.lua

```lua
Config = {}

Config.Vehicles = {
    ['bsfrtw17'] = true,
    ['bsfrtw'] = true,
    ['bsfrtw24'] = true,
}
-- Füge hier die SPAWNNAMEN deiner Fahrzeuge ein wie zum Beispiel ['adder'] = true,
Config.Volume = 0.6
-- Volume, zu deutsch Lautstärke, wie laut soll der Sound sein? 0-1 (1Laut 0Leise)
Config.MaxDistance = 20.0
-- In welchem Umfeld soll der Sound hörbar bleiben?
```

Das war's. Mehr gibt es nicht zur Konfigurieren.&#x20;

Wenn du einen eigenen Sound einfügen möchtest, dann musst du "html/rueckwarner.ogg" ersetzen. Achte darrauf, die Datei muss zwingend "rueckwarner.ogg" heißen.
