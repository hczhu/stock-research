file-created-at:: 2026-03-28

# OpenClaw: Open Source Projects & API Dependencies

Inventory of all open source projects and external APIs used by [OpenClaw](https://github.com/openclaw/openclaw), compiled from source code and documentation.

Source: OpenClaw repo as of 2026-03-13

## AI/LLM Model Provider APIs

| Provider | Endpoint / Notes |
|---|---|
| **OpenAI** | GPT-5.x, GPT-4.x, Codex; also TTS, Whisper STT, embeddings |
| **Anthropic** | Claude models (API key + OAuth token) |
| **Google Gemini** | Gemini models via API key, Gemini CLI OAuth, Vision, embeddings |
| **Google Vertex AI** | Claude on Vertex (Bedrock Converse API) |
| **Google Antigravity** | Internal/unofficial Google API |
| **Amazon Bedrock** | AWS SDK Converse API for Claude/other models |
| **xAI (Grok)** | Grok models + built-in web search |
| **Groq** | Whisper-large-v3 STT; fast inference |
| **Mistral** | LLM + Voxtral STT + embeddings |
| **Together AI** | `api.together.xyz/v1` |
| **NVIDIA API** | `integrate.api.nvidia.com/v1` |
| **OpenRouter** | `openrouter.ai/api/v1` aggregator |
| **Vercel AI Gateway** | Anthropic-compatible router |
| **Cloudflare AI Gateway** | OpenAI-compatible proxy |
| **LiteLLM** | LLM proxy/aggregator |
| **GitHub Copilot** | OAuth device flow |
| **Claude Max API Proxy** | Community proxy for Claude Max subscribers |
| **Venice AI** | Privacy-focused model proxy |
| **HuggingFace Inference** | Model discovery + inference |
| **Synthetic (HuggingFace)** | `api.synthetic.new/anthropic` |
| **Kilocode** | `api.kilocode.ai/api/v1` |
| **OpenCode (Zen/Go)** | Custom LLM implementations |
| **MiniMax** | `api.minimax.io/anthropic` + portal OAuth |
| **Moonshot AI (Kimi)** | `api.moonshot.ai/v1` + Kimi Coding endpoint |
| **Alibaba Qwen** | `portal.qwen.ai/v1` + portal OAuth |
| **Baidu Qianfan** | `qianfan.baidubce.com/v2` |
| **BytePlus DoubAo** | `ark.volcengineapis.com/api/v3` + coding endpoint |
| **Xiaomi MimoMI** | `api.xiaomimimo.com/anthropic` |
| **Zhipu GLM** | GLM models |
| **Cerebras (via Z.AI)** | Fast inference |

### Local/Self-Hosted LLM Runtimes

| Project | Notes |
|---|---|
| **Ollama** | Local model server (auto-discovery) |
| **vLLM** | OpenAI-compatible local inference |
| **LM Studio** | OpenAI-compatible format |
| **node-llama-cpp** | Optional peer dep for local GGUF models |

## Voice & Speech APIs

### Text-to-Speech (TTS)

| Service | Notes |
|---|---|
| **ElevenLabs** | Custom voices, streaming TTS |
| **OpenAI TTS** | `gpt-4o-mini-tts` (alloy, echo, fable, onyx, nova, shimmer, coral) |
| **Amazon Polly** | AWS TTS for voice call fallback |
| **Google Text-to-Speech** | Via Google.* voice prefix |
| **Microsoft Edge TTS** | Via `node-edge-tts` library |

### Speech-to-Text (STT)

| Service | Notes |
|---|---|
| **OpenAI Whisper** | `whisper-1` (batch + realtime WebSocket) |
| **Groq Whisper** | `whisper-large-v3` at Groq speed |
| **Deepgram** | Real-time transcription |
| **Mistral Voxtral** | Speech-to-text |
| **Google Gemini** | Audio understanding |
| **whisper-cpp** | Local CLI whisper |

### Telephony

| Service | Notes |
|---|---|
| **Twilio** | Voice calls |
| **Telnyx** | Voice calls |
| **Plivo** | Voice calls |

## Embeddings & Vector Search APIs

| Service | Notes |
|---|---|
| **OpenAI Embeddings** | `text-embedding-3-small/large`, `ada-002` |
| **Google Gemini Embeddings** | Via GEMINI_API_KEY |
| **Voyage AI** | Remote embeddings |
| **Mistral Embeddings** | Remote embeddings |
| **MiniMax Embeddings** | Remote embeddings |
| **Ollama Embeddings** | Local embeddings |

## Web Search APIs

| Service | Notes |
|---|---|
| **Brave Search** | `BRAVE_API_KEY` |
| **Perplexity** | `PERPLEXITY_API_KEY` |
| **Google Search** | Via Gemini grounding |
| **Grok Web Search** | Built-in xAI search |
| **Kimi Web Search** | Built-in Moonshot search |

## Communication Channel Platforms (APIs)

| Channel | Protocol / Library |
|---|---|
| **WhatsApp** | Baileys (web protocol) |
| **Telegram** | Bot API via grammY |
| **Discord** | discord.js + @discordjs/voice |
| **Slack** | Bolt SDK + Web API |
| **Signal** | signal-cli (CLI tool) |
| **iMessage / BlueBubbles** | BlueBubbles server API |
| **Google Chat** | Google Chat API + google-auth-library |
| **Microsoft Teams** | @microsoft/agents-hosting + Azure Bot |
| **Matrix** | @vector-im/matrix-bot-sdk + E2E crypto |
| **LINE** | @line/bot-sdk |
| **Feishu (Lark)** | @larksuiteoapi/node-sdk |
| **Mattermost** | REST API |
| **IRC** | IRC protocol |
| **Twitch** | @twurple/api + chat + auth |
| **Nostr** | nostr-tools |
| **Nextcloud Talk** | REST API |
| **Synology Chat** | Webhook API |
| **Tlon (Urbit)** | @tloncorp/api |
| **Zalo** | Zalo API |
| **Zalo Personal** | zca-js |

## Cloud & Infrastructure Services (APIs)

| Service | Use |
|---|---|
| **AWS (Bedrock, Polly, EC2)** | @aws-sdk/client-bedrock |
| **Google Cloud (Pub/Sub, Vertex)** | Gmail automation, model hosting |
| **Azure / Entra ID** | MS Teams bot auth, Microsoft Graph API |
| **Tailscale** | VPN tunneling (Serve/Funnel) |
| **Cloudflare Tunnel** | Remote gateway exposure |
| **ngrok** | Dev tunneling |
| **Fly.io** | VPS hosting |
| **Render** | PaaS hosting |
| **Railway** | PaaS hosting |
| **Northflank** | PaaS hosting |
| **Hetzner** | VPS hosting |
| **DigitalOcean** | VPS hosting |
| **Oracle Cloud** | VPS hosting |

## Email & Automation APIs

| Service | Notes |
|---|---|
| **Gmail (OAuth + Pub/Sub)** | Email watch with Google Pub/Sub |

## Auth Protocols / Proxies

| Service | Notes |
|---|---|
| **OAuth 2.0** | Generic OAuth for multiple providers |
| **SAML / OIDC** | Trusted proxy auth |
| **Pomerium** | Identity-aware proxy |
| **oauth2-proxy** | Reverse proxy with OAuth |

## Open Source Libraries (Node.js / TypeScript)

### Core Framework

| Library | Purpose |
|---|---|
| **TypeScript** | Language |
| **Express** 5 | HTTP server |
| **Hono** | Lightweight web framework (pinned override) |
| **Commander** | CLI argument parsing |
| **@clack/prompts** | Interactive CLI prompts |
| **Zod** | Schema validation |
| **@sinclair/typebox** | JSON/SQL schema definitions |
| **ajv** | JSON Schema validation |

### Agent / AI Runtime

| Library | Purpose |
|---|---|
| **@mariozechner/pi-ai** | AI model provider abstraction |
| **@mariozechner/pi-agent-core** | Agent framework core |
| **@mariozechner/pi-coding-agent** | Coding agent runtime |
| **@mariozechner/pi-tui** | Terminal UI agent interface |
| **@agentclientprotocol/sdk** | Agent Client Protocol |

### Media & Document Processing

| Library | Purpose |
|---|---|
| **sharp** | Image processing (resize, rotate, optimize) |
| **pdfjs-dist** | PDF text extraction |
| **@mozilla/readability** | Web article extraction |
| **ffmpeg** | Audio/video transcoding (system dep) |
| **opusscript** | Opus audio codec |
| **node-edge-tts** | Microsoft Edge TTS |
| **file-type** | File type detection |
| **music-metadata** | Audio metadata parsing |

### Web UI

| Library | Purpose |
|---|---|
| **Lit** | Web components framework |
| **@lit-labs/signals** | Signal-based reactivity |
| **Vite** | Build tool / dev server |
| **Marked** | Markdown to HTML |
| **DOMPurify** | XSS sanitization |
| **@noble/ed25519** | Cryptographic signatures |

### Browser Automation

| Library | Purpose |
|---|---|
| **Playwright** / **playwright-core** | Browser control (Chrome/Chromium/Brave/Edge) |

### Database & Storage

| Library | Purpose |
|---|---|
| **node:sqlite** (built-in) | Local SQLite database |
| **sqlite-vec** | SQLite vector search extension |
| **@lancedb/lancedb** | LanceDB vector database |

### Networking & Protocols

| Library | Purpose |
|---|---|
| **ws** | WebSocket client/server |
| **undici** | HTTP client |
| **https-proxy-agent** | HTTP proxy support |
| **protobufjs** | Protocol Buffers |
| **@grpc/grpc-js** | gRPC client |
| **@homebridge/ciao** | mDNS/Bonjour discovery |
| **ipaddr.js** | IP address parsing |

### Observability

| Library | Purpose |
|---|---|
| **OpenTelemetry** (full SDK) | Tracing, metrics, logs via OTLP |
| **tslog** | Structured JSON logging |

### Utilities

| Library | Purpose |
|---|---|
| **chalk** | Terminal colors |
| **chokidar** | File watching |
| **croner** | Cron scheduling |
| **jszip** | ZIP archives |
| **tar** | Tar archives |
| **yaml** | YAML parsing |
| **json5** | JSON5 parsing |
| **markdown-it** | Markdown parsing |
| **linkedom** | DOM implementation |
| **long** | 64-bit integers |
| **qrcode-terminal** | QR codes in terminal |
| **cli-highlight** | Syntax highlighting |
| **osc-progress** | Progress bars |
| **dotenv** | Environment variable loading |
| **jiti** | Dynamic TypeScript imports |

### Dev / Build Tools

| Library | Purpose |
|---|---|
| **tsdown** | TypeScript bundler |
| **tsx** | TypeScript executor |
| **Oxlint** | Rust-based linter |
| **Oxfmt** | Rust-based formatter |
| **Vitest** | Test framework |
| **jscpd** | Code duplication detection |
| **Knip** | Dead code analysis |

## Open Source Libraries (Android / Kotlin)

| Library | Purpose |
|---|---|
| **Jetpack Compose** (Material 3) | Declarative UI framework |
| **AndroidX** (Core, Lifecycle, Navigation, Camera, WebKit, Security) | Android platform libraries |
| **OkHttp** 5 | HTTP client |
| **Kotlin Coroutines** | Async programming |
| **Kotlin Serialization** | JSON serialization |
| **BouncyCastle** | Cryptography |
| **CommonMark** | Markdown rendering |
| **ZXing** | QR code scanning |
| **dnsjava** | DNS/mDNS |
| **Robolectric** | Android unit testing |
| **Kotest** | Kotlin test framework |

## Open Source Libraries (iOS / macOS Swift)

| Library | Purpose |
|---|---|
| **ElevenLabsKit** | TTS integration |
| **Textual** | Text formatting |
| **SwiftUI** + **Observation** framework | UI (system framework) |
| **AppIntents** | Siri / Shortcuts integration (system framework) |

## Docker / Container

| Image / Tool | Purpose |
|---|---|
| **node:22-bookworm** | Base runtime image |
| **debian:bookworm-slim** | Minimal sandbox |
| **Chromium** (APT) | Browser control in Docker |
| **noVNC / websockify** | VNC over WebSocket (sandbox) |
| **xvfb** | Virtual display (sandbox) |
| **Docker** / **Podman** | Containerization |

## Summary

OpenClaw integrates with `30+` AI/LLM provider APIs, `20+` messaging channel APIs, `6+` TTS/STT services, `3` telephony APIs, `5+` embedding services, `5` web search APIs, and uses `100+` open source libraries across TypeScript, Kotlin, and Swift.
