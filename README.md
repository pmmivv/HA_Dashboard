# Home Assistant Soft UI Dashboard

![alt text](https://github.com/pmmivv/HA_Dashboard/blob/main/images/Dashboard.png?raw=true)

## Instalation
You wil need to instal this via [HACS](https://hacs.xyz/docs/installation/manual)
- [Soft UI Theme](https://github.com/N-l1/lovelace-soft-ui)
- [Card Mode](https://github.com/thomasloven/lovelace-card-mod)
- [Button Card](https://github.com/custom-cards/button-card)

Then add the content of `button_card_templates.yaml` to your main lovelace configuration

---
# Minor tweeks

Change this at `/config/themes/light-soft-ui/light-soft-ui.yaml`

Colors:
```yaml
  red: "#d62b5b"
  yellow: "#f7bf42"
  blue: "#46bdea"
```
To set colums, replace de `card-mod-view-yaml` for this:
```yaml
  card-mod-view-yaml: |
    hui-masonry-view$: |
      .column {
        padding: 0px 5px;
        max-width: 400px !important;
      }
```

## The Idea
I just wanna have something easy to create and customize, so, my idea was to create this as blocks (defined as button card template) and then call them on the button card

```yaml
entity: switch.switch_portao
name: Garage Door
template:
  - main_style
  - button_grid
  - botao
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
  - botao - Used for the majority of button with On and Off states
  - sensor - Used to report sensor state
  - number - Used for input_number
  - termometro - Used for temperature sensors
  - time - Used for input_datetime
  - estores - Used for control covers

## Variables
Allmost every sensor state template have variables to define icons and states

  - icon_on: 'mdi:garage-open'
  - icon_off: 'mdi:garage-variant'
  - message_on: Open
  - message_off: Close
  - color: var(--yellow)




