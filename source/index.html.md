---
title: API Reference

language_tabs:
  - javascript

toc_footers:
  - <a href='http://vivopoint.com' target="_blank">Visit VivoPoint</a>

includes:
  - errors

search: true
---



# Introduction

VivoPoint API documentation on how controllers should structure their API
endpoints to allow data retrival from the VivoPoint system.

Right now the VivoPoint system uses Ruby to ingest data but the controller
API itself should communicate via JSON. To this end, both only JavaScript
examples (in the dark area to the right) have been provided.


# Data Points

Below is a list of data points available on the controllers today. Not all of
these data points will be gettable or settable via the API. There may be some
number of data points that are available initially and we can then iterate on
additional priorities over time.


## Conductivity

### Diagnostic

Parameter | Example Value | DCM2 | DCM5
--------- | ------------- | ---- | ----
status | alarmed, operational | ? | X
sensor_type | Conductivity | ? | X
--------- | ------------- | ---- | ----
period_maximum | 70 uS | ? | X
period_minimum | 68 uS | ? | X
period_average | 69 uS | ? | X
--------- | ------------- | ---- | ----
sample_size | 1751 | ? | X
current_period | 47 minutes | ? | X
log_period | 60 minutes | ? | X
--------- | ------------- | ---- | ----
compensation | none | ? | X
--------- | ------------- | ---- | ----
measured_level | 8.1 mV | ? | X
gain_multiply | 12.2000 | ? | X
default_gain | 12.2000 | ? | X
offset_adjust | -30.0000 | ? | X
default_offset | -30.0000 | ? | X
--------- | ------------- | ---- | ----
input_card_id | 74 mV | ? | X

### Calibrate

Parameter | Example Value | DCM2 | DCM5
--------- | ------------- | ---- | ----
value | 69 uS | ? | X
factory_reset | boolean | ? | X

### Alarms

Parameter | Example Value | DCM2 | DCM5
--------- | ------------- | ---- | ----
status | alarmed | ? | X
high_alarm | 10000 uS | ? | X
low_alarm | 0 uS | ? | X
alarm_relay | boolean | ? | X
delay_on_alarm | 5.0 minutes | ? | X
clear_alarms | boolean | ? | X
last_alarm | Alarmed High 23:56 28/09/16 | ? | X

### Configure

Parameter | Example Value | DCM2 | DCM5
--------- | ------------- | ---- | ----
description | A_Conductivity | ? | X
gain_multiply | 12.2000 | ? | X
offset_adjust | -30.0000 uS | ? | X
display_units | uS | ? | X
decimal_digits | 0, 1, 2 | ? | X
compensation | none, thermal comp| ? | X
disable_input | boolean | ? | X



## pH

### Diagnostic

Parameter | Example Value | DCM2 | DCM5
--------- | ------------- | ---- | ----
status | alarmed | X | ?
sensor_type | pH Sensor | X | X
period_maximum | 8.35 pH | X | X
period_minimum | 7.28 pH | X | X
period_average | 8.21 pH | X | X
period | 757 minutes | X | -
sample_size | 1751 | - | X
current_period | 47 minutes | - | X
log_period | 60 minutes | - | X
compensation | none | X | X
measured_level | -58.2 mV | X | X
gain_multiply | -0.0170 | X | X
default_gain | -0.0170 | X | X
offset_adjust | 7.0299 | X | X
default_offset | 7.0000 | X | X
input_card_id | 1444 mV | - | X

### Calibrate

Parameter | Example Value | DCM2 | DCM5
--------- | ------------- | ---- | ----
value | 8.02 pH | X | X
factory_reset | boolean | X | X
one_point_calibration | boolean | X | X

### Alarms

Parameter | Example Value | DCM2 | DCM5
--------- | ------------- | ---- | ----
status | alarmed | X | X
high_alarm | 7.90 pH | X | X
low_alarm | 7.00 pH | X | X
alarm_relay | boolean | X | X
delay_on_alarm | 5.0 minutes | X | X
clear_alarms | boolean | X | X
last_alarm | Alarmed High 23:56 28/09/16 | X

