# SignalBrief

A tiny, source-first SDR account research assistant. Enter a company name and it produces a one-page prospect brief with a sourced company summary, news from the past 90 days where available, clearly labeled buying-trigger hypotheses, suggested personas, likely pains and short outreach openers.

## Why I built it

I am a finance graduate moving into tech sales. I built SignalBrief as an SDR interview portfolio project to show how financial research habits can support better account preparation without inventing company facts.

## How v1 works

- **Wikipedia REST API (English and Spanish)** supplies a company description because it is free, requires no key and links back to a public source. If the typed name is not an exact article title, a full-text Wikipedia search looks for the right company article (for example, both "Santalucía" and "Santa Lucia" resolve to the Spanish insurer's article).
- **GDELT DOC API** searches recent public news because it is free and supports date-bounded queries.
- **Transparent JavaScript rules** suggest personas and pains because a small v1 should be understandable rather than hide logic behind a paid black box.
- **GitHub Pages** hosts the app because it is free for a static portfolio project.

Facts and sales hypotheses are displayed separately. If the free sources do not verify a field, the app says "Not verified."

## Demo: Reale Seguros

The built-in demo is based on official Reale sources. It describes Reale Seguros as the Spanish non-life insurer in Reale Group, with almost 1,000 employees, 341 agencies and more than 1.5 million policyholders. It cites current company activity around electric-mobility education and a multilingual expat proposition. Suggested personas and pains are labeled as hypotheses, not company facts.

Demo sources:
- [Official Reale Group company profile](https://www.realegroup.eu/EN/corporate/the-group-and-corporate-bodies/insurance-companies/reale-seguros)
- [Official Reale Expats site](https://www.reale.es/expats/en)
- [Reale EV battery guide, 31 Jul 2026](https://blog.reale.es/cuanto-dura-la-bateria-de-un-coche-electrico/)
- [Reale electric handbrake guide, 3 Aug 2026](https://blog.reale.es/como-quitar-el-freno-de-mano-electrico/)

## Run locally

```bash
python3 -m http.server 8000
```

Open `http://localhost:8000`.

## Limits

- Wikipedia may not have a page for every company; when no article can be matched confidently, the app says so instead of guessing.
- GDELT coverage and browser access vary, so missing results do not mean there was no news.
- Personas, pains and buying triggers are research hypotheses that a salesperson must validate.
- v1 does not scrape LinkedIn, identify named contacts or send outreach.
