# 06 Technical Specification

## Scope
This specification describes the behavior of the bus arrival board based only on the finalized overview.

## Inputs
- External bus arrival data feed
- Time reference for measuring age of each reading
- Power state of the board

## Outputs
- Route number
- Bus stop name
- Countdown showing estimated minutes until arrival
- Time since last update
- "Arrival information outdated" message when applicable
- Cleared screen when powered off

## Timing requirements
- The board checks the external feed every 30 seconds.
- A reading older than 60 seconds is considered outdated.
- The outdated state continues until fresh data is available.

## Display rules
- Fresh data: show route number, stop name, countdown, and time since last update.
- Stale data: show route number, stop name, "Arrival information outdated", and time since last update.
- Power off: clear the screen immediately.

## State rules
1. Powered on
   - Start checking the feed immediately.
2. Fresh data available
   - Show normal countdown.
3. Data older than 60 seconds
   - Replace only the countdown with "Arrival information outdated".
4. Feed stops updating
   - Continue showing "Arrival information outdated" and retry in 30 seconds.
5. Powered off
   - Stop updating and clear the screen.

## Data retention
- No arrival information is saved when the board is switched off.
- No persistent history is required by the scenario.

## Constraints
- No additional features may be introduced beyond the behavior described in the overview.
- No code is required for this document; it is a specification only.