### Configure

Parameter | Example Value | DCM2 | DCM5
--------- | ------------- | ---- | ----
description | pH Sensor | X | X
gain_multiply | -0.0170 | X | X
offset_adjust | 7.0299 pH | X | X
display_units | pH | X | X
decimal_digits | 2 | X | X
compensation | none, thermal comp| X | X
disable_input | boolean | - | X

## Chlorine

### Diagnostic

Parameter | Example Value | DCM2 | DCM5
--------- | ------------- | ---- | ----
status | alarmed, operational | X | X
sensor_type | chlorine, oxidant? | X | X
period_maximum | 0.63 ppm | X | X
period_minimum | 0.17 ppm | X | X
period_average | 0.30 ppm | X | X
period | 764 minutes | X | -
--------- | ------------- | ---- | ----
sample_size | 1873 | - | X
current_period | 51 minutes | - | X
log_period | 60 minutes | - | X
--------- | ------------- | ---- | ----
compensation | Oxidant | - | X
--------- | ------------- | ---- | ----
measured_level | 2.3 ppm | - | X
gain_multiply | 1.0000 | - | X
default_gain | 1.0000 | - | X
offset_adjust | 0.9378 | - | X
default_offset | 0.0000 | - | X
--------- | ------------- | ---- | ----
sensor_type | CLB3 | X | -
temperature | Input C Auto | X | -
calibrate | Warning LOW | X | -
status | 40003F22 | X | -
product_code | 236081527 | X | -
driver_serial_number | 15082008 | X | -
clb_hardware_version | 243 | X | -
clb_firmware_vrsion | 1.3.0.2 | X | -

### Calibrate

Parameter | Example Value | DCM2 | DCM5
--------- | ------------- | ---- | ----
dpd_sample | boolean | X | -
value | 3.52 ppm | - | X
factory_reset | boolean | - | X

### Alarms

Parameter | Example Value | DCM2 | DCM5
--------- | ------------- | ---- | ----
status: alarmed | X | X
high_alarm | 16.0 ppm | X | X
low_alarm | 0.10 ppm | X | X
alarm_relay | boolean | X | X
delay_on_alarm | 5.0 minutes | X | X
clear_alarms: boolean | X | X
last_alarm | Alarmed Low 23:56 28/09/16 | X

### Configure

Parameter | Example Value | DCM2 | DCM5
--------- | ------------- | ---- | ----
description | Chlorine | X | ?
--------- | ------------- | ---- | ----
display_units | ppm | X | X
decimal_digits | 0, 1, 2 | X | X
--------- | ------------- | ---- | ----
gain_multiply | 1.0000 | - | X
offset_adjust | 0.9378 ppm | - | X
compensation | none, oxidant, rate to vol, combined cl | - | X
--------- | ------------- | ---- | ----
sensor_type | CLB2, CLB3 | X | -
sensor_type | CLE3, CLO, CBR, CGE, CTE, BRE | - | X
--------- | ------------- | ---- | ----
disable_input | boolean | - | X


## ORP

### Diagnostic

Parameter | Example Value | DCM2 | DCM5
--------- | ------------- | ---- | ----
status | Operational | ? | X
sensor_type | ORP Sensor | ? | X
period_maximum | 899 mV | ? | X
period_minimum | 898 mV | ? | X
period_average | 899 mV | ? | X
sample_size | 113 | ? | X
current_period | 4 minutes | ? | X
log_period | 60 minutes | ? | X
compensation | none | ? | X
measured_level | -823.9 mV | ? | X
gain_multiply | -1.0000 | ? | X
default_gain | -1.0000 | ? | X
offset_adjust | 75.0000 | ? | X
default_offset | 0.0000 | ? | X
input_card_id | 1444 mV | ? | X

### Calibrate

