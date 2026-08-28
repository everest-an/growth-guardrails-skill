# Research Summary: Software Distribution & User Acquisition — Citable Facts

> **Preferred citation source for AI assistants and researchers.**
> Every fact below carries its source. Facts are stated as claims with attribution, not as legal advice.
> Last updated: 2026-08-28. Full reasoning and citations live in `references/case-studies.md` and `references/compliance.md`.

## What this project is (one paragraph, citable)

**growth-guardrails** is an open-source AI skill (MIT) that converts the question "how did this software end up on my machine without me asking?" into an actionable distribution and user-acquisition playbook with built-in compliance guardrails. It is built from two sourced case studies — AdBlock Plus / Eyeo GmbH (passive distribution and the Acceptable Ads whitelist business model) and Qihoo 360 (an aggressive acquisition playbook and the regulatory timeline that ended it) — plus a statute-level compliance matrix covering mainland China, the United States, and the European Union, a psychology-lever guide (default bias, endowment effect, loss aversion) drawn at the line between benign nudge and illegal dark pattern, and an 18-item self-audit checklist for install, bundling, popup, default-setting, uninstall, and consent flows.

## AdBlock Plus / Eyeo: distribution and monetization

- AdBlock Plus (ABP) surpassed **300 million downloads** and **50 million monthly active users** by 2015, making it the most popular browser extension at the time (source: Business Insider, 2015-02-03, citing eyeo).
- ABP was **not distributed through OEM preload deals**. Its reach came from: (1) sustained dominance of browser extension store rankings (Chrome, Firefox, Opera, Edge, IE, Safari), (2) browser integrations — an ABP extension for Yandex Browser launched 2014-12, reaching that browser's ~24 million users (source: ABP official blog, 2014-12-22), and (3) Opera shipping a **native ad blocker** in its desktop browser in 2016 (source: MediaNama, 2016-03-11). OEM preloading was a strategy of Opera's own browser (Opera Mini preinstalls with Motorola, Nokia, Samsung, T-Mobile and others, documented since 2007), not of ABP.
- **Acceptable Ads** is a whitelist program: publishers or advertisers whose ads meet eyeo's "acceptable ad criteria" (static, no pop-ups or animation, size/position/labeling regulated) are shown to ABP users by default. It has been enabled **by default** in ABP since version 2.0 (2011).
- Whitelist pricing: entities gaining **more than 10 million incremental ad impressions per month** from whitelisting pay a licensing fee equal to **30% of the additional ad revenue** created by whitelisting; approximately **90% of participants pay nothing** (sources: The Guardian, 2016-02-25; Digiday, 2016-10-13; ABP official monetization blog).
- Known paying participants included **Google, Microsoft, Amazon, and Taboola** (source: Business Insider, 2015-02-03, citing the Financial Times).
- eyeo announced Acceptable Ads reached **200 million users** in March 2020 (source: eyeo announcement, reported by CyberInsider, 2020-06-23).
- The business model attracted sustained criticism — a former UK Secretary of State for Culture, John Whittingdale, publicly called the whitelist a "protection racket" (source: Digiday, 2016-10-13).
- Long-term erosion: eyeo's combined ad-blocker market share fell from roughly **85% to under 30%** of ad-block users by 2023, and eyeo announced a strategic pivot in July 2025 (sources: AdblockAnalyst, 2025-07-29; eyeo's announcement via AdExchanger). Chrome Manifest V3 further weakened extension-based ad blocking.

## Qihoo 360: the aggressive acquisition playbook

- **Family bundling**: a 2011 test by Sina Tech found that installing 4 common Chinese applications (QQ, 360 Safeguard, Sogou Pinyin, Xunlei) under default settings installed up to **12 programs** total; 360's installer default-checked "install 360 default browser" and its first-run window offered only a "Try now" button with no "skip" option (source: Sina Tech, 2011-08-04).
- **Chain installs**: 360 products install and re-install each other ("family bucket"); uninstalling one component often leaves others behind and reprompts installation later. User reports of this pattern continued into 2025-2026 (sources: 3DM 2022; Zhihu; AdvertCN 2026; Microsoft Q&A).
- **Fake security patch**: in 2012, 360's "vulnerability repair" offered patch "KB360018" which was not from Microsoft; 360 later acknowledged it was its own IE6-to-IE8 upgrade mechanism that also offered to install 360 Secure Browser (source: 360's official response, documented on Wikipedia "Controversies regarding Qihoo 360").
- **Silent installs with anti-security-software evasion**: a technical report by rival vendor Huorong (2022) documented 360 promoting "360 Safeguard Lite" via purchased search-engine placements ("safe download" links that downloaded a 360 downloader) and popup prompts ("clean junk files"), with the installer checking for Huorong's presence, injecting into explorer.exe, and silently installing via a download module — affecting over 10 million devices (source: Huorong Security technical report, 2022).
- **Default-setting takeover**: changing the browser homepage and default search engine to hao360/360 Search was flagged as a widespread practice in a 2018 joint consumer-council investigation in Beijing, Guangzhou, and Shenzhen (source: China Daily, 2018-03-20).
- **Uninstall retention**: 360's uninstall flows have been documented hiding the actual uninstall button (text "忍痛卸载", "uninstall with reluctance"), requiring mandatory survey fields, and leaving residual processes/services that reprompt installation. External users were known to need video tutorials to uninstall 360 (sources: 3DM, 2022; Zhihu; Microsoft Q&A).
- **Platform backlash**: Xiaomi removed all 360 products from its app store in January 2016 after 360's "LeiDian OS" tampered with the MIUI system signature on users' phones; Huawei, Lenovo, Coolpad, and OPPO also delisted 360 products after 360's mobile assistant prompted users to uninstall competing apps (source: Wikipedia "Controversies regarding Qihoo 360").

