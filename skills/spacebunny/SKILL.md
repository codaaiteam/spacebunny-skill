---
name: spacebunny
description: Offload huge-context work to Space Bunny Alpha, an LLM with a 1,000,000-token context window, when a task is too big for your own context — analyzing a whole repository or monorepo, a long document, hours of transcripts, or many files at once — or when you want a second model's answer. Uses the `ask_space_bunny` tool (space-bunny MCP). Requires SPACE_BUNNY_API_KEY.
---

# Space Bunny — a 1M-token brain for your agent

Space Bunny Alpha is a fast LLM with a **1,000,000-token context window**, reached through the
`ask_space_bunny` tool (the bundled `space-bunny` MCP server). Use it to think over things that
**don't fit in your own context**.

## When to reach for it

- **Whole-repo / monorepo questions.** "Where is auth handled and what breaks if I move it?",
  "Trace how a request flows end to end", "Find every place that reads this config." Dump the
  relevant files (or the whole tree) into `context` and ask.
- **Long documents / transcripts.** Summarize, extract, or answer questions over something far
  larger than you can hold at once.
- **Many files at once.** When you'd otherwise read files one by one and lose the thread, pass
  them all in a single call.
- **A second opinion.** Get another model's take on a hard design or debugging question.

Do NOT use it for small, local edits or quick lookups you can do yourself — it's for scale.

## How to use it

Call the tool with:

- `prompt` — the question or instruction.
- `context` — (optional) the large text the prompt refers to: file dumps, docs, transcripts.
  This is the point — put the big stuff here (up to ~1M tokens).
- `system` — (optional) steer behavior, e.g. "Answer only with file paths and line numbers."
- `max_tokens` — (optional) output cap.

Example: to understand an unfamiliar codebase, gather the source (e.g. `git ls-files` → read the
key files, or a concatenated dump), pass it as `context`, and ask your question in `prompt`. Then
act on Space Bunny's answer with your own tools.

## Setup

Get a free API key at **https://spacebunnymodel.com/get-jev** and set `SPACE_BUNNY_API_KEY` in
your environment. The `space-bunny` MCP server (bundled with this plugin, run via
`npx github:codaaiteam/spacebunny-mcp`) reads it automatically.

Independent tool for the hosted spacebunnymodel.com API — not affiliated with the model's provider.
