# seo-content-machine-vn

Vietnamese SEO Content Engine packaged as an Agent Skill.

Skill này được thiết kế như một pipeline liền mạch, không phải ba prompt rời rạc. Nó nối SERP analysis, SEO reverse engineering, content strategy và article writing thành một workflow thực chiến cho thị trường Việt Nam.

## Purpose

Use this skill to generate Vietnamese SEO content that can both rank and support conversion.

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
├── AGENTS.md
├── metadata.json
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

## Install

Install from this repository with Agent Skills CLI:

```bash
npx skills add tuanhaviet22/ai-content-vietnamese-skills
```

If your client expects a GitHub source prefix:

```bash
npx skills add github:tuanhaviet22/ai-content-vietnamese-skills
```

Manual install for Claude Code:

```bash
mkdir -p ~/.claude/skills
cp -R skills/seo-content-machine-vn ~/.claude/skills/seo-content-machine-vn
```

Manual install for Codex and other `.agents/skills` clients:

```bash
mkdir -p ~/.agents/skills
cp -R skills/seo-content-machine-vn ~/.agents/skills/seo-content-machine-vn
```

Repo-scoped install for Codex, VS Code Copilot, and other Agent Skills clients:

```bash
mkdir -p .agents/skills
cp -R skills/seo-content-machine-vn .agents/skills/seo-content-machine-vn
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

## Agent Files

- `SKILL.md`: main progressive-disclosure instructions.
- `AGENTS.md`: expanded agent-facing guide for clients that prefer compiled docs.
- `metadata.json`: version, organization, abstract, and references.
