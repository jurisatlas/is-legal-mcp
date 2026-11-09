# Iceland Legal Research MCP Server (`is-legal-mcp`)

**[Íslenska](#lang-is) | [English Documentation](#english-documentation)**

---

<a id="lang-is"></a>
## Lögfræðilegur MCP-þjónn fyrir Ísland (`is-legal-mcp`) — Íslenska

### Um þetta gagnasafn

Þetta gagnasafn inniheldur Model Context Protocol (MCP) þjón sem tengir gervigreindarforritið þitt (Claude Desktop, Cursor, Windsurf, VS Code / Copilot eða Antigravity) beint við Lagasafn Alþingis (`althingi.is/lagasafn`) og dómasafn héraðsdómstóla, Landsréttar og Hæstaréttar Íslands (`domstolar.is`).

### Uppsetning (Val á gervigreindarforriti)

1. **Niðurhal:** Smelltu á **`<> Code` -> `Download ZIP`** efst til hægri og afþjappaðu möppunni á tölvunni þinni.
2. **Keyra uppsetningu:** Tvísmelltu á **`Click_Here_To_Install_Windows.bat`** (Windows) eða **`Click_Here_To_Install_Mac.command`** (macOS).
3. **Veldu forrit:** Merktu við þau gervigreindarforrit sem þú notar, smelltu á setja upp og endurræstu forritið.

**Öryggisathugasemd:** Uppsetningarforritið vinnur eingöngu í lesham (read-only) og snertir engar persónulegar skrár á tölvunni þinni.

### Dómstig og opinberar heimildir

| Dómstig | Dómstólar |
|:---|:---|
| **1. dómstig (8 Héraðsdómstólar)** | 8 Héraðsdómstólar (District Courts: Reykjavík, Reykjanes, Vesturland, Vestfirðir, Norðurland vestra, Norðurland eystra, Austurland, Suðurland) |
| **2. dómstig (Landsréttur)** | Landsréttur (Court of Appeal of Iceland — landsrettur.is) |
| **3. dómstig (Hæstiréttur Íslands)** | Hæstiréttur Íslands (Supreme Court of Iceland — haestirettur.is) & EFTA Court |

- **Alþingi Lagasafn (althingi.is/lagasafn):** [https://www.althingi.is/lagasafn/](https://www.althingi.is/lagasafn/) (`althingi.is`, `stjornartidindi.is`)
- **Dómstólar Íslands Unified Portal (domstolar.is — Héraðsdómstólar, Landsréttur & Hæstiréttur):** [https://www.domstolar.is](https://www.domstolar.is) (`domstolar.is`, `haestirettur.is`, `landsrettur.is`, `heradsdomstolar.is`)

---

<a id="english-documentation"></a>
## English Documentation

Model Context Protocol (MCP) server providing live, read-only access to **Iceland (IS)** legislation, official gazettes, multi-tier judicial decisions (First Instance, Regional/Cantonal/Appellate, and Supreme/Constitutional courts, including HTML and PDF full-text extraction), and statutory citation verification across all major AI clients (**ChatGPT Desktop, OpenAI Codex CLI, Claude Desktop, Claude Code CLI, Cursor, Windsurf, VS Code / GitHub Copilot / Cline / Roo Code, Google Antigravity / Gemini CLI, Perplexity, and Continue.dev**).

---

### Interactive Desktop Setup (Select Your AI Assistant)

This package includes a graphical installer for legal practitioners and non-technical users that lets you select which AI application(s) you use:

1. **Download:** Click **`<> Code`** at the top right of this repository, select **`Download ZIP`**, and extract the folder to your computer.
2. **Run the Setup Utility:**
   - **Windows:** Double-click `Click_Here_To_Install_Windows.bat`
   - **macOS:** Double-click `Click_Here_To_Install_Mac.command`
3. **Select Your AI Client(s) & Connect:** Check the box(es) for the AI assistant(s) installed on your computer (**ChatGPT Desktop & OpenAI Codex CLI**, **Claude Desktop & Claude Code CLI**, **Cursor**, **Windsurf**, **VS Code / GitHub Copilot / Cline / Roo Code**, **Google Antigravity / Gemini CLI**, or **Perplexity / Continue.dev**), click **Install to Selected AI Clients**, and restart your selected AI application.

**System Integrity Note:** The setup utility operates strictly in read-only mode with respect to your personal files and documents. It installs an isolated Python runtime inside the extracted folder and registers the server entry only in the AI client configuration files you select.

---

### Multi-Tier Judicial Hierarchy & Live Indexed National Archives

This server performs live queries across the full judicial hierarchy and official legal archives of **Iceland**, extracting full text from both HTML pages and official court/gazette PDF judgments:

| Judicial Tier | Covered Courts & Tribunals |
|:---|:---|
| **Tier 1 — First Instance** | 8 Héraðsdómstólar (District Courts: Reykjavík, Reykjanes, Vesturland, Vestfirðir, Norðurland vestra, Norðurland eystra, Austurland, Suðurland) |
| **Tier 2 — Regional / Cantonal / Appellate** | Landsréttur (Court of Appeal of Iceland — landsrettur.is) |
| **Tier 3 — Supreme & Constitutional** | Hæstiréttur Íslands (Supreme Court of Iceland — haestirettur.is) & EFTA Court |

#### Official Portals & Live Indexed Domains

- **National Legislation & Official Gazette:** Alþingi Lagasafn (althingi.is/lagasafn) — [https://www.althingi.is/lagasafn/](https://www.althingi.is/lagasafn/)
  - *Indexed Legislation Domains:* `althingi.is`, `stjornartidindi.is`
- **Court Decisions & Jurisprudence Archives:** Dómstólar Íslands Unified Portal (domstolar.is — Héraðsdómstólar, Landsréttur & Hæstiréttur) — [https://www.domstolar.is](https://www.domstolar.is)
  - *Indexed Judicial & Open Case Law Domains:* `domstolar.is`, `haestirettur.is`, `landsrettur.is`, `heradsdomstolar.is`

---

### Available MCP Tools

| Tool | Description |
|:---|:---|
| `search_legislation` | Searches enacted statutes, codes, decrees, and official gazette publications in Iceland. |
| `search_case_law` | Searches national jurisprudence and open judicial archives for Iceland. |
| `search_tiered_court_decisions` | Filters case law specifically by judicial instance (`first_instance`, `appellate_regional`, `supreme_constitutional`) or specific regional/cantonal/district court. |
| `list_court_hierarchy` | Returns the complete 3-tier court structure and supported regional court filters for Iceland. |
| `get_legal_document_markdown` | Retrieves full statutory or judicial texts (both HTML and official `.pdf` court judgments) and converts them into clean Markdown. |
| `verify_citation` | Validates statutory and case law citations against official registries. |

---

<details>
<summary><b>Manual Configuration for Developers (Optional)</b></summary>

```json
{
  "mcpServers": {
    "is-legal-mcp": {
      "command": "uvx",
      "args": [
        "--from",
        "https://github.com/jurisatlas/is-legal-mcp/archive/refs/heads/main.zip",
        "is-legal-mcp"
      ]
    }
  }
}
```
</details>
