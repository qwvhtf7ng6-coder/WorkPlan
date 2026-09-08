## 2025-02-14 - User-Department Relationship Complexity
**Learning:** In the CalendarGrid component, a user can belong to multiple departments. Assuming a strict 1-to-1 relationship with `Map<string, string>` when precomputing department data causes regressions.
**Action:** Always handle user-department mapping functionally by using `Map<string, string[]>` to map user IDs to arrays of department IDs.
