# Home Assistant Soft UI Dashboard

![alt text](https://github.com/pmmivv/HA_Dashboar/blob/main/images/Dashboard.png?raw=true)

# Instalation
You wil need to instal this via [HACS](https://hacs.xyz/docs/installation/manual)
- [Soft UI Theme](https://github.com/N-l1/lovelace-soft-ui)
- [Card Mode](https://github.com/thomasloven/lovelace-card-mod)

---
# Minor tweeks

Change this `/config/themes/light-soft-ui/light-soft-ui.yaml`

To change colors:
```
  red: "#d62b5b"
  yellow: "#f7bf42"
  blue: "#46bdea"
```
To set colums replace de `card-mod-view-yaml` for this:
```
  card-mod-view-yaml: |
    hui-masonry-view$: |
      .column {
        padding: 0px 5px;
        max-width: 400px !important;
      }
```
