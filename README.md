[![License][license-shield]](LICENSE)

UPDATE: Better use the Thermal Comfort sensor https://github.com/dolezsa/thermal_comfort.

# home-assistant-dewpoint
Home Assistant custom component to calculate dew point using temperature and humidity sensors.
Calculated using [psychrolib](https://github.com/psychrometrics/psychrolib).


## Installation

Use [hacs](https://hacs.xyz) with this repo URL https://github.com/fpauser/home-assistant-dewpoint or copy `custom_components/` to your HA configuration.

## Example configuration.yaml

```yaml
sensor:
  - platform: dewpoint
    sensors:
      dewpoint_outside:
        temperature: sensor.temperature_outside
        rel_hum: sensor.humidity_outside
      dewpoint_office:
        temperature: sensor.temperature_office
        rel_hum: sensor.humidity_office
      ...
```

## Configuration options

Key | Type | Required | Description
-- | -- | -- | --
`sensors` | `list` | `True` | List of dewpoint sensors to generate.

### Configuration options for `sensors` list

Key | Type | Required | Default | Description
-- | -- | -- | -- | --
`friendly_name` | `string` | `False` | `sensor name` | Custom name for the new sensor entity.
`temperature` | `entity_id` | `True` | `none` | Entity ID to read temperature from. (dry-bulb)
`rel_hum` | `entity_id` | `True` | `none` | Entity ID to read relative humidity from.
