# Quick Start Guide

**Can't figure out the setup? Just copy and paste these prompts into Claude Code!**

This guide provides ready-to-use prompts that you can send directly to Claude Code to set everything up automatically.

---

## Step 1: Clone the Repository

Open Claude Code in any directory and paste this prompt:

```
Clone the claude-code-polished-documents-skills repository from GitHub and set it up for me:
https://github.com/promptadvisers/claude-code-polished-documents-skills

After cloning:
1. Create a Python virtual environment
2. Install python-docx
3. Copy the skills to my global Claude skills folder at ~/.claude/skills/
4. Verify everything is set up correctly
```

---

## Step 2: Set Up FireCrawl MCP (Optional but Recommended)

If you want to extract branding from websites, paste this prompt:

```
Help me set up the FireCrawl MCP server for Claude Code. I need to:
1. Get an API key from firecrawl.dev (walk me through this)
2. Add the MCP server to my Claude Code configuration
3. Test that it's working by extracting branding from a sample website
```

---

## Step 3: Test the Document Polisher Skill

Once set up, test it with this prompt:

```
Use the document-polisher skill to:
1. Create a sample business report document with headings, bullet points, and a table
2. Apply the McKinsey brand styling to it
3. Save it as "test_mckinsey_report.docx"
```

---

## Common Prompts for Using Document Polisher

### Polish an Existing Document

```
Polish my document [FILENAME.docx] with the [BRAND] style.
Save it as [OUTPUT_FILENAME.docx]
```

**Available brands:** `economist`, `mckinsey`, `deloitte`, `kpmg`, `stripe`, `apple`, `ibm`, `notion`, `linear`, `figma`

### Create a New Styled Document

```
Create a professional report about [TOPIC] and style it with the Deloitte brand theme.
Include:
- Executive summary
- 3-4 main sections with findings
- A data table
- Recommendations
- Next steps
```

### Compare Multiple Brand Styles

```
Create the same document content styled with McKinsey, Stripe, and Notion themes
so I can compare how they look. Save them as separate files.
```

### Extract and Add a New Brand

```
Use FireCrawl to extract the branding from [WEBSITE_URL] and add it as a new
brand theme called "[BRAND_NAME]" to the document-polisher skill.
```

---

## Troubleshooting Prompts

### If Skills Aren't Found

```
Help me troubleshoot why Claude Code can't find my skills. Check:
1. Where my skills are installed (project vs global)
2. If the SKILL.md files exist
3. If permissions are configured correctly in settings.local.json
```

### If Fonts Look Wrong

```
The fonts in my polished document don't look right. Help me:
1. Check what fonts are specified in the brand-mapping.json
2. Verify these fonts are installed on my system
3. Suggest alternatives if needed
```

### If python-docx Isn't Working

```
I'm getting "ModuleNotFoundError: No module named 'docx'" errors. Help me:
1. Check if I have a virtual environment set up
2. Install python-docx in the correct environment
3. Configure Claude Code to use the right Python
```

---

## Power User Prompts

### Batch Process Multiple Documents

```
Apply the Stripe brand styling to all .docx files in my /documents folder.
Save the styled versions to /documents/styled/ with "_styled" added to the filename.
```

### Create a Custom Brand Theme

```
Create a custom brand theme for my company with these specifications:
- Primary color: #[HEX]
- Accent color: #[HEX]
- Heading font: [FONT_NAME]
- Body font: [FONT_NAME]
- Company name: [NAME]

Add it to the document-polisher skill and test it on a sample document.
```

### Generate Demo Documents for All Brands

```
Generate a demo document for each available brand in the document-polisher skill.
Use the same sample content for each so I can compare the styles side by side.
Save them all in a "brand_demos" folder.
```

---

## Quick Reference: Available Skills

| Skill | What It Does | Example Prompt |
|-------|--------------|----------------|
| `document-polisher` | Apply brand styling to documents | "Polish report.docx with McKinsey style" |
| `docx` | Create/edit Word documents | "Create a Word doc with headers and tables" |
| `pdf` | Work with PDFs | "Fill out this PDF form" |
| `xlsx` | Create/edit spreadsheets | "Create an Excel budget template" |
| `pptx` | Create/edit presentations | "Make a 10-slide pitch deck" |

---

## Need More Help?

Just ask Claude Code:

```
I'm having trouble with the document-polisher skill. Can you help me debug it?
Here's what's happening: [DESCRIBE YOUR ISSUE]
```

Claude Code has access to all the documentation and can help troubleshoot!
