# Truthifi MCP tools (29)

Truthifi's access to your bank and brokerage accounts is read-only: nothing your AI assistant does through Truthifi can move money, place trades or change settings there. Three of the 29 tools change data inside Truthifi: `create_asset_liability` adds an asset or liability you track by hand after showing a preview, `delete_asset_liability` permanently removes one, and `run_scan` refreshes your data now (3 credits). `connect_account`, `fix_connections` and `upgrade` only give you a link.

| Tool | Title | What it does | Limits | Credits | Plans | Changes data? |
|---|---|---|---|---|---|---|
| `get_accounts` | Get linked accounts | Lists your linked accounts, and how far back each one's data goes |  | 1 | All | No |
| `get_groups` | Get account groups | Your account groups, goals and wealth buckets |  | 1 | Pro+ | No |
| `get_advisors` | Get linked advisors | Financial advisors linked to your accounts, with details from public regulatory records |  | 1 | Pro+ | No |
| `get_dated_holdings` | Get holdings on a date | Your positions in each account on one day (the latest by default) | Sector, industry and country detail on Pro+ only | 2 | All | No |
| `get_composition` | Get portfolio composition | How your portfolio splits by asset class, sector, industry or country (top 10 of each) | Top 10 of each grouping | 1 | All | No |
| `get_equity_concentrations` | Get stock concentrations | Your exposure to individual stocks, including what you hold through funds |  | 1 | Pro+ | No |
| `get_market_cap_allocation` | Get market-cap allocation | How your portfolio splits across market-cap sizes, for stocks and funds separately |  | 1 | Pro+ | No |
| `get_balance_history` | Get balance history | Opening and closing balance for each account over a date range |  | 1 | All | No |
| `get_performance_history` | Get performance history | Return, income and gain or loss over a date range, compared with a similar benchmark |  | 1 | Pro+ | No |
| `get_fees` | Get fees | Fees per account, by type: maintenance, margin interest, advisory, commissions, fund fees |  | 1 | Max+ | No |
| `get_transactions` | Get transactions | Individual transactions, filterable and paged | 20 per call on Explore/Free Checkup, 100 on Pro/Monitoring, 150 on Max/Monitoring Plus+ | 1 | All | No |
| `get_budget_flow_summary` | Get spending and income summary | Spending and income by period and category (excludes card payments and investment income) |  | 1 | All | No |
| `get_investment_transactions_summary` | Get investment activity summary | Buys, sells, dividends and other investment activity, totalled by period |  | 1 | All | No |
| `get_asset_liabilities` | Get manual assets and liabilities | Assets and liabilities you track by hand, such as a home, a car or a mortgage |  | 1 | Pro+ | No |
| `create_asset_liability` | Add a manual asset or liability | Adds one asset or liability you track by hand. Shows a preview first, and saves only after you confirm |  | 0 | Pro+ | **Yes**, inside Truthifi |
| `delete_asset_liability` | Delete a manual asset or liability | Permanently deletes one asset or liability you track by hand |  | 1 | Pro+ | **Yes**, inside Truthifi (permanent) |
| `get_findings` | Get Truthifi Score findings | The financial health findings behind your Truthifi Score |  | 1 | Pro+ | No |
| `get_truthifi_score_history` | Get Truthifi Score history | Your Truthifi Score over time |  | 1 | Pro+ | No |
| `get_security_info` | Get security details | Reference details for up to 15 securities per call | Up to 15 securities per call (3 on Explore and Free Checkup) | 1 | All | No |
| `get_security_distributions` | Get dividend and capital-gain history | Dividend and capital-gain history for up to 15 securities per call, up to 2 years back | Up to 15 securities per call (3 on Explore and Free Checkup), up to 2 years back | 1 | All | No |
| `get_security_news` | Get security news | Recent news by stock ticker or by topic (stock tickers only, not funds) |  | 1 | Pro+ | No |
| `get_truthifi_info` | Ask about Truthifi | Answers questions about Truthifi, linking accounts and US personal-finance benchmarks |  | 0 | All | No |
| `run_scan` | Refresh a connection now | Refreshes one connection's data right now, instead of waiting for the automatic refresh |  | 3 | All | **Yes**, inside Truthifi |
| `get_scan_status` | Check refresh status | Checks how a refresh is going |  | 0 | All | No |
| `get_subscription_info` | Get plan and credits | Your plan, credits used, and which tools you can use |  | 0 | All | No |
| `connect_account` | Get a link to connect an account | Gives you a secure link to connect a new bank or brokerage account |  | 0 | All | No (returns a link) |
| `fix_connections` | Get a link to fix connections | Gives you a link to fix bank or brokerage connections that aren't refreshing (only when one needs fixing) |  | 0 | All | No (returns a link) |
| `upgrade` | Get a link to upgrade | Gives you a link to the plan picker, when a higher plan exists |  | 0 | All | No (returns a link) |
| `get_prompt_catalog` | Get ready-made prompts | Ready-made step-by-step prompts, such as a fee audit, a spending review or a tax preview. Instructions only, never account data |  | 0 | All | No |

Plans: **All** = every current plan · **Pro+** = Connect Pro, Connect Max, Monitoring, Monitoring Plus+ · **Max+** = Connect Max, Monitoring, Monitoring Plus+.
Source of truth: <https://truthifi.com/mcp-tools>. This page changes in the same release as any tool change.
