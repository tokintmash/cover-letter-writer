# Data Layout

## Expected Folders

Common private application workspace folders:

- `cv/` for the user's CV, profile, or background notes
- `examples/` for prior cover letters or style samples
- `recommendations/` for recommendation letters or third-party feedback
- `ads/` for job ads
- `output/raw/` for first drafts
- `output/final/` for application-ready letters

## Setup Flow

The user should:

1. Fill their CV and personal information in `cv/`.
2. Paste recommendation letter contents into files in `recommendations/`.
3. Add prior cover letter examples to `examples/`, if available.
4. Create one Markdown file per job ad in `ads/`.
5. Ask for a letter with a command such as `Write a cover letter for @ads/company-role.md`.

## Source Priority

Prefer:

1. Explicit user instructions in the current conversation
2. Project-local instruction files such as `AGENTS.md` or `CLAUDE.md`
3. The ad file explicitly referenced by the user
4. CV and background source files
5. Prior examples for tone and length
6. Recommendations for silent corroboration

## Missing Sources

If the ad file is missing or not readable, ask the user to create an ad file in `ads/` and paste the job ad contents into it.

If the CV is missing, ask for a CV or background summary before drafting.

If examples are missing, draft in a concise professional tone and say that no example style was available.

If recommendations are missing, continue without them. Do not imply third-party endorsement.

## Privacy

Do not publish or copy real CVs, recommendations, ads, generated letters, or identifying private details into public repositories. Use templates or placeholders when building reusable packages.
