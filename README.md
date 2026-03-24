# Aether 👋

![GitHub stars](https://img.shields.io/github/stars/afiren/open-aether?style=social)
![GitHub forks](https://img.shields.io/github/forks/afiren/open-aether?style=social)
![GitHub watchers](https://img.shields.io/github/watchers/afiren/open-aether?style=social)
![GitHub repo size](https://img.shields.io/github/repo-size/afiren/open-aether)
![GitHub last commit](https://img.shields.io/github/last-commit/afiren/open-aether?color=red)

![Aether Banner](./banner.png)

**Aether is an extensible, feature-rich, and user-friendly self-hosted AI platform designed to operate entirely offline.** It supports various LLM runners like **Ollama** and **OpenAI-compatible APIs**, with a **built-in inference engine** for RAG, making it a **powerful AI deployment solution**.

---

## Key Features ⭐

- 🚀 **Effortless Setup**: Install seamlessly using Docker or Kubernetes (kubectl, kustomize or helm) for a hassle-free experience with support for both `:ollama` and `:cuda` tagged images.

- 🤝 **Ollama/OpenAI API Integration**: Effortlessly integrate OpenAI-compatible APIs for versatile conversations alongside Ollama models. Customize the OpenAI API URL to link with **LMStudio, GroqCloud, Mistral, OpenRouter, and more**.

- 🛡️ **Granular Permissions and User Groups**: Administrators can create detailed user roles and permissions, ensuring a secure and customized user environment.

- 📱 **Responsive Design**: Enjoy a seamless experience across Desktop PC, Laptop, and Mobile devices.

- 📱 **Progressive Web App (PWA) for Mobile**: Enjoy a native app-like experience on your mobile device with offline access on localhost and a seamless user interface.

- ✒️🔢 **Full Markdown and LaTeX Support**: Comprehensive Markdown and LaTeX capabilities for enriched interaction.

- 🎤📹 **Hands-Free Voice/Video Call**: Seamless communication with integrated hands-free voice and video call features using multiple Speech-to-Text providers (Local Whisper, OpenAI, Deepgram, Azure) and Text-to-Speech engines (Azure, ElevenLabs, OpenAI, Transformers, WebAPI).

- 🛠️ **Model Builder**: Easily create and customize models via the Web UI. Add custom characters/agents, customize chat elements, and import models effortlessly.

- 🐍 **Native Python Function Calling Tool**: Enhance your LLMs with built-in code editor support. Add your own pure Python functions for seamless LLM integration.

- 📚 **Local RAG Integration**: Groundbreaking Retrieval Augmented Generation (RAG) support using your choice of 9 vector databases and multiple content extraction engines (Tika, Docling, Document Intelligence, Mistral OCR). Load documents directly into chat using the `#` command before a query.

- 🔍 **Web Search for RAG**: Perform web searches using 15+ providers including `SearXNG`, `Google PSE`, `Brave Search`, `Tavily`, `Perplexity`, `DuckDuckGo`, `Bing`, and more, injecting results directly into your chat experience.

- 🌐 **Web Browsing Capability**: Integrate websites into your chat using the `#` command followed by a URL.

- 🎨 **Image Generation Integration**: Generate images using multiple engines including OpenAI's DALL-E, Gemini, ComfyUI (local), and AUTOMATIC1111 (local).

- ⚙️ **Multi-Model Conversations**: Engage with various models simultaneously, harnessing their unique strengths for optimal responses.

- 🔐 **Role-Based Access Control (RBAC)**: Secure access with restricted permissions — only authorized individuals can access your models, with exclusive creation/pulling rights reserved for administrators.

- 🗄️ **Flexible Database & Storage Options**: Choose from SQLite, PostgreSQL, or configure cloud storage backends (S3, Google Cloud Storage, Azure Blob Storage).

- 🌐 **Multilingual Support**: Experience Aether in your preferred language with full internationalization (i18n) support.

---

## How to Install 🚀

### Installation via Python pip 🐍

Ensure you're using **Python 3.11** to avoid compatibility issues.

1. **Install Aether**:
   ```bash
   pip install open-webui
   ```

2. **Run Aether**:
   ```bash
   open-webui serve
   ```

Access Aether at [http://localhost:8080](http://localhost:8080).

---

### Quick Start with Docker 🐳

> **Note**: Include `-v open-webui:/app/backend/data` in your Docker command to ensure your database is properly mounted and data is not lost.

**If Ollama is on your computer:**
```bash
docker run -d -p 3000:8080 --add-host=host.docker.internal:host-gateway -v open-webui:/app/backend/data --name aether --restart always ghcr.io/open-webui/open-webui:main
```

**If Ollama is on a different server:**
```bash
docker run -d -p 3000:8080 -e OLLAMA_BASE_URL=https://example.com -v open-webui:/app/backend/data --name aether --restart always ghcr.io/open-webui/open-webui:main
```

**With Nvidia GPU support:**
```bash
docker run -d -p 3000:8080 --gpus all --add-host=host.docker.internal:host-gateway -v open-webui:/app/backend/data --name aether --restart always ghcr.io/open-webui/open-webui:cuda
```

**OpenAI API only:**
```bash
docker run -d -p 3000:8080 -e OPENAI_API_KEY=your_secret_key -v open-webui:/app/backend/data --name aether --restart always ghcr.io/open-webui/open-webui:main
```

Access Aether at [http://localhost:3000](http://localhost:3000).

---

### Troubleshooting

If you experience connection issues inside Docker, use the `--network=host` flag:

```bash
docker run -d --network=host -v open-webui:/app/backend/data -e OLLAMA_BASE_URL=http://127.0.0.1:11434 --name aether --restart always ghcr.io/open-webui/open-webui:main
```

Note: with `--network=host` the port changes from 3000 to 8080.

---

## License 📜

This project is based on code originally licensed under the BSD 3-Clause License. All new contributions are licensed under the MIT License. See [LICENSE](./LICENSE) for details.

## Support 💬

If you have any questions, suggestions, or need assistance, please open an [issue](https://github.com/afiren/open-aether/issues) on GitHub. 🤝
