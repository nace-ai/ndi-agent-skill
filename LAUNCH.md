# Launch post draft

Your coding agent can now help you get started with NDI and Drex through one API.

We released a shared Console skill for Claude Code and OpenAI Codex. It guides your agent through API setup, document processing and Drex decisions using the same key.

Install it:

```sh
npx skills add nace-ai/ndi-agent-skill --skill ndi-console -a codex -a claude-code
```

Then ask:

> Connect my project to NDI Console. Extract invoice fields with citations, then use Drex to evaluate them against my routing policy.

NDI: Parse. Extract. Classify. Split. Ground.

Drex: Yes/no probabilities. Label selection. Ordered scoring.

The same skill works in both agents. Your API key stays local; the included examples are synthetic.

Try it: https://github.com/nace-ai/ndi-agent-skill
Get an API key: https://console.nace.ai/dashboard/api-keys

What document or decision workflow should we add next? Open an issue with a synthetic example or tell us what you want to build.
