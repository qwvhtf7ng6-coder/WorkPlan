## 2025-02-20 - React `useMemo` date parsing
**Learning:** Optimizing `new Date(dateStr).toISOString().slice(0, 10)` by replacing it with `format(new Date(dateStr), "yyyy-MM-dd")` breaks timezone functionality, shifting calendar entries forward/backwards due to UTC versus local evaluation disparities.
**Action:** When extracting UTC date strings within O(N) map reductions, leave `new Date(dateStr).toISOString().slice(0, 10)` intact to preserve intended calendar alignment, while safely memoizing loop arrays and outer maps.
