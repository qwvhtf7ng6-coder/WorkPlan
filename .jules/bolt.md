## 2025-02-26 - Precompute static date strings before nested loops
**Learning:** Calling `date-fns` functions like `format()` and `isWeekend()` inside nested loops for React grids (e.g. iterating over Users * Days) causes severe render blocking due to O(N * M) string parsing.
**Action:** Always map the days into an array of precomputed objects (e.g. `dk`, `weekend`) using `useMemo` before mapping over rows/users in the table.
