# Scenario #10: Bus Arrival Board

1. It is a bus arrival board for people waiting for a bus, showing the current estimated arrival information for a bus stop.

2. The board receives arrival data from an external bus arrival data feed and displays the route number, bus stop name, and the time since the last update.

3. The board checks for new information every 30 seconds, whether a bus is stopped or not.

4. During normal operation, the screen shows the estimated number of minutes until the bus arrives as a countdown.

5. A reading is considered outdated after 60 seconds, and the board must not treat that stale time as current information.

6. When the latest available reading is older than 60 seconds, the countdown is replaced with "Arrival information outdated" while the route number and stop name remain visible.

7. The screen continues to show how long ago the data was last updated while the board is in the outdated state.

8. If the external feed stops updating, the board continues displaying "Arrival information outdated" and automatically retries every 30 seconds.

9. Once fresh data becomes available, the board returns to displaying the normal arrival countdown; when the board is powered on, it begins checking the external feed immediately and does not wait for a bus to stop.

10. When the board is switched off, it stops updating, clears the screen, and does not save or retain any arrival information.

## Instructions for the LLM

Before writing any documents, ask me about anything this overview does not answer. Ask one question at a time and keep asking until there is nothing left to guess. Add my answers to this overview.