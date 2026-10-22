<div align="center">

<img src="assets/banner.svg" alt="Barış Güngör: Backend & AI Engineer" width="100%"/>

<br/>

[![LinkedIn](https://img.shields.io/badge/LinkedIn-gungor--baris-0A66C2?style=flat)](https://www.linkedin.com/in/gungor-baris)
[![Email](https://img.shields.io/badge/Email-barisgungormail%40gmail.com-EA4335?style=flat&logo=gmail&logoColor=white)](mailto:barisgungormail@gmail.com)
![Location](https://img.shields.io/badge/Istanbul,%20Türkiye-1f2937?style=flat&logo=googlemaps&logoColor=white)
![Languages](https://img.shields.io/badge/Turkish%20·%20English-1f2937?style=flat&logo=googletranslate&logoColor=white)

</div>

---

## 👋 About me

I build the parts of a product that users never see but always feel: the services that take messages from
six different channels and route them in order, the queues that retry what failed and park what cannot be
saved, and the pipelines that turn messy documents into something an LLM can actually answer from.

For about five years I have been working mostly on the backend side with **Node.js (NestJS)** and
**Python (FastAPI)**, on multi-tenant and event-driven systems that run in production, plus enough
**Vue.js** to ship the screens on top of them. Lately most of my time goes into **LLM and RAG** work:
parsing, chunking, embeddings, vector search and wiring several model providers behind one interface.

## 🧭 What I work on

<table>
  <tr>
    <td width="50%" valign="top">

### 🏗️ Multi-tenant backends

Tenant-isolated environments, tenant-scoped caching, configuration that can be moved between tenants and
collections, REST APIs with versioning and OpenAPI docs. Authentication with JWT and refresh tokens,
authorization with attribute-based rules (CASL).

</td>
    <td width="50%" valign="top">

### 💬 Conversational & messaging systems

A unified messaging layer for WhatsApp, Telegram, MS Teams, Slack, Facebook and Discord. Webhook ingestion,
asynchronous processing, intent / entity / FAQ management, LLM-powered flow steps, speech-to-text and
text-to-speech, at loads of a few thousand conversations a day.

</td>
  </tr>
  <tr>
    <td width="50%" valign="top">

### 🧠 LLM & RAG pipelines

Document parsing that reads structure (headings, font sizes), semantic, recursive and size-based chunking,
embedding and enrichment steps (including LLM-based table enrichment), similarity search tuning in
**Qdrant**, and a provider layer over OpenAI, Anthropic, Google, Hugging Face and others.

</td>
    <td width="50%" valign="top">

### 📨 Event-driven architecture

**RabbitMQ** with retries, dead-letter, priority and delayed queues; in-process domain events in modular
monoliths; scheduled jobs, backup / restore and real-time analytics. I like systems where every message
has a known path, including the failure path.

</td>
  </tr>
  <tr>
    <td width="50%" valign="top">

### 📄 OCR & document intelligence

OCR on scanned PDFs (Tesseract, OCRmyPDF) with rule-based segmentation, so documents with many unrelated
records on one page can be split, filtered and handed to an LLM for structured extraction.

</td>
    <td width="50%" valign="top">

### 🚢 Delivery & quality

Unit, integration and end-to-end tests (Jest, Vitest, tests against a real PostgreSQL), raising coverage on
legacy code to 80%, refactoring old codebases, and CI/CD with Jenkins and Argo CD onto Kubernetes.

</td>
  </tr>
</table>

### A typical system I work on

```mermaid
flowchart LR
    CH["Channels<br/>WhatsApp · Telegram · Teams<br/>Slack · Facebook · Discord · Web"] -->|webhooks| CM[Channel manager]
    CM -->|publish| Q[(RabbitMQ<br/>retry · DLQ · priority · delay)]
    Q --> BOT[Bot engine<br/>flows · intents · FAQ]
    BOT -->|LLM step| LLM[LLM providers]
    BOT -->|retrieve| RAG[RAG service]
    DOC[Documents] --> ING[Parse → clean → chunk<br/>→ embed → enrich] --> V[(Qdrant)]
    RAG --> V
    BOT --- DB[(PostgreSQL + Redis<br/>tenant-scoped)]
```

## 🛠️ Tech stack

| Area | Tools |
|---|---|
| **Languages** | ![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=typescript&logoColor=white) ![JavaScript](https://img.shields.io/badge/JavaScript-323330?style=flat&logo=javascript&logoColor=F7DF1E) ![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white) |
| **Backend** | ![Node.js](https://img.shields.io/badge/Node.js-5FA04E?style=flat&logo=nodedotjs&logoColor=white) ![NestJS](https://img.shields.io/badge/NestJS-E0234E?style=flat&logo=nestjs&logoColor=white) ![Fastify](https://img.shields.io/badge/Fastify-000000?style=flat&logo=fastify&logoColor=white) ![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat&logo=fastapi&logoColor=white) ![OpenAPI](https://img.shields.io/badge/OpenAPI-6BA539?style=flat&logo=openapiinitiative&logoColor=white) ![JWT](https://img.shields.io/badge/JWT-000000?style=flat&logo=jsonwebtokens&logoColor=white) |
| **AI / LLM** | ![OpenAI](https://img.shields.io/badge/OpenAI-412991?style=flat) ![Anthropic](https://img.shields.io/badge/Anthropic-191919?style=flat&logo=anthropic&logoColor=white) ![Google Gemini](https://img.shields.io/badge/Gemini-8E75B2?style=flat&logo=googlegemini&logoColor=white) ![Hugging Face](https://img.shields.io/badge/Hugging%20Face-FFD21E?style=flat&logo=huggingface&logoColor=black) ![Qdrant](https://img.shields.io/badge/Qdrant-DC244C?style=flat&logo=qdrant&logoColor=white) ![Tesseract](https://img.shields.io/badge/Tesseract%20OCR-4B8BBE?style=flat) |
| **Data & messaging** | ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat&logo=postgresql&logoColor=white) ![Redis](https://img.shields.io/badge/Redis-FF4438?style=flat&logo=redis&logoColor=white) ![RabbitMQ](https://img.shields.io/badge/RabbitMQ-FF6600?style=flat&logo=rabbitmq&logoColor=white) ![TypeORM](https://img.shields.io/badge/TypeORM-FE0803?style=flat&logo=typeorm&logoColor=white) ![Sequelize](https://img.shields.io/badge/Sequelize-52B0E7?style=flat&logo=sequelize&logoColor=white) |
| **DevOps** | ![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white) ![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=flat&logo=kubernetes&logoColor=white) ![Jenkins](https://img.shields.io/badge/Jenkins-D24939?style=flat&logo=jenkins&logoColor=white) ![Argo CD](https://img.shields.io/badge/Argo%20CD-EF7B4D?style=flat&logo=argo&logoColor=white) ![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat) |
| **Testing** | ![Jest](https://img.shields.io/badge/Jest-C21325?style=flat&logo=jest&logoColor=white) ![Vitest](https://img.shields.io/badge/Vitest-6E9F18?style=flat&logo=vitest&logoColor=white) ![Postman](https://img.shields.io/badge/Postman-FF6C37?style=flat&logo=postman&logoColor=white) |
| **Frontend** | ![Vue.js](https://img.shields.io/badge/Vue.js-4FC08D?style=flat&logo=vuedotjs&logoColor=white) ![Svelte](https://img.shields.io/badge/Svelte-FF3E00?style=flat&logo=svelte&logoColor=white) ![Vite](https://img.shields.io/badge/Vite-646CFF?style=flat&logo=vite&logoColor=white) ![Naive UI](https://img.shields.io/badge/Naive%20UI-18A058?style=flat) ![Tailwind CSS](https://img.shields.io/badge/Tailwind%20CSS-06B6D4?style=flat&logo=tailwindcss&logoColor=white) |
| **Ways of working** | ![Jira](https://img.shields.io/badge/Jira-0052CC?style=flat&logo=jira&logoColor=white) ![Figma](https://img.shields.io/badge/Figma-F24E1E?style=flat&logo=figma&logoColor=white) ![Notion](https://img.shields.io/badge/Notion-000000?style=flat&logo=notion&logoColor=white)

## 🚀 Featured projects

<table>
  <tr>
    <td width="50%" valign="top">

### [📈 backtrail](https://github.com/baris-gungor/backtrail)

**Does what I tested match what actually happens?** A trading-strategy research platform: hourly market data,
11 indicators feeding rule-based strategies, an event-driven backtest engine with fees, slippage,
**walk-forward** and **Monte Carlo** analysis, and paper portfolios (internal and Alpaca paper).

The backtest and the paper portfolio share one execution engine, so a divergence report can prove the two
produce identical trades. Modular monolith with pure domain layers, ports and adapters, `decimal.js` for
money, end-to-end tests against a real PostgreSQL, and a bilingual Vue 3 dashboard.

![NestJS](https://img.shields.io/badge/NestJS-E0234E?style=flat-square&logo=nestjs&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Vue](https://img.shields.io/badge/Vue%203-4FC08D?style=flat-square&logo=vuedotjs&logoColor=white)
![Vitest](https://img.shields.io/badge/Vitest-6E9F18?style=flat-square&logo=vitest&logoColor=white)

</td>
    <td width="50%" valign="top">

### [📄 doc-ocr-llm-analyzer](https://github.com/baris-gungor/doc-ocr-llm-analyzer)

Turns scanned Turkish trade-registry gazette PDFs into structured company data with one HTTP call: Turkish
OCR, rule-based splitting of the many announcements printed on one page, company filtering, heading-aware
chunking, then per-chunk LLM extraction rendered as an HTML report.

The LLM layer is one abstract base class with retries and exponential backoff on rate limits; Groq,
OpenRouter, Hugging Face and Together AI are thin subclasses chosen by a single environment variable.

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![Tesseract](https://img.shields.io/badge/Tesseract-4B8BBE?style=flat-square)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)

</td>
  </tr>
</table>

## 🧩 How I like to build

- **One code path for the same decision.** If two features answer the same question, they should run the
  same code, so their results can be compared instead of argued about.
- **Plan for the failure path.** Retries, dead-letter queues, idempotent ids, kill switches and audit logs
  are part of the design, not an afterthought.
- **Keep the domain pure.** Business rules without framework imports, outside services behind ports, so the
  core is easy to test and easy to change.
- **Test against the real thing where it matters.** End-to-end tests on a real database, fakes only at the
  network edge.
- **Be honest about limits.** Every project README lists what it does not do yet.

---

<div align="center">
<sub>Open to conversations about backend architecture, messaging systems and LLM / RAG work.</sub>
</div>
