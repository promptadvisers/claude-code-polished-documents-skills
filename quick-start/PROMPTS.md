# Copy-Paste Prompts for Claude Code

Just copy any of these prompts and paste them directly into Claude Code.

---

## Setup Prompts

### Complete Auto-Setup (Recommended)
```
I want to use the document-polisher skill from this repo:
https://github.com/promptadvisers/claude-code-polished-documents-skills

Please:
1. Clone it to a suitable location
2. Set up the Python environment with python-docx
3. Install the skills globally to ~/.claude/skills/
4. Configure the necessary permissions
5. Test that everything works by creating a sample styled document
```

### Manual Clone + Setup
```
git clone https://github.com/promptadvisers/claude-code-polished-documents-skills.git

Then set up the Python environment and install the skills for me.
```

### Install Skills Only (If Already Cloned)
```
Copy the skills from ./claude-code-polished-documents-skills/.claude/skills/
to my global Claude skills directory at ~/.claude/skills/

Then verify they're accessible.
```

---

## FireCrawl MCP Setup

### Full MCP Setup
```
Set up the FireCrawl MCP server for me:
1. Show me how to get an API key from firecrawl.dev
2. Add the MCP server to my Claude Code config
3. Verify it's working
```

### Add MCP with Existing API Key
```
Add the FireCrawl MCP server to Claude Code with this API key: [YOUR_KEY]

Use this command:
claude mcp add firecrawl --command "npx" --args "-y" "@anthropic/firecrawl-mcp" --env "FIRECRAWL_API_KEY=[YOUR_KEY]"
```

---

## Document Polishing Prompts

### Basic Styling
```
Polish my document "report.docx" with the McKinsey brand style.
```

### Style with Specific Output Name
```
Apply Stripe branding to "proposal.docx" and save as "proposal_styled.docx"
```

### Create + Style in One Step
```
Create a professional quarterly business review document and apply the Deloitte style.
Include:
- Executive Summary
- Key Metrics (with a table)
- Achievements
- Challenges
- Next Quarter Goals
```

### All Available Brands
```
Show me all available brand styles in document-polisher and their descriptions.
```

---

## Brand-Specific Prompts

### The Economist (Editorial)
```
Create a thought leadership article about AI trends and style it like The Economist
with their signature red accents and serif typography.
```

### McKinsey (Consulting)
```
Create an executive strategy summary with McKinsey styling -
sharp corners, bold blue, professional serif headings.
```

### Deloitte (Consulting)
```
Style my audit report with Deloitte branding -
teal-blue accents, clean modern look.
```

### KPMG (Consulting)
```
Apply KPMG's bold corporate blue palette to my financial report.
```

### Stripe (Tech)
```
Style my API documentation with Stripe's tech-forward look -
dark blue with purple accents.
```

### Apple (Tech)
```
Create a minimalist product guide with Apple's clean aesthetic -
lots of whitespace, simple typography.
```

### IBM (Tech)
```
Style my technical documentation with IBM's enterprise look -
Carbon design system inspired.
```

### Notion (Productivity)
```
Create project documentation with Notion's clean, block-based style.
```

### Linear (Tech)
```
Style my product changelog with Linear's modern purple aesthetic.
```

### Figma (Design)
```
Create a design brief with Figma's vibrant multi-color palette.
```

---

## Advanced Prompts

### Extract Brand from Website
```
Use FireCrawl to extract the branding from https://[WEBSITE]
and add it as a new theme called "[BRAND_NAME]" to document-polisher.
```

### Compare Two Brands
```
Create the same document content with both McKinsey and Stripe styling
so I can compare them side by side.
```

### Batch Process
```
Apply the Notion style to all .docx files in my ./reports/ folder.
Save styled versions to ./reports/styled/
```

### Custom Brand Creation
```
Create a custom brand theme with:
- Name: "My Company"
- Primary: #2563EB
- Accent: #F59E0B
- Heading font: Georgia
- Body font: Calibri
- Style: Professional and modern

Add it to document-polisher and test it.
```

---

## Troubleshooting Prompts

### General Debug
```
The document-polisher skill isn't working. Help me debug:
1. Check if skills are installed correctly
2. Verify Python and python-docx are set up
3. Check permissions in settings
4. Run a test to find the issue
```

### Font Issues
```
My styled document shows Calibri but should show Georgia.
Help me fix the font rendering issue.
```

### Permission Errors
```
I'm getting permission denied errors when trying to use document-polisher.
Check my .claude/settings.local.json and fix the permissions.
```

### MCP Not Working
```
The FireCrawl MCP tools aren't showing up. Help me:
1. Check if the MCP server is configured
2. Verify the API key is set
3. Restart and test
```

---

## Quick Tests

### Test Skill Installation
```
List all installed Claude Code skills and verify document-polisher is available.
```

### Test Python Setup
```
Run: python -c "import docx; print('python-docx is working!')"
```

### Test Brand Application
```
Apply the "economist" brand to a test document and open it to verify styling.
```

### Test FireCrawl
```
Extract branding from https://stripe.com and show me the results.
```
