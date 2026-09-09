## 2024-05-18 - Nested loops with Array.some in useMemo
**Learning:** In React components like CalendarGrid, nesting a request iteration inside a department iteration and using `Array.some` to check user presence results in O(D * R * U * E) time complexity. This can cause significant main thread blocking during re-renders with large datasets.
**Action:** Replace nested O(N^3+) iterations with O(N) map lookups. Precompute relationship maps (e.g., `user -> department[]`) before the loop to drastically reduce computation overhead, ensuring to support many-to-many relationships if applicable.
