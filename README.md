# XTREE

XTREE is a real-time social media data infrastructure for developers and AI agents. It provides structured access to social platform data through REST APIs, a Python SDK, an MCP server, and reusable Skills. It reads live raw data for accounts, posts, video, and comments. It does not publish posts, and it is not a BI or analytics platform.

Live today: WeChat, Douyin, Xiaohongshu, Kuaishou, Weibo, Bilibili, TikTok, YouTube, Instagram, X, and Taobao. The public MCP server currently registers WeChat tools. Other platforms are REST and the Python SDK.

Website: [www.xtree.io](https://www.xtree.io) · Docs: [www.xtree.io/docs](https://www.xtree.io/docs) · API reference: [www.xtree.io/docs/apis](https://www.xtree.io/docs/apis) · Catalog: [www.xtree.io/catalog](https://www.xtree.io/catalog) · Skills: [www.xtree.io/skills](https://www.xtree.io/skills) · OpenAPI: [api.xtree.io/api/openapi.json](https://api.xtree.io/api/openapi.json)

Get an API Key: [sign up on xtree.io](https://www.xtree.io/login?tab=signup) → set `XTREE_API_KEY` → pay per call from wallet (CNY). Incomplete delivery is not billed. Bulk / bank transfer: [business@xtree.io](mailto:business@xtree.io).

## Which repo?

| Repo | Install / use | For |
|------|---------------|-----|
| [xtree-python](https://github.com/xtree-io/xtree-python) | Python SDK + CLI | Scripts & backends |
| [xtree-sdk](https://github.com/xtree-io/xtree-sdk) | `npm install` TypeScript client | Node / web backends |
| [xtree-mcp](https://github.com/xtree-io/xtree-mcp) | `uvx --from git+https://github.com/xtree-io/xtree-mcp.git xtree-mcp` | Cursor / Claude; WeChat tools |
| [xtree-examples](https://github.com/xtree-io/xtree-examples) | Copy-paste scenarios | Learn by running |
| [xtree-skills](https://github.com/xtree-io/xtree-skills) | Official `SKILL.md` packs | Agent workflows (fetch data only) |

## Quick start (Python)

```bash
pip install xtree-sdk
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
