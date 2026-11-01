# Exports

Dieses System bietet dir Unmengen an Exports die du in anderen Systemen einbauen kannst.&#x20;

#### Server

```lua
local v = exports.rdrp_mhs:GetVitals(source)
-- v.heartRate, v.systolic, v.diastolic, v.map, v.spo2 (nil = kein Signal), v.etco2, v.respRate,
-- v.temperature, v.gcs, v.pain, v.rhythm, v.rhythmLabel, v.status, v.bloodVolumePercent, v.bleeding,
-- v.bga = { ph, pco2, po2, sao2, hco3, be, lactate, hb, hct, na, k, cl, ca, anionGap, glucose, cohb, methb, fio2, horowitz },
-- v.labs = { troponin, pct, crp, leukocytes }

exports.rdrp_mhs:GetVital(source, 'heartRate')      -- auch BGA-/Laborschlüssel: 'ph', 'lactate', 'troponin'
exports.rdrp_mhs:GetBGA(source)
exports.rdrp_mhs:GetStatus(source)                   -- 'ok' | 'unconscious' | 'arrest' | 'dead'
exports.rdrp_mhs:IsDown(source) / IsDead(source)
exports.rdrp_mhs:GetProfile(source)
exports.rdrp_mhs:GetConditions(source) / HasCondition(source, id) / AddCondition(source, id, opts) / RemoveCondition(source, id)
exports.rdrp_mhs:GetInjuries(source) / AddInjury(source, id, part) / RemoveInjury(source, uid) / ApplyDamage(source, part, type, damage)
exports.rdrp_mhs:GiveMedication(source, medId, amount, route) / GetActiveMedications(source)
exports.rdrp_mhs:Revive(source, full) / Kill(source, cause) / CardiacArrest(source, rhythm)
exports.rdrp_mhs:ConsumeItem(source, itemName)       -- Ansteckung über Essen/Trinken
exports.rdrp_mhs:SetProfileValue(source, key, value) -- weight, fitness, bloodType, preconditions, allergies
exports.rdrp_mhs:GetRecords(source, limit)           -- Krankenakte
exports.rdrp_mhs:ReloadPlayer(source)                -- nach Charakterwechsel
```

#### Client

```lua
exports.rdrp_mhs:GetVitals()            -- eigene Kompaktwerte sofort (hr, sbp, dbp, map, spo2, etco2, rr, temp, gcs, rhythm, pain, ecg)
exports.rdrp_mhs:GetVitals(serverId)    -- eines anderen Spielers (Statebag)
exports.rdrp_mhs:GetFullVitals(serverId) -- inkl. BGA/Labor vom Server (im Thread; für andere nur Rettungsdienst)
exports.rdrp_mhs:GetStatus(serverId) / IsDown(serverId) / IsDead(serverId)
exports.rdrp_mhs:IsShockable(id) / Defibrillate(id) / GetPatientId(ped)   -- id: Spieler-ID oder Testpatient (negativ)
exports.rdrp_mhs:Eat(source, 7, 30)      -- Süße 7, Sättigung +30
exports.rdrp_mhs:Drink(source, 35, 0)    -- Flüssigkeit +35, ungesüßt
exports.rdrp_mhs:GetNutrition(source)    -- { nutrition, hydration, glucose, sugarLoad }
exports.rdrp_mhs:SetNutrition(source, 100, 100)
```

Statebag: `Player(serverId).state.mhs` → `{ s = status, v = {...}, fx = {...}, mv = {...}, ar = Restsekunden Stillstand }`.
