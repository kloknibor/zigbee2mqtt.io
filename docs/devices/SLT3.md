---
title: "Hive SLT3 control via MQTT"
description: "Integrate your Hive SLT3 via Zigbee2MQTT with whatever smart home
 infrastructure you are using without the vendors bridge or gateway."
---

*To contribute to this page, edit the following
[file](https://github.com/Koenkk/zigbee2mqtt.io/blob/master/docs/devices/SLT3.md)*

# Hive SLT3

| Model | SLT3  |
| Vendor  | Hive  |
| Description | Heating thermostat remote control |
| Exposes | battery, linkquality |
| Picture | ![Hive SLT3](../images/devices/SLT3.jpg) |

## Notes

None


## Exposes

### Battery (numeric)
Remaining battery in %.
Value can be found in the published state on the `battery` property.
It's not possible to read (`/get`) or write (`/set`) this value.
The minimal value is `0` and the maximum value is `100`.
The unit of this value is `%`.

### Linkquality (numeric)
Link quality (signal strength).
Value can be found in the published state on the `linkquality` property.
It's not possible to read (`/get`) or write (`/set`) this value.
The minimal value is `0` and the maximum value is `255`.
The unit of this value is `lqi`.

