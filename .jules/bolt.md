## 2025-03-01 - Avoid format and isWeekend in nested React Table/Grid loops
**Learning:** date-fns `format()` and `isWeekend()` are expensive operations. Calling them inside a nested component render loop for a table (e.g., O(Users * Days)) creates a significant performance bottleneck due to thousands of repeated string parsing operations.
**Action:** Precompute static column data like date strings and weekend booleans outside the nested loop into an array of objects using `useMemo` (reducing it to O(Days)), and iterate over the precomputed objects instead.