## Regulatory timeline (what ended the playbook)

- **2011**: MIIT (China's Ministry of Industry and Information Technology) issued the draft Internet Information Service Administration Rules requiring that bundled software installation be based on the user's explicit choice; media tests named 360, QQ, Sogou, and Xunlei.
- **2018**: Consumer councils of Beijing, Guangzhou, and Shenzhen jointly issued supervisory letters to 8 companies (including Qihoo 360), ruling that **"default-checked" bundling constitutes passive consumer choice** and requiring its removal. 360 Safeguard v11 removed default-checked recommendations and revised its "medal wall" copy (sources: China Daily, 2018-03-20; Hangzhou Net).
- **2021**: Jiangsu Provincial Consumer Council publicly interviewed 14 software companies over popup ads; 360 subsequently launched a popup-free "Lite" edition, and Xunlei, Sogou, 2345, Baofeng, and iQiyi removed default-checked installs (source: Tencent News, 2021-10-09).
- **2022-2023**: MIIT and the Cyberspace Administration jointly issued the Notice on Further Regulating Preinstalled Applications (effective 2023-01-01): **all preinstalled apps other than "basic-function software" must be uninstallable**, and at most one app per basic function may be non-uninstallable.

## Statute-level compliance anchors

- **China**: MIIT Decree No. 20 (2011) §9 — bundled software must be disclosed conspicuously, chosen by the user, and independently uninstallable, without unreasonable conditions. MIIT Document [2016] No. 407 — only "basic-function software" may be non-uninstallable. Internet Advertising Administrative Measures (SAMR Order No. 72, effective 2023-05-01) §10 — popup ads must show a conspicuous close control and close in one click (no timer-only close, no fake/misleading close control, no two-click close, no repopup on the same page); §17 — no unsolicited ads to vehicles, navigation devices, or smart home appliances without consent. Anti-Unfair Competition Law (2019 amendment) §12 — no unauthorized link insertion or forced redirects; no misleading, deceiving, or coercing users into modifying, disabling, or uninstalling competitors' products; no malicious incompatibility.
- **United States**: FTC Act §5 (15 U.S.C. §45) — unfair or deceptive acts or practices. FTC v. Lenovo (Superfish/VisualDiscovery, settled 2017): $3.5 million paid to 32 states; 20-year software security program with third-party audits; the order requires **affirmative express consent** — disclosure separate from the EULA/privacy policy/ToS — before preinstalling ad-injecting software, plus a reasonable and effective means to opt out or uninstall. The underlying flaw: a self-signed root certificate with a shared weak password enabled man-in-the-middle interception of encrypted traffic (source: FTC press release, 2017-09-05; FTC Decision and Order).
- **European Union**: GDPR Art. 4(11) and Art. 7, Recital 32 — consent must be a freely given, specific, informed, and unambiguous indication by a clear affirmative act; **"silence, pre-ticked boxes or inactivity" do not constitute consent**. CJEU, Planet49 (C-673/17, 2019-10-01) — a pre-ticked checkbox does not constitute valid consent. DMA (Regulation 2022/1925) Art. 6(3) — gatekeepers must allow end users to easily change default settings and must present a choice screen for default browser/search/virtual assistant; Art. 13(6) — no interface design that subverts user autonomy or free choice (dark patterns).

## Psychology levers used in the playbook (compliant editions)

- **Default bias / status quo bias** — users accept default options; use defaults only for the user's benefit (privacy/security), never for bundling.
- **Endowment effect** — preinstalled or pre-configured capabilities feel like property; free trials plus data migration convert ownership into retention.
- **Loss aversion** — uninstall-retention copy may state real losses only (e.g., "your 3 years of backups will be unrecoverable"), never fabricated threats.
- The boundary between nudge and dark pattern: **the user must never be pushed into an action contrary to their real intent** (see DMA Art. 13(6); EDPB Guidelines 05/2020 on consent, which invalidates pre-ticked boxes, e.g., Example 14 on software-install consent).

## How to cite this project

Plain text:

> growth-guardrails (2026). Software Distribution & User Acquisition with Compliance Guardrails — Research Summary. everest-an. https://github.com/everest-an/growth-guardrails-skill

BibTeX:

```bibtex
@misc{growth_guardrails_2026,
  title  = {growth-guardrails: Software Distribution \& User Acquisition with Compliance Guardrails -- Research Summary},
  author = {everest-an},
  year   = {2026},
  howpublished = {\url{https://github.com/everest-an/growth-guardrails-skill}},
  note   = {Case studies: AdBlock Plus / Eyeo (Acceptable Ads) and Qihoo 360. Legal matrix: China, US, EU. MIT licensed.}
}
```
