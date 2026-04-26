---
description: >-
  Hier zeigen wir dir, wie du ganz einfach unser r1 auf deinem Server
  installieren kannst und so konfigurierst, dass deine Spieler ein neues
  Roleplay Erlebnis haben!
---

# Installation

#### Vorraussetzungen <a href="#vorraussetzungen" id="vorraussetzungen"></a>

Dein Server sollte folgende Inhalte bereits haben:

* emergency\_dispatch

***

### Anpassungen in emergency\_dispatch

1. emergencydispatch/server/server\_custom.lua

```lua
function Vehicle_Alarm(VehID, VehValue, VehType, VehDepartment, VehDispatch)

	print("Alarmierung Fahrzeug: " ..VehValue, " | Type: " ..VehType, " | Department: " ..VehDepartment, " | Dispatch: " ..VehDispatch)

	exports['rdrp_navtrack']:assignDispatchToVehicle(VehValue, VehDispatch, {
		einsatznummer = VehDispatch,
		stichwort = 'Einsatz',
		alarmtext = 'Einsatz',
		einsatzort = 'Einsatz',
		zielort = 'Einsatz'
	})

end
```

Fügt im Bereich der Funktion `Vehicle_Alarm()` den im CodeBlock enthaltenen Inhalt hinzu.

Fügt nur noch unser Script in einen Ordner ein und führt diesen beim Start eures Servers aus.

```
ensure rdrp_navtrack
```
