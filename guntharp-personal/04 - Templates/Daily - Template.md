---
created: 2024-08-19T15:47:57-05:00
modified: 2024-08-20T08:03:58-05:00
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
---
# <% moment(tp.file.title,'YYYY-MM-DD').format("dddd, MMMM DD, YYYY") %>

<% tp.web.daily_quote() %>
