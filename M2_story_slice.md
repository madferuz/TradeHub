# M2 Story Slice — TradeHub

ISE4133 Software Engineering · Week 4 · Draft for M2 (Requirements Package)

---

## Worksheet 1 — Context and story 1

**Team / product / members / date**
AF Team / TradeHub / Adilbekov Adilbek, Madrakhimov Feruzbek, [add member] / [date]
Writer: [name] · Reviewer: [name] · Scope check: [name]

**M1 input: user and problem; feedback received**
User: self-directed retail trader (beginner to intermediate). Problem: charting, trade journaling, and trade ideas are spread across separate apps, so it is hard to connect a trade to its outcome.
Feedback: **No feedback yet** from real users. (AI critique on M1 raised: journal entry method and trading style are undefined.)

**One revision or decision to retain the current direction, with a reason**
Retain the M1 direction, but **narrow this slice to the journal part**: logging a demo trade and seeing it on the P&L calendar. Reason: it is the end of the M1 main task, it needs no real market data or social features, and it answers the M1 critique point by deciding that **trades are entered manually** in v1.

**User profile**
- Role: retail trader who trades several times a week with a demo/paper account.
- Situation: finishes a trade and wants to record it and review results by day.
- Skill/constraint: knows basic trade terms (entry, exit, quantity, long); uses an iPhone; no broker connection in v1.

**Evidence source, or clearly labeled assumption**
**Assumption.** Based on the team's general knowledge (M1). No interviews or observations yet.

**Scenario (2–3 sentences)**
After closing a demo trade, Aziz opens TradeHub and enters the asset, quantity, entry price, and exit price. The app saves the trade and shows its profit or loss on that day in the P&L calendar. At the end of the week he checks the calendar to see which days were winning or losing, without using a separate spreadsheet.

### S1 — First core story

**As a** retail trader, **I want** to log a closed demo trade, **so that** its profit or loss is recorded in my trade history.

**S1-AC1**
Given a closed **long** demo trade — AAPL, quantity 10, entry 100.00, exit 105.00, closed on 2026-10-05,
when the trader taps **Save**,
then the trade appears in the history list and the P&L calendar cell for **5 Oct** shows **+50.00**.

**S1-AC2**
Given a trade form with **quantity 0** or a **missing exit price**,
when the trader taps **Save**,
then an error message names the invalid field, the trade is **not** saved, and the history list and calendar are unchanged.

**Priority and rationale; dependency**
**Priority 1.** Without logged trades there is nothing to show on the calendar or history, so every other journal feature depends on this story. Dependency: none.

---

## Worksheet 2 — Story 2 and team review

### S2 — Second core story

**As a** retail trader, **I want** to see my total profit or loss for each day on a calendar, **so that** I can quickly spot winning and losing days and review my habits.

**S2-AC1**
Given two closed demo trades on 2026-10-06 — one with P&L **+50.00** and one with P&L **−20.00**,
when the trader opens the P&L calendar for October 2026,
then the cell for **6 Oct** shows **+30.00**, and tapping it lists both trades.

**S2-AC2**
Given **no** trades closed on 2026-10-07,
when the trader opens the P&L calendar for October 2026,
then the cell for **7 Oct** shows no amount, and tapping it shows the message "No trades on this day".

**Priority and rationale; dependency**
**Priority 2.** It delivers the performance-review value from M1, but it only works after trades can be logged. Dependency: **S1**.

**One alternate/invalid case covered, or one rule still needing agreement**
- Covered: invalid trade input (S1-AC2) and a day with no trades (S2-AC2).
- **Rule still needing agreement:** which day a trade belongs to — the **closing date** (used above) or the opening date — and in which time zone. Also open: whether **open trades** (no exit yet) appear on the calendar.

**One capability excluded from this slice, with a reason**
**Trade-idea social feed** (publish, comment, like). Reason: it is a separate value (community) with its own risky assumption, and this slice focuses on the journal task. **Real broker connection** also stays excluded, as in M1.

### Review the document, then save it

- [ ] Both stories relate to the same stated user task and scenario.
- [ ] Each criterion has a result another person could inspect.
- [ ] Assumptions, agreed draft rules, and open questions are distinguishable.
- [ ] The document describes expected behavior without inventing test results.

**Reviewer; ambiguity found; change made (or reason no change was needed)**
[team to fill in — e.g. "Reviewer asked whether P&L includes fees → added: P&L excludes fees in v1."]

**Saved file/location or commit link; person who reopened and checked it**
[repo link or file location] · [name]

**AI use**
Drafted with Claude (Anthropic) from the team's M1 document on [date]. Team checks: [team to fill in — e.g. checked the P&L numbers, confirmed stories match the SwiftUI prototype screens].

*Criteria describe expected future behavior. No check has been executed yet.*
