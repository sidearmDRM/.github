# Sidearm

**Protect your media from unauthorized AI training.**

Sidearm is an API platform for watermarking, AI content detection, content credentials, and similarity search. Run adversarial, proprietary, and open-source protection algorithms through a single API.

## Get Started

### MCP Server (for AI agents)

Add Sidearm tools to Cursor, Claude Desktop, Windsurf, or any MCP-compatible agent:

```json
{
  "mcpServers": {
    "sdrm": {
      "command": "npx",
      "args": ["-y", "@sidearmdrm/mcp"],
      "env": { "SDRM_API_KEY": "sk_live_..." }
    }
  }
}
```

### TypeScript SDK

```bash
npm install @sidearmdrm/sdk-node
```

```typescript
import { Sidearm } from "@sidearmdrm/sdk-node";

const client = new Sidearm({ apiKey: "sk_live_..." });
const job = await client.protect({
  media_url: "https://example.com/artwork.png",
  level: "maximum",
});
const result = await job.wait();
```

### REST API

```bash
curl -X POST https://api.sdrm.io/api/v1/protect \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"media_url": "https://example.com/artwork.png", "level": "maximum"}'
```

## Repositories

| Repo | Description |
|------|-------------|
| [mcp-server](https://github.com/sidearmDRM/mcp-server) | MCP server with 17 tools for AI agents |
| [sdk-node](https://github.com/sidearmDRM/sdk-node) | TypeScript/Node.js SDK with typed client and job polling |

## What It Does

- **Watermarking** -- Invisible marks that survive compression, cropping, and reformatting
- **AI Training Poison** -- Adversarial perturbations that confuse models trained on your content
- **Style Protection** -- Prevents AI from mimicking your artistic style or voice
- **Content Credentials** -- Cryptographic provenance signing with tamper-evident chain of custody
- **AI Detection** -- Detect whether content was AI-generated across image, video, audio, and text
- **Similarity Search** -- Find stolen or derivative content across your indexed library
- **Membership Inference** -- Prove whether an AI model trained on your protected content

## Links

- [Documentation](https://sdrm.io/docs)
- [API Reference](https://sdrm.io/docs)
- [Get an API Key](https://sdrm.io/api-keys)
- [Algorithm Catalog](https://api.sdrm.io/api/v1/algorithms)
