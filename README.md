Add the calendar of your football team to Home Assistant. The data is gathered from the RBFA

[![Hacs validation](https://github.com/rgerbranda/rbfa/actions/workflows/validate.yaml/badge.svg)](https://github.com/rgerbranda/rbfa/actions/workflows/validate.yaml)
[![Hassfest validation](https://github.com/rgerbranda/rbfa/actions/workflows/hassfest.yaml/badge.svg)](https://github.com/rgerbranda/rbfa/actions/workflows/hassfest.yaml)


Configuration
-
![Example](https://github.com/rgerbranda/rbfa/blob/main/images/configuration.png)

The team number is the number after 'ploeg': https://www.rbfa.be/nl/club/2438/ploeg/300872/overzicht

Example card
-
![Example](https://github.com/rgerbranda/rbfa/blob/main/images/example.png)

Match card
-
<img src="https://github.com/rgerbranda/rbfa/blob/main/images/match_sheet.png" alt="Match card" width=528>

Ranking card
-

```
type: markdown
title: Ranking
content: >-
  {% set sensor = "sensor.result_279669" %}

  {{state_attr(sensor, "Series") }}

  -

  {% if state_attr(sensor, "Ranking") != None %}
  {% for item in state_attr(sensor, "Ranking") %}

  {{ item.position }}. {% if item.id == state_attr(sensor, "TeamID") %}**{{item.team}}**
  {% else %}{{item.team}}
  {% endif %}
  {% endfor %} 
  {% endif %}
```

<img src="https://github.com/rgerbranda/rbfa/blob/main/images/ranking.png" alt="Ranking" width=528>


[![github release](https://img.shields.io/github/v/release/rgerbranda/rbfa?logo=github)](https://github.com/rgerbranda/rbfa/releases)
[![github release date](https://img.shields.io/github/release-date/rgerbranda/rbfa)](https://github.com/rgerbranda/rbfa/releases)

<img src="https://github.com/home-assistant/brands/blob/c359584cf6719b89aee0428cdb55da55c5b34593/custom_integrations/rbfa/logo.png" alt="Royal Belgian Football Association" height=128>
