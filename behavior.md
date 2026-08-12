# Behavior

## Timer Interaction

- Clicking a Stopwatch activity name immediately starts its stopwatch.
- Clicking the active Stopwatch activity stops it.
- Clicking a Countdown activity name immediately starts its countdown.
- Countdown duration is predefined per activity.
- Clicking the active Countdown activity stops it.
- Only one timer can run at a time.
- Starting any timer automatically stops the currently active timer.
- No confirmation dialogs.
- No timer setup screens.
- No separate Start/Stop buttons.

## Timer Calculation

- Use timestamps to calculate elapsed time.
- Do not increment timers using `setInterval` as the source of truth.
- `setInterval`/`requestAnimationFrame` may only update the displayed timer.
- On start, save `started_at`.
- On stop, calculate:
  `elapsed = current_time - started_at`
- Calculate TC from actual elapsed time using the multiplier in `rules.md`.
- Round/display TC consistently.
- A stopped timer immediately applies its TC change.

## Countdown

- Each Countdown activity has a predefined duration.
- On start, save:
  - `started_at`
  - `duration`
  - `category`
- Remaining time:
  `remaining = duration - (current_time - started_at)`
- When remaining time reaches 0:
  - Stop the timer.
  - Apply the full TC cost.
  - Clear the active timer.
- If the app is closed during a countdown, reconstruct its state from the stored timestamps when reopened.

## TC

- TC is persistent.
- Save TC immediately after every TC-changing event.
- TC must never be stored only in memory.
- TC may become negative.
- Apply all multipliers, caps, and limits from `rules.md`.
- Use integer/fixed-point values internally; avoid floating-point currency calculations.

## Checklist

- Clicking a checkbox immediately toggles completion.
- Completing a task awards its TC reward.
- Unchecking a task removes its TC reward.
- Checklist state persists across restarts.
- No confirmation dialogs.

## Persistence

Use IndexedDB as the primary local database.

Store at minimum:
- TC balance
- Daily earned TC
- Active timer
- Stopwatch/checklist activity definitions
- Checklist tasks
- Settings
- Last valid state

Never use `localStorage` as the primary database.

## Timer Persistence

Store timestamps, not continuously updated elapsed values.

Example:

```js
{
  type: "stopwatch",
  category: "study",
  started_at: 1786534200000
}
