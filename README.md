# Claude Code Skills Collection

> **Transform documents into professionally-styled masterpieces with world-class brand aesthetics**

A comprehensive collection of Claude Code skills for document generation, styling, and manipulation. Includes the **Document Polisher** skill that applies premium brand styling (McKinsey, Deloitte, Stripe, Apple, and more) to your documents, plus essential skills for working with DOCX, PDF, XLSX, and PPTX files.

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Claude Code](https://img.shields.io/badge/Claude%20Code-Skills-orange.svg)

---

## New to This? Start Here!

**Don't want to read documentation?** Just copy-paste prompts directly into Claude Code!

### One-Line Setup

Open Claude Code anywhere and paste this:

```
Clone https://github.com/promptadvisers/claude-code-polished-documents-skills and set it up for me - install the Python environment, copy skills to ~/.claude/skills/, and test it works.
```

### More Prompts

See the **[quick-start/](quick-start/)** folder for:
- [QUICK-START.md](quick-start/QUICK-START.md) - Step-by-step prompts for setup
- [PROMPTS.md](quick-start/PROMPTS.md) - Copy-paste prompts for every use case

---

## Features

### Document Polisher
Transform plain documents into professionally-styled reports with 10 premium brand themes:

| Category | Brands | Best For |
|----------|--------|----------|
| **Editorial** | The Economist | Reports, analysis, thought leadership |
| **Consulting** | McKinsey, Deloitte, KPMG | Strategy decks, executive summaries, audits |
| **Tech** | Stripe, Apple, IBM, Linear | API docs, developer guides, product specs |
| **Productivity** | Notion | Wikis, project plans, documentation |
| **Design** | Figma | Creative briefs, design docs, brand guidelines |

### Core Document Skills
- **docx** - Create and edit Word documents with full formatting support
- **pdf** - Generate, merge, split, and fill PDF forms
- **xlsx** - Work with spreadsheets including formulas and data analysis
- **pptx** - Create and modify PowerPoint presentations

### MCP Server Integration
- **FireCrawl MCP** - Extract brand identity from any website to create custom themes

---

## Quick Start

### 1. Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/claude-code-skills.git
cd claude-code-skills
```

### 2. Set Up Python Environment

```bash
# Create virtual environment
python3 -m venv venv

# Activate it
source venv/bin/activate  # macOS/Linux
# or
.\venv\Scripts\activate   # Windows

# Install dependencies
pip install python-docx
```

### 3. Copy Skills to Claude Code

Copy the `.claude/skills` folder to your project or global Claude Code directory:

```bash
# For project-specific skills
cp -r .claude/skills /path/to/your/project/.claude/

# For global skills (available in all projects)
cp -r .claude/skills ~/.claude/skills/
```

### 4. Configure Permissions

Copy the example settings file and customize:

```bash
cp .claude/settings.example.json .claude/settings.local.json
```

See [docs/SETUP.md](docs/SETUP.md) for detailed configuration options.

---

## Usage

### Using Document Polisher

In Claude Code, simply ask to polish a document:

```
Polish my report.docx with the McKinsey style
```

Or use the skill directly:

```
/skill document-polisher
```

Then select from the brand menu and provide your document.

### Command Line Usage

```bash
# Activate virtual environment
source venv/bin/activate

# Apply brand styling to a document
python .claude/skills/document-polisher/scripts/apply_brand.py \
    input.docx \
    mckinsey \
    output.docx

# List available brands
python .claude/skills/document-polisher/scripts/apply_brand.py --list
```

### Available Brands

| Brand ID | Brand Name | Style |
|----------|------------|-------|
| `economist` | The Economist | Georgia serif, red accents |
| `mckinsey` | McKinsey & Company | Georgia headings, sharp blue |
| `deloitte` | Deloitte | Calibri, teal-blue accents |
| `kpmg` | KPMG | Calibri, two-tone blue |
| `stripe` | Stripe | Arial, dark blue + purple |
| `apple` | Apple | Arial, minimalist |
| `ibm` | IBM | Arial, enterprise blue |
| `notion` | Notion | Segoe UI, clean aesthetic |
| `linear` | Linear | Arial, modern purple |
| `figma` | Figma | Arial, multi-color |

---

## MCP Server Setup (FireCrawl)

The FireCrawl MCP server enables extracting brand identity from any website to create custom themes.

### Get FireCrawl API Key

1. Go to [firecrawl.dev](https://firecrawl.dev)
2. Sign up for an account
3. Navigate to API Keys section
4. Generate a new API key

### Add MCP Server to Claude Code

**Option 1: Via Claude Code CLI**

```bash
claude mcp add firecrawl \
  --command "npx" \
  --args "-y" "@anthropic/firecrawl-mcp" \
  --env "FIRECRAWL_API_KEY=your_api_key_here"
```

**Option 2: Manual Configuration**

Add to your Claude Code MCP settings (`~/.claude/mcp_servers.json`):

```json
{
  "mcpServers": {
    "firecrawl": {
      "command": "npx",
      "args": ["-y", "@anthropic/firecrawl-mcp"],
      "env": {
        "FIRECRAWL_API_KEY": "your_api_key_here"
      }
    }
  }
}
```

### Extract Brand from Website

Once configured, ask Claude Code:

```
Extract the branding from https://example.com and add it as a new brand theme
```

See [docs/MCP-SERVERS.md](docs/MCP-SERVERS.md) for complete MCP configuration guide.

---

## Repository Structure

```
claude-code-skills/
├── .claude/
│   ├── skills/
│   │   ├── document-polisher/     # Main document styling skill
│   │   │   ├── SKILL.md           # Skill instructions
│   │   │   ├── brands/            # Brand reference files
│   │   │   ├── scripts/           # Python scripts
│   │   │   └── templates/         # Brand configuration JSON
│   │   ├── docx/                  # Word document skill
│   │   ├── pdf/                   # PDF manipulation skill
│   │   ├── xlsx/                  # Spreadsheet skill
│   │   └── pptx/                  # PowerPoint skill
│   └── settings.example.json      # Example permissions
├── docs/
│   ├── SETUP.md                   # Detailed setup guide
│   ├── MCP-SERVERS.md             # MCP server configuration
│   └── TROUBLESHOOTING.md         # Common issues & solutions
├── examples/
│   └── scripts/
│       └── create_demo_docs.py    # Generate demo documents
├── .gitignore
├── LICENSE
└── README.md
```

---

## Creating Custom Brands

### Method 1: Using FireCrawl (Recommended)

```
Use FireCrawl to extract branding from https://company.com and add it as a new brand
```

### Method 2: Manual Configuration

1. Add entry to `.claude/skills/document-polisher/templates/brand-mapping.json`:

```json
{
  "my_brand": {
    "name": "My Brand",
    "description": "Description of the brand style",
    "category": "consulting",
    "colors": {
      "primary": "#0066CC",
      "accent": "#FF6600",
      "background": "#FFFFFF",
      "textPrimary": "#333333",
      "textSecondary": "#666666"
    },
    "typography": {
      "headingFont": "Arial",
      "bodyFont": "Calibri",
      "headingWeight": "bold",
      "bodyWeight": "normal"
    },
    "styles": {
      "h1": {"size": 32, "color": "#0066CC", "bold": true},
      "h2": {"size": 24, "color": "#0066CC", "bold": true},
      "h3": {"size": 16, "color": "#333333", "bold": true},
      "body": {"size": 11, "color": "#333333"},
      "caption": {"size": 9, "color": "#666666"}
    },
    "elements": {
      "borderRadius": 4,
      "tableStyle": "clean_lines",
      "accentUse": "headers_and_highlights"
    }
  }
}
```

2. Optionally create a reference file at `.claude/skills/document-polisher/brands/my_brand.md`

---

## Troubleshooting

### Fonts Not Displaying Correctly

The skill uses cross-platform fonts (Arial, Calibri, Georgia, Segoe UI) that work on both Mac and Windows. If fonts appear different:

1. Ensure the document is opened in Microsoft Word (not Preview or other viewers)
2. Check that the specified fonts are installed on your system
3. Word may substitute fonts in Compatibility Mode

### python-docx Not Found

```bash
pip install python-docx
```

### Permission Errors

Copy `settings.example.json` to `settings.local.json` and ensure the required permissions are allowed.

See [docs/TROUBLESHOOTING.md](docs/TROUBLESHOOTING.md) for more solutions.

---

## Contributing

Contributions are welcome! Please:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/new-brand`)
3. Commit your changes (`git commit -am 'Add new brand theme'`)
4. Push to the branch (`git push origin feature/new-brand`)
5. Open a Pull Request

### Adding New Brands

When adding new brand themes:
- Use only cross-platform fonts (Arial, Calibri, Georgia, Times New Roman, Segoe UI)
- Test on both Mac and Windows if possible
- Include both JSON config and markdown reference file
- Update the README brand table

---

## License

MIT License - see [LICENSE](LICENSE) for details.

---

## Acknowledgments

- Built for [Claude Code](https://claude.com/claude-code) by Anthropic
- Brand extraction powered by [FireCrawl](https://firecrawl.dev)
- Document generation with [python-docx](https://python-docx.readthedocs.io/)

---

## Support

- **Issues**: [GitHub Issues](https://github.com/YOUR_USERNAME/claude-code-skills/issues)
- **Discussions**: [GitHub Discussions](https://github.com/YOUR_USERNAME/claude-code-skills/discussions)
- **Claude Code Help**: Run `/help` in Claude Code

---

Made with AI assistance
