<h1 align="center">Dwains Light Theme</h1> 


<p align="center">
  <a href="https://github.com/LRvdLinden/dwains_light_theme">
    <img src="https://img.shields.io/github/v/release/LRvdLinden/dwains_light_theme" />
  </a>
      <a href="https://github.com/LRvdLinden/dwains_light_theme">
    <img src="https://img.shields.io/github/downloads/LRvdLinden/dwains_light_theme/latest/total?color=purple&label=%20release%20Downloads" />
  </a>
    <a href="https://github.com/LRvdLinden/">
    <img src="https://img.shields.io/github/followers/LRvdLinden?style=social" />
  </a>
    </a>
    <a href="https://discord.gg/7yt64uX">
    <img src="https://img.shields.io/discord/688401603811999885" />
  </a>
</p>

<p align="center">A Lovelace light theme based on <a href=https://github.com/dwainscheeren/dwains-lovelace-dashboard>Dwains Dashboard</a></p>
<p align="center">Created by <a href="https://github.com/LRvdLinden">Léon van der Linden</a></p> 

<p align="center">
  <img src="https://user-images.githubusercontent.com/77990847/114995388-0e7c9880-9e9e-11eb-813b-ac55fb055534.png" />
</p>


## Prerequisite
---
- Make sure you can access youre Home Assistant config files with [Samba Share](https://www.youtube.com/watch?v=udqY2CYzYGk)


## Installation Dwains Light Theme
---
- Download the `dwains_light_theme` folder and place in your `config/themes` directory.
- Reboot Home Assistant

## Selecting Dwains Light Theme
---
- Click on youre profile picture
- By `themes` you need to select Dwains Light Theme 

![image](https://user-images.githubusercontent.com/77990847/114995688-61565000-9e9e-11eb-9787-e1d1a672e6bb.png)


## Set HA theme for day and night
---
- When you whant to switch automatic between the Dark and Light theme based on the sun, please copy this code in youre `automations.yaml` or `directory`
```
yaml
- alias: Set HA theme for day and night
  id: set_theme_for_day_and_night
  trigger:
    - platform: homeassistant
      event: start
    - platform: state
      entity_id: sun.sun
      to: above_horizon
    - platform: state
      entity_id: sun.sun
      to: below_horizon
  action:
    - service: frontend.set_theme
      data:
        name: >
          {% if states.sun.sun.state == "above_horizon" %}
            Dwains Light Theme
          {% else %}
            Dwains Dark Theme
          {% endif %}
```
## Result
---
![image](https://user-images.githubusercontent.com/77990847/114995529-366bfc00-9e9e-11eb-929a-a19d4d4d494f.png)
![image](https://user-images.githubusercontent.com/77990847/114995357-04f33080-9e9e-11eb-951f-2588ec75bb2b.png)
---
Enjoy my card? Help me out for a couple of :beers: or a :coffee:!

[![coffee](https://www.buymeacoffee.com/assets/img/custom_images/black_img.png)](https://www.buymeacoffee.com/LRvdLinden)
