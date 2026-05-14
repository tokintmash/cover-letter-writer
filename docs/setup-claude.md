# Claude Setup

## Local Testing

Load this repository as a Claude plugin using your local plugin workflow, for example:

```bash
claude --plugin-dir .
```

Adjust the path to match where you cloned or created the repository.

Install the upstream humanizer skill separately:

```bash
mkdir -p ~/.claude/skills
git clone https://github.com/blader/humanizer.git ~/.claude/skills/humanizer
```

This plugin intentionally does not bundle a copied humanizer skill. Claude should use `https://github.com/blader/humanizer` as the humanizer source.

## Invocation Examples

Use the plugin namespace when available:

```text
/cover-letter-agent:cover-letter-writer
```

Use the upstream humanizer skill for the final polish pass:

```text
/humanizer
```

You can also ask naturally:

```text
Write a cover letter for @ads/company-role.md
```

## Reloading After Edits

Restart Claude or reload the plugin after editing `SKILL.md`, plugin manifests, or metadata files. Reinstall or update `~/.claude/skills/humanizer` when you want upstream humanizer changes.
