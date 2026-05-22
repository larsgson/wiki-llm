# LLM Wiki — Faith, Creation Care & Pastoralism

An Obsidian vault and AI-assisted knowledge base covering three interconnected domains: the Five Marks of Mission, Creation Care, and Nomadic Pastoralism. Built using the [Karpathy LLM Wiki pattern](https://www.mindstudio.ai/blog/andrej-karpathy-llm-wiki-knowledge-base-claude-code) — raw sources go in, structured cross-referenced wiki pages come out.

## How It Works

1. Drop source documents (`.docx`, `.md`, `.pdf`) into `raw/`
2. Ask your AI assistant to ingest them
3. The AI reads the source, fetches external links, and compiles structured wiki pages under the appropriate topic
4. External resources are summarised in the AI's own words (never copied) with the original URL kept as canonical reference
5. All fetched URLs are logged in `wiki/source-registry.md`

## Structure

```
raw/                          # Source documents (immutable — never edited)
wiki/                         # AI-managed wiki pages
  index.md                    # Master index
  source-registry.md          # Tracks all fetched external URLs
  Five Marks of Mission/      # Topic 1 — proclamation, service, justice, creation care
  Creation Care/              # Topic 2 — ecosystems, biodiversity, stewardship
  Nomadic Pastoralism/        # Topic 3 — mobility, commons, indigenous knowledge
.obsidian/                    # Obsidian vault config
```

## Browsing

Open the root folder as a vault in [Obsidian](https://obsidian.md/). All `[[wikilinks]]` resolve to pages within the vault. The Homepage plugin opens `wiki/index.md` on startup.

## Conventions

All wiki conventions — page formats, naming rules, ingest workflow, source handling — live in `CLAUDE.md`. This file is read automatically by Claude Code. **If you use a different AI tool** (Cursor, Copilot, Gemini, etc.), feed `CLAUDE.md` to your tool at the start of each session so it follows the same rules.

Key rules:
- The three top-level topics are fixed and must not be renamed or restructured
- Subfolder structure under each topic is flexible — only add subfolders when they help
- External content is never stored verbatim (copyright) — only AI-generated summaries with source URLs
- Every fetched URL is logged in `wiki/source-registry.md` with status, date, and focus
- `raw/` is immutable — source documents are never modified after being added

## Contributing

This project will soon support multi-user collaboration. See `ROADMAP.md` for the planned workflow. Until then, contributions are managed by a single maintainer.

When multi-user mode is active:
- Work on a named branch (`yourname/topic`)
- Open a PR to `main` — no direct pushes
- Check `wiki/source-registry.md` before ingesting to avoid duplicate work
- Review PRs for content contradictions and overlapping summaries
