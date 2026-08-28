# growth-guardrails · 增长护栏

> **Software distribution & user-acquisition strategy, with compliance guardrails built in.**
> 软件分发与用户获取策略研究——渠道照抄、套路变体、红线避开。

A ready-to-use AI skill that turns the "how did this app get on my machine without me asking" question
into an actionable playbook. Built from deep case studies of **AdBlock Plus** (passive distribution +
Acceptable Ads B2B monetization) and **Qihoo 360** (aggressive acquisition, and what it cost them),
plus a jurisdiction-level compliance matrix (China / US / EU) and a copy-paste self-audit checklist.

Unlike "growth hacking" playbooks that age into lawsuits, this skill ships with guardrails: every
tactic has a **compliant variant** and every red line has its **statute citation**.

---

## Why

- **Channel inventory** — 8 passive-distribution channels (store placement, browser/OS integration,
  OEM preload, download-site bundling, cross-family referral, onboarding popups, default-settings,
  uninstall retention), each with a compliant and a forbidden form.
- **Case studies with sources** — how ABP actually got distributed (store dominance + browser
  integration + default-on whitelist — *not* OEM deals, a common misconception), the Acceptable Ads
  economics (30% of incremental ad revenue above 10M monthly impressions, 90% of participants free),
  and the full 360 playbook (family bundling, scareware popups, fake patches, silent installs,
  uninstall retention) with the regulatory timeline that shut it down.
- **Compliance matrix** — China (MIIT Decree No. 20 §9, 2023 preload notice, Internet Ad Measures §10,
  Anti-Unfair-Competition Law §12), US (FTC Act §5, the FTC v. Lenovo/Superfish order), EU
  (GDPR Art. 4(11)/7/Recital 32, CJEU Planet49, DMA Arts. 6(3)/13(6)) — article-level, not vibes.
- **Psychology levers, compliant editions** — default bias, endowment effect, loss aversion: how to
  use each without crossing into dark patterns (the line: *the user must never be forced into an action
  against their real intent*).
- **Self-audit checklist** — 18 checkbox items covering install/bundle/popup/default/uninstall/data
  consent before you ship anything.

---

## Installation

This is a standard `SKILL.md` skill directory — the repo root *is* the skill.

### opencode

```bash
# option A: clone into your skills folder
git clone https://github.com/everest-an/growth-guardrails-skill.git .opencode/skills/growth-guardrails

# option B: clone anywhere and register the path in opencode.json
# { "skills": { "paths": ["/path/to/growth-guardrails"] } }
```

### Claude Code / Cursor

```bash
git clone https://github.com/everest-an/growth-guardrails-skill.git ~/.claude/skills/growth-guardrails
```

### Any AI / manual

Point the model at `SKILL.md` and the four files in `references/`. No code required.

Restart your editor after installing so the skill loader picks it up.

---

## Quick start

Ask your AI anything like:

- "How do I get distribution without buying ads?" *(channel inventory)*
- "Can we bundle our client with the main product? Is that legal?" *(red-line check)*
- "How did AdBlock Plus/360 actually grow?" *(case deep-dive)*
- "Review our uninstall flow / popups / default settings for compliance" *(self-audit)*

The skill runs a 5-step workflow: **collect input → inventory channels → compliance screen →
generate strategy → deliver a distribution strategy doc** (channel table, ✅/⚠️/🚫 verdicts with
citations, prioritized combo, checklist, risk register).

---

## Repository layout

```
growth-guardrails/
├── SKILL.md                      # workflow + trigger keywords + key findings
├── references/
│   ├── case-studies.md           # ABP & 360 deep dives, sourced
│   ├── compliance.md             # CN / US / EU regulatory matrix
│   ├── playbook.md               # 8 compliant tactics, 10 red lines, checklist, templates
│   └── examples.md               # real-world mapping: ABP/360 tactics → compliant variants
├── LICENSE                       # MIT
└── README.md
```

---

## Core findings (so you get the punchline fast)

1. **ABP had no OEM deals.** It grew via store dominance (300M+ downloads), browser integrations
   (Yandex 24M users; Opera later built its *own* blocker), and a **default-on** Acceptable Ads
   whitelist — the default-on part is also what eroded its reputation (market share ~85% → <30%).
2. **Acceptable Ads = B2B-funded defaults.** Advertisers above 10M incremental impressions/month pay
   30% of the whitelist-driven ad revenue; ~90% of participants pay nothing. Google, Microsoft,
   Amazon, Taboola all paid.
3. **360's playbook worked only in a regulatory vacuum.** After 2018 (Beijing/Guangzhou/Shenzhen
   consumer councils) and 2021 (Jiangsu) enforcement, default-checked bundling and scareware popups
   were forced out of the industry. Copying them today is not a growth hack, it's a fine.

---

## Disclaimer

This project is research and an operational framework, **not legal advice**. Regulations change;
verify citations against official texts (links in `references/`) before relying on them. When in
doubt, have counsel review the specific tactic.

---

## License

[MIT](./LICENSE) © 2026 everest-an. Free to use, modify, redistribute — keep the copyright notice.

---

## 中文简介

**增长护栏** —— 一个开箱即用的 AI 技能:把「这软件怎么没让我装就上来了」拆成可复用的分发渠道模型与不可触碰的红线清单。

- 深度案例:ABP(被动分发 + Acceptable Ads B 端变现,含常见误解纠正)与 360(激进获客全集 + 监管时间线)
- 合规矩阵:中国大陆(工信部 20 号令第九条、2023 预置通告、互联网广告管理办法第十条、反不正当竞争法第十二条)/ 美国(FTC §5、FTC v. Lenovo 案)/ 欧盟(GDPR、Planet49、DMA)——条款号级,不是感觉级
- 心理学杠杆的合规版:默认偏差、所有权效应、损失厌恶——判据:**用户是否被迫做了违背真实意图的事**
- 18 项自查 checklist + 输出模板

**安装**(任一 AI 工具):clone 到 `.opencode/skills/` 或 `~/.claude/skills/`,或直接把 `SKILL.md` + `references/` 丢给任意 AI。向 AI 说「分发策略 / 获客 / 捆绑 / OEM 预装 / 弹窗 / 卸载留客 / 合规边界」即触发。

**免责声明**:本项目是研究框架,不构成法律意见;引用前请以官方文本复核。