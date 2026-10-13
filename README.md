<div align="center">

# Hi, I'm Vishnu Sangadala 👋

[![Typing SVG](https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=22&duration=2800&pause=900&color=58A6FF&center=true&vCenter=true&width=760&lines=Backend+Engineer+%7C+Java+%2B+Spring+Boot;C%2B%2B+%2B+CUDA+%7C+GPU-Accelerated+Systems;Distributed+Systems+%7C+Event-Driven+Architecture;LLM-Powered+UI+Automation+%7C+AI+Engineering)](https://git.io/typing-svg)

**Software Engineer with 2+ years of experience building reliable backend systems, distributed services, and developer-focused automation.**

I build across the stack where performance and reliability matter—from **Java microservices** and **C++/CUDA compute pipelines** to **AI agents that operate desktop interfaces**.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/vishnusangadala/)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/vishnusangadala)
[![Profile Views](https://komarev.com/ghpvc/?username=vishnusangadala&style=for-the-badge&color=58a6ff&label=PROFILE+VIEWS)](https://github.com/vishnusangadala)

<sub>MS in Data Science, Stony Brook University · Software engineering experience at Infor India</sub>

</div>

---

## Explore my work

[Java Backend](#java-backend-engineering) · [C++ & CUDA](#c--cuda-systems) · [UI Automation](#ai-powered-ui-automation) · [Featured Projects](#featured-projects) · [Tech Stack](#technology-toolbox) · [GitHub Activity](#github-activity)

## What I build

| Focus | What that means in practice |
|---|---|
| ☕ **Java backend engineering** | Spring Boot services, REST APIs, persistence, validation, event-driven workflows, and clean service boundaries |
| ⚡ **C++ & CUDA systems** | Native C++17 applications, custom GPU kernels, CPU/GPU validation, benchmarking, and performance-aware design |
| 🧩 **Distributed systems** | Microservices, Kafka event streams, polyglot persistence, Docker-based environments, and observable workflows |
| 🤖 **AI & UI automation** | LLM-guided agents, structured verification, speech interfaces, Windows UI Automation, and human-in-the-loop execution |

## Java backend engineering

My backend work centers on **Java 17/21, Spring Boot, and well-defined API contracts**. I care about systems that are understandable under failure—not just systems that work in the happy path.

- Designed independent services with database ownership and asynchronous Kafka communication
- Built REST APIs with validation, DTO boundaries, persistence, and testable service layers
- Used PostgreSQL, Neo4j, Redis, and H2 according to the data and workflow model
- Containerized multi-service applications for reproducible local development
- Separated deterministic business logic from probabilistic AI components

<details>
<summary><b>See a Java microservices architecture</b></summary>

```text
user-service ──┐
               ├── events ──> Kafka ──> feed-service
post-service ──┘

user-service ──> Neo4j       post-service ──> PostgreSQL
```

The services in my [Distributed Social Networking Platform](https://github.com/vishnusangadala/Distributed_Social_Networking) communicate through events instead of direct service-to-service calls, keeping ownership and coupling explicit.

</details>

## C++ & CUDA systems

I use **modern C++ and CUDA** to build native, performance-sensitive pipelines. My CUDA image-processing project implements matched CPU and GPU paths for grayscale conversion, Gaussian blur, and Sobel edge detection.

- Custom CUDA kernels with 16×16 thread blocks and coalesced memory access
- Shared-memory halo tiling for neighborhood filters
- Constant memory for Gaussian coefficients
- CUDA event timing for upload, kernel, and download phases
- CPU/GPU correctness checks and reproducible multi-resolution benchmarks
- CMake presets, automated tests, Docker, and CPU-only CI

<details>
<summary><b>Open the CPU/GPU execution model</b></summary>

```text
Input image
   ├──> C++ / OpenCV reference path
   └──> CUDA path: upload ─> custom kernel ─> download
                    │
                    └──> timing + correctness validation + CSV report
```

Explore the implementation: [CUDA Image Processing Accelerator](https://github.com/vishnusangadala/cuda-image-processing)

</details>

## AI-powered UI automation

My [GUI Automation using LLMs](https://github.com/vishnusangadala/UI-automation) project turns spoken instructions into desktop actions on Windows.

```mermaid
flowchart LR
    A[Voice command] --> B[Local speech-to-text]
    B --> C[LLM planning agent]
    D[Windows UI tree] --> C
    C --> E[Structured action]
    E --> F[PyWinAuto execution]
    F --> D
```

The tool combines **Faster Whisper**, **LangChain/LangGraph**, **Windows UI Automation**, and **PyWinAuto**. It reads the active window's accessibility tree, selects a verifiable control, performs one action, and re-reads the interface before continuing. A tray interface, hotkey-driven recording, and text-to-speech feedback make the workflow usable as a desktop assistant.

<details>
<summary><b>Why accessibility-tree automation?</b></summary>

Structured UI controls provide titles, control types, and application state that can be validated before an action. That makes the execution loop more inspectable and repeatable than relying only on screen coordinates.

</details>

## Featured projects

<details open>
<summary><b>⚡ CUDA Image Processing Accelerator — C++17 · CUDA · OpenCV · CMake</b></summary>

Matched CPU and GPU implementations of three image filters, with custom optimized kernels, output validation, phase-level timing, and benchmark reporting across multiple resolutions.

**Engineering focus:** GPU memory behavior, kernel optimization, measurement quality, correctness, and reproducible builds.

[View repository →](https://github.com/vishnusangadala/cuda-image-processing)

</details>

<details>
<summary><b>🏦 CreditFlow AI — Java 21 · Spring Boot · Python · LangGraph · React</b></summary>

A multi-agent credit-analysis platform that extracts evidence from loan documents, computes financial ratios deterministically, drafts a credit memo, verifies its own output, and routes questionable cases to a human reviewer.

**Engineering focus:** audit trails, source-grounded extraction, human oversight, background processing, and clear boundaries between Java orchestration and Python agent services.

[View repository →](https://github.com/vishnusangadala/creditflow-ai)

</details>

<details>
<summary><b>🌐 Distributed Social Network — Java 17 · Spring Boot · Kafka · Neo4j · PostgreSQL</b></summary>

Three independently owned microservices for users, posts, and feeds. Kafka events connect the services while Neo4j models relationships and PostgreSQL stores content.

**Engineering focus:** event-driven architecture, polyglot persistence, loose coupling, JWT-based login, and Docker Compose environments.

[View repository →](https://github.com/vishnusangadala/Distributed_Social_Networking)

</details>

<details>
<summary><b>🖥️ LLM UI Automation — Python · LangGraph · PyWinAuto · Faster Whisper</b></summary>

A voice-driven Windows desktop agent that grounds LLM decisions in the live UI Automation tree and executes structured, incremental actions with spoken feedback.

**Engineering focus:** tool-using agents, accessibility APIs, local speech recognition, action validation, and iterative UI state inspection.

[View repository →](https://github.com/vishnusangadala/UI-automation)

</details>

<details>
<summary><b>📊 LLM Inference Benchmark — Python · vLLM · PyTorch · Prometheus · Docker</b></summary>

A reproducible framework for comparing LLM serving configurations across batch sizes and token lengths. It captures TTFT, inter-token latency, throughput, GPU utilization, and peak GPU memory.

**Engineering focus:** defensible performance experiments, raw result artifacts, baseline comparisons, NVML sampling, and CPU-only CI.

[View repository →](https://github.com/vishnusangadala/llm-inference-benchmark)

</details>

## Technology toolbox

### Languages

![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![C++](https://img.shields.io/badge/C++-00599C?style=flat-square&logo=cplusplus&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![CUDA](https://img.shields.io/badge/CUDA-76B900?style=flat-square&logo=nvidia&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat-square&logo=postgresql&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)

### Backend, data & distributed systems

![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![Kafka](https://img.shields.io/badge/Apache_Kafka-231F20?style=flat-square&logo=apachekafka&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Neo4j](https://img.shields.io/badge/Neo4j-4581C3?style=flat-square&logo=neo4j&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white)

### Systems, AI & infrastructure

![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=flat-square&logo=opencv&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=flat-square&logo=langchain&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonwebservices&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black)

## Engineering principles

```text
Measure before optimizing     Verify probabilistic output
Own data at service boundaries     Make failure states observable
Prefer reproducible evidence over impressive-looking claims
```

## GitHub activity

<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github-readme-stats.vercel.app/api?username=vishnusangadala&show_icons=true&hide_border=true&theme=github_dark&rank_icon=github">
  <source media="(prefers-color-scheme: light)" srcset="https://github-readme-stats.vercel.app/api?username=vishnusangadala&show_icons=true&hide_border=true&theme=default&rank_icon=github">
  <img alt="Vishnu's GitHub statistics" src="https://github-readme-stats.vercel.app/api?username=vishnusangadala&show_icons=true&hide_border=true&theme=github_dark&rank_icon=github" height="165">
</picture>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github-readme-stats.vercel.app/api/top-langs/?username=vishnusangadala&layout=compact&hide_border=true&theme=github_dark&langs_count=8">
  <source media="(prefers-color-scheme: light)" srcset="https://github-readme-stats.vercel.app/api/top-langs/?username=vishnusangadala&layout=compact&hide_border=true&theme=default&langs_count=8">
  <img alt="Vishnu's most-used languages" src="https://github-readme-stats.vercel.app/api/top-langs/?username=vishnusangadala&layout=compact&hide_border=true&theme=github_dark&langs_count=8" height="165">
</picture>

</div>

---

<div align="center">

### Let's build systems that are fast, reliable, and easy to reason about.

[Explore my repositories](https://github.com/vishnusangadala?tab=repositories) · [Connect on LinkedIn](https://www.linkedin.com/in/vishnusangadala/)

</div>
