---
created: 2024-08-19T15:47:57-05:00
modified: 2024-08-28T15:55:57-07:00
week: <% tp.date.now("YYYY-[W]ww", 0, tp.file.title, "YYYY-MM-DD") %>
year: <% tp.date.now("YYYY", 0, tp.file.title, "YYYY-MM-DD") %>
tags:
  - "#daily-note"
weight: 
steps: 
zone minutes: 
distance: 
calories (b): 
sleep: 
water: 
banner: "![[firewatch.jpg]]"
cssclasses: 
---
# <% moment(tp.file.title,'YYYY-MM-DD').format("dddd, MMMM DD, YYYY") %>

<% tp.web.daily_quote() %>

Capture: `BUTTON[highlights, lowlights, notes, task]`

```meta-bind-button
style: primary
id: highlights
label: Highlights
hidden: true
action:
  type: command
  command: quickadd:choice:c3fa1c95-2b7a-4738-9e45-9b3344abc7bd
```

```meta-bind-button
style: primary
id: lowlights
label: Lowlights
hidden: true
action:
  type: command
  command: quickadd:choice:3116e09d-7000-4a73-9706-471c7b2503bd
```

```meta-bind-button
style: primary
id: notes
label: Notes
hidden: true
action:
  type: command
  command: quickadd:choice:f04724da-b9ad-4aa8-aef0-f7fb2ae5c7e4
```

```meta-bind-button
style: primary
id: task
label: Task
hidden: true
action:
  type: command
  command: quickadd:choice:933cbb21-8fb3-45d0-a6cf-578e6403da5f
```

## Activities

### Highlights
 
### Lowlights

### Notes

### Tasks

#### Due This Month

```dataview
TASK
WHERE !completed AND due.month = date(today).month AND due.year = date(today).year
```