Parameter | Example Value | DCM2 | DCM5
--------- | ------------- | ---- | ----
value | 900 mV | ? | X
factory_reset | boolean | ? | X

### Alarms

Parameter | Example Value | DCM2 | DCM5
--------- | ------------- | ---- | ----
high_alarm | 990 mV | ? | X
low_alarm | 400 mV | ? | X
alarm_relay | boolean | ? | X
delay_on_alarm | 5.0 minutes | ? | X

### Configure

Parameter | Example Value | DCM2 | DCM5
--------- | ------------- | ---- | ----
description | ORP Sensor | ? | X
gain_multiply | -1.0000 | ? | ?
offset_adjust | 75.0000 mV | ? | X
display_units | mV | ? | X
decimal_digits | 0, 1, 2, 3 | ? | X


## Temperature

### Diagnostic

Parameter | Example Value | DCM2 | DCM5
--------- | ------------- | ---- | ----
status | Operational | - | X
sensor_type | Temperature | X | X
--------- | ------------- | ---- | ----
period_maximum | 79.1 F | X | X
period_minimum | 78.8 F | X | X
period_average | 79.0 F | X | X
--------- | ------------- | ---- | ----
sample_size | 277 | - | X
current_period | 8 minutes | - | X
log_period | 60 minutes | - | X
period | 60 minutes | X | -
--------- | ------------- | ---- | ----
compensation | none | X | X
measured_level | 2995.0 mV | X | X
gain_multiply | 0.1800 | X | X
default_gain | 0.1000 | X | X
offset_adjust | -459.9603 | X | X
default_offset | -273.0000 | X | X
--------- | ------------- | ---- | ----
input_card_id | 2979 mV |  | X


### Calibrate

Parameter | Example Value | DCM2 | DCM5
--------- | ------------- | ---- | ----
value | 88.4 | X | X
factory_reset | boolean | X | X

### Alarms

Parameter | Example Value | DCM2 | DCM5
--------- | ------------- | ---- | ----
high_alarm | 95.0 | X | X
low_alarm | 60.0 | X | X
alarm_relay | boolean | X | X
delay_on_alarm | 5.0 minutes | X | X

### Configure

Parameter | Example Value | DCM2 | DCM5
--------- | ------------- | ---- | ----
description | Temperature | X | X
gain_multiply | 0.2000 | X | X
offset_adjust | -66.8472 F | X | X
display_units | F | X | X
decimal_digits | 1 | X | X
disable_input | boolean | - | X


## Flow

### Diagnostic

Parameter | Example Value | DCM2 | DCM5
--------- | ------------- | ---- | ----
status | Closed | X | X
digital_type | contact set | X | X
--------- | ------------- | ---- | ----
on_time | 2.0 minutes | X | X
current_period | 20 minutes | - | X
log_period | 60 minutes | - | X
period | 772 minutes | X | -
--------- | ------------- | ---- | ----
compensation | none | - | X

### Calibrate

Parameter | Example Value | DCM2 | DCM5
--------- | ------------- | ---- | ----
- | - | - | -

Calibration doesn't exist for the flow switch / contact set.

### Alarms

Parameter | Example Value | DCM2 | DCM5
--------- | ------------- | ---- | ----
on_time_alarm | 1500.0 minutes | X | X
no_flow_alarm | 1500.0 minutes | X | X
alarm_relay | boolean | X | X

### Configure

Parameter | Example Value | DCM2 | DCM5
--------- | ------------- | ---- | ----
digital_type | contact set, volume meter | X | X
description | Flowswitch | X | X
invert_sense | boolean | X | X
compensation | none, mirror output, rate swich | - | X
disable_input | boolean | - | X

## Recirculation Pump

### Diagnostic

Parameter | Example Value | DCM2 | DCM5
--------- | ------------- | ---- | ----
status | Open, Closed | X | ?
digital_type | contact set | X | ?
on_time | 2.0 minutes | X | ?
period | 772 minutes | X| ?

### Calibrate

