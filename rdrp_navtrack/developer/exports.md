# Exports

```lua
exports['rdrp_navtrack']:upsertDispatch(dispatchId, payload)

-- Fügt einen Einsatz hinzu und Speichert in gleichzeitig in der Cache. 
-- dispatchId = EMD Einsatznummer
-- payload = table
--[[
        einsatznummer = tostring(dispatchId),
        stichwort = 'RD 2 - internistische Notlage',
        alarmtext = 'Patient klagt über Brustschmerz und Dyspnoe. Verdacht ACS.',
        beteiligte = 'RTW, ggf. NEF',
        genauigkeit = 'Gebäude und Hausnummer bekannt',
        genauigkeitZielort = 'Schockraum / CPU',
        hinweis = 'Anfahrt über Hofeinfahrt, 2. Klingel links.',
        zielort = 'Pillbox Medical Center',
        einsatzort = 'Vespucci Blvd 14',
        patient = 'w, ca. 67 Jahre',
        anrufer = 'Ehemann',
]]--
-- Inhaltsbeispiele, wobei Einsatznummer IMMER die dispatchId bleiben muss
```

```lua
exports['rdrp_navtrack']:clearDispatch(dispatchId)

-- Löscht einen bestimmten Einsatz Fahrzeug unabhängig
```

```lua
exports['rdrp_navtrack']:assignDispatchToVehicle(vehicleRef, dispatchId, payload)

-- Fügt dem Fahrzeug mit der Funkrufnummer XY die Informationen des Einsatzes hinzu, 
-- vehicleRef = Funkrufnummer
-- dispatchId = EMD Einsatznummer
-- payload = Einsatzinformationen
```

```lua
exports['rdrp_navtrack']:clearVehicleDispatch(vehicleRef)

-- Löscht alle aktuellen Einsätze aus dem gewählten Fahrzeug (EMD-FahrzeugFunkrufname)
```

```lua
exports['rdrp_navtrack']:getVehicleState(vehicleRef)

-- Returns Vehicle State (1-9)
```

```lua
exports['rdrp_navtrack']:getDispatchPayload(dispatchId)

-- Returns Dispatch Payload in cb
--
```
