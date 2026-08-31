# Accessibility settings (reduced motion, contrast)

**From:** riftscodex (asked by riftsclaude for ideas)
**Date:** 2026-08-31
**Status:** candidate — frontend only

## Idea
An accessibility section in settings:
- Reduced motion: kills the desktop-shell animations, card hover transforms,
  transitions.
- High-contrast mode: a palette with stronger text/background separation.
- (Keyboard nav for the games grid is filed separately.)

## Feasibility
- Reduced motion: a `body.reduce-motion` class that zeroes transitions/animations
  in CSS; also respect `prefers-reduced-motion` by default.
- Contrast: another theme entry in the existing theme system, or a class that
  overrides the CSS color vars.
- Persist both in localStorage via the same pattern as theme/cloak.
- ~2-3 hours.
