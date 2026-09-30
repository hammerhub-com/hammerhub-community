# HammerHub Community

Public repo. Feedback intake for HammerHub products: GitHub Discussion categories with forms, and docs. No application code.

Players only ever use Discussions. Issues are maintainer-only: we open one ourselves (or convert a discussion) once a report is accepted. Never point players at the Issues tab.

Branding: HammerHub is the engine, not a consumer product. Old World Rankings is the only HammerHub product so far, so user-facing copy names "Old World Rankings" (and its Battle Builder) and treats HammerHub as the engine behind it. The repo name and structure stay generic so later products slot in. When a second product launches, add a product dropdown to the forms and a category per product rather than forking the repo.

Everything here is public. Never add Jira links, credentials, internal ticket numbers, user emails or private repo details to any file, issue or discussion.

## Layout

- `.github/DISCUSSION_TEMPLATE/`: one form per category, named by category slug (`data-issues.yml`, `bugs.yml`, `ideas.yml`, `q-a.yml`).
- `README.md`: reporter-facing. Keep it short and free of internal process.

## Prefill contract

The builder links here from `feedbackOptions.ts` in the OWR Rails repo (`app/frontend/components/hh_builder/`). Links prefill form fields by query string, keyed by field `id`:

`.../discussions/new?category=data-issues&platform=iOS+app&content_version=2026.09.30`

Renaming or removing a field `id`, a template filename (which must equal the category slug), or a category slug silently breaks those links. Change them here and in `feedbackOptions.ts` together. Prefill works on `input` and `textarea` fields. Dropdown prefill did not work when tested, so prefillable fields are inputs.

## Labels

`data` and `bug` are applied by the discussion forms and must exist as repo labels, otherwise GitHub drops them silently. `needs-triage` is for maintainers.

## Style

- No em dashes.
- Keep forms short. Required fields only where a report is useless without them.
- Plain, friendly wording aimed at players, not developers.

## Triage

Read the discussion, ask follow-ups in the thread, then create the internal ticket. Convert to an Issue only when the work should be tracked publicly. Reply on the discussion when the fix ships. Do not reference internal tickets in public threads.
