# UNJSPF Reference — personal Q&A site

A single-page website that answers questions about the UNJSPF Regulations,
Administrative Rules, Rules of Procedure, and Pension Adjustment System,
grounded in the official documents you load into it.

## One-time setup

1. Create a repository on GitHub (e.g. `unjspf-qa`).
2. Upload everything in this folder to the repository, keeping the structure:
   - `index.html`
   - `data/manifest.json`
   - `data/unjspf-regulations-2026-rev30.json`
3. In the repository: **Settings → Pages → Source: Deploy from a branch →
   Branch: main / (root) → Save.**
4. After a minute the site is live at
   `https://YOUR-USERNAME.github.io/unjspf-qa/`
5. Open the site, click **Settings**, and paste your Anthropic API key
   (from console.anthropic.com). The key stays in your browser only.

## Adding a new document (the ongoing routine)

1. Upload the PDF to Claude in a chat and ask: "process this for my UNJSPF site."
2. Claude returns one `.json` file and the exact line to add.
3. In GitHub, upload the `.json` file into the `data` folder.
4. Edit `data/manifest.json` and add the new filename to the `files` list:

```json
{
  "files": [
    "unjspf-regulations-2026-rev30.json",
    "the-new-file.json"
  ]
}
```

That's it — reload the site and the new document is searchable.

## Notes

- The site works entirely in your browser: it searches the loaded documents
  for the most relevant provisions, sends only those excerpts to the Claude
  API, and shows the answer with the provisions it consulted.
- Costs are your Claude API usage only — typically well under a cent per question.
- The answers cite Articles/Sections and effective dates, but always verify
  against the official text before acting on anything.
