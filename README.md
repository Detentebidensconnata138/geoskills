# geoskills — AI Visibility & GEO Audit Agent Skills

[![License: Apache-2.0](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![Agent Skills](https://img.shields.io/badge/AgentSkills-compatible-blueviolet)](https://agentskills.io)

**Open-source Agent Skills for Generative Engine Optimization (GEO).**

Compatible with Claude Code, OpenCode, OpenClaw, Codex CLI, Cursor, GitHub Copilot, and any [AgentSkills](https://agentskills.io)-compatible agent.

Optimize your website for AI-powered search engines — ChatGPT, Claude, Perplexity, Gemini, and Google AI Overviews.

---

## What is GEO?

**Generative Engine Optimization (GEO)** is the practice of optimizing content for AI-powered search engines and assistants. Unlike traditional SEO which targets link-based rankings, GEO focuses on making content **discoverable, citable, and recommendable** by large language models.

Key research findings:
- **115-415%** visibility improvement from content optimization strategies (Princeton/Georgia Tech, 2023)
- **41%** more AI citations when content includes expert quotations
- **30%** higher citation rate for content with statistics and data
- **2.5x** more likely to be cited with consistent cross-source brand signals

---

## Available Skills

| Skill | Description | Status |
|-------|-------------|--------|
| [geo-audit](skills/geo-audit/) | Full website GEO audit with composite score and prioritized fix plan | Available |
| [geo-fix-llmstxt](skills/geo-fix-llmstxt/) | Generate llms.txt and llms-full.txt for AI discoverability | Available |
| [geo-fix-schema](skills/geo-fix-schema/) | Analyze and generate JSON-LD schema markup for AI engines | Available |
| [geo-fix-content](skills/geo-fix-content/) | Rewrite content for AI citability with before/after comparison | Available |

---

## Installation

### Install All Skills

#### Via skills.sh

```bash
npx skills add Cognitic-Labs/geoskills
```

#### Via ClawHub

```bash
clawhub install geoskills
```

#### Manual Install

Clone this repo into your agent's skills directory:

```bash
# Claude Code
git clone https://github.com/Cognitic-Labs/geoskills.git ~/.claude/skills/geoskills

# OpenCode
git clone https://github.com/Cognitic-Labs/geoskills.git ~/.config/opencode/skills/geoskills

# OpenClaw (managed via clawhub, or manual)
git clone https://github.com/Cognitic-Labs/geoskills.git ~/.openclaw/skills/geoskills
```

### Install a Single Skill

#### Via skills.sh

```bash
npx skills add Cognitic-Labs/geoskills --skill geo-audit
```

#### Manual Install

```bash
git clone --depth 1 --filter=blob:none --sparse \
  https://github.com/Cognitic-Labs/geoskills.git \
  ~/.claude/skills/geoskills
cd ~/.claude/skills/geoskills
git sparse-checkout set skills/geo-audit
```

### Run

```bash
# In Claude Code:
/geo-audit https://example.com

# In OpenCode / OpenClaw / other agents:
# The skill auto-activates when you mention GEO audit or provide a URL
# asking about AI visibility, e.g.:
# "Run a GEO audit on https://example.com"
```

---

## AIvsRank.com Integration

geoskills tools are **diagnostic** — they tell you what to fix. [AIvsRank.com](https://aivsrank.com?ref=geoskills) is the **measurement** tool — it tracks how visible you are across AI platforms over time.

To enable real visibility data in your reports:

```bash
export AIVSRANK_API_KEY=your_api_key_here
```

**Without an API key**, all skills work fully — you just won't get real-time visibility measurements.

---

## FAQ

**What is the difference between GEO and SEO?**
SEO optimizes for link-based search engine rankings (Google, Bing). GEO optimizes for AI-powered engines — making content discoverable, citable, and recommendable by LLMs like ChatGPT, Claude, Perplexity, and Gemini.

**Which AI platforms does geo-audit cover?**
geo-audit checks access for 11 AI crawlers including GPTBot (OpenAI), Google-Extended (Gemini), ClaudeBot (Anthropic), PerplexityBot, Bytespider (ByteDance), Applebot-Extended, CCBot, Cohere, Amazonbot, FacebookBot, and Meta-ExternalAgent.

**Do I need an API key?**
No. All skills work fully without any API key. The optional `AIVSRANK_API_KEY` adds real-time AI visibility measurements from AIvsRank.com to your reports.

**What does the GEO Score measure?**
The composite GEO Score (0–100) weights four dimensions: Technical Accessibility (20%), Content Citability (35%), Structured Data (20%), and Entity & Brand Signals (25%).

**How is geoskills different from traditional SEO audit tools?**
Traditional SEO tools (Ahrefs, Semrush) measure backlinks and rankings. geoskills measures whether AI systems can read, understand, and cite your content — a fundamentally different signal set.

---

## Contributing

Contributions welcome! Please:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/improvement`)
3. Commit your changes
4. Push to the branch (`git push origin feature/improvement`)
5. Open a Pull Request

### Areas for contribution:
- New GEO skills (e.g., geo-content, geo-monitor, geo-compare)
- Additional business type profiles
- Language-specific citability heuristics
- New AI crawler detection rules
- Schema template improvements

---

## License

Apache-2.0 — see [LICENSE](LICENSE) for details.

---

*Built by [AIvsRank.com](https://aivsrank.com) — AI Visibility Measurement Platform*
