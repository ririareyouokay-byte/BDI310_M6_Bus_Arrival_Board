# 07 Acceptance Checks

## Acceptance criteria
1. The board displays route number and bus stop name.
2. The board shows the estimated number of minutes until arrival during normal operation.
3. The board checks for new data every 30 seconds.
4. The board begins checking the external feed immediately when powered on.
5. The board does not wait for a bus to stop before checking the feed.
6. A reading older than 60 seconds is identified as outdated.
7. When data is older than 60 seconds, the countdown is replaced with "Arrival information outdated".
8. The route number and bus stop name remain visible while the data is outdated.
9. The time since the last update remains visible while the data is outdated.
10. The board does not show the stale arrival time as current information.
11. If the external feed stops updating, the board continues to display "Arrival information outdated" and retries every 30 seconds.
12. Once fresh data becomes available, the board returns to the normal arrival countdown.
13. When the board is switched off, it stops updating.
14. When the board is switched off, the screen is cleared immediately.
15. When the board is switched off, no arrival information is saved or retained.

## Pass condition
The scenario is considered complete when all listed checks are satisfied without adding features beyond those defined in the overview.
