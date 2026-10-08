# NDI Console + Drex skill

Give **Claude Code and OpenAI Codex** the instructions to connect your project to [NDI Console](https://console.nace.ai) for document processing and **Drex** decisions through one API and one key.

Parse documents into Markdown, extract fields with citations, classify files, split packets, and locate quotes. Use Drex to answer yes/no questions with probabilities, choose labels or score text and JSON. Combine the two to make decisions from extracted document data. Synthetic document and Drex examples are included.

## Install

From your project directory:

```sh
npx skills add nace-ai/ndi-agent-skill --skill ndi-console -a codex -a claude-code
```

The [Skills CLI](https://github.com/vercel-labs/skills) supports both clients. Review its installation prompt and select project or personal scope as appropriate. Installation itself does not call the NDI API or require an API key.

Then start a new session and ask:

**Codex**

```text
$ndi-console Connect this project to NDI Console. Check my API connection, then parse the bundled synthetic invoice and show me the result.
```

**Claude Code**

```text
/ndi-console Connect this project to NDI Console. Check my API connection, then parse the bundled synthetic invoice and show me the result.
```

Both clients use the same [SKILL.md](skills/ndi-console/SKILL.md), [document API guide](skills/ndi-console/references/api.md) and [Drex guide](skills/ndi-console/references/drex.md). The skill name remains `ndi-console` for both capabilities.

For a first Drex evaluation, ask either client:

> Use the ndi-console skill to check my API connection, then run the bundled synthetic Drex request. Explain the yes/no probability, chosen support queue and urgency score.

## Connect your account

1. Sign in to [NDI Console](https://console.nace.ai).
2. Create an API key in [API Keys](https://console.nace.ai/dashboard/api-keys).
3. Store it locally as `DREX_API_KEY`, the public Console API's documented environment variable. Do not paste it into an agent conversation or commit it.
4. Ask the agent to verify the connection and process your chosen document or evaluate your text/JSON with Drex.

Signing in to the Console authenticates your browser; the agent still needs the API key. Set the variable in the environment used to launch the agent or configure your project's local environment loader. A `.env` file is not automatically loaded by every runtime.

Authentication and model discovery use `GET /v1/models`. Document processing and Drex evaluations use the same account credit. Document jobs return job IDs for polling; `/v1/systemone` returns Drex answers directly with a request ID.

## Try next

- “Extract invoice number, currency and total from this invoice, with citations.”
- “Add a server-side PDF-to-Markdown endpoint to this app.”
- “Classify these documents as invoices or receipts. Show me the proposed batch before running it.”
- “Split this packet into documents and keep unknown pages visible.”
- “Find this exact quote and show the source location.”
- “Use Drex to route this support message and report the probabilities for each queue.”
- “Score these product descriptions against my ordered criteria.”
- “Extract this invoice, then use Drex to evaluate the fields against my routing policy.”

## Manual installation

Clone or download this public repository. Copy the complete `skills/ndi-console` folder into one of these locations:

| Client | This project | All local projects |
| --- | --- | --- |
| Codex | `.agents/skills/ndi-console/` | `~/.agents/skills/ndi-console/` |
| Claude Code | `.claude/skills/ndi-console/` | `~/.claude/skills/ndi-console/` |

Start a new client session if the skill is not discovered. The folder contains one shared workflow; `agents/openai.yaml` supplies optional Codex display metadata. Manual installation needs no Node.js or package manager.

See the official [Codex skill documentation](https://developers.openai.com/codex/skills/) and [Claude Code skill documentation](https://code.claude.com/docs/en/skills).

## Privacy and scope

The package contains instructions, public documentation links and synthetic examples. It includes no credentials, customer files, account IDs, session data or internal configuration. API keys stay in your environment and on your server; document outputs and decision inputs belong in your own project storage. When opening an issue, share a minimal synthetic reproduction and remove keys, private content and signed URLs.

This skill connects to the hosted Console API. Public documentation: [documents](https://console.nace.ai/docs/perception/documents), [Drex](https://console.nace.ai/docs/drex/quickstart), [OpenAPI](https://console.nace.ai/openapi.json). Compatible skill format and installation conventions are documented for both clients; live results depend on your account, input and API availability.

MIT licensed. Contributions and reproducible feedback are welcome.
