## 2023-10-31 - Safe Map Keys for Dates
**Learning:** Using `new Date(dateStr).toISOString().slice(0, 10)` to generate map keys extracts the UTC date, which can cause severe timezone regressions if the original logic expected local time comparisons (like `isSameDay`).
**Action:** Use `format(parseISO(dateStr), "yyyy-MM-dd")` instead to safely format dates while strictly preserving local time semantics when creating string keys for Map lookups.
