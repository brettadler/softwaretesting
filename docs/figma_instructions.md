# Figma Make — System Guidelines

> Purpose: give Figma Make just enough direction to generate consistent, accessible, performant UI that matches our brand and codebase. Keep this file concise—rules over prose.

**How to use this file**
- Update the **Tokens**, **Components**, and **Do/Don’t** sections as our system evolves.
- If a rule conflicts with our design system docs, **design system wins**.
- When you add or change rules, update the **Changelog** at the end.

---

## 1) General Generation Rules

**Must**
- Prefer responsive layouts (Flex/Grid) over absolute positioning.
- Generate semantic HTML first; add ARIA only when semantics aren’t enough.
- Keep code composable: small components, single responsibility, clear props.
- Refactor as you go: remove dead code, deduplicate styles/vars.
- Performant by default: defer non-critical work, lazy-load heavy chunks, optimize images.
- Accessible by default: keyboard support, visible focus, 44×44 tap targets, WCAG AA contrast.

**Avoid**
- Inline styles for reusable patterns (use tokens/utility classes/vars).
- Magic numbers; use spacing/size/typography tokens instead.
- New colors or one-off shadows without tokens.
- More than 2 levels of nesting in CSS/variants.

**Never**
- Hardcode copy that should be localized.
- Use time-based animations for critical UX (e.g., to reveal errors).
- Ship components without tests for critical logic (forms, auth, complex state).

---

## 1.1 Target Framework & Language

- Generate **React 18 + TypeScript**.
- Prefer **Next.js (App Router)** when scaffolding routes.
- Style with **CSS variables + Tailwind** (if unavailable, use CSS Modules).
- Tests: **Vitest/Jest + React Testing Library**.
- Linting: **eslint** (incl. **eslint-plugin-jsx-a11y**, **typescript-eslint**) + **prettier**.

---

## 2) Project Structure & Conventions

- `/src`
  - `/app` — routes & pages
  - `/components` — reusable UI
  - `/features` — domain components + hooks
  - `/lib` — utilities (formatting, fetchers, analytics, logging)
  - `/styles` — globals, tokens bridge
  - `/types` — shared types/interfaces
  - `/icons` — SVG icons as React components

**File & naming**
- Components: `PascalCase.tsx`
- Hooks: `useThing.ts`
- Utilities: `thing.ts`
- Tests: `Component.test.tsx` (co-located)
- Stories: `Component.stories.tsx`
- Next.js routes: `page.tsx`, `layout.tsx`, `loading.tsx`, `error.tsx`

**Imports**
- Absolute from `/src` (e.g., `import { Button } from 'components/Button'`)

---

## 3) Design System Guidelines

> Our design system is **[YourBrand DS]**. Use tokens and components from this DS. When in doubt, pick the closest existing token/variant—do not invent new ones.

### 3.1 Tokens (authoritative)

**Typography**
- Base font size: **16px**; line-height: **1.5–1.7**

**Colors**
- Primary, secondary, danger, success, warning, background, surface, text, muted
- Contrast: **≥ 4.5:1** for text, **≥ 3:1** for UI elements

**Spacing (8px scale)**
- 0, 4, 8, 12, 16, 24, 32, 48 px

**Radii & Shadows**
- Small, medium, large radii; standardized shadows only

**Motion**
- Easing: `cubic-bezier(0.2, 0, 0, 1)`
- Durations: **120ms** (micro), **200ms** (standard), **320ms** (complex)
- Respect `prefers-reduced-motion`

### 3.1.1 Token & Variable Mapping

- Figma variables in the **`core/*`** collection are **source of truth**.
- Map Figma variables to CSS custom properties by lowercasing and replacing `/` with `-`.
  - Example: `core/color/primary/600` → `--color-primary-600`
- If a token is missing, choose the closest existing token and add `// TODO(token)`.

### 3.2 Layout Rules

- **Grid** for macro layout (pages/sections); **Flex** for micro layout (rows/columns).
- Page gutters: **32px** desktop, **16px** mobile.
- Content max width: **1200px** (up to **1440px** for data-dense views).

