# 04 Flowchart

## Flowchart description
The system follows the decision flow below.

```text
Start
  |
  v
Board powered on
  |
  v
Begin checking external bus arrival feed every 30 seconds
  |
  v
Is fresh data available?
  |-- No --> Show "Arrival information outdated"
  |           |
  |           v
  |       Retry again in 30 seconds
  |           |
  |           v
  |      Is fresh data available now?
  |          |-- Yes --> Continue normal display
  |          |-- No --> Keep showing "Arrival information outdated"
  |
  v
Is data older than 60 seconds?
  |-- Yes --> Show "Arrival information outdated"
  |           |
  |           v
  |      Keep route number and stop name visible
  |      Continue showing time since last update
  |      Retry again in 30 seconds
  |
  |-- No --> Show normal countdown
              |
              v
      Show route number, stop name, countdown, and time since last update

Board switched off
  |
  v
Stop updating
Clear screen
Do not save any arrival information
End
```

## Key decisions
- The board does not wait for a bus to stop before checking the feed.
- The board checks every 30 seconds.
- A reading older than 60 seconds triggers the outdated state.
- The outdated state does not remove the route number or stop name.
- Power off clears the screen and ends all updates.
