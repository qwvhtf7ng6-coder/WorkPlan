## 2025-05-18 - Optimized Nested Department Capacity Lookups
**Learning:** In React grid components, nested array lookups like `dept.users.some()` across outer department and request loops create significant bottlenecks during rendering.
**Action:** Pre-compute relationships (e.g., mapping users to departments via `Map<string, string[]>`) and pre-populate output Maps with all expected keys to ensure O(1) lookups and maintain the exact return contract.
