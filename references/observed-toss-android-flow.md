# Observed Toss Android Flow

This reference records a privacy-minimized Mobile MCP exploration of the Toss Android app on a real Galaxy device on 2026-11-06. It contains interaction evidence for generalization, not proprietary assets, exact layouts, financial data, or instructions to reproduce Toss.

## Scope and boundary

Observed safe, view-only paths:

```text
Biometric gate -> Home -> All -> Search -> Back -> Back -> All
                           |
                           +-> Benefits tab
```

No transfer, payment, account creation, application, balance detail, personal profile, or other consequential financial flow was opened. Names, balances, points, account identifiers, and personalized amounts were excluded from the record.

The app can change after this observation. Re-observe current behavior when the exact contemporary product matters.

## Home

Observed structure:

- biometric authentication appears before the signed-in home;
- a persistent five-destination bottom navigation anchors primary areas;
- the top area provides a small set of utilities such as notifications and QR-related actions;
- the body leads with account or status summaries rather than a feature directory;
- each summary exposes a contextual action near the information it affects;
- related categories are grouped behind a compact “view all” style action;
- spending, status, and credit-related summaries appear as separate vertical modules;
- promotional or reward content can appear inline and includes a dismiss control.

Generalize this as:

1. make the home a personalized status dashboard;
2. pair each status with one nearby action;
3. defer the full service catalog to a catch-all destination;
4. keep promotional content dismissible and visually distinct from core records.

Do not generalize the financial nouns, the exact number of modules, or the five-tab count when another domain has fewer recurring jobs.

## All-services destination

Observed structure:

- quick category shortcuts appear first;
- recently used services are surfaced before the full catalog;
- recommendations are separated from the service directory;
- the complete catalog is grouped by domain rather than shown as one flat list;
- search, support, settings, and profile entry points remain easy to find;
- primary bottom navigation remains visible and preserves the selected state.

Generalize this as a secondary discovery layer. Put recent and likely tasks before the long tail, keep recommendations labeled, and provide search when the catalog exceeds what users can scan quickly.

## Search and back behavior

Observed behavior:

- opening search focuses the text field immediately;
- the software keyboard opens with the focused field;
- popular searches provide useful starting points before typing;
- the first Android system Back dismisses the keyboard while preserving the search screen;
- the second Back returns to the All-services parent;
- the parent destination remains selected after return.

Generalize this as layered back handling:

```text
transient input layer -> focused child screen -> parent destination
```

Dismiss the most transient layer first. Preserve the user's context instead of jumping to home or exiting the app. Apply the same order to open keyboards, menus, sheets, dialogs, and nested routes where platform conventions support it.

## Benefits destination

Observed structure:

- the user's current reward or point state appears near the top;
- offers are grouped into vertically scannable modules;
- repeated opportunities use list rows with a concise label, value, and one action;
- advertising is explicitly marked;
- the primary bottom navigation remains stable.

Generalize this as state-first incentives: show what the user already has or can do now before promotional inventory. Keep one action per offer, label commercial content, and do not use countdowns or personalization to obscure cost, consent, eligibility, or risk.

## Reusable acceptance checks

When applying these observations to another app or mobile web product, verify:

- home communicates current state before exposing the full catalog;
- a catch-all destination organizes the long tail without crowding home;
- recent tasks and search reduce catalog navigation effort;
- primary navigation selection survives child-screen round trips;
- Back dismisses keyboard or overlay before leaving its screen;
- recommendations and ads are distinguishable from user-owned records;
- personalized summaries do not expose sensitive data unnecessarily;
- each summary, list row, or offer has one dominant action;
- the product uses its own language, brand, components, and visual proportions.
