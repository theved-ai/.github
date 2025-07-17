# 💡 theved‑ai Open‑Source

Welcome to **theved‑ai** – a suite of building blocks for personal AI agents, retrieval‑augmented generation, and cross‑tool automation. Every repository here powers part of the end‑to‑end stack behind Ved’s native IPaaS vision.

## ✨ Core Philosophy

* **Open by default** – share everything that can help the community build reliable AI agents.
* **Modular** – each repo is an independent service or client that can be swapped or reused.
* **Edge‑friendly** – prefer local/streaming architectures, minimal infra, and privacy‑respecting design.

## 🗂 Repository Index

| Repo                            | What it does                                                                                                                                                | Main tech                            |
| ------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------ |
| **ved‑mcp‑service**             | Reference *Model‑Context‑Protocol* (MCP) server that exposes tools such as Gmail, Slack, Calendar, and Pensieve search over streamable HTTP for LLM agents. | Python · FastAPI · Postgres · Qdrant |
| **ved‑data‑retrieval‑service**  | Fully asynchronous micro‑service that orchestrates OpenAI Agents SDK + MCP to answer natural‑language queries and stream results back in real time.         | Python · Uvicorn · AsyncIO           |
| **ved‑data‑ingestion‑service**  | High‑throughput ingestion pipeline that chunks, embeds, and stores documents/audio into Qdrant for RAG. Includes worker scripts and Docker compose.         | Python · Kafka · Qdrant              |
| **ved‑data‑ingestion‑clients**  | Desktop (Electron) and web clients that let end users push notes, files, and transcripts into the ingestion API.                                            | JavaScript · Electron · React        |
| **ved‑audio‑ingestion‑poc‑app** | macOS proof‑of‑concept that records Chrome tab + mic via ScreenCaptureKit, streams raw PCM for Whisper transcription.                                       | Swift · Electron · FFmpeg            |

## 🛠 High‑level Architecture

```text
           [Clients]
               |
               | ingest
               v
(1) Ingestion‑Service  ────▶  Qdrant (Vector DB)
                            ▲
                            | semantic search
(4) Agent / LLM  ◀── (3) Retrieval‑Service  ◀── (2) MCP‑Service
```

*For a more detailed diagram see individual READMEs.*

## 🚀 Quick Start

1. Clone the repo you’re interested in, e.g.:

   ```bash
   git clone https://github.com/theved-ai/ved-mcp-service.git
   cd ved-mcp-service
   ```

2. Follow the project‑level README for prerequisites and `docker-compose` instructions.

3. Mix‑and‑match services – they share a common `.env` contract and communicate over HTTP/WebSocket.

## 💬 Join the Community

We’re building a welcoming space for AI builders, hackers, and enthusiasts.

👉 Join the Slack: [theved.ai Slack Workspace](https://join.slack.com/t/thevedai/shared_invite/zt-38q9owy11-Ysll9m72xd8Gs4zBhjuzkw) (Share projects, discuss PRs, swap memes, and explore new LLM tooling.)

## 🤝 Contributing

We love issues, discussions, and PRs! Start with the [`good‑first‑issue`](https://github.com/theved-ai/ved-mcp-service/labels/good-first-issue) label or open a design doc if you want to propose a bigger change.

## 📜 License

All projects are released under the MIT License unless noted otherwise in the repo.

---

Built with ❤️ by **Ved** — putting real AI workflows at your fingertips.
