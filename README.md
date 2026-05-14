# Cover Letter Agent

Reusable Codex and Claude workflow for drafting tailored cover letters.

This repository contains public workflow logic, templates, and sanitized examples only. It does not include real CVs, recommendation letters, job ads, generated cover letters, or identifying personal data.

## What This Provides

- `cover-letter-writer`: drafts fact-based cover letters from a job ad, CV, prior examples, and optional recommendation material.
- Plugin metadata for Codex and Claude.
- Starter templates for private CV, recommendation, and job ad source files.

For a dedicated humanization pass, install the upstream `humanizer` skill separately from:

```text
https://github.com/blader/humanizer
```

This repository does not republish that skill.

## Recommended Workspace

Keep this repository public and reusable. Keep personal application material in `my-applications/`, or in a separate private workspace with the same shape:

```text
my-applications/
├── ads/
├── cv/
├── examples/
├── recommendations/
└── output/
```

Fill it like this:

1. Add your CV and personal information to `cv/`.
2. Paste recommendation letters into Markdown files in `recommendations/`.
3. Add prior cover letter examples to `examples/`, if you have them.
4. Create a new Markdown file in `ads/` for each job and paste the full ad contents into it.
5. Ask the agent to write a letter for that ad file.

Example:

```text
Write a cover letter for @ads/company-role.md
```

The writer skill will use the referenced ad file, then look for supporting source material in sibling folders such as `cv/`, `recommendations/`, `examples/`, and `output/`.

## Install For Codex

Clone this repository:

```bash
git clone https://github.com/your-name/cover-letter-agent.git
cd cover-letter-agent
```

Install the writer skill by copying or symlinking it into Codex's skills directory:

```bash
mkdir -p ~/.codex/skills
ln -s "$(pwd)/skills/cover-letter-writer" ~/.codex/skills/cover-letter-writer
```

If you prefer copying instead of symlinking:

```bash
mkdir -p ~/.codex/skills
cp -R skills/cover-letter-writer ~/.codex/skills/
```

Install the upstream humanizer skill for Codex:

```bash
mkdir -p ~/.codex/skills
git clone https://github.com/blader/humanizer.git ~/.codex/skills/humanizer
```

Restart Codex after installing new skills.

### Codex Usage

From `my-applications/` or your private application workspace, ask:

```text
Write a cover letter for @ads/company-role.md
```

For a separate polish pass:

```text
Use $humanizer to rewrite this draft without changing its facts.
```

## Install For Claude

Clone this repository:

```bash
git clone https://github.com/your-name/cover-letter-agent.git
cd cover-letter-agent
```

Load it as a Claude plugin using your local plugin workflow, for example:

```bash
claude --plugin-dir .
```

Install the upstream humanizer skill for Claude:

```bash
mkdir -p ~/.claude/skills
git clone https://github.com/blader/humanizer.git ~/.claude/skills/humanizer
```

Restart or reload Claude after installing new plugins or skills.

### Claude Usage

Use the plugin namespace for drafting:

```text
/cover-letter-agent:cover-letter-writer
```

Use the upstream humanizer for the polish pass:

```text
/humanizer
```

You can also ask naturally from `my-applications/` or your private application workspace:

```text
Write a cover letter for @ads/company-role.md
```

## Starter Files

The `my-applications/` directory contains sanitized starter files:

- `my-applications/cv/cv.template.md`
- `my-applications/recommendations/recommendation.template.md`
- `my-applications/ads/ad.template.md`
- `my-applications/examples/example-letter-en.template.md`
- `my-applications/examples/example-letter-ee.template.md`

Copy or rename these files inside your private workspace and fill them with your real material there.

## Privacy

Before publishing or sharing a fork, confirm that the repository does not contain:

- Real CV content
- Recommendation letters
- Job ads tied to a private application
- Generated cover letters
- Personal identifiers or private background notes

See `docs/privacy-model.md` for the intended boundary.
