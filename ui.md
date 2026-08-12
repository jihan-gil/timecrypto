# UI Rules

## Window
- Size: 600×700 px.
- Single-page dashboard.
- No sidebar or unnecessary navigation.

## Layout
1. TC Balance Header
2. Stopwatch and Countdown panels side-by-side
3. Full-width Checklist below

## TC Header
- Display current TC balance prominently.
- Show human-readable time equivalent below it.

## Stopwatch Panel
- Left panel.
- Always display every stopwatch category:
  - Study — 1.25× — +75 TC/hr
  - Work / Projects — 1.15× — +69 TC/hr
  - Exercise — 1.10× — +66 TC/hr
  - Chores — 1.00× — +60 TC/hr
  - Creative — 0.95× — +57 TC/hr
  - Reading — 0.95× — +57 TC/hr
- Each row is directly clickable.
- Clicking a row starts that stopwatch.
- Active stopwatch shows its elapsed time on the selected row.

## Countdown Panel
- Right panel.
- Always display every countdown category:
  - Break — 0.50× — −30 TC/hr
  - Watching — 0.90× — −54 TC/hr
  - Gaming — 1.00× — −60 TC/hr
  - Browsing — 1.15× — −69 TC/hr
- Each row is directly clickable.
- Clicking a row starts a countdown.
- User selects the countdown duration when starting it.
- Active countdown shows remaining time on the selected row.

## Timer Behavior
- Only one timer can run at a time.
- Starting another timer automatically stops the currently running timer.
- Stopwatch earns TC continuously while running.
- Countdown spends TC continuously while running.
- Timer rows remain visible regardless of active state.

## Checklist
- Full-width section below timers.
- Display checklist tasks as simple rows:
  - Checkbox
  - Task name
  - TC reward
- Completing a task immediately awards its TC.
- Add Task button.
- Completed tasks may be hidden/collapsed.

## Visual Style
- Minimal and compact.
- No dropdowns for timer categories.
- No activity history in the main UI.
- No unnecessary cards or decoration.
- Strong typography hierarchy.
- TC balance and active timer receive the most visual emphasis.
