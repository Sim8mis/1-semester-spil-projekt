# AGENTS.md — Level 2 Game Template Project

This file defines how AI coding agents should work in this repository.

## Project intent

Build and maintain a **beginner-friendly** top-down web game template for Multimediedesign 1st semester students.

Students are beginners:
- Basic HTML/CSS
- Little/no JavaScript

So code must be:
- Clear
- Small
- Well-commented
- Easy to modify without deep JS knowledge

---

## Tech constraints (hard rules)

- Stack: **HTML, CSS, vanilla JavaScript**
- No frameworks/libraries unless explicitly approved
- No build tools required for basic run
- Must run directly in browser from `index.html`
- Keep architecture simple and teachable

---

## Core gameplay requirements (do not break)

- World grid: **32x32 px**
- Player sprite: **32x32 px**
- Movement:
  - visually smooth
  - grid-snapped
  - releasing movement key mid-step still completes next snap point
- Camera:
  - fixed viewport
  - follows player
  - clamped to map bounds

---

## Dynamic logic requirements (critical)

Support beginner-editable trigger system with at least:

Trigger types:
- `onEnterCell`
- `onInteractCell` (facing/pointing at cell + Space)

Action types:
- `playSound`
- `openModalText`
- `openModalVideo`
- `openModalHtml`
- `teleport`

Triggers/actions must be configurable in simple data files/objects.
Avoid requiring students to edit game engine logic for common tasks.

---

## Priority order when implementing

1. Correctness (movement/camera/trigger behavior)
2. Beginner readability
3. Maintainability
4. Visual polish

---

## File organization expectations

Keep project structure stable and intuitive:

- `/css` for styling
- `/js` for logic modules
- `/assets` for media
- `/content` for editable text/modal content

Do not move files unnecessarily.
Do not introduce deep/complex nesting.

---

## Coding style rules

- Follow Godot/GDScript-inspired readability discipline for JS/CSS:
- clear names
- short functions
- one responsibility per module
- Prefer explicit code over clever code
- Add comments where students are expected to edit
- Avoid hidden magic values; centralize constants/config
- Keep line lengths readable

---

## Safety and robustness

- Never crash app on missing/invalid trigger/media config
- Fail gracefully with console warnings
- Invalid trigger/action should be skipped, not fatal
- Missing sound/video/html content should not break gameplay loop

---

## Agent workflow rules

When making changes:

1. Keep diffs focused and minimal
2. Preserve beginner-facing APIs/config formats
3. Update README if behavior/setup changes
4. If tests exist, update/add tests for logic changes
5. Do not silently change conventions or structure

---

## PR expectations for agents

Every PR/change should include:

- What changed
- Why it changed
- Any student-facing impact
- If existing tests changed, short explanation

---

## Non-goals (avoid scope creep)

Do **not** add unless explicitly requested:
- Framework migrations
- Heavy architecture patterns
- Advanced rendering systems
- Complex game state systems
- Backend dependencies

This is a teaching template, not a production game engine.

---

## Definition of done

A change is done when:

- It satisfies requested behavior
- It keeps beginner-editability intact
- It does not break core movement/camera/trigger features
- It keeps project simple to understand and teach
