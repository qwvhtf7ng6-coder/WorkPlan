## 2024-05-17 - Precomputing Date String Formats in Grids
**Learning:** In React grid or table components, avoid calling `date-fns` `format()` or similar expensive string parsing inside nested loops (e.g., O(Users * Days)).
**Action:** Precompute this static column data into an array of objects using `useMemo` to reduce calculation overhead to O(Days).
