# Alchemist Agents Landing Page — Design Brief

## Product

**Product**: [getalchemist.io](https://getalchemist.io) — SAS migration platform by T1A
**New Feature**: Alchemist MCP & Alchemist Skill — agent-native integrations for SAS code conversion

## Page Goal

Drive visitors to **book a demo / contact sales** for setup or full end-to-end migration.

## Primary Audience

**Data engineers and developers** who would configure the MCP integration themselves.

## Tech Stack

Standalone HTML/CSS/JS — will be injected into Webflow (getalchemist.io runs on Webflow with custom code injection support).

---

## Design Direction

### Style
- Match existing Alchemist brand: **dark theme**, **neon green accents** (#00FF88), particle-style backgrounds
- Fonts: Space Grotesk (display/body) + JetBrains Mono (code)
- Inspiration: [basecamp.com/agents](https://basecamp.com/agents) — technology preview framing, developer-first tone, dual offering presentation

### Two Approaches Under Review

**Approach A — "The Flow"** (narrative-driven scroll):
1. Hero — badge + headline + embedded YouTube video
2. Animated code block — SAS to PySpark conversion
3. Problem framing — 3 cards (time, consistency, engineer-dependency)
4. Architecture diagram — animated dashed lines showing agent → Alchemist → notebook flow
5. MCP vs Skill — side-by-side comparison cards
6. Supported agents — logo strip (Databricks, Snowflake, Claude Code, Any Other)
7. Deployment options — Cloud vs Docker (air-gapped)
8. CTA — Book a Demo / Contact Sales

**Approach B — "The Showcase"** (demo-centered):
1. Cinematic hero — grid overlay + headline + video with reflection effect
2. Feature cards — 4-column grid (Speed, Consistency, Agent-Native, Deploy Anywhere)
3. Full-width terminal-style code demo (macOS window chrome)
4. Tabbed MCP/Skill switcher with mini diagrams
5. Agent logos strip
6. CTA

---

## Content Source

Video demo (3 min): https://youtu.be/IBZDeOhHPc8?si=qiE-zlq2bY8ScpwT
Embedded in hero section of both approaches.

### Key Messages (from video)

- **Problem**: Manual SAS migrations are slow, inconsistent, and require specialized engineers
- **Solution**: Alchemist MCP and Skill let non-engineering/business teams perform migrations faster via coding agents
- **How it works**: User asks agent in natural language → agent delegates to Alchemist → converted code returned → user reviews and executes
- **Supported agents**: Databricks Genie Code, Snowflake Cortex Code, Claude Code, any other MCP-compatible agent
- **Deployment**: Alchemist Cloud (api.getalchemist.io) or air-gapped Docker deployment
- **CTA**: Contact sales or customer success for setup

### Code Example (from video)

**SAS input:**
```sas
data work.high_power_cars;
  set sashelp.cars;
  where horsepower > 300;
  tax_category = 'Premium';
  adjusted_msrp = msrp * 1.05;
run;
```

**PySpark output:**
```python
from pyspark.sql import functions as F

df = spark.table("sashelp.cars")
df = df.filter(F.col("horsepower") > 300)
df = df.withColumn("tax_category", F.lit("Premium"))
df = df.withColumn("adjusted_msrp", F.col("msrp") * 1.05)
```

---

## Assets

Located in `/logos/`:
- `alchemist logo_colour.svg` — Alchemist brand logo
- `Databricks.png` — Databricks logo (display at 46px)
- `snowflake.png` — Snowflake logo (display at 32px)
- `claude-logo.svg` — Claude Code logo (display at 26px)
- "Any Other" — placeholder SVG icon

---

## Integration Methods

### Alchemist MCP (Model Context Protocol)
- Standardized protocol for agent-to-tool communication
- Works with any MCP-compatible coding agent
- Cloud or air-gapped Docker deployment
- **Best for**: Teams using multiple agents or building custom workflows

### Alchemist Skill (Custom Agent Skill)
- Native skill integration for specific platforms
- Deep integration with agent capabilities
- Platform-optimized conversion pipeline
- **Best for**: Teams committed to a single agent platform like Databricks

---

## Deployment Options

| Option | Description | Endpoint |
|--------|-------------|----------|
| **Alchemist Cloud** | Public internet, zero infra | api.getalchemist.io |
| **Air-Gapped (Docker)** | Private cloud, full control | Self-hosted |

---

## Status

- [x] Design brief
- [x] Approach A mockup (`approach-a-the-flow.html`)
- [x] Approach B mockup (`approach-b-the-showcase.html`)
- [x] Approach C mockup (`approach-c-the-terminal.html`)
- [ ] User selects final approach
- [ ] Design spec
- [ ] Implementation plan
- [ ] Production build
