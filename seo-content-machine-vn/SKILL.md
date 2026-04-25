---
name: seo-content-machine-vn
description: Vietnamese SEO content engine for building SEO plans, reverse-engineering SERP patterns, defining content strategy, and writing full Vietnamese SEO articles from keyword, product, audience, and goal.
argument-hint: '"keyword" "product" "target_customer" "goal"'
---

# SEO Content Machine VN

Use this skill to turn a Vietnamese SEO content request into a complete production workflow:

```text
INPUT
-> SERP ANALYZER
-> SEO REVERSE ENGINEER
-> STRATEGY ENGINE
-> CONTENT GENERATION
-> SEO QA
-> FINAL OUTPUT
```

Do not treat audit, reverse engineering, and writing as separate tasks. Always run them as one connected pipeline unless the user explicitly asks for only one stage.

## Required Input

Collect or infer these fields before producing the final article:

```json
{
  "keyword": "...",
  "product": "...",
  "target_customer": "...",
  "goal": "traffic | sales | branding",
  "market": "Vietnam",
  "tone": "thuc chien | chuyen gia | de hieu | ban hang mem"
}
```

If one field is missing, make the most reasonable assumption and state it in `Input Summary`. If the keyword or product is missing, ask one short clarification question before continuing.

## Operating Rules

- Write for Vietnamese search behavior, not generic English SEO templates.
- Prioritize useful, trust-building content over keyword stuffing.
- Do not write freestyle. Generate the article only after SERP pattern, gap, and strategy are defined.
- If SERP data is provided, use it. If not, simulate a SERP-informed analysis based on the keyword and clearly label it as an inferred analysis.
- Make the content commercially useful when the goal is `sales`, but avoid hard-selling too early in informational articles.
- Prefer concrete Vietnamese examples, local objections, local buying behavior, and practical checklists.
- Keep headings scannable and aligned with search intent.
- Use natural Vietnamese. Avoid robotic phrasing, excessive buzzwords, and repeated exact-match keywords.

## Pipeline

### 1. Normalize Input

Produce an `Input Summary` with:

- keyword
- product or offer
- target customer
- content goal
- market
- assumed tone
- missing assumptions

### 2. SERP Analyzer

Analyze the likely or provided top-ranking pages.

Extract:

- dominant search intent
- top content types: blog, listicle, guide, landing page, comparison, checklist, tool page
- recurring heading patterns
- common intro angles
- approximate content depth
- trust signals used by competitors
- missing or weak sections

Output:

- `Search Intent`
- `SERP Pattern`
- `SERP Risk`

See `references/serp-analysis-framework.md` for deeper criteria when needed.

### 3. SEO Reverse Engineer

Convert SERP analysis into a ranking blueprint.

Identify:

- what Google likely rewards for this query
- must-have sections
- optional differentiator sections
- content gaps
- freshness requirements
- examples or proof points needed for Vietnam

Output:

- `Ranking Blueprint`
- `Content Gap`
- `Differentiation Angle`

### 4. Strategy Engine

Define the content strategy before writing.

Decide:

- primary persona
- buyer/search maturity level
- conversion goal
- content angle
- hook
- CTA style
- trust-building elements
- internal link opportunities

Output:

- `Strategy`
- `CTA Plan`

See `references/content-strategy-framework.md` for strategy patterns.

### 5. Content Generation

Create:

- SEO outline with H1, H2, H3
- full Vietnamese article
- meta title
- meta description
- suggested slug
- CTA block
- FAQ section when useful

Writing requirements:

- H1 must match the search promise.
- Intro must confirm the reader's problem within the first 2-3 sentences.
- Use short paragraphs.
- Include examples relevant to Vietnam.
- Add practical steps, checklists, or decision criteria where appropriate.
- Mention the product naturally only where it helps the reader make progress.

### 6. SEO QA

Before finalizing, check:

- intent match
- heading completeness
- keyword naturalness
- article uniqueness versus common SERP pattern
- conversion alignment
- trust signals
- over-selling risk
- missing local Vietnam context

## Final Output Format

Return the result in this order:

```text
1. Input Summary
2. Search Intent
3. SERP Pattern
4. Ranking Blueprint
5. Content Gap
6. Strategy
7. SEO Outline
8. Full Article
9. Meta Title
10. Meta Description
11. Suggested Slug
12. CTA
13. Internal Link Suggestions
14. SEO QA Checklist
```

## Supporting References

- Use `references/vietnamese-seo-guidelines.md` for Vietnamese SEO and conversion behavior.
- Use `references/serp-analysis-framework.md` for SERP extraction criteria.
- Use `references/content-strategy-framework.md` for persona, angle, hook, and CTA logic.
- Use `examples/input-basic.md` for a minimal valid input.
- Use `examples/output-seo-plan.md` for the planning output style.
- Use `examples/output-full-article.md` for full article output style.
