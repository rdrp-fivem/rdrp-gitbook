---
description: >-
  Hier zeige ich dir, wie du rdrp_mhs einfach installierst, was du benötigst und
  was du einstellen kannst!
---

# Installation

#### Vorraussetzungen <a href="#vorraussetzungen" id="vorraussetzungen"></a>

Dein Server sollte folgende Inhalte bereits haben:

* oxmysql
* ox\_lib
* ox\_inventory
* ox\_target



Zum Installieren von **rdrp\_mhs** benötigst du die items.lua (die findest du im "./install" Ordner. Diese fügst du ganz einfach in deine items.lua in der "ox\_inventory/data/items.lua" hinzu. **ACHTE** dabei auf Dopplungen, dadurch könnten Fehler entstehen. \
\
Danach benötigst du die import.sql, auch zu finden in dem Ordner "./install/". Diese lädst du in deine Server-Datenbank hoch, alles weitere erstellt das System von alleine.&#x20;

**Startreihenfolge**

```md
ensure oxmysql
ensure ox_lib
ensure ox_inventory
ensure ox_target

## Basis-Scripts ##
ensure rdrp_mhs
ensure rdrp_rd3t
ensure rdrp_oxymat
ensure rdrp_airways

## Props ##
ensure rdrp_rpcpr
ensure rd3t_prop
ensure rdrp_beatmomat
```
