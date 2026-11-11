## 2024-11-11 - Optimize frequent rendering and dragging calls
**Learning:** In highly frequent animation loops (like `_draw` in `Animator`) or mouse move dragging (`_updateLocation`), jQuery `.css()` creates significant overhead due to object creation, style parsing, and cross-browser normalizations.
**Action:** Use native DOM `.style` manipulation on `el[0]` directly for critical hot paths that run every few milliseconds to improve frame rate and reduce garbage collection pauses.
