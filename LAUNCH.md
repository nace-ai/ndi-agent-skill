# Launch post draft

Your coding agent can now help you get started with NDI.

We released a shared NDI Console skill for Claude Code and OpenAI Codex. It guides your agent through API setup, your first document, and adding document processing to your project.

Install it:

```sh
npx skills add nace-ai/ndi-agent-skill --skill ndi-console -a codex -a claude-code
```

Then ask:

> Connect my project to NDI Console and extract the invoice number, currency and total from a document, with citations.

Parse. Extract. Classify. Split. Ground.

The same skill works in both agents. Your API key stays local; the included example is synthetic.

Try it: https://github.com/nace-ai/ndi-agent-skill
Get an API key: https://console.nace.ai/dashboard/api-keys

What document workflow should we add next? Open an issue with a synthetic example or tell us what you want to build.
