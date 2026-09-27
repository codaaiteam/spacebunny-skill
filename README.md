# spacebunny (Claude Code plugin)

Give your agent a **1,000,000-token brain**. This plugin adds a Space Bunny Alpha tool
(`ask_space_bunny`) so Claude Code — capped around 200K tokens — can offload work that doesn't
fit: **whole-repo analysis, long documents, hours of transcripts, or many files at once**, via the
hosted [spacebunnymodel.com](https://spacebunnymodel.com) API.

It bundles the [`space-bunny` MCP server](https://github.com/codaaiteam/spacebunny-mcp) and a skill
that teaches the agent when to reach for it.

## Install (Claude Code)

```bash
claude plugin marketplace add codaaiteam/spacebunny-skill
claude plugin install spacebunny@spacebunny
```

Get a free API key at **https://spacebunnymodel.com/get-jev** and set it once:

```bash
export SPACE_BUNNY_API_KEY=sb_live_...
```

## Use it

Just ask Claude Code something that needs a lot of context — "read the whole repo and tell me
where auth is handled" — and it will offload to Space Bunny's 1M window and act on the answer.

## Other agents

Not on Claude Code? The MCP server works in Cursor, opencode, Codex and any MCP client —
see [spacebunny-mcp](https://github.com/codaaiteam/spacebunny-mcp).

---

Independent tools for the hosted spacebunnymodel.com API. Not affiliated with the model's provider.