### 3.3 Component Usage Rules

- **Buttons**: one **primary** per view; others secondary/tertiary.
- **Links vs Buttons**: navigation = Link; actions = Button.
- **Forms**: labels required; inline validation; reserve space for errors.
- **Lists/Tables**: prefer pagination over infinite scroll; sticky table headers.
- **Empty states**: include a primary CTA + hint.
- **Icons**: use approved set; sizes **16**, **20**, **24** px.

---

## 4) Component Specs

### 4.1 Component Source of Truth

Use DS components by **exact** names:
`Button`, `Input`, `Select`, `Textarea`, `Checkbox`, `Radio`, `Switch`, `Card`, `Tabs`, `Modal`, `Tooltip`, `Toast`, `Table`, `Skeleton`, `Badge`, `Avatar`, `Breadcrumbs`, `Pagination`.

If a component is missing:
- Compose primitives; **do not** add new third-party UI libraries.
- Prefix provisional components with `Experimental*` and add a TODO for DS review.

### 4.2 Button

- **Variants**: primary, secondary, tertiary, danger, ghost, icon
- **Rules**
  - Exactly **one primary** per section.
  - Loading disables click; spinner to the **left** of label; width remains stable.
  - Icon buttons require an `aria-label`.

### 4.3 Text Input / Text Area

- External label (placeholder is **not** a label).
- Validation message below input; reserve space to avoid layout shift.
- Errors use danger color and polite live region on submit.

### 4.4 Select / Combobox

- If options ≤ **2**, use a segmented control (not a dropdown).
- Keyboard: arrows, typeahead, `Enter`, `Esc`.
- Multi-select shows chips with remove buttons.

### 4.5 Tabs

- For sibling content, not route navigation.
- Activate on **click** (not hover).
- Must have **visible focus ring**.

### 4.6 Card

- Padding: **16px** (mobile) / **24px** (desktop).
- Optional header with title + right-aligned actions.
- Elevation: **small** only; don’t mix multiple elevations in one group.

### 4.7 Table

- Sticky header; optional sticky first column.
- Column min width **120px**; truncate with tooltip for overflow.
- Client-side sort on visible columns; filters above; pagination below.
- Row actions in an overflow menu; primary action as a separate button in last column.

### 4.8 Standard UX States

- **Loading**: use `Skeleton` components; avoid spinner-only for content > 400ms.
- **Empty**: illustration/icon (optional), guidance copy, and a primary CTA.
- **Error**: concise title + remediation; include a **Retry** action when possible.

### 4.9 Form Validation & Submit

- Validate on **blur** and **submit**; show inline error text with `aria-describedby`.
- Disable submit until required fields are valid; on failure, focus first invalid field.
- Non-navigating success shows a toast; navigate on create/update when appropriate.

---

## 5) Accessibility (A11y)

- Keyboard: all interactive elements reachable in logical order; `:focus-visible` styles.
- ARIA: add roles/states only when semantics aren’t enough.
- Contrast: **WCAG 2.2 AA** minimum.
- Forms: associated labels; errors described via `aria-describedby`.
- Motion: provide non-animated alternatives for reduced-motion users.

### 5.1 A11y Test Requirements

- Add automated **axe** checks in component tests.
- Provide a documented **keyboard map** for Dialog/Modal, Menu, Combobox, Tabs, Tooltip.
- Include at least one **RTL** test for interactive components when text direction can change.

---

## 6) Theming (Light/Dark/High Contrast)

- Themes are toggled by `data-theme="light" | "dark" | "contrast"` on `<html>`.
- All colors resolve from tokens: `var(--color-*)`. **No hex values** in components.
- Provide a high-contrast theme (`contrast`) that meets **7:1** ratio for body text.

---

## 7) Data, State & API

- Fetchers in `/lib/api`; handle **loading/empty/error** explicitly.
- Prefer local UI state; lift to context/store only when shared across routes.
- Errors: actionable messages (what happened + next step); never raw stack traces.

