# Codex Setup

## Install

Place this repository where your Codex environment can load local plugins, or copy the `skills/` directory into your Codex skills directory.

Keep real application materials in a separate private project, not in this plugin repository.

## Invocation Examples

```text
Write a cover letter for @ads/company-role.md
```

```text
Use $humanizer to rewrite this draft without changing its facts.
```

The `humanizer` skill is not bundled here. Use a compatible local install of `https://github.com/blader/humanizer` if your Codex setup supports it, or let `cover-letter-writer` do the final polishing pass itself.

Natural language requests such as "Draft a cover letter for this backend role using my CV and examples" should also trigger the writer skill when installed.

## Reloading After Edits

Restart or refresh the Codex session after changing skill metadata so the updated descriptions and prompts are available.
