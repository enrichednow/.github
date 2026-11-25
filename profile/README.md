# EnrichedNow

**Web data as clean, structured records.** Call a ready-made scraper, run a playbook that hands back a finished list, or get the data itself as a dataset.

[Website](https://enrichednow.com) · [Documentation](https://docs.enrichednow.com) · [Console](https://app.enrichednow.com) · [Changelog](https://docs.enrichednow.com/changelog/) · [Status](https://enrichednow.com/status/) · hello@enrichednow.com

## What it does

- **Scraper API.** Hundreds of ready-made scrapers for job boards, shops, maps, property, social, finance and news sites. Each one is called the same way and returns the same fields every time: `null` when a value is not on the page, never a guess.
- **Playbooks.** Multi-step workflows that do a search you would otherwise run by hand: they search several sources, match results to real companies, remove duplicates, check emails and return one list, best first. Run one once, or keep it running weekly.
- **Datasets.** Data with its history, without scraping it yourself. The first one, job openings, is in early access.

Every account gets 1,000 free units a month, and a run that fails costs nothing.

## Official libraries and tools

| | Install | Repository |
|---|---|---|
| Python | `pip install enrichednow` | [enrichednow-python](https://github.com/enrichednow/enrichednow-python) |
| JavaScript / TypeScript | `npm install enrichednow` | [enrichednow-js](https://github.com/enrichednow/enrichednow-js) |
| Go | `go get github.com/enrichednow/enrichednow-go@latest` | [enrichednow-go](https://github.com/enrichednow/enrichednow-go) |
| Java | `com.enrichednow:enrichednow-java` on Maven Central | [enrichednow-java](https://github.com/enrichednow/enrichednow-java) |
| CLI | `curl -fsSL https://raw.githubusercontent.com/enrichednow/enrichednow-cli/main/install.sh \| sh` | [enrichednow-cli](https://github.com/enrichednow/enrichednow-cli) |
| MCP server (for AI agents) | `https://api.enrichednow.com/mcp` | [Docs](https://docs.enrichednow.com/mcp/) |

## Quick start

```bash
export ENRICHEDNOW_API_KEY="en_live_..."   # create one in the console under API keys
```

```python
from enrichednow import EnrichedNow

client = EnrichedNow()  # reads ENRICHEDNOW_API_KEY
result = client.scrape("ats.board", {"board_url": "https://boards.greenhouse.io/acme"})
for record in result.records:
    print(record["title"])
```

Or over plain HTTP:

```bash
curl -X POST https://api.enrichednow.com/v1/scrapers/ats.board/runs \
  -H "Authorization: Bearer $ENRICHEDNOW_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"input": {"board_url": "https://boards.greenhouse.io/acme"}}'
```

## Contact

- Questions and sales: hello@enrichednow.com
- Security: [how we handle data and reports](https://enrichednow.com/security/)
- Issues with a library: open an issue in its repository.

EnrichedNow is a product of ProficientNow Management Consultancies - FZE, Dubai, United Arab Emirates.