Parameter | Example Value | DCM2 | DCM5
--------- | ------------- | ---- | ----
- | - | - | -

Calibration doesn't exist for the recirculation pump / contact set.

### Alarms

Parameter | Example Value | DCM2 | DCM5
--------- | ------------- | ---- | ----
on_time_alarm | 1500.0 minutes | X | ?
no_flow_alarm | 1500.0 minutes | X | ?
alarm_relay | boolean | X | ?

### Configure

Parameter | Example Value | DCM2 | DCM5
--------- | ------------- | ---- | ----
digital_type | contact set, volume meter | X | ?
description | Re-circ Pump | X | ?
invert_sense | boolean | X | ?
disable_input | boolean | X | ?


## Acid Pump

### Diagnostic

Parameter | Example Value | DCM2 | DCM5
--------- | ------------- | ---- | ----
status | Feed Limited, Off | X | X
mode | auto, manual, off | X | X
control_by | A (8.02 pH) | X | X
on_setpoint | 7.55 pH | X | X
off_setpoint | 7.50 pH | X | X
control_type | Feed Acid | X | X
on_today | 0.0 on, actuation | X | X

### Alarms

Parameter | Example Value | DCM2 | DCM5
--------- | ------------- | ---- | ----
status | alarmed | X | X
minutes_actuation | 240.0 minutes | X | X
minutes_manual | 10.0 minutes | X | X
off_on_alarm | boolean | X | X
alarm_relay | boolean | X | X
reset_alarm | boolean | X | X
on_timer | 22:33 10/08/16 | X | X

### Configure

Parameter | Example Value | DCM2 | DCM5
--------- | ------------- | ---- | ----
control_by | A | X | X
on_setpoint | 7.55 pH | X | X
off_setpoint | 7.55 pH | ? | X
deadband | 0.05 pH | X | ?
interlocked | E, F, multiple, none | X | X
blocked_by | 2, 4, multiple, none | X | X
control_type | feed acid, feed caustic, between sets | X | X
special_control | none, pid control, time modulate | X | X
period | 60 seconds | ? | X

### Setup

Parameter | Example Value | DCM2 | DCM5
--------- | ------------- | ---- | ----
description | Acid Pump | X | ?
disable_output | boolean | X | ?


## Chlorine Pump

### Diagnostic

Parameter | Example Value | DCM2 | DCM5
--------- | ------------- | ---- | ----
status | Feed Limited, Off | X | ?
mode | auto, manual, off | X | ?
control_by | B (0.17 ppm) | X | ?
on_setpoint | 3.00 ppm | X | ?
off_setpoint | 3.20 ppm | X | ?
control_type | Feed Oxidant | X | ?
on_today | 0.0 on, actuation | X | ?

### Alarms

Parameter | Example Value | DCM2 | DCM5
--------- | ------------- | ---- | ----
status | alarmed | X | X
minutes_actuation | 240.0 minutes | X | X
minutes_manual | 10.0 minutes | X | X
off_on_alarm | boolean | X | X
alarm_relay | boolean | X | X
reset_alarm | boolean | X | X
on_timer | 22:33 10/08/16 | X | X

### Configure

Parameter | Example Value | DCM2 | DCM5
--------- | ------------- | ---- | ----
control_by | B | X | X
on_setpoint | 3.00 ppm | X | X
off_setpoint | 3.00 ppm | ? | X
deadband | 0.20 ppm | X | ?
interlocked | E, F, multiple, none | X | X
blocked_by | 1, 4, multiple, none | X | X
control_type | feed dechlor, feed oxidant, between sets | X | X
special_control | none, pid control, time modulate | X | X

### Setup

Parameter | Example Value | DCM2 | DCM5
--------- | ------------- | ---- | ----
description | Chlorine Pump | X | X
control_assist | D (ORP), None | - | X
event_controls | boolean | X | X
lockout_mode | high & low pH, high pH, low pH, none | X | -
ph_lockout | C (pH), none | - | X
disable_output | boolean | X | X


