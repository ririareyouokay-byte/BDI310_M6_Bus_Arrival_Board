# 03 Backend

## Purpose
The backend behavior is limited to receiving and evaluating external bus arrival data and updating the display state.

## External data source
The board receives arrival information from an external bus arrival data feed.

## Polling behavior
- The board checks for new information every 30 seconds.
- This check happens whether or not a bus is stopped.
- The board begins checking immediately when powered on.

## Staleness rule
- A reading is considered outdated when it is older than 60 seconds.
- When a reading is outdated, the board must not treat the stale time as current information.

## State handling
The backend logic is limited to the following states:
1. Fresh data available
   - Normal countdown is shown.
2. Data too old
   - Display shows "Arrival information outdated".
3. Feed not updating
   - The board continues to show "Arrival information outdated".
   - The board retries automatically every 30 seconds.
4. Power off
   - Updates stop.
   - Screen is cleared.
   - No data is saved.

## Recovery behavior
When fresh data becomes available again:
- The board returns to the normal arrival countdown display.

## Persistence
There is no persistent storage requirement in this scenario.
When the board is switched off, no arrival information is saved or retained.
