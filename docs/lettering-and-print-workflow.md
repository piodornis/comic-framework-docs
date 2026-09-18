# Lettering and print workflow — first integration step

Status: documented pilot workflow, 2026-09-17. The Production framework implements planning schemas/templates only. A native layout template, executable importer and verified print export are not delivered by this documentation.

## Ownership

| Information or decision | Owner |
|---|---|
| Exact wording, speaker, narrative order and adaptation acceptance | Story/project |
| Visual identity, reference roles, preservation anchors and design status | Design/project |
| Physical page map, final placement, typography, balloon geometry and printer settings | Production/project |
| Final release of an exact delivery revision | Creator or explicitly authorized project workflow |

The Story-side guidance is `comic-framework-story/schemas/lettering-handoff.md`; the Design-side guidance is `comic-framework-design/schemas/production-handoff.md`. Those repositories own their handoff details. This page connects them without introducing a universal CSV schema or a new Production status lifecycle.

## Working sequence

1. Record the selected layout application and collect an existing example if available. Preserve the original package and inspect a copy, noting application version, fonts, links, reference PDF and prior printer requirements.
2. Reconcile Story pages with physical slots and reserve text space in rough layouts before producing finished art.
3. Produce artwork with the agreed image/lettering separation. Keep intentional in-world text and approved integrated effects distinguishable from added dialogue/captions.
4. Derive the lettering list from a named Story revision. Use stable text IDs, speakers, reading order and source evidence; exact machine-readable fields remain project/Production-defined.
5. Assemble linked images, editable text and editable balloon/caption forms in the layout application. Final styling follows a tested project template.
6. Review the actual page size, facing pages and reading flow. Log text corrections and synchronize the Story/adaptation source, derived list and layout document.
7. Confirm the current printer's parameters. Check links, fonts, effective image resolution, bleed, colors, text overflow and export settings; inspect the exported PDF as a separate artifact.
8. Record release evidence for the exact PDF revision and archive its source/layout assets and settings. A checked layout does not automatically release an unchecked export.

## InDesign as one project implementation

A project already using InDesign can retain it as the final assembly/export application. Its pilot can use separate artwork, balloons, text, page elements and nonprinting guides, with reusable paragraph/object styles. These are implementation suggestions, not mandatory framework defaults. Native INDD/IDML structure and importer behavior must be verified against the supplied document and installed application version.

Automation follows the pilot: establish the template, define source IDs and object mapping, validate inputs, then implement first placement and controlled text updates. Reimport should preserve manual positioning and report local text conflicts. A completed documentation step is not evidence that any script has run or that a native template exists.

## Project-local artifacts

Possible locations beneath a project's declared Production root include `references/`, `templates/`, `indesign/` (only if relevant), and issue-specific `lettering/`, `artwork/`, `layout/`, `exports/review/`, `exports/print/` and `reviews/`. These are an optional pilot convention, not additions to the normative v0.1 planning structure. Retain existing paths and document alternatives rather than migrating automatically.

Projects record source revisions, exact asset references and release evidence. Decide large-file storage explicitly before adding heavy binaries; no automatic Git LFS migration. Record font availability and license constraints rather than assuming all fonts may be redistributed. Prior print presets are examples, not current printer approval.

## Decisions intentionally open

The framework does not choose a universal trim size, bleed, font, minimum text size, color profile, image-resolution threshold, PDF variant or printer. It does not require InDesign or define final-asset status enums. These need project choices and evidence from real layout/print tests.

## Current pilot evidence

Human Park has project-local workflow documentation, directories, empty lettering/asset/change templates and print/review checklists. Its previous InDesign example has been received and an initial metadata/geometry intake and provider-source specification have been recorded (2026-09-17). Native and PDF geometry differ and require reconciliation; complete font/link validation remains pending. No native template, importer or print PDF has been created by that preparation. Its physical slots, page counts, dimensions, IDs and visual identity are not reusable defaults.

Next: reconcile the example geometry, verify links/fonts and the selected printer configuration, document reusable conventions, exercise a representative spread and text-dense page, then implement and verify the smallest useful import. Formalize reusable Production schemas only after the pilot provides evidence.

## Printer evidence and legacy-layout comparison

Production now owns optional guidance in `comic-framework-production/guides/printer-specification-intake.md`. It separates provider-published claims, project proposals, calculated geometry and requirements confirmed for an exact configuration. Country/product-specific conflicts remain explicit; a printer's values do not replace reusable defaults automatically. Native page geometry and PDF page boxes are checked independently before adopting a template. Historical example settings and requirements for the next job remain separate project records.
