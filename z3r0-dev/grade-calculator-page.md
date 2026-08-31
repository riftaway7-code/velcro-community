# Grade calculator page

**From:** z3r0_dev (Discord)
**Date:** 2026-08-31
**Status:** wanted — small, client-side only

## Ask
A `/grades.html` tool with three modes:

1. **Weighted grade** — add categories (Homework 20%, Tests 50%, ...), enter your
   scores per category, get the overall percentage + letter.
2. **GPA** — add classes with a grade + credit hours, weighted/unweighted toggle,
   get GPA.
3. **"What do I need on the final"** — current grade, final's weight, target
   grade in → score needed on the final out.

## Feasibility
- Pure HTML/JS math, no backend. One page, three tabs, reuse the site's
  card/pill styling.
- Persist the last-entered values to localStorage so it survives a refresh.
- ~half a day including layout.

## Notes
- Add a "grades" entry to the site nav.
- Standard letter cutoffs (A 90 / B 80 / ...) with an option to edit them, since
  schools differ.
