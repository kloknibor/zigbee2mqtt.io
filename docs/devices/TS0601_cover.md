---
title: "TuYa TS0601_cover control via MQTT"
description: "Integrate your TuYa TS0601_cover via Zigbee2MQTT with whatever smart home
 infrastructure you are using without the vendors bridge or gateway."
---

*To contribute to this page, edit the following
[file](https://github.com/Koenkk/zigbee2mqtt.io/blob/master/docs/devices/TS0601_cover.md)*

# TuYa TS0601_cover

| Model | TS0601_cover  |
| Vendor  | TuYa  |
| Description | Curtain motor/roller blind motor/window pusher/tubular motor |
| Exposes | cover (state, position), options, linkquality |
| Picture | ![TuYa TS0601_cover](../images/devices/TS0601_cover.jpg) |
| White-label | Yushun YS-MT750, Zemismart ZM79E-DT, Binthen BCM100D, Binthen CV01A, Zemismart M515EGB, Tuya M515EGZT, TuYa DT82LEMA-1.2N, Moes AM43-0.45/40-ES-EB, Larkkey ZSTY-SM-1SRZG-EU, Zemismart ZM25TQ, Zemismart AM43, Zemismart M2805EGBZTN, Zemismart BCM500DS-TYZ, A-OK AM25 |

## Notes


### Configuration of device attributes
By publishing to `zigbee2mqtt/FRIENDLY_NAME/set` various device attributes can be configured:
```json
{
    "options":{
        "reverse_direction": xxx
    }
}
```

- **reverse_direction**: (`true`/`false`, default: `false`). Device can be configured to act in an opposite direction.

### Device type specific configuration
*[How to use device type specific configuration](../information/configuration.md)*

* `invert_cover`: By default the position/tilt values mean: open = 100, closed = 0. This can be inverted by setting this option to true (so open = 0, close = 100).



## Exposes

### Cover 
The current state of this cover is in the published state under the `state` property (value is `OPEN` or `CLOSE`).
To control this cover publish a message to topic `zigbee2mqtt/FRIENDLY_NAME/set` with payload `{"state": "OPEN"}`, `{"state": "CLOSE"}`, `{"state": "STOP"}`.
It's not possible to read (`/get`) this value.
To change the position publish a message to topic `zigbee2mqtt/FRIENDLY_NAME/set` with payload `{"position": VALUE}` where `VALUE` is a number between `0` and `100`.

### Options (composite)
Can be set by publishing to `zigbee2mqtt/FRIENDLY_NAME/set` with payload `{"options": {"motor_speed": VALUE}}`
- `motor_speed` (numeric): Motor speed. 

### Linkquality (numeric)
Link quality (signal strength).
Value can be found in the published state on the `linkquality` property.
It's not possible to read (`/get`) or write (`/set`) this value.
The minimal value is `0` and the maximum value is `255`.
The unit of this value is `lqi`.

