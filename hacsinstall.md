# lovelace-hass-blink

## Hints for HACS installation

These notes are provided to help with a HACS install if you use the GUI rather than edit yaml. 

1. Install "HACS" as per their documentation [![hacs_badge](https://img.shields.io/badge/HACS-Default-orange.svg?style=for-the-badge)](https://github.com/custom-components/hacs)
2. Let the HACS addon download its data - this takes at least an hour to fetch data initial due to rate limiting - see HACS documentation
3. Choose HACS from the Sidebar
4. For installation of this card select the HACS ```Frontend``` option
5. Click + and search for "Lovelace Hass Arlo"
6. Choose ```Install this repository in HACS```
7. Choose ```Install```. This completes the installation of the repository. 
8. Now enable/install the module in Home Assistant by choosing the Configuration panel
9. Choose ```Lovelace Dashboards``` from the configuration panel
10. Click into the ```Resource``` tab
11. Click ```+``` button to add a new resource and enter:

```
Url
/hacsfiles/lovelace-hass-blink/hass-blink.js 

Resource Type:
JavaScript Module
```

12. Now you should edit your dashboard as usual to add the new card. One for each camea. When adding the blink-glance card you will need to choose the ```Manual``` option (bottom of the GUI list of available cards). Editing manually to insert some configuration
code to match your camera. 

Here is a working config for a camera known to Arlo as ```kitchen``` and to Home Assistant as ```camera.blink_kitchen```
  
  
  ```
  type: 'custom:blink-glance'
  entity: camera.blink_kitchen
  name: A camera in my Kitchen
  show:
    - motion
    - sound
    - snapshot
    - battery_level
    - signal_strength
    - captured_today
    - image_date
  top_title: false
  top_status: false
  top_date: false
  image_click: play
  ```
The options of ```top_title```, ```top_status``` and ```top_date``` can be set to ```true``` if you prefer the indicated information at the top of the card.