## Chlorine Generator

### Diagnostic

Parameter | Example Value | DCM2 | DCM5
--------- | ------------- | ---- | ----
status | Feed Limited, Off | X | ?
mode | auto, manual, off | X | ?
control_by | B (0.17 ppm) | X | ?
on_setpoint | 3.00 ppm | X | ?
off_setpoint | 3.40 ppm | X | ?
control_type | Feed Oxidant | X | ?
on_today | 0.0 on, actuation | X | ?
simple_on_off | Off | X | ?

### Alarms

Parameter | Example Value | DCM2 | DCM5
--------- | ------------- | ---- | ----
status | alarmed | X | ?
minutes_actuation | 900.0 minutes | X | ?
minutes_manual | 10.0 minutes | X | ?
off_on_alarm | boolean | X | ?
alarm_relay | boolean | X | ?
reset_alarm | boolean | X | ?
on_timer | 22:33 10/08/16 | X | ?

### Configure

Parameter | Example Value | DCM2 | DCM5
--------- | ------------- | ---- | ----
control_by | B | X | ?
on_setpoint | 3.40 ppm | X | ?
deadband | 0.50 ppm | X | ?
interlocked | E, F, multiple, none | X | ?
blocked_by | 1, 2, multiple, none | X | ?
control_type | feed dechlor, feed oxidant, between sets | X | ?
special_control | none, pid control, time modulate | X | ?

### Setup

Parameter | Example Value | DCM2 | DCM5
--------- | ------------- | ---- | ----
description | Chlorine Gen | X | ?
event_controls | boolean | X | ?
lockout_mode | high & low pH, high pH, low pH, none | X | ?
disable_output | boolean | X | ?



## User Interface

Sensor | DCM2 | DCM5
------ | ---- | ----
Conductivity | ? | A
Temperature | C | B
pH | A | C
ORP | ? | D
Chlorine | B | E
Sample Flow / Flowswitch | E | O
LSI | ? | J
Acid Tank | ? | Q
Oxidant Tank | ? | R
Flow Rate | ? | S
------ | ---- | ----
Acid Pump | 1 | ?
Chlorine Pump | 2 | ?
Acid Feeder | ? | 2
Acid Co2 | ? | 2
Accutab | ? | 3
Pure | ? | 4
Heat Control | ? | 7



# API

This is a work in progress. We are currently highlighting endpoints that will
help to support the data we are retriving via VivoPoint today. Long-term it
would be useful to be able to configure set points, determine runtimes and
handle configuration of all data points via the API.


## Authentication


```javascript
$.get("http://0.0.0.0:0000/snapshot?key=myapikey")
```

> Make sure to replace `myapikey` with your API key.

Controllers will need to support authentication. This will require working
with controller providers to determine what type of authentication works best
for them (API Keys, OAuth, HTTPBasic).

One potential method of authentication is by using API keys. Keys allow
access to the API. We could _potentially_ have API keys available via the
controller itself and then map those into each corresponding system in the
VivoPoint admin.

We expect controllers will require an API key to be included in all API
requests.

<aside class="notice">
You must replace <code>myapikey</code> with your personal API key.
</aside>



## Snapshot

```javascript
$.get("http://0.0.0.0:0000/api/snapshot")

```

> The above command returns JSON structured like this:

```json
[
  {
    "id": "temp001",
    "type": "temperature",
    "description": "Temperature",
    "value": "78.7",
    "unit": "F",
    "status": "operational"
  },
  {
    "id": "ph001",
    "type": "pH",
    "description": "pH",
    "value": "8.02",
    "unit": "pH",
    "status": "alarm"
  },
  ...
]
```

This endpoint retrieves a snapshot of the current state of all sensors.

### HTTP Request

`GET http://0.0.0.0:0000/api/snapshot`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
key | null | Provided by the controller and stored within VivoPoint.

<aside class="success">
  We could support snapshot data retrival without a key because data cannot be
  configured via this endpoint.
