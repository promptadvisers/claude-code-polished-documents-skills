# FireCrawl Setup Guide

**Want to extract branding from ANY website and turn it into a document theme?**

FireCrawl lets you scrape a company's website and automatically extract their colors, fonts, and styling. Then you can apply that branding to your documents!

---

## Do I Need This?

**You DON'T need FireCrawl if:**
- You're happy with the 10 built-in brand themes (McKinsey, Stripe, Apple, etc.)
- You just want to polish documents with existing styles

**You DO need FireCrawl if:**
- You want to extract branding from a client's website
- You want to create custom themes from any company
- You want to match a specific brand not in the default list

---

## Step 1: Get Your Free API Key

### Option A: Let Claude Help You (Recommended)

Just paste this into Claude Code:

```
I want to set up FireCrawl to extract website branding.
Walk me through getting an API key from firecrawl.dev step by step.
Open the signup page for me and tell me exactly what to click.
```

### Option B: Do It Yourself

1. **Go to FireCrawl**: https://firecrawl.dev

2. **Click "Get Started" or "Sign Up"**

3. **Create an account** (you can use Google, GitHub, or email)

4. **Go to Dashboard** after signing in

5. **Find "API Keys"** in the sidebar or settings

6. **Click "Create API Key"** or "Generate New Key"

7. **Copy your key** - it looks like: `fc-xxxxxxxxxxxxxxxxxxxxxxxx`

8. **Save it somewhere safe** - you'll need it in the next step!

---

## Step 2: Add FireCrawl to Claude Code

### Option A: One-Line Setup (Easiest)

Paste this into Claude Code, replacing `YOUR_API_KEY` with your actual key:

```
Add the FireCrawl MCP server to Claude Code with API key: fc-YOUR_API_KEY_HERE

Run this command:
claude mcp add firecrawl --command "npx" --args "-y" "@anthropic/firecrawl-mcp" --env "FIRECRAWL_API_KEY=fc-YOUR_API_KEY_HERE"
```

### Option B: Have Claude Do Everything

Paste this and Claude will guide you:

```
I have my FireCrawl API key: fc-YOUR_API_KEY_HERE

Please:
1. Add the FireCrawl MCP server to my Claude Code
2. Verify it's working
3. Test it by extracting branding from stripe.com
```

### Option C: Manual Setup

If you prefer to do it yourself:

```bash
claude mcp add firecrawl \
  --command "npx" \
  --args "-y" "@anthropic/firecrawl-mcp" \
  --env "FIRECRAWL_API_KEY=fc-YOUR_API_KEY_HERE"
```

---

## Step 3: Verify It's Working

Paste this into Claude Code:

```
Test my FireCrawl setup by extracting the branding from https://linear.app
Show me the colors, fonts, and style they detected.
```

If it works, you'll see output like:
- Primary color: #5E6AD2
- Fonts: Inter, system fonts
- Style: Modern, minimal

---

## Step 4: Extract Your First Custom Brand

Now the fun part! Try this:

```
Extract the branding from https://[ANY-WEBSITE-YOU-WANT]
and add it as a new brand theme called "[BRAND_NAME]" to document-polisher.
Then create a test document using that new theme.
```

**Example:**
```
Extract the branding from https://notion.com
and add it as a new brand theme called "notion-custom" to document-polisher.
Then create a test document using that new theme.
```

---

## Troubleshooting

### "FireCrawl tools not found"

Paste this:
```
The FireCrawl MCP tools aren't showing up. Help me debug:
1. Check if the MCP server is in my config
2. Verify the API key is set correctly
3. Restart Claude Code if needed
4. Test the connection
```

### "API key invalid"

Paste this:
```
I'm getting API key errors with FireCrawl. Help me:
1. Verify my key format (should start with fc-)
2. Check if I need to regenerate it on firecrawl.dev
3. Update the MCP configuration with the correct key
```

### "Rate limit exceeded"

The free tier has limits. Options:
- Wait a few minutes and try again
- Upgrade your FireCrawl plan at firecrawl.dev
- Cache/save results so you don't re-extract the same sites

### "Timeout on large sites"

Paste this:
```
FireCrawl is timing out on [WEBSITE].
Try extracting from a specific page instead of the homepage,
like their About or Product page.
```

---

## Quick Reference: FireCrawl Prompts

### Extract Branding
```
Extract branding from https://[WEBSITE] and show me the results
```

### Add as New Theme
```
Extract branding from https://[WEBSITE] and add it as a "[NAME]" theme to document-polisher
```

### Compare Two Brands
```
Use FireCrawl to compare the branding of https://[SITE1] and https://[SITE2]
```

### Full Workflow
```
1. Extract branding from https://[CLIENT-WEBSITE]
2. Add it as a theme called "[CLIENT-NAME]"
3. Create a proposal document using their brand style
4. Save it as "[CLIENT-NAME]_proposal.docx"
```

---

## Free Tier Limits

FireCrawl's free tier includes:
- ~500 pages/month
- Basic rate limiting
- All extraction features

This is plenty for:
- Extracting 10-20 brand themes
- Occasional client website scraping
- Personal/small team use

If you need more, check https://firecrawl.dev/pricing

---

## Security Note

Your API key is stored locally in your Claude Code MCP configuration. It's NOT:
- Uploaded to GitHub (if you use our .gitignore)
- Shared with anyone
- Stored in the cloud

Keep your key private and don't share it in public repos or chats!
