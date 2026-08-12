# Time Currency Ruleset

## Core
- Time is the currency: `TC` (Time Currency).
- 1 real minute = 1 base TC.
- Stopwatch activities earn TC.
- Countdown activities spend TC.
- Checklist activities give fixed TC rewards.

## Stopwatch — Earn TC

| Category | Multiplier |
|---|---:|
| Study | 1.25x |
| Work / Projects | 1.15x |
| Exercise | 1.10x |
| Chores | 1.00x |
| Creative | 0.95x |
| Reading | 0.95x |

Formula:
`TC earned = minutes × multiplier`

## Countdown — Spend TC

| Category | Multiplier |
|---|---:|
| Break | 0.50x |
| Watching | 0.90x |
| Gaming | 1.00x |
| Browsing | 1.15x |

Formula:
`TC spent = minutes × multiplier`

## Checklist — Fixed Rewards

Checklist tasks do not use timers.

| Task importance | TC reward |
|---|---:|
| Small | +2 TC |
| Normal | +10 TC |
| Important | +20 TC |
| Major | +25 TC |

## Economy Limits

### Daily earning cap
- Maximum spendable TC earned per day: `+180 TC`.
- Stopwatch time may continue being tracked after reaching the cap, but additional TC is not added.

### Wallet soft cap
- Target maximum wallet: `+720 TC` (12 hours).
- TC earning efficiency decreases as the wallet grows.

| Wallet balance | Earning efficiency |
|---|---:|
| 0–240 TC | 100% |
| 241–480 TC | 75% |
| 481–720 TC | 50% |
| >720 TC | 0% |

- TC may go negative.
- Spending never creates additional penalties beyond the TC spent.

## Design Principle

- Productivity should roughly fund equivalent leisure.
- Higher-value activities earn slightly more.
- Time-wasting activities cost slightly more.
- The system rewards consistency, not extreme grinding.
- The system must prevent productive bursts from creating months of stored leisure time.
