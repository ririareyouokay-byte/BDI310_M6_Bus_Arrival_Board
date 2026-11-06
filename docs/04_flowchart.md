# 04 Flowchart

## Flowchart description
The system follows the decision flow below.

```text
[START]
   |
   v
[Power on board]
   |
   v
[Check external bus arrival feed]
   |
   v
<Is fresh data available?>
   |
   |-- YES --> <Is data older than 60 seconds?>
   |                 |
   |                 |-- NO --> [Show normal countdown,
   |                 |           route number and stop name]
   |                 |
   |                 |-- YES --> [Show "Arrival information
   |                              outdated", keep route
   |                              number and stop name]
   |
   |-- NO --> [Show "Arrival information outdated"]
   |
   v
<Is board powered off?>
   |
   |-- YES --> [Stop updating]
   |                 |
   |                 v
   |            [Clear screen]
   |                 |
   |                 v
   |               [END]
   |
   |-- NO --> [Wait 30 seconds]
                     |
                     v
             [Return to checking
              external data feed]
                     |
                     v
             [Check external bus
              arrival feed again]
```

## Key decisions
- The board does not wait for a bus to stop before checking the feed.
- The board checks every 30 seconds.
- A reading older than 60 seconds triggers the outdated state.
- The outdated state does not remove the route number or stop name.
- Power off clears the screen and ends all updates.
