# geoskills

[![License: Apache-2.0](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![Claude Code Skills](https://img.shields.io/badge/Claude_Code-Skills-blueviolet)](https://skills.sh)

**Open-source Claude Code skills for Generative Engine Optimization (GEO).**

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
| [geo-audit](skills/geo-audit/) | Full website GEO+SEO audit with composite score and prioritized fix plan | Available |

---

## Installation

### Via skills.sh

```bash
npx skills add geoskills
```

### Via ClawHub

```bash
clawhub install geoskills
```

### Manual Install

Clone this repo into your Claude Code skills directory:

```bash
git clone https://github.com/anthropics/geoskills.git ~/.claude/skills/geoskills
```

### Run

```bash
# In Claude Code, just type:
/geo-audit https://example.com
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
