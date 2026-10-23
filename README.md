<div align="center">
  <img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=0:111827,35:4338ca,70:7c3aed,100:fb7185&height=190&section=header&text=Ideator&fontSize=68&fontColor=ffffff&animation=twinkling&fontAlignY=36&desc=Turn%20a%20rough%20idea%20into%20a%20clear%20next%20step.&descAlignY=58&descSize=16" alt="Ideator animated header" />

  <p>
    <img src="https://img.shields.io/badge/Frontend-React%2019-61DAFB?style=for-the-badge&logo=react&logoColor=111827" alt="React 19" />
    <img src="https://img.shields.io/badge/API-FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white" alt="FastAPI" />
    <img src="https://img.shields.io/badge/Search-Qdrant%20%2B%20embeddings-7C3AED?style=for-the-badge" alt="Qdrant and embeddings" />
    <a href="LICENSE"><img src="https://img.shields.io/badge/License-MIT-FDA4AF?style=for-the-badge" alt="MIT License" /></a>
  </p>
</div>

## 💡 What it does

Ideator is an AI-assisted ideation app. A user can explore a project direction through a chat interface; the backend combines model calls, embeddings, stored idea context, and external data integrations to help refine the concept and check for nearby ideas.

<p align="center"><img src="frontend/src/assets/hero.png" width="86%" alt="Ideator interface illustration" /></p>

## 🧠 Request path

```mermaid
flowchart LR
  A[React client] --> B[FastAPI chat API]
  B --> C[LLM routing and tools]
  C --> D[Embedding and memory services]
  D --> E[MongoDB and Qdrant]
  C --> F[Response to client]
```

## 🧰 Stack

| Area | Tools |
|---|---|
| Client | React 19, Vite, Mantine, Tabler Icons |
| API | Python 3.12, FastAPI, Uvicorn |
| Persistence/cache | MongoDB, Redis |
| Retrieval | Qdrant, sentence-transformers |
| Models | Provider routing configured in `backend/config/llm_providers.yaml` |

## 🚀 Run locally

```bash
git clone https://github.com/ChristopherJoshy/ideator.git
cd ideator/backend
python -m venv .venv
# Windows: .venv\Scripts\Activate.ps1
# macOS/Linux: source .venv/bin/activate
pip install -r requirements.txt
uvicorn main:app --reload
```

In another terminal, start the frontend:

```bash
cd ideator/frontend
npm install
npm run dev
```

Set the model provider, MongoDB, Redis, and Qdrant configuration in a local environment file. Provider credentials are not included. The frontend and backend are separate services.

## 🗂️ Layout

```text
backend/   API, model routing, memory, embeddings and data services
frontend/  React interface and chat flow
```

## 📄 License

MIT. See [`LICENSE`](LICENSE).