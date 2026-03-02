# Emailzap Design Language — v2 (Superhuman-Inspired)

**Status:** Active
**Version:** 2.0
**Updated:** 2026-02-28

---

## Core Philosophy

**"Step into a different product."**

When a user clicks "All Inboxes," Emailzap owns 100% of the right-side pane. This is not Gmail with a widget — it's a distinct, intentional product surface. The primary design inspiration is [Superhuman](https://superhuman.com): high contrast, near-black header, tight density, electric blue accents, and a split-pane email open flow that feels instant and purposeful.

**Three-word design brief:** Fast. Focused. Owned.

---

## What Changed from v1

| Dimension | v1 | v2 |
|---|---|---|
| Header | White, Gmail-like | Dark `#1c1c1e` — immediately signals ownership |
| Primary blue | `#1967d2` Google blue | `#0066ff` electric blue — brighter, more distinctive |
| Filter controls | Chip row (pill shape) | Tab strip — All / Important / Not Important |
| CTA location | Always visible chip | Conditional bar, only on "Not Important" tab |
| Email density | 54px rows | 48px rows — denser, Superhuman-standard |
| Email open | No open view | Split pane — list narrows, detail slides in |
| Settings | Preferences + Accounts | + Automations + Support + Danger Zone |
| Font weight feel | 500/700 mix | 600/700 in key surfaces — more confident |

---

## 1. Color Palette

### Brand / Interaction Colors

| Token | Hex | Usage |
|---|---|---|
| `--ez-blue` | `#0066ff` | Primary actions, active tab borders, reply button, links |
| `--ez-blue-light` | `#e8f0fe` | Active row tint, badges, selected state |
| `--ez-blue-deep` | `#0050cc` | Hover on blue buttons |
| `--ez-important` | `#f5a623` | Important indicator (⚡ icon), automation accents |
| `--ez-compose-bg` | `#c2e7ff` | Compose button |
| `--ez-compose-hover` | `#b3deff` | Compose button hover |

### Header (Dark Surface)

| Token | Hex | Usage |
|---|---|---|
| `--ez-header-bg` | `#1c1c1e` | Dark header bar — signals Emailzap ownership |
| `--ez-header-text` | `#f5f5f5` | Text on dark header |
| `--ez-header-muted` | `#8e8e93` | Icons and secondary text on dark |
| `--ez-header-hover` | `rgba(255,255,255,0.1)` | Icon hover on dark |
| `--ez-search-bg` | `rgba(255,255,255,0.08)` | Search input background on dark |

### Account Identity Colors (6 fixed slots)

| Token | Hex | Slot |
|---|---|---|
| `--ez-account-1` | `#1a73e8` | Account 1 — Blue |
| `--ez-account-2` | `#34a853` | Account 2 — Green |
| `--ez-account-3` | `#f9ab00` | Account 3 — Amber |
| `--ez-account-4` | `#ea4335` | Account 4 — Red |
| `--ez-account-5` | `#a142f4` | Account 5 — Purple |
| `--ez-account-6` | `#00bcd4` | Account 6 — Teal |

Each account gets one color slot, used consistently across: sidebar dot, email row dot, sender avatar background, and account card.

### Neutrals

| Token | Hex | Usage |
|---|---|---|
| `--ez-text-primary` | `#202124` | All primary text |
| `--ez-text-secondary` | `#5f6368` | Timestamps, counts, sub-labels |
| `--ez-text-muted` | `#80868b` | Placeholders, section headers (caps), disabled |
| `--ez-bg-base` | `#ffffff` | Main content pane, email list |
| `--ez-bg-surface` | `#f8f9fa` | Cards, settings panel sub-sections, email sidebar |
| `--ez-bg-hover` | `#f1f3f4` | Row hover, secondary button bg |
| `--ez-border` | `#e0e0e0` | Dividers, panel borders |
| `--ez-border-light` | `#dadce0` | Lighter dividers |

### Semantic

| Token | Hex | Usage |
|---|---|---|
| `--ez-danger` | `#ea4335` | Not Important badge, Remove button, Delete, Danger Zone |
| `--ez-danger-dark` | `#d33426` | Danger hover |
| `--ez-success` | `#34a853` | Online status dot |
| `--ez-not-important-bg` | `#fff4f4` | CTA bar background |
| `--ez-not-important-border` | `#fcd4d4` | CTA bar border |

---

## 2. Typography

