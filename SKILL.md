---
name: toss-flow-design
description: "Design or improve mobile apps and responsive web apps using a Toss-inspired flow system: persistent navigation, summary-first home screens, card-based information hierarchy, one clear action per context, progressive disclosure, and trustworthy feedback. Use for user flows, information architecture, wireframes, UI specifications, prototypes, or frontend implementation across service domains. Do not use to copy Toss branding, proprietary assets, or screens pixel-for-pixel."
---

# Toss-inspired Mobile Flow Design

Turn any service into a mobile-first product that feels simple even when its underlying workflow is complex. Generalize the interaction logic; never imitate Toss trademarks, copy, illustrations, icons, motion, or exact layouts.

Use this skill as a flow system, not as a visual theme. Preserve the product's own brand, domain language, and design system.

The reusable rules are partly grounded in a real-device observation of the Toss Android app. Read [references/observed-toss-android-flow.md](references/observed-toss-android-flow.md) when the task benefits from concrete evidence about summary hierarchy, service discovery, search, keyboard/back behavior, incentives, or persistent navigation. Treat the observation as evidence, not as a stable specification or a screen-copying template.

## Start from the user's job

Identify:

- the user's most frequent job;
- the urgent or high-consequence job;
- the information needed before acting;
- the smallest action that creates visible progress;
- actions that require review, confirmation, or recovery.

If the domain is unfamiliar or high-stakes, verify its real constraints before designing. Preserve the user's chosen platform, technology, and business model.

## Build the product spine

Create a stable mobile navigation model with 3–5 destinations. Prefer:

1. a summary-first home;
2. one destination per recurring job;
3. a create/capture destination when creation is central;
4. a catch-all area for infrequent settings and secondary services.

Label destinations with the user's nouns or verbs, not internal department names. On responsive web, keep the same conceptual destinations while adapting navigation placement to viewport size.

Most operational products should connect a small set of reusable route types:

```text
Summary home -> collection/list -> entity detail -> focused task -> review -> result
                         ^              |                |
                         |              +-- related task-+
                         +---------- recovery/back -------
```

The entity detail is the contextual hub. When a user starts a related task, carry the selected entity into the task, show that context, and return to the same detail after completion. Do not make users reselect the customer, project, case, order, job, or record at every step.

Read [references/flow-patterns.md](references/flow-patterns.md) when planning routes, entity context, multi-step work, or completion behavior.

## Shape each screen

Apply these rules unless the domain requires otherwise:

- Lead with the current state or next useful action.
- Use large cards to group one topic, decision, or status.
- Give each card one dominant action; demote alternatives.
- Use strong title, concise explanation, and clear status hierarchy.
- Show summaries first and reveal detail through drill-down or “view all.”
- Keep persistent navigation stable across primary destinations.
- Personalize with recent, relevant, or unfinished work when data permits.
- Introduce new or promotional content without blocking core work; always provide dismiss or later.
- Confirm consequential actions and show immediate, specific feedback.
- Provide loading, empty, error, offline, permission-denied, success, and recovery states.

Avoid turning every item into a card. Use lists for repeated homogeneous records, cards for grouped summaries or decisions, and full-screen steps for focused input.

## Adapt the pattern to the domain

Read [references/domain-adaptation.md](references/domain-adaptation.md) when translating the system into a new industry or when deciding navigation labels, trust patterns, and primary actions.

## Design input flows

For multi-step forms or capture workflows:

- ask only what is needed for the next decision;
- group fields by user intent, not database structure;
- show progress when there are multiple meaningful steps;
- prefer device-native capture for camera, audio, location, and files;
- preserve drafts and make interruption recovery obvious;
- validate near the field and keep entered data after errors;
- place review before irreversible submission.

Use a full-screen focused flow for meaningful multi-step work. Keep the primary navigation visible only when it helps orientation; hide or demote it when it competes with a focused task. Provide an explicit back or close action either way.

For mobile web implementation, read [references/mobile-web-behavior.md](references/mobile-web-behavior.md) before implementing navigation, forms, camera/audio capture, or fixed controls.

## Trust and accessibility

- Distinguish view, edit, submit, pay, publish, and delete actions visually and verbally.
- Never use urgency, rewards, or personalization to obscure cost, consent, or risk.
- Do not expose personal or sensitive information unnecessarily in summaries or screenshots.
- Use adequate contrast, scalable text, touch targets of roughly 44 CSS pixels or larger, semantic controls, keyboard support, and visible focus.
- Do not rely on color alone for status.

## Deliverable

Match the artifact to the request. For planning or design work, provide:

- navigation map;
- primary happy path and important recovery paths;
- screen inventory with each screen's goal and dominant action;
- content hierarchy and component rules;
- state matrix for loading, empty, error, success, and permissions;
- responsive behavior when web is included;
- assumptions and validation questions.

For implementation, translate the same model into routes, components, state, and real responsive behavior. Reuse an existing design system when present instead of replacing it.

When the user asks to build rather than only plan, implement complete paths instead of disconnected screens. At minimum, verify one primary path from entry to completion and one recovery path using the real interface.

## Review before handoff

Check that a first-time user can identify where they are, what matters now, what the main action does, and how to recover. Ensure secondary features do not crowd the home screen, navigation labels remain stable, promotional surfaces are dismissible, and sensitive actions include proportionate confirmation.

For shipped mobile web or app flows, also verify:

- system/browser back and visible back return to a predictable prior context;
- reopening a linked task preserves its entity context;
- the software keyboard does not cover the active field or primary action;
- fixed navigation respects safe areas and does not cover scrollable content;
- validation retains entered values and points to the exact field;
- permission denial, cancellation, refresh, and interruption have recovery paths;
- completion changes the detail summary, activity/history, or next action immediately.
