## 2025-02-14 - Optimize nested component aggregation
**Learning:** In components rendering heavy aggregation logic like `deptCapacity` over multiple arrays (Departments, Users, Requests), nested loops using `some()` or `.find()` inside `useMemo` create O(N^3) bottlenecks on large datasets.
**Action:** Pre-compute mappings (e.g., User -> Department IDs) into Hash Maps before iterating over the main data array (e.g., Requests) to reduce the complexity to O(N).