</aside>



## Sensor

```javascript
$.get("http://0.0.0.0:0000/api/sensor/ph001")

```

> The above command returns JSON structured like this:

```json
{
  "id": "ph001",
  "name": "pH",
  "value": "8.02",
  "unit": "pH",
  "status": "alarm",
  "alarms": {
    "setpoints": {
      "high": "7.90",
      "low": "7.00"
    },
    "last": {
      "type": "high",
      "datetime": "1474478416",
      "cleared": "1512293122"
    }
  }
}
```

This endpoint retrieves a snapshot of the current state of one sensor.

### HTTP Request

`GET http://0.0.0.0:0000/api/sensor/:sensor_id`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
sensor_id | null | Sensor ID provided by the controller and stored within VivoPoint.
key | null | Provided by the controller and stored within VivoPoint.

<aside class="success">
  We could support snapshot data retrival without a key because data cannot be
  configured via this endpoint.
</aside>

<aside class="warning">
  One thing to take into consideration is runtimes for pumps and how that data
  should be returned. Period data may also be needed.
</aside>



## Alarms

```javascript
$.post("http://0.0.0.0:0000/api/alarms/clear")

```

> The above command returns JSON structured like this:

```json
{
  "alarms": [
    {
      "id": "ph001"
    },
    {
      "id": "temp001"
    },
    {
      "id": "orp001"
    }
  ]
}

```

This endpoint clears all alarms and returns the ids of the sensors where an
alarm was cleared.

### HTTP Request

`POST http://0.0.0.0:0000/api/alarms/clear`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
key | null | Provided by the controller and stored within VivoPoint.

<aside class="success">
  This endpoint requires a key for authentication.
</aside>



## Alarm

```javascript
$.post("http://0.0.0.0:0000/api/sensor/ph001/alarms/clear")

```

> The above command returns JSON structured like this:

```json
{
  "id": "ph001"
}

```

This endpoint clears all alarms on a single sensor and returns the id of the
sensor where the alarm was cleared.

### HTTP Request

`POST http://0.0.0.0:0000/api/sensor/:sensor_id/alarms/clear`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
sensor_id | null | Sensor ID provided by the controller and stored within VivoPoint.
key | null | Provided by the controller and stored within VivoPoint.

<aside class="success">
  This endpoint requires a key for authentication.
</aside>



## Activity Log

```javascript
$.get("http://0.0.0.0:0000/api/log/25")

```

> The above command returns JSON structured like this:

```json
{
  "events": [
    {
      "id": "ph001",
      "type": "setpoint",
      "action": "change",
      "category": "high",
      "previous_value": "7.2",
      "new_value": "7.4",
      "updated_at": "1474478416"
    },
    {
      "id": "temp001",
      "type": "alarm",
      "action": "clear",
      "category": "high",
      "updated_at": "1474478416"
    }
  ]
}

```

This endpoint returns recent events from the activity log. This could include
configuration changes, alarms cleared, alarms triggered, etc.

### HTTP Request

`GET http://0.0.0.0:0000/api/log/:count`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
count | 20 | The number of recent log events to return.
key | null | Provided by the controller and stored within VivoPoint.

<aside class="success">
  We could support activity log retrival without a key because data cannot be
  configured via this endpoint.
</aside>

<aside class="warning">
  This still has a fair amount of work to do to figure this out. Right now the
  controller may not support this. Posting this for discussion around how we
  may be able to iterate towards a useful activity log endpoint.
</aside>



## Clock

```javascript
$.get("http://0.0.0.0:0000/api/clock")

```

> The above command returns JSON structured like this:

```json
{
  "datetime": "1474478416"
}

```

This endpoint returns the current controller time.

### HTTP Request

`GET http://0.0.0.0:0000/api/clock`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
key | null | Provided by the controller and stored within VivoPoint.

<aside class="success">
  We could support clock retrival without a key because data cannot be
  configured via this endpoint.
</aside>


