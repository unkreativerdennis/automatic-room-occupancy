# automatic-room-occupancy
Automatic Home Occupancy Home Assistant Blueprint

**Automatic Home Occupancy Home Assistant Blueprint**

Automatically turn on and off an occupancy input_boolean helper entity for a single room based on activity or non-activity (with timeout).

------SETUP------

The following helper entities are required:
- input_boolean.[room]_occupancy (input_boolean that will be turned on/off with occupancy)

The following entities are optional for full automation functionality:
- input_boolean.[room]_occupancy_disabled (input_boolean that disables the automation)

------LOGIC------

Occupied triggered when ANY of the following conditions are met (all are optional).
- media player(s) state as specified (default: "playing")
- motion binary_sensor (or group) state to "on"

Occupancy is cleared when ALL of the following conditions are met (all are optional):
- door binary_sensor (or group) state to "on"/open for specified time (default: 0 mins)
- any media player state to state as specified (default: "playing")

------OPTIONAL HELPERS------

Uses the following helpers to allow for front end control of timeouts. Defaults are as specified below:
- input_number.media_occupancy_timeout (in minutes, default: 10)
- input_number.motion_occupancy_timeout (in minutes, default: 10)
