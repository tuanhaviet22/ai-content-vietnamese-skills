# AI Content Vietnamese Skills

Repo này chứa các **Agent Skills cho content tiếng Việt**, tập trung vào SEO, content strategy, reverse SERP và viết bài có khả năng hỗ trợ chuyển đổi.

Mục tiêu của repo không phải là lưu vài prompt rời rạc. Mục tiêu là đóng gói các workflow content thực chiến thành skill có cấu trúc chuẩn, có thể cài bằng Agent Skills CLI và dùng lại trên nhiều agent như Claude Code, Claude Desktop, Codex, VS Code Copilot, Cursor hoặc các client hỗ trợ chuẩn Agent Skills.

## Cài Đặt Nhanh

Cài toàn bộ skills trong repo bằng `npx`:

```bash
npx skills add tuanhaviet22/ai-content-vietnamese-skills
```

Nếu client hoặc CLI yêu cầu prefix GitHub:

```bash
npx skills add github:tuanhaviet22/ai-content-vietnamese-skills
```

Sau khi cài, agent tương thích sẽ tự phát hiện skill khi prompt khớp với description, hoặc bạn có thể gọi skill theo tên nếu client hỗ trợ slash command / skill mention.

## Skill Hiện Có

### `seo-content-machine-vn`

Vietnamese SEO Content Engine cho thị trường Việt Nam.

Skill này biến input như keyword, sản phẩm, khách hàng mục tiêu và mục tiêu content thành một pipeline đầy đủ:

```text
INPUT
-> SERP ANALYZER
-> SEO REVERSE ENGINEER
-> STRATEGY ENGINE
-> CONTENT GENERATION
-> SEO QA
-> FINAL OUTPUT
```

Input mẫu:

```json
{
  "keyword": "phan mem quan ly ban hang online",
  "product": "SaaS quan ly don hang va ton kho cho shop online",
  "target_customer": "chu shop online nho tai Viet Nam",
  "goal": "sales",
  "market": "Vietnam",
  "tone": "thuc chien"
}
```

Output gồm:

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

## Cấu Trúc Repo

Repo dùng cấu trúc chuẩn kiểu `vercel-labs/agent-skills`: tất cả skill nằm trong thư mục `skills/`.

```text
.
├── README.md
├── LICENSE
└── skills/
    └── seo-content-machine-vn/
        ├── SKILL.md
        ├── README.md
        ├── AGENTS.md
        ├── metadata.json
        ├── examples/
        │   ├── input-basic.md
        │   ├── output-full-article.md
        │   └── output-seo-plan.md
        └── references/
            ├── content-strategy-framework.md
            ├── serp-analysis-framework.md
            └── vietnamese-seo-guidelines.md
```

## Dùng Với Claude Code / Claude CLI

Cách khuyến nghị:

```bash
npx skills add tuanhaviet22/ai-content-vietnamese-skills
```

Manual install nếu muốn copy trực tiếp:

```bash
mkdir -p ~/.claude/skills
cp -R skills/seo-content-machine-vn ~/.claude/skills/seo-content-machine-vn
```

Gọi trực tiếp nếu client hỗ trợ slash command:

```text
/seo-content-machine-vn "phan mem quan ly ban hang online" "SaaS quan ly don hang va ton kho" "chu shop online nho" "sales"
```

Hoặc hỏi tự nhiên:

```text
Viết bài SEO cho keyword "phần mềm quản lý bán hàng online" cho sản phẩm SaaS quản lý đơn hàng và tồn kho. Khách hàng là chủ shop online nhỏ, mục tiêu sales.
```

## Dùng Với Claude Desktop

Nếu Claude Desktop của bạn hỗ trợ Agent Skills, cài bằng:

```bash
npx skills add tuanhaviet22/ai-content-vietnamese-skills
```

Nếu chưa hỗ trợ cài skill trực tiếp, dùng repo này như prompt package:

1. Mở `skills/seo-content-machine-vn/SKILL.md`.
2. Đưa nội dung vào project instructions hoặc conversation context.
3. Khi cần context sâu hơn, thêm các file trong `references/`.

## Dùng Với Codex

Codex hỗ trợ Agent Skills và đọc skills từ `.agents/skills`, user skills hoặc plugin. Để cài nhanh qua Agent Skills CLI:

```bash
npx skills add tuanhaviet22/ai-content-vietnamese-skills
```

Manual install cho user scope:

```bash
mkdir -p ~/.agents/skills
cp -R skills/seo-content-machine-vn ~/.agents/skills/seo-content-machine-vn
```

Manual install cho repo scope:

```bash
mkdir -p .agents/skills
cp -R skills/seo-content-machine-vn .agents/skills/seo-content-machine-vn
```

Trong Codex, có thể gọi bằng skill mention nếu client hỗ trợ, hoặc prompt tự nhiên:

```text
Use seo-content-machine-vn to create a Vietnamese SEO article.
Keyword: phan mem quan ly ban hang online
Product: SaaS quan ly don hang va ton kho cho shop online
Target customer: chu shop online nho tai Viet Nam
Goal: sales
```

## Development Workflow

Khi phát triển skill mới:

1. Tạo folder trong `skills/<skill-name>/`.
2. Luôn có `SKILL.md` làm entry chính.
3. Đảm bảo `name` trong frontmatter khớp tên folder.
4. Giữ `SKILL.md` gọn, tập trung vào điều phối workflow.
5. Đưa framework dài vào `references/`.
6. Đưa input/output mẫu vào `examples/`.
7. Thêm `metadata.json` và `AGENTS.md` nếu skill cần phân phối rộng cho nhiều agent.

## Nguyên Tắc Thiết Kế

- Skill phải giải quyết một workflow thật, không chỉ là prompt đẹp.
- Output phải có chiến lược trước khi viết bài.
- SEO tiếng Việt cần cân bằng giữa traffic, trust và conversion.
- Nội dung nên có ví dụ Việt Nam, pain point Việt Nam và CTA phù hợp thị trường Việt Nam.
- Không viết bài freestyle nếu chưa có intent, SERP pattern, gap và strategy.

## License

MIT. Xem `LICENSE`.
