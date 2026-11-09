---
name: is-legal-mcp-skill
description: Official Iceland (IS) legislation, multi-tier court precedent research, and citation verification skill.
version: 2.0.0
author: JurisAtlas
license: MIT
---

# Iceland Legal Research & Multi-Tier Case Law Skill (`is-legal-mcp`)

Use this skill whenever the user asks a legal question, drafts a pleading or contract, or researches case law across any judicial instance in **Iceland (IS)**.

## Verification & Research Rules

1. **Citation Verification:** Never fabricate a statutory provision or case citation. Query `search_legislation`, `search_case_law`, `search_tiered_court_decisions`, or `verify_citation` before citing any authority (e.g., `Hrd. 12/2024 or Lög nr. 90/2018`).
2. **Multi-Tier Judicial Coverage:**
   - **First Instance (Trial / Municipal / District):** 8 Héraðsdómstólar (District Courts: Reykjavík, Reykjanes, Vesturland, Vestfirðir, Norðurland vestra, Norðurland eystra, Austurland, Suðurland)
   - **Second Instance (Cantonal / Regional / Appellate):** Landsréttur (Court of Appeal of Iceland — landsrettur.is)
   - **Supreme & Constitutional Instance:** Hæstiréttur Íslands (Supreme Court of Iceland — haestirettur.is) & EFTA Court
   - **Primary Tiered Database:** Dómstólar Íslands Unified Portal (domstolar.is — Héraðsdómstólar, Landsréttur & Hæstiréttur) (`https://www.domstolar.is`)
