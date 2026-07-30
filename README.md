# NevkaR — Digital Business Card

**Live card:** https://cards.sharkitectdigital.com/nevkar/
**NFC / QR target:** https://cards.sharkitectdigital.com/nevkar/contact.vcf

Program the physical NFC card and the printed QR with the **`contact.vcf` URL**, not the card page.
GitHub Pages serves `.vcf` as `text/x-vcard`, so a tap or scan opens "Add Contact" directly with the
logo attached — no extra taps.

## Contact on the card

| Field | Value |
|---|---|
| Name | Noe Ceballos |
| Company | NevkaR |
| Phone | (816) 469-4380 |
| Website | https://nevkar-auto.vercel.app |
| Tagline | Buy it · Fix it · Tow it · Sell it |
| Services | Used Cars, Mechanic Shop, 24/7 Towing, Body & Paint |
| Area | Kansas City Metro (bilingual EN/ES — Se habla español) |

## Intentionally omitted (not fabricated)

Email, office street address, booking link, and job title. No data existed for these at build time.
They strip cleanly the same way the `_template` optional blocks do. **Backfill them in place**
(edit `index.html` + `contact.vcf`) when Noe has them — this is a normal update, not a rebuild.

## Files

| File | Purpose |
|---|---|
| `index.html` | The card page. Orange→blue accents match the NevkaR brand. |
| `contact.vcf` | vCard 3.0 with the logo embedded as `PHOTO`. **The NFC/QR target.** |
| `qr-code.png` | On-page QR modal image (points at `contact.vcf`), rounded modules + centered logo disc. |
| `logo.png` | Card logo, 640×640, transparent (from the client's circular mark). |
| `manifest.json` | PWA manifest for "Add to Home Screen". |

## Brand

`#F36A1B` (orange) / `#2F9FD8` (blue) — pulled directly from Supabase `company_profiles` /
the live NevkaR site (`nevkar-auto.vercel.app`), not re-sampled.

**Divider ornament:** small checkered-flag icon (kept true black/white for recognizability,
per the client's own "checkered-flag racing energy" brand identity — visible in the client's
logo itself), with a brand-orange drop-shadow glow.

## Related

- **HubSpot:** Company `334389993189` · Contact `521299966704`
- **Supabase brain:** `company_profiles` row `d1a07281-855e-4e49-a5c4-713c4f4d3a61` (`card_template_slug: "nevkar"`, `virtual_card_url` set on ship)
- Barter engagement (branding + bilingual site + Airtable ↔ truck repair) — see `projects/clients/nevkar/README.md`

---
Built by [Sharkitect Digital](https://www.sharkitectdigital.com)
