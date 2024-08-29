---
created: 2024-08-19T15:47:57-05:00
modified: 2024-08-28T17:02:29-07:00
banner: "![[watchtower.jpg]]"
cssclasses: 
---

# :LiHome: Home
```dataview
TABLE WITHOUT ID Folder, rows.file.link AS Files
FROM "06 - Examples"
FLATTEN regexreplace(file.folder, "06 - Examples/", "") AS Folder
GROUP BY Folder
```