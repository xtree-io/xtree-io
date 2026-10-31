# XTREE

**Developer APIs for real-time social media data** (WeChat, Douyin, Xiaohongshu, Kuaishou, Weibo, Bilibili, TikTok, YouTube) and Taobao item data — raw payloads for accounts, content, media, and comments. **Not** a BI or analytics platform.

Website: [www.xtree.io](https://www.xtree.io) · Docs: [www.xtree.io/docs](https://www.xtree.io/docs) · Catalog: [www.xtree.io/catalog](https://www.xtree.io/catalog) · OpenAPI: [api.xtree.io/api/openapi.json](https://api.xtree.io/api/openapi.json)

Get an API Key: [sign up on xtree.io](https://www.xtree.io/login?tab=signup) → set `XTREE_API_KEY` → pay per call from wallet (CNY). Incomplete delivery is not billed. Bulk / bank transfer: [business@xtree.io](mailto:business@xtree.io).

## Which repo?

| Repo | Install / use | For |
|------|---------------|-----|
| [xtree-python](https://github.com/xtree-io/xtree-python) | Python SDK + CLI | Scripts & backends |
| [xtree-sdk](https://github.com/xtree-io/xtree-sdk) | `npm install` TypeScript client | Node / web backends |
| [xtree-mcp](https://github.com/xtree-io/xtree-mcp) | `uvx xtree-mcp` | Cursor / Claude / any MCP host |
| [xtree-examples](https://github.com/xtree-io/xtree-examples) | Copy-paste scenarios | Learn by running |
| [xtree-skills](https://github.com/xtree-io/xtree-skills) | Official `SKILL.md` packs | Agent workflows (fetch data only) |

## Quick start (Python)

```bash
pip install "git+https://github.com/xtree-io/xtree-python.git"
export XTREE_API_KEY=xt_live_...
python -c "from xtree import XTreeClient; print(XTreeClient().account.balance().data)"
```

## Quick start (MCP / Cursor)

```json
{
  "mcpServers": {
    "xtree": {
      "command": "uvx",
      "args": ["--from", "git+https://github.com/xtree-io/xtree-mcp.git", "xtree-mcp"],
      "env": { "XTREE_API_KEY": "xt_live_..." }
    }
  }
}
```

## Product notes

- Auth header: `X-XTREE-Key: xt_live_{prefix}_{secret}`
- Envelope: `ok` / `data` / `meta` / `error` (`meta` includes `request_id`, `cost_cny`, `balance_cny`)
- Unit prices: [API Catalog](https://www.xtree.io/catalog) — no volume tiers, no `/pricing` plans page
- Contact: [business@xtree.io](mailto:business@xtree.io) · [support@xtree.io](mailto:support@xtree.io)

> These repositories are **public mirrors**. Application code lives in a private monorepo. Open issues here for SDK / docs feedback.