**Font stack:** `'Google Sans', -apple-system, 'Helvetica Neue', Arial, sans-serif`

### Type Scale

| Role | Size | Weight | Color |
|---|---|---|---|
| Dark header search placeholder | 14px | 400 | `--ez-header-muted` |
| Dark header search input | 14px | 400 | `--ez-header-text` |
| Toolbar label | 13px | 400/500 | `--ez-text-secondary` |
| Filter tab (inactive) | 13px | 500 | `--ez-text-secondary` |
| Filter tab (active) | 13px | 600 | tab color (blue/amber/red) |
| CTA bar text | 13px | 500 | `--ez-danger-dark` |
| Email sender (unread) | 13px | 600 | `--ez-text-primary` |
| Email sender (read) | 13px | 400 | `--ez-text-secondary` |
| Email subject | 13px | 400 | `--ez-text-primary` |
| Email preview | 13px | 400 | `--ez-text-secondary` |
| Email timestamp | 12px | 400 | `--ez-text-secondary` |
| Nav label (sidebar) | 14px | 400/700 | `--ez-text-primary` |
| Account submenu | 13px | 400 | `--ez-text-primary` |
| Detail header subject | 15px | 600 | `--ez-header-text` |
| Detail meta name | 15px | 600 | `--ez-text-primary` |
| Detail body | 14px | 400 | `--ez-text-primary` |
| Settings section label | 11px | 500 | `--ez-text-muted` |
| Settings row label | 14px | 500 | `--ez-text-primary` |
| Settings row sub | 12px | 400 | `--ez-text-secondary` |
| Automation card title | 14px | 600 | `--ez-text-primary` |
| Automation card description | 13px | 400 | `--ez-text-secondary` |
| Sender avatar initials | 13–15px | 700 | `#ffffff` |

### Rules

- **Header is always 600+ weight** on text that matters (subject, sender name)
- **Read emails:** sender drops to 400 weight + `--ez-text-secondary` color
- **Section labels** in settings: 11px, uppercase, letter-spacing `0.08em`
- **Body copy** (detail pane): 14px / line-height 1.7 — readable

---

## 3. Spacing System

**Base unit: 8px**

| Token | Value |
|---|---|
| `--space-1` | 4px |
| `--space-2` | 8px |
| `--space-3` | 12px |
| `--space-4` | 16px |
| `--space-5` | 20px |
| `--space-6` | 24px |
| `--space-7` | 28px |

### Key Fixed Dimensions

| Element | Dimension |
|---|---|
| Gmail left sidebar | `256px` |
| Dark header bar | `52px` height |
| Toolbar | `40px` height |
| Filter tab strip | `36px` height |
| CTA bar | `40px` height |
| Email list row | `48px` height |
| Email list (narrow, email open) | `380px` width |
| Email detail pane | `flex: 1` |
| Email contextual sidebar | `220px` width |
| Settings panel | `400px` width |
| Sender avatar (list) | `34px` diameter |
| Sender avatar (detail) | `40px` diameter |
| Account dot (sidebar) | `10px` diameter |
| Account dot (email row) | `8px` diameter |
| User avatar (header) | `28px` diameter |

---

## 4. Border Radius System

| Component | Radius | Rationale |
|---|---|---|
| Compose button | `16px` | Pill-like, friendly |
| Search bar (dark header) | `24px` | Full pill — open/inviting |
| Email row hover | `6px` | Subtle, tighter than v1 |
| Email open (active row left border) | `0` | Left border indicator only |
| Filter tab strip | `0` | Tab paradigm — no rounding |
| Automation cards | `12px` | Card warmth |
| Settings panel | `16px 0 0 16px` | Left-exposed edge rounded |
| Account cards (settings) | `12px` | Consistent with automation cards |
| Confirmation dialogs | `16px` | Floating modal |
| Reply buttons | `8px` | Functional, not pill |
| CTA move button | `8px` | Consistent with reply buttons |
| Nav items (sidebar) | `0 20px 20px 0` | Gmail-native pill — unchanged |
| Account/sender avatars | `50%` | Perfect circle |
| Primary badge | `10px` | Compact label |
| Danger confirm input | `8px` | Form input standard |

---

## 5. Elevation & Shadow

**Principle:** Flat for content, minimal depth for panels, visible for dialogs.

