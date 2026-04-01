---
name: research
description: >
  Search the web, browse pages, verify sources, and synthesize information
  using multiple providers: Perplexity API for AI-powered search, Google
  Custom Search for traditional results, Tavily for agent-optimized search,
  and browser automation for direct page access.
---

# Research Skill

Research is the external intelligence layer. Use it when agents need
information from the outside world — regulations, news, product comparisons,
medical guidance, pricing, legal precedent, or anything not in the vault.

## Providers

Multiple search providers are supported. Use the best one for the task.

### Provider: Perplexity API (AI-Powered Search)

Auth: API key via `PERPLEXITY_API_KEY` environment variable.
API Base: `https://api.perplexity.ai`

Best for: questions that need synthesized answers with citations.

```bash
curl -X POST https://api.perplexity.ai/chat/completions \
  -H "Authorization: Bearer $PERPLEXITY_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "model": "sonar",
    "messages": [
      {"role": "user", "content": "What are the 2026 IRS estimated tax payment deadlines?"}
    ]
  }'
```

### Provider: Google Custom Search API

Auth: API key via `GOOGLE_SEARCH_API_KEY` + search engine ID `GOOGLE_SEARCH_CX`.
API Base: `https://www.googleapis.com/customsearch/v1`

Best for: specific factual lookups, finding official sources.

```bash
curl "https://www.googleapis.com/customsearch/v1?key=$GOOGLE_SEARCH_API_KEY&cx=$GOOGLE_SEARCH_CX&q=texas+property+tax+rates+2026&num=5"
```

### Provider: Tavily API (Agent-Optimized Search)

Auth: API key via `TAVILY_API_KEY` environment variable.
API Base: `https://api.tavily.com`

Best for: AI agent workflows that need structured, relevant results.

```bash
curl -X POST https://api.tavily.com/search \
  -H "Content-Type: application/json" \
  -d '{
    "api_key": "'$TAVILY_API_KEY'",
    "query": "best 401k contribution strategy for high earners 2026",
    "search_depth": "advanced",
    "include_answer": true,
    "max_results": 5
  }'
```

### Provider: Browser Automation

For pages that require interaction or don't have APIs. Use Playwright
or Puppeteer for direct page access, form filling, and data extraction.

```bash
npx playwright open https://www.irs.gov/forms-instructions
```

## When to Use Which Provider

| Need | Best Provider |
|------|--------------|
| Quick factual question | Perplexity |
| Find an official .gov source | Google Custom Search |
| Structured research for agent decision | Tavily |
| Scrape data from a specific website | Browser automation |
| Compare products/services | Perplexity or Tavily |
| Verify a claim across sources | Google Custom Search (multiple results) |

## Usage Rules

- Always cite sources when surfacing researched information
- For medical, legal, or financial research: note findings are informational, not professional advice
- Prefer authoritative sources: .gov, official org sites, established publications
- When sources conflict, flag the conflict rather than resolving it
- Pass research output to `writing` when it will be included in content

## Vault Integration

Save durable research to the vault via `storage`:

- Legal/regulatory research → `legal/00_current/`
- Health research → `health/00_current/`
- Tax guidance → `tax/00_current/`
- Business/market research → `business/00_current/`
- General reference → `mind/00_current/`

Name: `YYYY-MM-DD_research-topic-summary.md`
Only vault research that serves as a durable reference — not every search.
