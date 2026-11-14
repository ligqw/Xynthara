# Xynthara

**Xynthara** is a local AI assistant built on top of `llama.cpp`. It runs entirely offline and provides a command-line interface, a web UI, and an OpenAI-compatible API. It features Retrieval-Augmented Generation (RAG), encrypted memory, automatic document indexing, plugins, and built-in tools.

> **Current version:** `v1.0.0` — see [Changelog](#changelog) for version history.

---

## Table of Contents

- [Features](#features)
- [Requirements](#requirements)
- [Installation](#installation)
- [Configuration](#configuration)
- [Usage](#usage)
- [Knowledge Base (RAG)](#knowledge-base-rag)
- [Memory](#memory)
- [Plugins](#plugins)
- [Tools](#tools)
- [Building a Standalone Executable](#building-a-standalone-executable)
- [Project Structure](#project-structure)
- [Changelog](#changelog)
- [Roadmap](#roadmap)
- [Troubleshooting](#troubleshooting)
- [License](#license)

---

## Features

- **Local & Private** – All processing and data storage happen on your machine.
- **Daemon Mode** – Automatically launches `llama-server` and keeps the model in memory.
- **Web Interface** – Chat via browser.
- **OpenAI-Compatible API** – Endpoint `/v1/chat/completions` for integration with other tools.
- **RAG (Retrieval-Augmented Generation)** – Indexes documents from `knowledge_base/` (TXT, MD, PDF) and injects relevant context.
- **Encrypted Memory** – Chat history and long-term facts are encrypted with Fernet.
- **Automatic Indexing** – Watches the knowledge base folder and rebuilds the index on changes.
- **Plugins** – Extend functionality by dropping Python files into `plugins/`.
- **Built-in Tools** – Calculator via `[CALC expression]` in model responses.
- **Profiles** – Switch between multiple system prompts.
- **Streaming Generation** – Real-time token streaming in CLI and API.
- **Resource Monitoring** – Optional RAM limit monitoring.

> Features may be added, changed, or removed between versions. See [Changelog](#changelog) for details.

---

## Requirements

- Python 3.9+
- Windows (primary target, but Linux/macOS should work with minor tweaks)
- `llama-server.exe` and a GGUF model file (e.g., `model.gguf`) placed in the `models/` directory.

Install Python dependencies:

```bash
pip install -r requirements.txt
