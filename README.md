# SES Family — Customer Success Workboard (prototype)

A single-file, self-contained prototype of a Customer Success workboard for SES Family.
It covers portfolio triage, a per-account Customer Journey workflow, account-aware
recommendations, target-group reach, a municipality strategy layer, and document
generation.

## Running it

Open `index.html` in any modern browser (Chrome, Edge, Safari, or Firefox).
There is no build step and no server to run — it is one file.

Fonts (Raleway and Inter) load from Google Fonts when you are online; offline, the
tool falls back to system fonts and still works.

## What's inside

One self-contained `index.html`: HTML, CSS, JavaScript, and embedded data snapshots.
No dependencies, no package manager, no build pipeline.

## Features

- **Portfolio** — all municipalities, triaged by progress signal, with a focus/next-step
  column, sortable columns, a sticky header, and filters for country, stage, owner,
  size band, and tenure band.
- **Customer Journey workflow** (per account) — stage stepper, a "next best action"
  hero, readiness gates, progress signal, action plan, and an account-aware
  "Recommended for this account" panel.
- **Target group & reach** — SES reach against the municipality's own target group
  (Danmarks Statistik), with a one-year and a five-year window.
- **Strategy & rollout** — channels, focus areas, and the business case agreed with
  Sales; recommendations adapt to what a municipality has marked out of scope.
- **Document generation** — start-up agenda, status report, and other drafts,
  printable to PDF.
- **Guided CS assistant** — an offline, playbook-grounded helper.

## Data

- **Engagement exports (DK / SE / IS)** — real, snapshot dated 19 June 2026.
- **Danmarks Statistik municipal data (DK)** — real (population, divorce statistics,
  target groups, low income, origin, school absence). Sweden is pending.
- **Account and Salesforce-style fields** — real.
- **NPS and "Last contact"** — sample placeholders until live CRM and NPS sources are
  connected. These are marked as sample in the interface.
- **Recommendations** are grounded in the SES Customer Success playbook, not generated
  by an external model.

Reach is counted over a rolling window from the export date to match the target-group
window. The earliest user data is from autumn 2021, so the five-year window first takes
effect around September 2026.

## State and persistence

All input you make in the tool — action plans, signal selections, readiness gates,
strategy choices, and the business case — is held in the browser session only and
resets when the page is reloaded. There is no backend yet. The data is structured per
account so it can be wired to real storage when the prototype goes live; at that point
the site itself hosts and generates this data (it is not read from Salesforce).

## Data sensitivity — read before publishing

This file embeds **real municipality names, real usage figures, and real contact
person names** (with roles). There are no email addresses or phone numbers, but the
contact names and customer data are still sensitive.

**Use a private repository.** If the workboard needs to be shared publicly, an
anonymized build can be produced first (placeholder municipality and contact names,
scrubbed figures).

## Conventions

US English with American spelling. SES Family brand: deep green `#3F6553`, with Raleway
for headings and Inter for body and data.

## Roadmap

- Integrate the Sweden statistics workbook (same structure as the DK one).
- Add a per-year children flow so the one-year child target is a true annual figure.
- Wire session state to real storage at go-live.
- Continue refining the remaining recovery recommendation groups.
