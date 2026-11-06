# 02 Frontend

## Purpose
The frontend is the bus arrival screen that presents up-to-date arrival information to waiting passengers.

## Screen content
The screen shows the following information:
- Route number
- Bus stop name
- Countdown showing the estimated number of minutes until the bus arrives when fresh data is available
- Time since the last update

## Normal state
When fresh data is available and the most recent reading is not older than 60 seconds:
- The route number is visible.
- The bus stop name is visible.
- The countdown shows the estimated minutes until arrival.
- The time since the last update is visible.

## Outdated state
When the latest available reading is older than 60 seconds:
- The route number remains visible.
- The bus stop name remains visible.
- The countdown is replaced with: "Arrival information outdated"
- The time since the last update remains visible.
- The old arrival time is not shown as current information.

## Power-off state
When the board is switched off:
- The screen is cleared immediately.
- No power-off message is displayed.
- No arrival information is retained.

## Required message text
The only required message text defined in the overview is:
- "Arrival information outdated"

No additional user-facing messages or features are included in this scenario.
