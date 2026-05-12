# Home Assistant Blueprints

Eine Sammlung von Home Assistant Blueprints für die Heimautomatisierung.

---

## ❄️ Klimaanlage – Anwesenheit & Saison

Steuert Klimageräte automatisch in Abhängigkeit von Anwesenheit,
Außentemperatur und Tageszeit. Im Winter heizen, im Sommer kühlen –
vollautomatisch und mit Hysterese gegen ständiges An-/Abschalten.

### Features

- 🌡️ Automatischer Wechsel zwischen Heiz- und Kühlmodus anhand Außentemperatur
- 🏠 Anwesenheitserkennung mit sparsamem Abwesenheits-Versatz
- 🌙 Separate Zieltemperaturen für Tag und Nacht
- ⏰ Frei konfigurierbare Nachtzeiten
- 💨 Fan-Only wenn Zieltemperatur bereits erreicht
- 🔁 Hysterese verhindert ständiges An-/Abschalten
- 🌡️ Eigener Innentemperatur-Sensor wählbar

### Import

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2Frehle65%2Fhomeassistant-blueprints%2Fblob%2Fmain%2Fblueprints%2Fautomation%2Fclimate_presence.yaml)

Oder manuell über **Einstellungen → Automatisierungen → Blueprints → Blueprint importieren** mit folgender URL:

```
https://github.com/rehle65/homeassistant-blueprints/blob/main/blueprints/automation/climate_presence.yaml
```

### Konfigurierbare Parameter

| Parameter | Beschreibung | Standard |
|---|---|---|
| Klimagerät | Home Assistant Entität des Midea-Geräts | – |
| Anwesenheitssensor | Person, binary_sensor oder input_boolean | – |
| Außentemperatur-Sensor | Bestimmt Heiz- vs. Kühlmodus | – |
| Innentemperatur-Sensor | Raumtemperatur für Hysterese-Logik | – |
| Sommer-Schwellwert | Ab dieser Außentemp. wird gekühlt | 20 °C |
| Zieltemperatur Kühlen Tag | Raumtemperatur tagsüber im Sommer | 24 °C |
| Zieltemperatur Kühlen Nacht | Raumtemperatur nachts im Sommer | 26 °C |
| Zieltemperatur Heizen Tag | Raumtemperatur tagsüber im Winter | 21 °C |
| Zieltemperatur Heizen Nacht | Raumtemperatur nachts im Winter | 18 °C |
| Abwesenheits-Versatz | Temperaturversatz + Eco-Modus bei Abwesenheit | 3 °C |
| Nachtbeginn | Start der Nacht-Zieltemperatur | 22:00 |
| Nachtende | Ende der Nacht-Zieltemperatur | 07:00 |
| Hysterese | Toleranzbereich gegen Short-Cycling | 0,5 °C |
| Minimale Laufzeit | Kompressorschutz, verhindert zu kurze Zyklen | 10 min |