| Surface | Shadow |
|---|---|
| Compose button (hover) | `0 1px 3px rgba(60,64,67,0.3)` |
| Settings panel | `0 4px 24px rgba(0,0,0,0.14)` |
| Automation card (hover) | `0 2px 8px rgba(0,0,0,0.08)` |
| Confirmation dialog | `0 8px 32px rgba(0,0,0,0.20)` |
| Email rows | none — background only |
| Email detail pane | none — border separation |

---

## 6. Motion

| Interaction | Duration | Easing | Notes |
|---|---|---|---|
| Email open (list narrow) | `250ms` | `ease` | flex/width transition |
| Email detail slide-in | `250ms` | `ease` | translateX + opacity |
| Nav submenu expand | `250ms` | `ease` | max-height |
| Chevron rotate | `200ms` | `ease` | CSS transform |
| Filter tab switch | `150ms` | `ease-in-out` | border-bottom color |
| Settings panel slide | `250ms` | `ease-out` | translateX |
| Settings backdrop fade | `150ms` | `ease` | opacity |
| Dialog appear | `200ms` | `ease-out` | scale(0.96→1) + opacity |
| Mark as Read feedback | `100ms` | `ease` | opacity on row |
| Toggle switch | `200ms` | `ease` | translateX on thumb |

**No spinner, ever.** If data isn't available: skeleton shimmer. Stale data while fetching.

---

## 7. Screen Inventory

### Screen A: Gmail (no Emailzap visible)
- Triggered by clicking "Inbox" in sidebar
- Emailzap injects nothing into the content pane
- Gmail renders natively with its own tabs and email list

### Screen B: All Inboxes — List View
1. **Dark header** (52px) — search bar + settings gear + user avatar
2. **Toolbar** (40px) — select all, mark as read, pagination
3. **Filter tab strip** (36px) — All | Important | Not Important
4. **CTA bar** (40px, conditional) — shown only on "Not Important" tab
5. **Email list** — 48px rows, account dot + avatar + inline sender/subject/preview

### Screen C: Email Open — Split View
- Email list narrows to `380px`
- Detail pane slides in: dark header + sender meta + body + reply bar
- Contextual sidebar (220px): Actions, Labels, From info

### Screen D: Settings — Main
- Sections: Preferences, Accounts, Automations, Support, Danger Zone
- Slides in from right (250ms), backdrop fade

### Screen E: Settings — Automations
- Sub-view within settings panel (back button)
- Active/Inactive automation cards with toggles

### Screen F: Delete Account
- 2-step: Warning → Type-to-confirm
- Confirm button disabled until user types "DELETE"

---

## 8. Component Reference

| Component | File Location | Key Classes |
|---|---|---|
| All Inboxes nav | mock.html | `.all-inboxes-row`, `.submenu`, `.submenu-item` |
| Dark header | mock.html | `.ez-header`, `.search-wrap`, `.search-input` |
| Toolbar | mock.html | `.toolbar`, `#select-all-cb`, `#mark-read-btn` |
| Filter tabs | mock.html | `.filter-tabs`, `.filter-tab`, `.active-all/.active-imp/.active-not-imp` |
| CTA bar | mock.html | `.cta-bar.visible` (JS-toggled) |
| Email row | mock.html | `.email-row`, `.row-dot`, `.row-avatar`, `.not-imp-badge` |
| Split pane | mock.html | `.split-pane`, `.email-list-pane.narrow`, `.email-detail-pane.visible` |
| Contextual sidebar | mock.html | `.email-sidebar`, `.esb-action`, `.esb-label-pill` |
| Settings panel | mock.html | `.settings-panel.visible`, `#sp-main`, `#sp-automations` |
| Automation card | mock.html | `.automation-card.active/.inactive` |
| Delete dialog step 1 | mock.html | `#delete-dialog-1` |
| Delete dialog step 2 | mock.html | `#delete-dialog-2`, `#delete-confirm-input` |

---

## 9. Accessibility

- All interactive rows and buttons: minimum `32px` height, `36px` preferred
- Focus outline: `2px solid var(--ez-blue)`, `2px offset`
- Color is never the sole differentiator — icons and labels always accompany color
- Account identity: dot + text label always present (never color alone)
- Dark header: contrast ratio verified for `#8e8e93` on `#1c1c1e` (AAA for large text)
- `prefers-reduced-motion`: all transitions disabled, only opacity fades
- Confirmation dialogs: focus trapped, keyboard navigable, `Escape` closes
- Delete confirm input: requires typing exact text — prevents accidental activation
