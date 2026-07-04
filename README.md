# Unhidden — The Index

> The lifetime structural cost of being a woman, made visible.

The Index is the free, public, citation-backed calculator at the center of **Unhidden**, a pay equity platform. It's not a lead magnet — it's the thesis. Everything else Unhidden builds (the Employer SaaS, the Verified certification) exists to close the gap this calculator measures.

Formerly named **Eqly** — some files and legacy references still carry the old name during the transition.

---

## Live

- 🇸🇪 Swedish: `eqly_index_sv.html`
- 🇬🇧 English (UK/US/Canada/Europe): `the_hidden_cost_of_being_a_woman.html`

Hosted on GitHub Pages. *(Confirm/update these links once the pages are live under their final paths.)*

---

## What it does

Six cost categories — pay, career, parenthood, health & body, safety, and (in the Swedish version) an enforcement-gap section for what happens when a system that claims equality doesn't deliver it. Each category:

- Has a name, plain-language description, and a **cited source** (government statistics, peer-reviewed research, or named public agency)
- Is either a fixed lifetime estimate (`base`) or computed live from user inputs like salary and years worked (`dynamic`)
- Can be toggled on/off, since not every cost applies to every woman

The Swedish version also carries a `verified_matrix` layer — a set of legal/structural "levers" (real, actionable rights a person can exercise, like filing for omvårdnadsbidrag or triggering a lönekartläggning) that are verified against primary legal sources before they're enabled. See `verified_matrix.json` and `DECISIONS.md` for how that verification process works.

---

## Tech

Static HTML/CSS/JS. No framework, no build step, no backend, nothing stored or transmitted client-side. This is a deliberate, fixed architectural choice — fast iteration and zero GDPR complexity — not a placeholder waiting to be "upgraded" to a framework.

**To run locally:** just open the HTML file directly in a browser, or serve the folder:

```bash
python3 -m http.server 8000
```

No dependencies to install.

---

## Repo structure

```
/                    → the Index (this file's home) — Caroline owns
/employer-app/       → Unhidden for Employers (Python SaaS) — not yet built
/docs/               → shared reference: pitch doc, concept paper, DECISIONS.md
```

See **`DECISIONS.md`** for what's already been decided, who owns what, and what's still open. If a technical question isn't answered there, it's genuinely undecided — open a GitHub Issue rather than guessing.

---

## Sources & accuracy

Every cost category cites its source inline (Medlingsinstitutet, Försäkringskassan, Socialstyrelsen, peer-reviewed studies, etc.). Legal claims specifically are verified against primary sources (riksdagen.se, do.se, government agencies) before being enabled — see `verified_matrix.json`. If you spot a source that looks outdated or a legal citation that looks wrong, please open an Issue; accuracy is the entire credibility model this project runs on.

---

## Contributing

This repo is currently maintained by the Unhidden founding team. If you're joining as the Employer SaaS developer, start with `DECISIONS.md` — it's written to give you working independence in `/employer-app` without needing to sync on every call.

---

## License

Content and calculation logic © Unhidden. The public Index is free to use and share — if you cite figures from it, please credit Unhidden and link back to the live calculator.
