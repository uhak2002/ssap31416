# Mobile Web Behavior

Read this before implementing responsive web flows with routing, forms, fixed navigation, media capture, or permissions.

## Navigation and history

- Give every meaningful screen a stable URL or route state.
- Push history when moving to a new user-visible screen; replace history for automatic redirects or state cleanup.
- Make browser/system back mirror the visible back action.
- Close a modal or step overlay before leaving its parent route.
- On direct entry or refresh, reconstruct enough context to render safely; if context is missing, route to a useful fallback.
- Do not trap the user by immediately pushing the route they just left.

For hash routing, centralize route changes and handle `hashchange`/`popstate` once. Avoid independent click handlers that mutate views without updating history.

## Forms and the software keyboard

- Use semantic input types and `autocomplete` values.
- Keep the focused field visible when the keyboard opens.
- Avoid viewport-height assumptions based only on `100vh`; prefer dynamic viewport units with practical fallbacks.
- Keep primary actions reachable without covering fields. If an action is fixed, add matching scroll padding.
- Submit through the form so Enter/Go works; do not rely only on a button click handler.
- Move focus to the first invalid field and retain every valid value.

## Fixed navigation and safe areas

- Add bottom padding equal to the fixed navigation height plus `env(safe-area-inset-bottom)`.
- Keep touch targets about 44 CSS pixels or larger.
- Hide or demote global navigation in focused flows when it would compete with the task or be obscured by the keyboard.
- Test narrow widths, text zoom, landscape, and devices with browser chrome.

## Camera, microphone, location, and files

- Trigger permission prompts only from a direct user action.
- Explain the benefit before prompting and provide a non-permission alternative where feasible.
- Treat unsupported APIs, denial, dismissal, and interrupted capture as normal states.
- Do not assume camera/audio behavior is identical across in-app browsers, Safari, Chrome, and installed PWAs.
- Show selected file count, preview, replacement/removal, and upload/saved status.

## Drafts and persistence

- Persist a stable entity ID, current step, and safe draft values when interruption is likely.
- Scope drafts by user and entity; do not let one case's data appear in another.
- Version persisted data so schema changes can fall back safely.
- Clear drafts only after confirmed success or explicit discard.

## Implementation acceptance test

Verify on an actual narrow viewport:

1. Open home, collection, and detail through visible controls.
2. Start a linked task and confirm the selected entity is shown.
3. Enter text, trigger validation, and confirm values remain visible.
4. Move forward and backward between steps.
5. Use browser/system back and confirm the expected parent context returns.
6. Simulate denial/cancel for each requested permission.
7. Reach the final action with the keyboard and fixed navigation present.
8. Complete once and confirm the detail state/history updates without a duplicate.
