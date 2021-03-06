---
layout: page
title: "Daikin AC"
description: "Instructions on how to integrate Hive devices with Home Assistant."
date: 2017-12-10 21:00
sidebar: true
comments: false
sharing: true
footer: true
logo: daikin.png
ha_category: Climate
ha_release: 0.59
ha_iot_class: "Local Polling"
---


The `daikin` component integrates Daikin air conditioning systems into Home Assistant.

## {% linkable_title Supported hardware %}

**Only** the european versions of Daikin ACs (models BRP069A41, 42, 43, 45).

The model BRP069A42 does not support setting of fan speed or fan swing mode.

Please note that some AC devices may report outside temperature only when they are turned on.

## {% linkable_title Configuration %}

To automatically add all your Daikin devices (ACs and associated sensors) into your Home Assistant installation, add the following to your `configuration.yaml` file:

```yaml
# Full manual example configuration.yaml entry
daikin:
  hosts:
    - 192.168.4.161
  monitored_conditions:
    - inside_temperature
    - outside_temperature
```

{% configuration %}
hosts:
  description: List of IP addresses or hostnames.
  required: false
  default: All discovered hosts
  type: array
monitored_conditions:
  description: List of items you want to monitor for each device.
  required: false
  default: All conditions
  type: list
  keys:
    inside_temperature:
      description: The current temperature measured inside the house.
    outside_temperature:
      description: The current temperature measured outside the house.      
{% endconfiguration %}

