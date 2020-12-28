# Home Assistant Soft UI Dashboard

![alt text](https://github.com/pmmivv/HA_Dashboard/blob/main/images/Dashboard.png?raw=true)

# Instalation
You wil need to instal this via [HACS](https://hacs.xyz/docs/installation/manual)
- [Soft UI Theme](https://github.com/N-l1/lovelace-soft-ui)
- [Card Mode](https://github.com/thomasloven/lovelace-card-mod)
- [Button Card](https://github.com/custom-cards/button-card)

Then add the `button_card_templates` to your main lovelace Configuration

---
# Minor tweeks

Change this `/config/themes/light-soft-ui/light-soft-ui.yaml`

To change colors:
```yaml
  red: "#d62b5b"
  yellow: "#f7bf42"
  blue: "#46bdea"
```
To set colums replace de `card-mod-view-yaml` for this:
```yaml
  card-mod-view-yaml: |
    hui-masonry-view$: |
      .column {
        padding: 0px 5px;
        max-width: 400px !important;
      }
```
