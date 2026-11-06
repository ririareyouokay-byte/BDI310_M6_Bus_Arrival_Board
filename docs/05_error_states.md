# 05 Error States

## Overview
This scenario has a limited set of error and warning conditions based only on the finalized overview.

## 1. Data stale after 60 seconds
Condition:
- The newest available arrival reading is older than 60 seconds.

Display behavior:
- Route number remains visible.
- Bus stop name remains visible.
- Countdown is replaced with "Arrival information outdated".
- Time since last update remains visible.

## 2. External feed not updating
Condition:
- The external bus arrival feed stops providing new data.

Display behavior:
- The board continues displaying "Arrival information outdated".
- It automatically retries every 30 seconds.

## 3. No fresh data available at start-up
Condition:
- The board is powered on but the external feed has not yet supplied fresh data.

Display behavior:
- The board starts checking immediately.
- It shows the normal countdown only once fresh data is available.
- Until then, it can display the stale/outdated state if the latest available reading is older than 60 seconds.

## 4. Power-off state
Condition:
- The board is switched off.

Behavior:
- The board stops updating.
- The screen is cleared.
- No arrival data is saved.

## Background message requirement
The only required background message is:
- "Arrival information outdated"

No additional error text, alerts, or background messages are defined by the overview.
