# seo-content-machine-vn

Development package for a Vietnamese SEO content skill.

This skill is designed as a single pipeline, not three separate tools. It connects SERP analysis, SEO reverse engineering, content strategy, and article writing into one practical workflow for the Vietnam market.

## Purpose

Use this skill to generate SEO content that can both rank and support conversion.

The core workflow:

```text
keyword + product + target customer + goal
-> SERP analysis
-> reverse engineering
-> strategy
-> outline
-> full article
-> SEO QA
```

## Package Structure

```text
seo-content-machine-vn/
├── SKILL.md
├── README.md
├── examples/
│   ├── input-basic.md
│   ├── output-seo-plan.md
│   └── output-full-article.md
└── references/
    ├── vietnamese-seo-guidelines.md
    ├── serp-analysis-framework.md
    └── content-strategy-framework.md
```

## Expected Input

```json
{
  "keyword": "phan mem quan ly ban hang",
  "product": "SaaS quan ly don hang va ton kho cho shop online",
  "target_customer": "chu shop online nho tai Viet Nam",
  "goal": "sales",
  "market": "Vietnam",
  "tone": "thuc chien"
}
```

## Expected Output

The skill should return:

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

## Development Notes

- Keep `SKILL.md` short and orchestration-focused.
- Put detailed frameworks in `references/`.
- Put expected behavior examples in `examples/`.
- Do not make this a set of separate skills unless there is a strong reason to expose individual modules later.

## Optional Install Later

If you later want to use this as a personal Claude skill, copy the folder to:

```bash
~/.claude/skills/seo-content-machine-vn
```

For project-only use, copy it to:

```bash
.claude/skills/seo-content-machine-vn
```
