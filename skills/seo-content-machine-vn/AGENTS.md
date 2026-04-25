# SEO Content Machine VN

**Version 1.0.0**  
AI Content Vietnamese Skills  
April 2026

> This document is for AI agents and LLMs that need a complete Vietnamese SEO content workflow. It expands the skill into a compiled guide that can be used by clients that prefer `AGENTS.md` style context.

---

## Abstract

SEO Content Machine VN is a Vietnamese SEO content engine. It turns a keyword, product, target customer, and goal into a complete SEO plan and article using a production-style pipeline:

```text
INPUT
-> SERP ANALYSIS
-> SEO REVERSE ENGINEERING
-> STRATEGY ENGINE
-> CONTENT GENERATION
-> SEO QA
-> FINAL OUTPUT
```

The skill is optimized for the Vietnam market, where SEO content often needs to rank, build trust, and support sales at the same time.

---

## When To Use

Use this workflow when the user asks to:

- write a Vietnamese SEO article
- create an SEO outline for a Vietnamese keyword
- analyze or reverse engineer a SERP
- create a content plan from keyword and product
- generate meta title, meta description, CTA, FAQ, and internal links
- create content for traffic, sales, or branding in Vietnam

Do not use this workflow for generic content writing when SEO, SERP, keyword, ranking, or conversion intent is not relevant.

---

## Required Inputs

Collect or infer:

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

If `keyword` or `product` is missing, ask one short clarification question. If other fields are missing, infer them and state assumptions in the output.

---

## Core Rules

- Always define intent, SERP pattern, gap, and strategy before writing the full article.
- Write for Vietnamese search behavior, not generic English SEO templates.
- Balance ranking, trust, and conversion.
- Use practical Vietnamese examples and local business situations.
- Avoid keyword stuffing and robotic repetition.
- Use the product naturally only where it helps the reader make progress.
- If SERP data is not provided, label the analysis as inferred.
- If SERP data is provided, use it as the primary source of pattern and gap analysis.

---

## Pipeline

### 1. Normalize Input

Return an input summary with keyword, product, target customer, goal, market, tone, and assumptions.

### 2. SERP Analyzer

Analyze provided or inferred top-ranking pages.

Extract:

- dominant search intent
- content type distribution
- common heading structure
- common intro angles
- approximate content depth
- trust signals
- missing sections
- SERP risk

### 3. SEO Reverse Engineer

Convert SERP patterns into a ranking blueprint.

Identify:

- what Google likely rewards
- must-have sections
- differentiator sections
- content gaps
- freshness needs
- Vietnam-specific examples or proof points

### 4. Strategy Engine

Define:

- persona
- search maturity
- primary goal
- primary content angle
- hook
- CTA style
- trust elements
- internal link path

### 5. Content Generation

Create:

- SEO outline with H1, H2, H3
- full Vietnamese article
- meta title
- meta description
- suggested slug
- CTA
- FAQ when useful
- internal link suggestions

### 6. SEO QA

Check:

- intent match
- heading completeness
- keyword naturalness
- uniqueness against common SERP pattern
- conversion alignment
- trust signals
- over-selling risk
- Vietnam market context

---

## Final Output Format

Return sections in this order:

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

---

## Reference Files

- `references/vietnamese-seo-guidelines.md`: Vietnamese SEO and conversion behavior.
- `references/serp-analysis-framework.md`: SERP extraction and risk framework.
- `references/content-strategy-framework.md`: persona, angle, hook, and CTA strategy.
- `examples/input-basic.md`: minimal valid input.
- `examples/output-seo-plan.md`: planning output style.
- `examples/output-full-article.md`: article output style.
