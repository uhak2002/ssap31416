# Domain Adaptation

Use this reference to translate the flow system without forcing every product into a finance-shaped interface.

## Choose destinations from recurring jobs

Derive navigation from frequency and user intent. Common mappings:

| Domain | Example primary navigation |
| --- | --- |
| Field service | Home, Jobs, Intake, Quotes, More |
| Healthcare | Today, Appointments, Records, Messages, More |
| Education | Home, Learn, Practice, Progress, More |
| Commerce | Home, Search, Cart, Orders, More |
| Logistics | Overview, Stops, Scan, Exceptions, More |
| Creator tools | Home, Projects, Create, Analytics, More |

These are starting points, not fixed templates. Remove destinations that are not recurring user jobs.

## Select the home-screen summary

Home should answer three questions:

1. What needs attention now?
2. What changed since the last visit?
3. What is the next useful action?

Use a compact stack such as urgent item, current workload, recent change, and contextual shortcut. Avoid presenting the complete sitemap on home.

## Match interaction to consequence

| Action type | Pattern |
| --- | --- |
| Browse or filter | Immediate, reversible response |
| Create a draft | Autosave with visible draft state |
| Submit or publish | Review screen and explicit confirmation |
| Pay, sign, prescribe, or approve | Show amount/scope/recipient and require strong confirmation |
| Delete or revoke | Explain impact and offer recovery when possible |

## Find the recurring entity

Many services become clearer when one recurring entity anchors related tasks:

| Domain | Entity hub | Related tasks |
| --- | --- | --- |
| Field service | Job/site | Record work, quote, collect, follow up |
| Healthcare | Appointment/case | Intake, consult, prescribe, schedule |
| Education | Course/lesson | Learn, practice, review, track progress |
| Commerce | Order | Pay, track, return, contact support |
| Logistics | Stop/shipment | Scan, navigate, record exception, complete |
| Consulting | Client/project | Intake, plan, deliver, invoice |

Keep the selected entity attached while the user moves into a related task. Return to its detail after completion so status, history, and the recommended next action can change.

## Use personalization responsibly

Helpful personalization includes recent items, unfinished work, saved preferences, and role-relevant shortcuts. Avoid inferring sensitive traits, hiding alternatives, or presenting ads as neutral recommendations.

## Separate mobile app and mobile web behavior

- Mobile app may use native bottom navigation, push notifications, biometric confirmation, and durable local drafts.
- Mobile web should account for browser chrome, safe areas, back navigation, permission prompts, install state, and intermittent media capture support.
- Preserve the same labels and conceptual route structure across both when they serve the same audience.

## Decide when not to use the pattern

Do not force persistent five-tab navigation onto a single-purpose landing page, a short checkout, a kiosk flow, or an expert desktop workspace whose main value is dense simultaneous information. Use the underlying clarity principles while selecting a more suitable shell.
