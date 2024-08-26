---
created: 2024-08-26T10:48:22-07:00
modified: 2024-08-26T11:40:47-07:00
week: <% tp.date.now("YYYY-[W]W", 0, tp.file.title, "YYYY-[W]W") %>
---
## Review
- Review your Daily Notes and think about any outcomes or things discovered this week.
---
## Planning
- Open your Calendar and start planning.
- Follow your routine for weekly planning.

👉 Make sure you improve based on what you've learned this week.
___
## Daily Notes

```dataview
TABLE
week as "Week"
FROM "03 - Periodic/01 - Daily"
WHERE week = "<% tp.file.title %>"
```

## Outcomes this week

```dataview
TABLE WITHOUT ID
file.link AS "Day",
regexreplace(Lists.text, "(#\S+)+", "") AS "Outcome"
FROM #outcome
FLATTEN file.lists AS Lists
WHERE contains(Lists.tags, "#outcome")
```