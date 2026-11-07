# Reusable Flow Patterns

Use these patterns to turn domain workflows into connected mobile routes. Choose only the patterns the product needs.

## 1. Summary home

Home answers:

1. What needs attention now?
2. What changed?
3. What should I do next?

Prefer one next-action card, a short workload summary, recent or unfinished work, and a few contextual shortcuts. Do not duplicate the entire navigation or every feature on home.

## 2. Collection and filters

Use a list for repeated records such as appointments, jobs, orders, lessons, claims, or projects. Keep filters few, legible, and tied to real states. Each row should expose status and the smallest useful summary; open detail for decisions and secondary data.

## 3. Entity detail as a hub

The detail route should keep related work attached to one entity. It normally contains:

- identity and current status;
- the most important facts;
- one recommended next action;
- secondary related actions;
- a chronological history or recent activity.

When a related action starts, pass a stable entity ID rather than copying display text. Show a compact context strip such as “Connected order,” “Current patient,” or “Selected site,” with a deliberate change action.

After success, return to the detail route and update its status, history, and next-action card. This gives the user visible proof that the action had an effect.

## 4. Focused task

Split work into steps only when each step has a distinct user intent or decision. A useful shape is:

```text
Context -> inputs/capture -> review -> explicit completion -> result
```

Examples:

- consultation: person -> needs -> recommendation -> review;
- field service: site -> work note -> photos -> review;
- commerce: cart -> delivery -> payment -> confirmation;
- education: goal -> activity -> answer review -> progress;
- logistics: stop -> scan -> exception details -> completion.

Use short step labels, visible progress, local validation, preserved data, and a clear previous action. Avoid exposing the final submit action before the review state is ready.

## 5. Capture flow

For camera, audio, files, barcode, or location:

- explain why access is useful before the permission prompt;
- allow manual input or skipping when the domain permits it;
- preview captured data and allow replacement or removal;
- preserve other form data when capture is cancelled or denied;
- distinguish “captured locally,” “uploading,” and “saved.”

## 6. Completion and next action

Success feedback should name the completed action and its destination. Then offer one relevant next action, not a generic menu of everything possible.

Examples: “Quote saved to this job,” “Application submitted,” “Lesson complete,” or “Delivery issue recorded.” When appropriate, provide undo, edit, receipt, share, or return-to-detail.

## 7. Recovery paths

Design recovery alongside the happy path:

| Failure or interruption | Recovery |
| --- | --- |
| Required field missing | Preserve values, focus the field, explain the fix |
| Back during unsaved work | Save a draft or ask whether to leave |
| Permission denied | Explain settings/manual alternative without blocking unrelated work |
| Network loss | Keep a local draft and show retry/sync state |
| Duplicate submission | Disable while pending and make completion idempotent |
| Stale entity state | Refresh, explain what changed, preserve safe inputs |

## Mapping a new domain

Before naming screens, write the domain as:

```text
Actor -> recurring entity -> recurring job -> consequential action -> proof of completion
```

Use the user's vocabulary for each part. Then map it onto only the route types needed. Do not force finance language or a five-tab shell onto every product.
