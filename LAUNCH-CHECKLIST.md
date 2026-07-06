# Launch checklist — revenue fixes branch

Everything on this branch is safe to merge as-is: the form falls back to a pre-filled
email if unconfigured, the booking button stays hidden until a URL is set, and the
case study is `noindex` until its figures are verified. Work through this list to
switch each piece fully on.

## 5-minute items
- [ ] **Form backend** — create a free form at https://formspree.io (or Basin/Getform),
      then in `index.html` replace `REPLACE_WITH_FORM_ID` in the form `action` with your
      endpoint (e.g. `https://formspree.io/f/abcdwxyz`). Until then the form opens a
      pre-filled email instead — nothing breaks.
- [ ] **Booking link** — create a Cal.com or Calendly event ("Sovereignty briefing — 30 min"),
      then in `index.html` replace `REPLACE_WITH_BOOKING_URL` on the `#enq-book` anchor.
      The button un-hides itself automatically once the placeholder is gone.
- [ ] **ABN + entity** — add to the footer of `index.html` (TODO comment marks the spot)
      and to `privacy.html` (two TODO comments). A privacy-compliance vendor without a
      visible ABN/privacy policy is a credibility self-own.
- [ ] **Form provider disclosure** — name the chosen form provider in `privacy.html`
      section 3 (TODO comment marks the spot).

## Higher-impact items
- [ ] **Founders / team** — add names, photos and LinkedIn URLs to the Proof section of
      `index.html`, and `sameAs` links (LinkedIn company page) to the JSON-LD `#org` node.
      Anonymity is the single biggest conversion killer for high-trust enterprise sales.
- [ ] **Case study numbers** — replace every `MEASURE` badge in
      `case-study-carbon-project.html` with verified figures (time records, supplier
      bills, ledger exports). Then: remove the `<meta name="robots" content="noindex">`
      line, add the page to `sitemap.xml`, and uncomment the case-study link in the
      Proof section of `index.html` (TODO comment marks the spot).
- [ ] **Collateral copy alignment** — regenerate the PDFs with two wording changes:
      1. "every Claude skill you use today" → "a full agentic skills library — skills,
         workflows and named agents — on local open-weight models, with consented burst
         to frontier models (e.g. Anthropic Claude) for the hardest tasks." Claude is a
         cloud API; claiming its skills ship on local hardware is a trademark/accuracy
         risk that savvy buyers will catch.
      2. R&DTI page: drop the template hypothesis and "the appliance can help fund
         itself" framing; mirror the language of `ai-rd-tax-incentive.html`
         (eligibility assessed case-by-case, registered tax agent prepares the claim,
         Omniscient provides the contemporaneous records). Avoids ACL s18 / promoter
         exposure and TASA issues.
- [ ] **Google Search Console** — verify the domain and submit `sitemap.xml`.

## What changed on this branch
- `index.html`: enquiry form + booking CTA (replaces bare mailto), nav + footer links to
  new pages, privacy link, FAQPage + Product JSON-LD, static "50" in the cost counter so
  crawlers see a real figure, TODO markers for ABN / team / case-study link.
- New: `appliance.html` (unified offer, tiers, pricing anchors), `security.html`
  (ungated CISO page), `sovereign-ai-melbourne.html` (SEO/AEO service page),
  `ai-rd-tax-incentive.html` (compliant R&DTI page), `case-study-carbon-project.html`
  (noindex until measured), `privacy.html`, `llms.txt`, expanded `sitemap.xml`.
