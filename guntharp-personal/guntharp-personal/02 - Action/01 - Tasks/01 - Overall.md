---
created: 2024-08-19T20:02:50-05:00
modified: 2024-08-20T07:23:34-05:00
---
# Tasks Dashboard

```dataview
TASK
WHERE contains(tags, "#todo")
GROUP BY file.name
```