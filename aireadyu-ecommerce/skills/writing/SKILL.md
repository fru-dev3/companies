---
name: writing
description: >
  Generate, edit, rewrite, and repurpose written content using LLM capabilities.
  Platform-agnostic — handles long-form articles, short-form posts, outlines,
  newsletters, reports, and scripts. Style and tone are set by the calling agent.
---

# Writing Skill

Writing is the content creation layer. It generates, edits, and transforms
written content across any format or platform. This skill is LLM-native —
the agent itself is the writing engine. No external API is needed.

The writing skill has no platform opinion. It produces text. The calling
agent defines the style, audience, and purpose.

## When to Use

- Drafting a new article, post, or newsletter
- Editing or rewriting existing content
- Changing tone (formal, conversational, punchy, long-form)
- Creating an outline before drafting
- Repurposing content for a different platform or format
- Generating a summary or executive brief
- Writing a report for another agent or the user

## Operations

| Operation | Description |
|-----------|-------------|
| `draft` | Write a new piece from a brief or topic |
| `outline` | Generate a structured outline before drafting |
| `edit` | Improve clarity, structure, or grammar |
| `rewrite` | Rewrite in a different tone or style |
| `repurpose` | Adapt content from one format to another |
| `summarize` | Condense a longer piece into a shorter one |
| `expand` | Expand bullet points or notes into full content |
| `headline` | Generate title or headline options |

## Platform Style Guides

Style is passed by the calling agent. Common patterns:

**LinkedIn post:** Short paragraphs, no headers, personal voice, hook in
line 1, professional insight, ends with a question or CTA. 150–300 words.

**Medium article:** Long-form, structured with H2/H3 headers, narrative-driven,
first-person, 800–2500 words. Opens with a story or provocative statement.

**Newsletter:** Intimate and conversational, direct address ("you"), digestible
sections, one clear CTA. 300–600 words.

**Report:** Formal, structured, factual. Headers, bullets, tables. Conclusion
with next steps.

**YouTube script:** Conversational, hook in first 10 seconds, structured
segments, clear call to action at end. Written for spoken delivery.

## Brief Template

Before drafting, the calling agent should provide:

```
Topic: [what to write about]
Platform: [LinkedIn / Medium / newsletter / report / YouTube]
Audience: [who is reading/watching]
Tone: [professional / casual / educational / persuasive]
Length: [word count or duration target]
Key points: [must-include information]
CTA: [what should the reader do next]
```

## Usage Rules

- Always receive a brief before drafting
- Do not invent facts — use the `research` skill first if sourcing is needed
- When repurposing, note what changed and why
- Drafts are output only — use `publishing` to deliver to a platform
- Use `design` for any visual assets that accompany the content

## Vault Integration

Save finalized drafts to the vault before publishing via `storage`:

- Business content → `business/00_current/`
- Personal writing, ideas → `mind/00_current/`
- General reference documents → `mind/00_current/`
- Legal/compliance documents → `legal/00_current/`

Save before calling `publishing`. Name: `YYYY-MM-DD_content-title.md`
If repurposed into multiple formats, save each with a suffix:
`YYYY-MM-DD_title_linkedin-post.md`, `YYYY-MM-DD_title_newsletter.md`
