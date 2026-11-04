## 2024-05-24 - Precomputing formatted dates for loop optimization
**Learning:** Formatting Date objects inside nested loops in React components is expensive, particularly `date-fns` `format()` and `isWeekend()`. This can lead to significant overhead when rendering large tables (e.g., O(Users * Days) complexity).
**Action:** Instead of calling `format()` or `isWeekend()` in every table cell loop over `days`, precompute this information into an array of objects `formattedDays` using `useMemo` (making the formatting complexity O(Days)), and use this precomputed data inside the table cells.
