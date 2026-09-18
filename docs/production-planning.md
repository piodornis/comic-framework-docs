# Production planning foundation

Status: initial local foundation, `comic-production-standard-v0.1-draft`. Experimental planning schemas and templates exist; no executable Production Skills, rendering pipeline or print export is implemented.

## First increment

Follow the established repository pattern: reusable schemas, resources, project templates and a future skills directory. Production introduces format profiles rather than duplicating Design Style Packs. Detailed rules belong in `comic-framework-production/schemas/`; this page only explains integration.

Start with a format, total physical page count, binding constraints and reserved advertising. Derive the available Story pages before scripting. Use a default panel target and preserve explicit page exceptions for splash pages, pacing and dialogue needs. Advertising consumes physical space; it does not grant permission to shorten narrative content.

Production owns the physical slot map. Story keeps script pages, storyboard staging, narrative panel intent and reading flow. The issue plan links both numbering systems. Inserting an ad must trigger a page-turn/spread review rather than silently renumbering or rewriting the script. Design supplies approved identity when actual artwork begins; its absence need not block preliminary budget planning.

## Supplied format information

The supplied requirements file gives 170 × 260 mm and approximately 6.625 × 10.25 inches. These are distinct sizes. The foundation preserves a metric profile and a separate exact-inch conversion profile. Bleed and safe-area assumptions are explicit, and printer confirmation remains OPEN. The attachment is reference material, not authorization to export or apply all printing choices universally.

## Configurable extent

The planning draft accepts issue-specific total page counts, including 24 and 32 pages; four cover sides are included in these example totals. The owning framework now provides both examples. Page count is independent of format dimensions and must satisfy the selected product/binding constraints.

The generic 24-page example allocates 4 covers, 16 Story pages, 2 full interior ads and 2 editorial pages. Optional ads on three cover sides are already included in the cover count. Editorial reserves and cover advertising are project choices, not mandatory defaults.

A first planning pass may begin from unpaginated prose. Provisional budget IDs link to source paragraphs and a recorded revision; they do not claim that accepted Story pages exist. Story-page coverage remains OPEN until Story adapts and accepts the mapping. This distinction is now documented in the owning draft schema.

## Worked 32-page budget

The generic example allocates 32 physical pages: 4 cover sides, 26 Story pages and 2 interior ad pages. Three cover sides also contain ads, making five advertising sides in total. The panel default is five; one splash uses one and an action page uses seven, for 128 story panels. These are example choices, not fixed framework requirements.

Full-page, partial-page and cover advertising reservations include positions and asset/acceptance state. A partial ad shares one physical page with story content; it does not add another page. The draft requires explicit non-overlapping areas and a subsequent readability review.

## Cover, editorial and advertising functions

The creator-supplied US-comic structure notes are integrated as optional publication planning guidance in `comic-framework-production/schemas/publication-structure.md`. U1–U4 map to existing C1–C4 IDs. The framework tracks front-cover elements, imprint versus ad use on U2, preview/merchandise/ad choices on U3 and a full-page advertiser option on U4. Ad kind distinguishes house and third-party advertising; editorial content and splash credits receive explicit locations.

The suggested Story/ad/editorial page ranges are not independent quotas. With 32 total sides including covers, only 28 interior sides remain. Two illustrative reconciled budgets are 4 covers + 22 Story + 4 interior ads + 2 editorial, and 4 + 20 + 6 + 2. Cover ads are counted separately in the advertising inventory and never added to physical page totals again. The 24-page option remains available.

Single and double-page splashes may carry credits. A double-page splash occupies two facing physical pages but may contain one shared panel; it needs explicit shared-panel ownership, not a fictitious additional page or duplicate panel. Story decides narrative intent; Production manages allocation and lettering space.

## Storyboard-to-Production reconciliation

After provisional prose budgets, Story creates a separate `issues/<issue-id>/storyboard.md` with draft page/panel IDs, staging, image descriptions and text allocation. Production links each budget ID to a draft Story page and its physical slot; draft coverage does not imply creator acceptance. The original published prose remains unchanged.

For a text-faithful first pass, check that every source sentence is allocated once in source order. Silent panels may be inserted as explicit staging proposals. Count words to identify dense panels, then verify lettering in the actual page format; arithmetic is not a readability test. A shortened visual adaptation requires an explicit Story decision, not an automatic production-budget repair.

Review facing pages across ad insertions. The reader sees both sides of a spread together; a panel sequence cannot claim to hide a reveal already visible on the opposite page. Update the Production plan and project work overview when a draft storyboard is available, without treating completion as narrative/design/print approval.

## Adoption and next step

Add `production-project.md` and an issue plan to a comic project only when adopting the draft. Reference existing Story and Design records/revisions. No changes to those framework contracts are required.

Next validate a real issue's format choice, total page budget, advertising placement and panel exceptions with its script/storyboard. Then implement `comic-production-planner` using that experience. Rendering, lettering, correction and export follow in later increments. Plan acceptance is distinct from canon, Design approval and print readiness.

## Optional educational companion content

Projects may pair a comic with factual learning material. Keep a real-world educational glossary separate from the fictional canon glossary. Project-owned editorial records identify the issue, reserved physical slot, learning objective, spoiler boundary, evidence/source status and last factual review. This is descriptive integration guidance, not a new required contract field.

A printed knowledge note can link by readable URL and QR code to a stable, issue-specific web destination; an app may later reuse the content. Publication requires a working destination, checked references and no unresolved print placeholders. If the companion is not yet available, use an explicitly reviewed external reading list instead of promising nonexistent content. Reuse the existing editorial budget and track any later pagination change. Scientific evidence, editorial readiness and narrative canon are independent statuses.

## Lettering and print preparation — 2026-09-17

[Lettering and print workflow](lettering-and-print-workflow.md) documents the next project-level experiment: prior-layout intake, text-space planning, editable lettering, correction synchronization and review of an exact PDF revision. Story and Design now provide optional handoff guidance in their owning schemas. Human Park has prepared folders and templates. Its previous InDesign sample is now received with a first metadata/geometry intake and a researched printer-specification draft; geometry reconciliation, font/link checks, a native production template, importer and actual print test remain pending. This documents preparation without expanding the implemented v0.1 planning contract.
