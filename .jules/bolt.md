## 2024-11-05 - Optimize nested array filtering in useMemo loops
**Learning:** Performing `requests.filter` inside `.map(users)` and then evaluating `.filter` on dates 12 times creates large O(N*M) bottlenecks.
**Action:** Pre-group datasets (e.g. by userId or departmentId) in Maps before loops, and replace successive array mapping/filtering inside loops with a single-pass `for...of` accumulation block to drastically cut processing time.
