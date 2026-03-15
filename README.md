# pollinations.ai × OpenClaw

Use **25+ AI models** as your OpenClaw brain through a single API.

**Kimi K2.5** as default (256K context, vision, tools, reasoning), with DeepSeek, GLM-5, GPT-5 Mini, Gemini Flash Lite, Claude Haiku, Mistral, Qwen Coder, MiniMax, Nova, and more as free alternatives. Premium models (GPT-5.2, Claude Sonnet/Opus, Gemini 3 Flash/Pro, Grok 4) available on paid tier.

## 30-Second Setup

```bash
curl -fsSL https://raw.githubusercontent.com/pollinations/pollinations/main/apps/openclaw/setup-pollinations.sh \
  | bash -s -- YOUR_API_KEY
```

Get your API key at [enter.pollinations.ai](https://enter.pollinations.ai) (free tier available).

After setup, install OpenClaw if you haven't already:

```bash
curl -fsSL https://openclaw.ai/install.sh | bash
openclaw onboard --install-daemon
```

## Switch Models

Switch models anytime in chat with `/model pollinations/<n>`:

**Free models:**

| Model | ID | Best for |
|---|---|---|
| **Kimi K2.5** ⭐ | `pollinations/kimi` | Agentic tasks, vision, reasoning (256K context) |
| **DeepSeek V3.2** | `pollinations/deepseek` | Efficient reasoning & agentic AI |
| **GLM-5** | `pollinations/glm` | 744B MoE, long context reasoning (198K) |
| **GPT-5 Mini** | `pollinations/openai` | Fast & balanced, vision |
| **GPT-5 Nano** | `pollinations/openai-fast` | Ultra fast & affordable |
| **GPT-4o Audio** | `pollinations/openai-audio` | Voice input & output |
| **Gemini Flash Lite** | `pollinations/gemini-fast` | Ultra fast, vision, search |
| **Gemini + Search** | `pollinations/gemini-search` | Web search grounded answers |
| **Claude Haiku 4.5** | `pollinations/claude-fast` | Fast & intelligent |
| **Mistral Small 3.2** | `pollinations/mistral` | Efficient & cost-effective |
| **Qwen3 Coder** | `pollinations/qwen-coder` | Specialized for code generation |
| **MiniMax M2.1** | `pollinations/minimax` | Multi-language & agent workflows (200K) |
| **Nova Micro** | `pollinations/nova-fast` | Ultra fast & ultra cheap |
| **Perplexity Sonar** | `pollinations/perplexity-fast` | Fast web search |
| **Perplexity Reasoning** | `pollinations/perplexity-reasoning` | Advanced reasoning + web search |
| **NomNom** | `pollinations/nomnom` | Web research with search, scrape & crawl |
| **Polly** | `pollinations/polly` | Pollinations AI assistant with code search & web |

**Paid models:**

| Model | ID | Best for |
|---|---|---|
| **GPT-5.2** 💰 | `pollinations/openai-large` | Most powerful & intelligent (reasoning) |
| **Claude Sonnet 4.6** 💰 | `pollinations/claude` | Most capable & balanced |
| **Claude Opus 4.6** 💰 | `pollinations/claude-large` | Most intelligent model |
| **Gemini 3 Flash** 💰 | `pollinations/gemini` | Pro-grade reasoning at flash speed |
| **Gemini 3 Pro** 💰 | `pollinations/gemini-large` | 1M context, vision, audio & video |
| **Grok 4 Fast** 💰 | `pollinations/grok` | High speed & real-time |

## Manual Configuration

If you prefer to edit `~/.openclaw/openclaw.json` directly:

```json
{
  "env": { "POLLINATIONS_API_KEY": "YOUR_KEY" },
  "models": {
    "mode": "merge",
    "providers": {
      "pollinations": {
        "baseUrl": "https://gen.pollinations.ai/v1",
        "apiKey": "${POLLINATIONS_API_KEY}",
        "api": "openai-completions",
        "models": [
          { "id": "kimi", "name": "Kimi K2.5", "reasoning": true,
            "input": ["text", "image"], "contextWindow": 256000 },
          { "id": "deepseek", "name": "DeepSeek V3.2", "reasoning": true,
            "input": ["text"], "contextWindow": 128000 },
          { "id": "glm", "name": "GLM-5", "reasoning": true,
            "input": ["text"], "contextWindow": 198000 }
        ]
      }
    }
  }
}
```

This is a minimal example with 3 models. The setup script configures all 23 models automatically. See all available models at [gen.pollinations.ai/v1/models](https://gen.pollinations.ai/v1/models).

## Why Pollinations?

- **Free tier** — generous credits for development and personal use
- **23 models** — best open and frontier models in one API
- **OpenAI-compatible** — drop-in replacement, no code changes
- **Web search built-in** — Perplexity integration for real-time data
- **Vision & audio** — multimodal models included
- **Open source** — [github.com/pollinations/pollinations](https://github.com/pollinations/pollinations)
