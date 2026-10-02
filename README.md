<p align="center"><img src="assets/truthifi-logo-256.png" width="96" alt="Truthifi logo"></p>

<h1 align="center">Truthifi MCP server</h1>

<p align="center"><b>Your holdings, fees, performance and Truthifi Score in your AI assistant.</b><br>
It can't move money or place trades at your bank or brokerage.</p>

<p align="center">
<a href="https://cursor.com/install-mcp?name=truthifi&config=eyJ1cmwiOiJodHRwczovL2FwaS50cnV0aGlmaS5jb20vbWNwIn0%3D"><img src="https://cursor.com/deeplink/mcp-install-dark.svg" alt="Add Truthifi to Cursor" height="32"></a>
<a href="https://insiders.vscode.dev/redirect/mcp/install?name=truthifi&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.truthifi.com%2Fmcp%22%7D"><img src="https://img.shields.io/badge/VS_Code-Install_Truthifi-0098FF?logo=visualstudiocode&logoColor=white" alt="Install in VS Code" height="32"></a>
</p>
<p align="center">
<img src="https://img.shields.io/badge/transport-streamable_http-555" alt="Streamable HTTP">
<img src="https://img.shields.io/badge/auth-OAuth_%2B_DCR-555" alt="OAuth with Dynamic Client Registration">
<img src="https://img.shields.io/badge/registry-com.truthifi%2Fmcp-555" alt="Official MCP Registry name">
</p>

Truthifi connects your AI assistant to your investment and banking data from 18,000+ supported institutions (through data partners; available data varies by institution): holdings, fees, performance, cash flow, the advisors on your accounts, and your **Truthifi Score** with the findings behind it.

This repository holds **documentation, client configuration and agent skills only**. The server is hosted by Truthifi at `https://api.truthifi.com/mcp`; there is nothing to build or run.

## Quick start

