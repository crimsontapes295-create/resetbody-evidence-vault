# ResetBody Evidence Vault

Responsive multi-page frontend prototype for an evidence-led fitness education brand.

## Pages
- `index.html` — landing page, verdict overview, featured claims, Muscle Ledger Lite form demo.
- `vault.html` — live search and verdict-filterable claims database.
- `claim-detail.html?id=protein-muscle` — reusable claim detail template populated from the local dataset.
- `methodology.html` — verdict definitions, certainty labels, and audit process.
- `privacy.html` — privacy-policy placeholder that must be replaced before launch.

## Run locally
No build step or package installation is required. Open `index.html` in a browser, or serve the folder locally for a more realistic production-like setup:

```bash
python -m http.server 8000
```

Then visit `http://localhost:8000` from this folder.

## Structure
```text
resetbody-evidence-vault/
├── index.html
├── vault.html
├── claim-detail.html
├── methodology.html
├── privacy.html
├── assets/
│   ├── app.js
│   ├── styles.css
│   └── brand.svg
└── data/
    └── claims.js
```

## Data model
Each entry in `data/claims.js` includes an ID, category, verdict, certainty, summary, plain-English takeaway, study design, population, limitations, citations, and an editorial review note. The detail template resolves a claim with the `id` query parameter. To add a claim, add a new object with a unique `id` and the same fields.

## Important pre-launch work
- **Research validation:** Verify each source, DOI/PMID, study design, population, and interpretation against the full paper. Review all verdicts and certainty labels with a qualified evidence reviewer. The starter dataset is educational prototype content, not a completed systematic review.
- **Source consistency:** The Nunes entry is intentionally a PubMed search landing page rather than an exact article DOI. Replace it with the exact verified publication before launch.
- **Lead magnet:** The signup form is intentionally a demo. Connect it to a consent-aware email service or backend and add the real tracker download/delivery flow before collecting email addresses.
- **Privacy/legal:** Replace `privacy.html` with a reviewed policy and implement appropriate consent, retention, unsubscribe, and security processes for your markets.
- **Production hardening:** Add automated tests, analytics only with appropriate privacy controls, CSP/security headers, deployment configuration, and an editorial review date/versioning workflow.

## Design and accessibility
- Manrope body type and DM Mono metadata (Google Fonts with system fallbacks).
- Responsive mobile menu, semantic page structure, accessible filter state, live result count, form status region, keyboard focus styles, and reduced-motion support.
- No frontend framework or runtime dependencies.
