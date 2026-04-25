# AI Content Vietnamese Skills

Repo này chứa các **Agent Skills cho content tiếng Việt**, tập trung vào SEO, content strategy, reverse SERP và viết bài có khả năng hỗ trợ chuyển đổi.

Mục tiêu không phải tạo prompt rời rạc, mà là đóng gói các workflow thực chiến thành skill có cấu trúc rõ ràng, dễ cài, dễ sửa và dễ dùng lại trên nhiều AI coding/agent tool.

## Skill Hiện Có

### `seo-content-machine-vn`

Một SEO Content Engine cho thị trường Việt Nam.

Pipeline chính:

```text
INPUT
-> SERP ANALYZER
-> SEO REVERSE ENGINEER
-> STRATEGY ENGINE
-> CONTENT GENERATION
-> SEO QA
-> FINAL OUTPUT
```

Skill này nhận đầu vào như:

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

```text
.
├── README.md
└── seo-content-machine-vn/
    ├── SKILL.md
    ├── README.md
    ├── examples/
    │   ├── input-basic.md
    │   ├── output-full-article.md
    │   └── output-seo-plan.md
    └── references/
        ├── content-strategy-framework.md
        ├── serp-analysis-framework.md
        └── vietnamese-seo-guidelines.md
```

## Cài Đặt Cho Claude CLI / Claude Code

Claude Code hỗ trợ skills theo chuẩn `SKILL.md`.

Cài như personal skill để dùng ở mọi project:

```bash
mkdir -p ~/.claude/skills
cp -R seo-content-machine-vn ~/.claude/skills/seo-content-machine-vn
```

Sau đó có thể gọi trực tiếp:

```text
/seo-content-machine-vn "phan mem quan ly ban hang online" "SaaS quan ly don hang va ton kho" "chu shop online nho" "sales"
```

Hoặc hỏi tự nhiên:

```text
Viết bài SEO cho keyword "phần mềm quản lý bán hàng online" cho sản phẩm SaaS quản lý đơn hàng và tồn kho. Khách hàng là chủ shop online nhỏ, mục tiêu sales.
```

Nếu muốn skill chỉ áp dụng cho một project, copy vào thư mục project:

```bash
mkdir -p .claude/skills
cp -R seo-content-machine-vn .claude/skills/seo-content-machine-vn
```

## Dùng Với Claude Desktop

Claude Desktop không phải lúc nào cũng có cơ chế load skills giống Claude Code. Cách dùng phụ thuộc phiên bản và tính năng đang được bật.

Nếu Claude Desktop của bạn hỗ trợ Agent Skills:

1. Thêm folder `seo-content-machine-vn` vào khu vực skills theo hướng dẫn của Claude Desktop.
2. Đảm bảo file entry là `SKILL.md`.
3. Gọi skill bằng tên `seo-content-machine-vn` hoặc paste request phù hợp với description.

Nếu Claude Desktop chưa hỗ trợ skills trực tiếp, dùng như prompt package:

1. Mở `seo-content-machine-vn/SKILL.md`.
2. Paste nội dung vào project instructions hoặc conversation context.
3. Khi cần chi tiết hơn, paste thêm file trong `references/`.

## Dùng Với Codex / OpenAI Codex CLI

Codex hiện không load Claude Skills native theo cùng cơ chế `~/.claude/skills`.

Cách dùng khuyến nghị:

1. Dùng repo này như một **prompt/workflow package**.
2. Đưa nội dung `seo-content-machine-vn/SKILL.md` vào instructions của Codex.
3. Khi cần output chuẩn hơn, cung cấp thêm các file trong `references/` và `examples/`.

Ví dụ prompt cho Codex:

```text
Use the workflow in seo-content-machine-vn/SKILL.md to create a Vietnamese SEO article.
Keyword: phan mem quan ly ban hang online
Product: SaaS quan ly don hang va ton kho cho shop online
Target customer: chu shop online nho tai Viet Nam
Goal: sales
```

Nếu tool của bạn hỗ trợ custom instructions theo project, có thể trỏ hoặc copy nội dung `SKILL.md` vào phần đó.

## Development Workflow

Khi phát triển skill mới:

1. Tạo folder riêng cho từng skill.
2. Luôn có `SKILL.md` làm entry chính.
3. Giữ `SKILL.md` gọn, tập trung vào điều phối workflow.
4. Đưa framework dài vào `references/`.
5. Đưa input/output mẫu vào `examples/`.
6. Tránh tạo nhiều skill nhỏ nếu user thực tế cần một pipeline liền mạch.

## Nguyên Tắc Thiết Kế

- Skill phải giải quyết một workflow thật, không chỉ là prompt đẹp.
- Output phải có chiến lược trước khi viết bài.
- SEO tiếng Việt cần cân bằng giữa traffic, trust và conversion.
- Nội dung nên có ví dụ Việt Nam, pain point Việt Nam và CTA phù hợp thị trường Việt Nam.
- Không viết bài freestyle nếu chưa có intent, SERP pattern, gap và strategy.

## License

Chưa khai báo license.
