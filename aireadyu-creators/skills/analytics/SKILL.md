---
name: analytics
description: >
  Collect and interpret performance metrics from YouTube, Medium, LinkedIn,
  and Buffer via their respective APIs. Use to detect trends, compare
  performance, and surface actionable insights.
---

# Analytics Skill

Analytics collects metrics from content platforms, detects patterns, compares
performance over time, and surfaces insights the calling agent can act on.

## Workflow Position

```
publishing → distribution → analytics → (informs next writing cycle)
```

## Provider: YouTube Analytics API

Auth: OAuth2 token via `YOUTUBE_ACCESS_TOKEN` environment variable.
API Base: `https://youtubeanalytics.googleapis.com/v2`

### Get channel overview

```bash
curl "https://youtubeanalytics.googleapis.com/v2/reports?ids=channel==MINE&startDate=2026-01-01&endDate=2026-03-31&metrics=views,estimatedMinutesWatched,averageViewDuration,subscribersGained&dimensions=month" \
  -H "Authorization: Bearer $YOUTUBE_ACCESS_TOKEN"
```

### Get top performing videos

```bash
curl "https://youtubeanalytics.googleapis.com/v2/reports?ids=channel==MINE&startDate=2026-01-01&endDate=2026-03-31&metrics=views,likes,comments&dimensions=video&sort=-views&maxResults=10" \
  -H "Authorization: Bearer $YOUTUBE_ACCESS_TOKEN"
```

### Get audience demographics

```bash
curl "https://youtubeanalytics.googleapis.com/v2/reports?ids=channel==MINE&startDate=2026-01-01&endDate=2026-03-31&metrics=viewerPercentage&dimensions=ageGroup,gender" \
  -H "Authorization: Bearer $YOUTUBE_ACCESS_TOKEN"
```

## Provider: Medium (Stats)

Medium's public API has limited analytics. For detailed stats, use the
partner program dashboard or scrape stats from the Medium stats page.

### Get publication stats (via RSS/scraping)

```bash
curl "https://medium.com/feed/@your-username" | # parse for post URLs
# Then for each post, Medium provides basic stats in the partner dashboard
```

For programmatic access, consider using Medium's unofficial stats endpoint
(requires authenticated session cookie):
```bash
curl "https://medium.com/@your-username/stats/total/YOUR_POST_ID" \
  -H "Cookie: sid=$MEDIUM_SESSION_ID"
```

## Provider: LinkedIn Analytics

Auth: OAuth2 token via `LINKEDIN_ACCESS_TOKEN` environment variable.
API Base: `https://api.linkedin.com/v2`

### Get post analytics

```bash
curl "https://api.linkedin.com/v2/organizationalEntityShareStatistics?q=organizationalEntity&organizationalEntity=urn:li:person:PERSON_ID&shares=urn:li:share:SHARE_ID" \
  -H "Authorization: Bearer $LINKEDIN_ACCESS_TOKEN"
```

### Get follower statistics

```bash
curl "https://api.linkedin.com/v2/networkSizes/urn:li:person:PERSON_ID?edgeType=CompanyFollowedByMember" \
  -H "Authorization: Bearer $LINKEDIN_ACCESS_TOKEN"
```

## Provider: Buffer Analytics

### Get post performance

```bash
curl "https://api.bufferapp.com/1/updates/UPDATE_ID/interactions.json?access_token=$BUFFER_ACCESS_TOKEN"
```

### Get profile analytics

```bash
curl "https://api.bufferapp.com/1/profiles/PROFILE_ID/updates/sent.json?access_token=$BUFFER_ACCESS_TOKEN&count=20"
```

## Operations

| Operation | Description |
|-----------|-------------|
| `get_metrics` | Retrieve metrics for a specific post or time window |
| `compare_periods` | Compare two date ranges |
| `top_content` | List highest-performing content by metric |
| `detect_trend` | Identify growth, plateau, or decline |
| `audience_breakdown` | Demographic or geographic data |
| `channel_summary` | High-level summary of recent performance |
| `export_report` | Generate a structured report |

## Usage Rules

- Always include date range and comparison baseline when reporting
- Surface anomalies (positive spikes and drops) with context
- Provide data and let the calling agent make strategy decisions
- For YouTube, separate organic vs promoted metrics when both exist

## Vault Integration

Save periodic reports to the vault via `storage`:

- Content performance → `mind/00_current/YYYY-MM_content-analytics.md`
- Business analytics → `business/00_current/` if it informs business strategy

Monthly or quarterly cadence. Name: `YYYY-MM_analytics-platform-summary.md`