| | |
|---|---|
| **Server URL** | `https://api.truthifi.com/mcp` |
| **Transport** | Streamable HTTP |
| **Sign-in** | OAuth with Dynamic Client Registration. You sign in to Truthifi in your browser; no bank or brokerage credentials pass through the assistant |
| **Registry name** | `com.truthifi/mcp` (official MCP Registry) |
| **Account** | A Truthifi account (see the [Terms](https://truthifi.com/terms) for eligibility). Start free (limits apply); [plans](https://truthifi.com/pricing) |

**Claude** (web or desktop; then available on mobile): Customize → Connectors → **+** → *Add custom connector* → paste `https://api.truthifi.com/mcp` and leave Advanced settings empty. Free plans allow one custom connector. On Team or Enterprise, an Owner adds it first under Organization settings → Connectors.

**ChatGPT** (web): ChatGPT connects custom MCP servers through developer mode, which OpenAI describes as intended for developers; read OpenAI's guidance before turning it on. Then create an app, paste `https://api.truthifi.com/mcp` and choose OAuth. Which ChatGPT plans can use it, and whether tools that change data are allowed, is set by OpenAI; current steps: <https://truthifi.com/connect>.

**Claude Code**

```bash
claude mcp add --transport http truthifi https://api.truthifi.com/mcp
# or install the plugin (connector plus skills):
/plugin marketplace add truthifi/truthifi-mcp
/plugin install truthifi@truthifi
```

**Gemini CLI**

```bash
gemini extensions install https://github.com/truthifi/truthifi-mcp
```

**OpenAI Codex**

```bash
codex mcp add truthifi --url https://api.truthifi.com/mcp
# if the browser sign-in was skipped or expired: codex mcp login truthifi
```

**Agent skills** (skills-aware agents)

```bash
npx skills add truthifi/truthifi-mcp
```

Configs for Cursor, VS Code, GitHub Copilot CLI, Windsurf/Devin, Antigravity, Kiro, Zed, JetBrains, Cline, Goose, Continue, OpenCode, LM Studio and more are in [`configs/`](configs/), with which ones we've tested.

**Cursor plugin** (connector plus skills): install *Truthifi* from the Cursor Marketplace, or use the button above for the MCP server only. **Kiro power:** Powers → Import power from GitHub → `https://github.com/truthifi/truthifi-mcp`. Step-by-step guides: <https://truthifi.com/connect>.

## What you can ask

- What am I paying in fees across all my accounts, and which account costs the most?
- How is my portfolio split by asset class, and where am I most concentrated?
- How has my portfolio performed this year compared with its benchmark?
- Which individual stocks am I most exposed to, counting what I hold through funds?
- What are the findings behind my Truthifi Score?

## Tools

29 tools. Truthifi's access to your bank and brokerage accounts is read-only: nothing your AI assistant does through Truthifi can move money, place trades or change settings there. Three tools change data inside Truthifi only, marked below.

| Tool | What it does | Credits | Changes data? |
|---|---|---|---|
| `get_accounts` | Lists your linked accounts, and how far back each one's data goes | 1 | No |
| `get_groups` | Your account groups, goals and wealth buckets | 1 | No |
| `get_advisors` | Financial advisors linked to your accounts, with details from public regulatory records | 1 | No |
| `get_dated_holdings` | Your positions in each account on one day (the latest by default) | 2 | No |
| `get_composition` | How your portfolio splits by asset class, sector, industry or country (top 10 of each) | 1 | No |
| `get_equity_concentrations` | Your exposure to individual stocks, including what you hold through funds | 1 | No |
| `get_market_cap_allocation` | How your portfolio splits across market-cap sizes, for stocks and funds separately | 1 | No |
| `get_balance_history` | Opening and closing balance for each account over a date range | 1 | No |
| `get_performance_history` | Return, income and gain or loss over a date range, compared with a similar benchmark | 1 | No |
| `get_fees` | Fees per account, by type: maintenance, margin interest, advisory, commissions, fund fees | 1 | No |
| `get_transactions` | Individual transactions, filterable and paged | 1 | No |
| `get_budget_flow_summary` | Spending and income by period and category (excludes card payments and investment income) | 1 | No |
| `get_investment_transactions_summary` | Buys, sells, dividends and other investment activity, totalled by period | 1 | No |
| `get_asset_liabilities` | Assets and liabilities you track by hand, such as a home, a car or a mortgage | 1 | No |
| `create_asset_liability` | Adds one asset or liability you track by hand. Shows a preview first, and saves only after you confirm | 0 | **Yes**, inside Truthifi |
| `delete_asset_liability` | Permanently deletes one asset or liability you track by hand | 1 | **Yes**, inside Truthifi (permanent) |
| `get_findings` | The financial health findings behind your Truthifi Score | 1 | No |
| `get_truthifi_score_history` | Your Truthifi Score over time | 1 | No |
| `get_security_info` | Reference details for up to 15 securities per call (fewer on some plans) | 1 | No |
| `get_security_distributions` | Dividend and capital-gain history for up to 15 securities per call (fewer on some plans), up to 2 years back | 1 | No |
| `get_security_news` | Recent news by stock ticker or by topic (stock tickers only, not funds) | 1 | No |
| `get_truthifi_info` | Answers questions about Truthifi, linking accounts and US personal-finance benchmarks | 0 | No |
| `run_scan` | Refreshes one connection's data right now, instead of waiting for the automatic refresh | 3 | **Yes**, inside Truthifi |
| `get_scan_status` | Checks how a refresh is going | 0 | No |
| `get_subscription_info` | Your plan, credits used, and which tools you can use | 0 | No |
| `connect_account` | Gives you a secure link to connect a new bank or brokerage account | 0 | No (returns a link) |
| `fix_connections` | Gives you a link to fix bank or brokerage connections that aren't refreshing (only when one needs fixing) | 0 | No (returns a link) |
| `upgrade` | Gives you a link to the plan picker, when a higher plan exists | 0 | No (returns a link) |
| `get_prompt_catalog` | Ready-made step-by-step prompts, such as a fee audit, a spending review or a tax preview. Instructions only, never account data | 0 | No |

Some tools need a higher plan, and some have per-plan limits; `get_subscription_info` (free) tells your assistant what yours includes. Full reference: [docs/tools.md](docs/tools.md) · machine-readable: [docs/tools.json](docs/tools.json) · live page: <https://truthifi.com/mcp-tools>.

## Skills included

| Skill | What it does |
|---|---|
| [`truthifi-portfolio-review`](skills/truthifi-portfolio-review/SKILL.md) | Allocation, concentration, performance and Score findings in one summary |
| [`truthifi-fee-review`](skills/truthifi-fee-review/SKILL.md) | Fees reported across your accounts, by account and type |
| [`truthifi-setup`](skills/truthifi-setup/SKILL.md) | Connecting Truthifi and linking a first account |

## Security and privacy

- Your assistant can't move money, place trades or change anything at your bank or brokerage. Three tools change data inside Truthifi only.
- Data the tools return goes to the AI assistant you chose and is handled under that provider's terms.
- OAuth sign-in; credentials never pass through the chat.
- Details: [docs/security-and-privacy.md](docs/security-and-privacy.md) · [Privacy](https://truthifi.com/privacy) · [Terms](https://truthifi.com/terms) · [Security](https://truthifi.com/security) · report a vulnerability: [SECURITY.md](SECURITY.md)

## Important information

Truthifi is not a registered investment adviser or broker-dealer. Truthifi provides data and analysis, not investment, tax or legal advice, and nothing here is a recommendation to buy or sell any security. The Truthifi Score and findings reflect Truthifi's own methodology. Past performance does not guarantee future results; benchmark comparisons are for context. Account data comes from your institutions through aggregation partners and may be delayed or incomplete; check important figures against your statements. Answers are written by the AI assistant you use, not by Truthifi, and may contain mistakes. Use of Truthifi is governed by the [Truthifi terms](https://truthifi.com/terms).

## Support

[Help center](https://truthifi.com/help) · support@truthifi.com · [FAQ](docs/faq.md)

## License and trademarks

Text, configuration and skill files are MIT licensed (see [LICENSE](LICENSE) and [NOTICE](NOTICE)). The Truthifi name, logo and Truthifi Score are trademarks of Truthifi and are not licensed under MIT; see [TRADEMARKS.md](TRADEMARKS.md). Claude, ChatGPT, Gemini, Copilot, Cursor and other product names are trademarks of their owners and are used only to describe compatibility.
