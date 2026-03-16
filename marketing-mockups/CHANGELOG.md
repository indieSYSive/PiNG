# UI Mockup Change Log

> Running record of all changes across Steve & Jony hostile reviews.

---

## Review 1 — 7 Nits (Design Polish)

| # | File | Change |
|---|------|--------|
| 1 | home-v2.html | `.cal-evt` font-size 8px → 9px |
| 2 | project-unified-v2.html | `.kanban-col-header` font-weight 600 → 700, added `letter-spacing: 0.02em` + `background: var(--bg-elevated)` |
| 3 | chat-pane-v3.html | Sidebar toggle: rectangular tab (16x48px, border-radius 6px) → circular button (24x24px, border-radius 50%, box-shadow) matching Project's `.col-btn` |
| 4 | skills-v2.html | Aligned 12 CSS variables to canonical hex values: `--bg-hover`, `--bg-active`, `--border`, `--border-subtle`, `--accent-dim`, `--accent-glow`, `--green`, `--red`, `--yellow`, `--green-dim`, `--yellow-dim` + font stacks to `'Inter'` / `'JetBrains Mono'` |
| 5 | project-unified-v2, chat-pane-v3, skills-v2 | Sidebar width standardized to 220px (Project 210→220, Chat 230→220, Skills 200→220; Home already 220) |
| 6 | home-v2.html | `.resize-handle` opacity 0 → 0.25 (visible but subtle) |
| 7 | skills-v2.html | Scrollbar thumb `rgba(255,255,255,0.08)` → `var(--bg-active)` |

---

## Review 2 — 5 Nits (Token Hygiene)

| # | File | Change |
|---|------|--------|
| 1 | skills-v2.html | `--orange: #fb923c` → `#f5a623` (canonical); `--orange-dim` realigned |
| 2 | skills-v2.html | ~17 raw `rgba(255,255,255,...)` in body → tokenized (`var(--border-subtle)`, `var(--border)`, `var(--bg-active)`) |
| 3 | home-v2, skills-v2 | Added `--radius: 8px` to `:root`; added `--pink`, `--pink-dim`, `--blue`, `--blue-dim` to files that lacked them; added `--warm-accent-dim` to skills-v2 |
| 4 | all 4 files | Sidebar `border-right` unified to `1px solid var(--border-subtle)` |
| 5 | — | N/A (sidebar widths already standardized in R1) |

---

## Review 3 — 5 Nits (Interaction & Spacing)

| # | File | Change |
|---|------|--------|
| 1 | chat-pane-v3.html | Chat input border: `var(--border)` → `var(--border-subtle)` (1px solid), focus ring `var(--accent)` with `box-shadow: 0 0 0 1px var(--accent-dim)` |
| 2 | chat-pane-v3, skills-v2 | Sidebar active state: added `border-left: 2px solid var(--accent)` + `padding-left: 10px` (chat), `padding-left: 14px` (skills) |
| 3 | project-unified-v2, skills-v2 | Header bottom border: added `1px solid var(--border-subtle)` |
| 4 | home-v2.html | KPI card padding `12px 16px` → `16px 20px`; `.kpi-label` margin-bottom 2px → 4px |
| 5 | skills-v2.html | Skill card hover: added `border-color: var(--accent-dim)` + `box-shadow: 0 0 0 1px var(--accent-dim)` |

---

## Review 4 — Allan Feedback

| # | File | Change |
|---|------|--------|
| 1 | home-v2.html | Added sidebar resize handle (`#sidebar-resize` + `makeDraggable` JS) matching Project view pattern — drag edge to resize, min 140px, max 350px |
| 2 | home-v2.html | Removed `max-width: 1200px` from `.widget-grid` — widgets now fill all available horizontal space |
| 3 | home-v2.html | Widget resize now allows any column span 3–12 (was snapping to `[3,4,5,6,7,8,12]` only); added missing `.wg-9`, `.wg-10`, `.wg-11` CSS classes |
| 4 | project-unified-v2.html | Chat Details panel `col-btn` toggle fixed: `left:0` → `left:-12px` to match workspace/folders button positioning pattern; collapse/expand/resize all consistent |
| 5 | home-v2.html | Widget resize now silky smooth — pixel-level drag during move, snaps to grid column (3–12) only on mouse release; cursor + userSelect set during drag |
| 6 | home-v2.html | Added `col-btn` collapse toggle to sidebar (matching Project view pattern) — circular `«`/`»` button on right edge, with `.col-btn` CSS + `toggleSidebar()` JS |
| 7 | home-v2.html | Widget resize no longer shuffles other widgets — resizing widget is pulled out of grid flow (absolute positioned) with a hidden placeholder holding its slot; snaps back to grid on release |
| 8 | project-unified-v2.html | Moved detail panel controls container BEFORE `.chats-detail` (was after); `col-btn` toggle now sits on **left border** of Chat Details panel using `right:-12px` positioning — matches workspace/folders pattern exactly; removed ✕ header button (wrong approach) |
| 9 | project-unified-v2.html | Resize handles now subtly visible at rest: added `opacity: 0.25; background: var(--border-subtle)` to `.resize-handle` base state |
| 10 | project-unified-v2.html | Fixed Chat Details collapse: parent container gets `z-index:30` so `col-btn` click isn't swallowed; `.collapsed` changed from `width:0` hack to `display:none` (flexbox was ignoring width transitions); base removed `min-width`/transition — clean toggle now |
| 11 | home-v2.html | Fixed widget jumping to top-left on resize: added `position: relative` to `.widget-grid` so absolute-positioned widgets stay anchored to their grid position |
| 12 | home-v2.html | Topbar globe tooltip changed from "Globe view" to "Global Browser" — it opens the global browser, not a view |
| 13 | home-v2.html | Every project row now has hover-reveal action buttons: globe (open project browser) + `⋮` (more options) — `.proj-actions` with `opacity:0` on idle, `opacity:1` on `:hover` |
| 14 | chat-pane-v3.html | Message alignment: assistant messages left-aligned (`margin-right: auto`), user messages right-aligned (`margin-left: auto`, `max-width: 600px`) — removed `margin: 0 auto` centering |
| 15 | chat-pane-v3.html | "Jump to bottom" button enabled: removed `style="display:none"` — scroll handler shows/hides it automatically; button scrolls chat-area to bottom on click |

---

## Review 5 — Pending

_(changes will be logged here)_
