# UI Change Verification Workflow

Use this workflow for visible UI work: layout, spacing, typography, color, interaction states, responsive behavior, design-system migrations, and asset-backed surfaces.

## Core Rule

Build the real surface, then inspect it visually. Static code success is not enough for UI quality.

## Workflow

1. Identify the owning component, style files, and visual reference.
2. Read local design-system rules before editing.
3. Keep production structure subordinate to the source app architecture; prototypes are visual references.
4. Make the smallest coherent UI change.
5. Run the app or preview surface.
6. Capture or inspect relevant sizes and states.
7. Check spacing, overflow, clipping, wrapping, contrast, focus, hover, active, disabled, loading, empty, and error states.
8. Fix and repeat when inspection fails.
9. Report exactly what was visually verified.

## Responsive Rule

Use container-based reflow when a component can be narrow inside a wide viewport. Use viewport media queries for page shell, global overlays, or full-window surfaces.

## Asset-Backed Rule

For generated images, sprite sheets, HUDs, canvas, or HTML prototypes:

- classify assets as structural, decorative, data-shell, or data-bearing
- keep live text and controls in the semantic UI layer
- do not ship baked placeholder data as production truth
- verify pixels or rendered output, not just DOM structure
- keep an honest fallback for narrow or degraded states

## Tool Use

MCPs, browser automation, design tools, and component registries can help inspect or generate first drafts. They do not replace the local design rules or screenshot loop.

## Checklist

- [ ] Visual reference identified.
- [ ] Owning files inspected.
- [ ] Real surface rendered.
- [ ] Relevant sizes and states inspected.
- [ ] Text is readable and does not overlap.
- [ ] Focus, hover, active, disabled, loading, empty, and error states considered.
- [ ] Final note names the visual verification performed.