### 7.1 Data Contracts & Validation

- Define request/response schemas with **Zod** in `/src/lib/schemas`.
- Validate all API inputs/outputs at boundaries; fail with typed errors.
- Provide **mock factories** in `/src/lib/mocks` and use them in stories and tests.

---

## 8) Content & i18n

- Tone: plain, concise, friendly.
- Sentence case in UI; Title Case for page titles only.
- Don’t concatenate translated strings; use interpolation placeholders.
- Format numbers/dates with locale-aware utilities.

### 8.1 Microcopy Patterns

- Error titles: concise noun phrases (“Payment failed”); body: next step first.
- Buttons: verb-first, present tense (“Save”, “Invite”, “Retry”).
- Empty states: outcome first (“Create your first project”), then how.

---

## 9) Performance Budget

- **LCP < 2.5s**, **CLS < 0.1**, **INP < 200ms** (targets).
- Images: responsive sources, width/height set, lazy-load offscreen.
- Defer non-critical scripts; code-split heavy components/routes.

---

## 10) Responsive & Supported Targets

- Breakpoints: **640 • 768 • 1024 • 1280 • 1536 px** (mobile-first).
- Devices: mobile ≥ **360px**; desktop ≤ **1920px**; degrade gracefully below 360px.
- Browsers: last **2** versions of evergreen (Chromium, Firefox, Safari).

---

## 11) Images & Media

- Prefer **SVG** for icons/illustrations; raster only for photos.
- Use responsive `<img srcset>` or framework equivalent; always set `width`/`height`.
- Optimize through the build pipeline; avoid base64 inlines > **2 KB**.

---

## 12) Security & Privacy

- Never log PII (email, phone, address, tokens); use redaction helpers in `/lib/logging`.
- Read secrets only from env (`process.env.*`). Never commit sample secrets.
- Sanitize any HTML/content from APIs to prevent XSS.
- For auth-gated UI, render skeleton while checking session; never flash protected content.

---

## 13) Analytics

- Fire events via `/lib/analytics` only.
- Event names: `page:view`, `entity:create|update|delete`, `ui:click`, `form:submit`.
- Include `component`, `variant`, and `screen_id` in event payloads.

---

## 14) AI Prompting Rules (for Figma Make)

**Always include in prompts:**
1. Goal (user task & outcome)
2. Data shape (keys, types, example)
3. Constraints (breakpoints, width, platform)
4. Components + allowed variants
5. Edge cases (empty/loading/error)
6. Acceptance criteria (a11y, perf, tests)

**AI Guardrails**
- If a required token/component is missing, **use the closest existing** and add a `// TODO(token|component)` comment—do **not** invent new primitives.
- Do **not** introduce third-party deps unless explicitly requested.
- Prefer reusing patterns already present in the repo.

**Example Prompt**
“Build a responsive ‘Team Members’ page. Use Grid (3 cols ≥1024px, 2 cols ≥768px, 1 col mobile). Card per member with avatar, name, role, email, and actions (Primary: Invite, Secondary: Message). Use Card, Button (primary/secondary), and Combobox to filter by role. Handle loading (skeleton), empty (Invite CTA), and error (retry). Respect tokens and dark mode.”

---

## 15) Do / Don’t (Quick Reference)

**Do**
- Reuse DS tokens & components.
- Ensure contrast & focus visibility.
- Build resilient responsive layouts.

**Don’t**
- Invent new colors or shadows.
- Use dropdowns for ≤ **2** options.
- Skip loading/empty/error states.

---

## 16) Governance & Handoff

- Branching: `feat/*`, `fix/*`, `chore/*`. One feature per PR.
- PR must include:
  - Screenshots (light/dark), keyboard path notes, a11y summary
  - Performance notes (bundle diff when applicable)
  - Checklist: tokens reused; states covered (loading/empty/error); tests passing
- Gates: at least one `@design-systems` **and** one `@frontend` approval.

---

## 17) Changelog

- _[YYYY-MM-DD]_ – Initial version consolidated with platform/process standards.
