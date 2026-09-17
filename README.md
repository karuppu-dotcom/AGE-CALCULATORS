# 📅 Age Calculator 🗓️➖

A single-screen Android app, built with **MIT App Inventor**, that compares two dates and tells you the gap between them in years and months — just tap and pick, no typing needed.

## How it works

1. Tap **DatePicker1** and choose the first date
2. Tap **DatePicker2** and choose the second date
3. The app shows each selected date on screen as you pick it
4. Tap **Button1** to calculate
5. It shows the result as **years.months**, e.g. *"26.0"*

## Features

- 📆 Two-tap date selection via native Android date picker — no manual entry
- 🏷️ Live label updates as each date is selected
- 🧮 One-tap year/month difference calculation
- 🖥️ Simple single-screen UI — works entirely offline

## Tech Stack

- **Platform:** MIT App Inventor (block-based, no native code)
- **Components:** `DatePicker1`, `DatePicker2`, `Label1`, `Label2`, `Label3`, `Button1`, `VerticalArrangement1`
- **Permissions:** None — no internet or microphone required

## Example

| DatePicker1  | DatePicker2  | Result   |
|--------------|--------------|----------|
| 15/09/2000   | 15/09/2026   | 26.0     |
| 01/01/2005   | 15/09/2026   | 21.8     |
| 20/03/1998   | 15/09/2026   | 28.6     |
| 10/12/2020   | 15/09/2026   | 6.-3     |

## Screenshot

![App Screenshot](Screenshot%20(placeholder).png)

*The app in action — showing both selected dates and the computed year/month difference.*

## Limitations (v1.0)

- Result is a raw year/month subtraction, not a calendar-adjusted duration — the day-of-month isn't factored in
- No borrowing between year and month differences, so the month value can come out negative (see last example above)
- The date-display block for the second picker currently reads from the first picker's date instead of its own
- No validation if the first date is later than the second date
- No calculation history — resets each session

## Future Improvements

- Fix the second date-picker label to reference its own component
- Add day-level precision with proper calendar borrowing
- Validate date order and show an error for invalid input
- Friendlier result format (e.g. "26 years, 0 months" instead of "26.0")
- Persistent history of past comparisons

---
