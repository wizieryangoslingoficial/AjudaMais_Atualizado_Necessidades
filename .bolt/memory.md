# Project memory

## Product intent & audience

- Web app focused on donations (money and items), accessed by mobile and desktop users.
- Forms include: donor fields (name, phone, email, address, city), preset money values (R$ 20–500), payment methods (Credit Card and others), item categories with quantity counters.

## Brand personality & voice

- Direct, practical communication in Portuguese.
- Honest about testing limitations (no browser in the environment; static validation).

## Visual design & UX direction

- Breakpoint main: 760px (mobile ≤760px, desktop >760px).
- Mobile widths to test: 320px, 360px, 375px, 390px, 430px; plus sub-breakpoint at ≤420px.
- Responsive via CSS media queries only, appended to `frontend/css/home.css`.
- Grids collapse on mobile: item categories 4→2 cols, counters 2→1 col, form 2→1 col, presets 5→3 (≤420px: 2), payment 3→1 col inline icon+text.
- Touch targets: + and − buttons enlarged to 40px on mobile.
- Primary action ("Confirmar Doação") full-width on mobile, below total value.
- Internal paddings reduced on mobile (32px → 22/16px; ≤420px → 18/12px).
- Category/payment labels at 12px must stay readable.
- Hard rule: never hide fields, categories, items, options, or buttons to make layout fit.
- Quantity counters and add/remove buttons must remain fully functional.

## Decisions, constraints & rationale

- CSS-only fixes preferred; do not touch JS/HTML/backend unless necessary — `home.js` generates forms and controls counters, must stay intact.
- Desktop layout must remain byte-identical (no regressions).
- Forms must be fillable and submittable on mobile.
- Runtime: Windows 10, VS Code, Live Server or existing Express server; CSS served as static file, no new config needed.
- `.bolt/prompt` currently empty — no global instructions to reference.

## Open questions & assumptions

- Real visual validation pending: no browser available in environment, validated only via static analysis (selector matching, specificity, brace balance).
- Assumption: existing `home.js` inline styles (`padding: 28px 32px`, `32px`, `0 32px`) match the selectors targeted by the new media queries.
- May need further tweaks if any section looks cramped at specific widths after real device testing.