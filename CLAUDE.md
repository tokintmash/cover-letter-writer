# Cover Letter Writer

## Purpose

This is a public plugin and skill repository for drafting tailored cover letters. Keep the repository reusable and free of private application material.

## Public Repository Boundary

Allowed:

- Skill instructions
- Plugin manifests
- Sanitized templates
- Sanitized examples
- Setup and privacy docs

Not allowed:

- Real CV content
- Real recommendation letters
- Real job ads
- Generated cover letters
- Identifying personal details
- One-user-specific career facts

## Workflow To Preserve

The intended user flow is:

1. Fill CV and personal information in `cv/`.
2. Paste recommendation letters into `recommendations/`.
3. Add prior examples to `examples/`, if available.
4. Create an ad file in `ads/` and paste the full job ad into it.
5. Ask for a cover letter with:

```text
Write a cover letter for @ads/company-role.md
```

The agent should use the referenced ad file and then read supporting material from the sibling folders.

## Cover Letter Rules

1. Never invent facts.
2. Use only claims supported by the user's CV, personal information, examples, recommendations, job ad, or current prompt.
3. Research the company before drafting unless the user explicitly opts out.
4. Research values, culture, product or service, customer segment, and role context.
5. Map company signals to the user's source material and bring out real overlap naturally.
6. Write in the same language as the job ad unless the user asks otherwise.
7. Match the user's prior examples for tone and approximate length when examples exist.
8. Use recommendations as background support only. Do not quote or directly reference them unless asked.
9. For specialist or individual-contributor roles, do not emphasize leadership or management unless the ad explicitly asks for it.
10. Remove em dashes and other obvious AI writing patterns before finalizing.

## Company Research

Company research is required. Look for:

- Values or mission
- Product or service
- Customer segment
- Industry and business model
- Careers-page tone
- Culture and collaboration signals
- Recent credible context when relevant

Use research to shape emphasis. Do not list values mechanically or overpraise the company.

## Humanization

This repository does not bundle the humanizer skill. Use the upstream `humanizer` skill from `https://github.com/blader/humanizer` when installed.

Claude polish command:

```text
/humanizer
```

If the upstream skill is unavailable, manually humanize the draft while preserving facts.

## Repository Maintenance

When editing this repo:

- Keep `skills/cover-letter-writer/SKILL.md` concise and procedural.
- Put detailed guidance in `skills/cover-letter-writer/references/`.
- Keep setup instructions in `README.md` and `docs/`.
- Do not bundle a copied local humanizer skill.
- Keep starter files under `my-applications/` sanitized.
