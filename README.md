# Home Assistant Soft UI Dashboard

![alt text](https://github.com/pmmivv/HA_Dashboard/blob/main/images/Dashboard.png?raw=true)

## Instalation
You will need to install this via [HACS](https://hacs.xyz/docs/installation/manual)
- [Card Mod](https://github.com/thomasloven/lovelace-card-mod)
- [Button Card](https://github.com/custom-cards/button-card)

And @KTibow's soft-ui-theme
- [Soft UI Theme](https://github.com/KTibow/lovelace-light-soft-ui-theme)

Then add the content of `button_card_templates.yaml` to your main Lovelace configuration

---
## Minor tweeks

Change this at `/config/themes/light-soft-ui/light-soft-ui.yaml`

Colors:
```yaml
  red: "#d62b5b"
  yellow: "#f7bf42"
  blue: "#46bdea"
```
To set colums, replace `card-mod-view-yaml` with this:
```yaml
  card-mod-view-yaml: |
    hui-masonry-view$: |
      .column {
        padding: 0px 5px;
        max-width: 400px !important;
      }
```

## The Idea
I want to have something easy to create and customize, so my idea was to create this as blocks (defined as button card template) and then call them on each button card

```yaml
entity: switch.switch_portao
name: Garage Door
template:
  - main_style
  - button
type: 'custom:button-card'
variables:
  icon_on: 'mdi:garage-open'
  icon_off: 'mdi:garage-variant'
  message_on: Open
  message_off: Close
  color: var(--yellow)
```

## Templates

  - main_style - This defines card dimentions
  - button - Used for the majority of buttons with On and Off states
  - sensor - Used to report sensor state
  - number - Used for input_number
  - temperature - Used for temperature sensors
  - time - Used for input_datetime
  - cover - Used to control covers

## Variables
Almost every sensor state template have variables to define icons and states

  - icon_on: 'mdi:garage-open'
  - icon_off: 'mdi:garage-variant'
  - message_on: Open
  - message_off: Close
  - color: var(--yellow)

## Examples
### Temperature
<img src="https://github.com/pmmivv/HA_Dashboard/blob/main/images/Temperature.png" width="30%" height="30%" />

```yaml
entity: sensor.home_temperature
name: Inside
template:
  - main_style
  - temperature
show_state: true
show_label: true
label: Temperature
type: 'custom:button-card'
variables:
  sensor_name: |
    [[[  return states['sensor.home_humidity'].state; ]]]
```
### Select
<img src="https://github.com/pmmivv/HA_Dashboard/blob/main/images/Select.png" width="30%" height="30%" />

```yaml
icon: 'mdi:palette'
entity: input_select.varanda
name: Color
template:
  - main_style
  - select
  - color
type: 'custom:button-card'

```
### Cover
<img src="https://github.com/pmmivv/HA_Dashboard/blob/main/images/Cover.png" width="30%" height="30%" />

```yaml
entity: cover.estore1
name: Living<br/>room
icon: 'mdi:blinds'
template:
  - main_style
  - cover
type: 'custom:button-card'

```
### Sensor
<img src="https://github.com/pmmivv/HA_Dashboard/blob/main/images/Sensor.png" width="30%" height="30%" />

```yaml
entity: input_boolean.b_garagem_fechar_portao_auto
name: Night<br/>alarm
template:
  - main_style
  - sensor
type: 'custom:button-card'
variables:
  icon_on: 'mdi:shield-lock-outline'
  icon_off: 'mdi:shield-off-outline'
  message_on: 'On'
  message_off: 'Off'
  color: var(--green)

```
### Button
<img src="https://github.com/pmmivv/HA_Dashboard/blob/main/images/button.png" width="30%" height="30%" />

```yaml
entity: input_boolean.b_garagem_fechar_portao_auto
name: Close garage<br/>door auto
template:
  - main_style
  - button
type: 'custom:button-card'
variables:
  icon_on: 'mdi:arrow-decision-auto-outline'
  icon_off: 'mdi:arrow-decision-auto-outline'
  message_on: 'Yes'
  message_off: 'No'
  color: var(--green)

```
### Number
<img src="https://github.com/pmmivv/HA_Dashboard/blob/main/images/Number.png" width="30%" height="30%" />

```yaml
icon: 'mdi:brightness-percent'
entity: input_number.varanda
name: Bright
template:
  - main_style
  - number
type: 'custom:button-card'

```
### Sensor 2
<img src="https://github.com/pmmivv/HA_Dashboard/blob/main/images/Sensor2.png" width="30%" height="30%" />

```yaml
entity: sensor.ups_consumo
name: Ups
template:
  - main_style
  - sensor_number
type: 'custom:button-card'
variables:
  icon: 'mdi:car-battery'
  color: var(--blue)
  default_status: 'on'

```
### Theme
<img src="https://github.com/pmmivv/HA_Dashboard/blob/main/images/Theme.png" width="30%" height="30%" />

```yaml
entity: input_boolean.natal
icon: 'mdi:pine-tree'
template:
  - button_little
type: 'custom:button-card'
variables:
  color: var(--green-yellow)

```

## Bugs and optimizations
This is work in progress so expect some bugs and some things that can be improved.



