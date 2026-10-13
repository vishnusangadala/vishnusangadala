<div align="center">

<a href="https://github.com/vishnusangadala?tab=repositories">
  <img src="./assets/hero.svg" width="100%" alt="Vishnu Sangadala — Java backend, C++ and CUDA systems, and AI-powered UI automation" />
</a>

<br/>

[![About](https://img.shields.io/badge/01_ABOUT-0d1117?style=for-the-badge&labelColor=238636)](#hello)
[![Work](https://img.shields.io/badge/02_SELECTED_WORK-0d1117?style=for-the-badge&labelColor=1f6feb)](#selected-work)
[![Systems](https://img.shields.io/badge/03_UNDER_THE_HOOD-0d1117?style=for-the-badge&labelColor=8957e5)](#under-the-hood)
[![Stack](https://img.shields.io/badge/04_TOOLBOX-0d1117?style=for-the-badge&labelColor=bf8700)](#toolbox)
[![Activity](https://img.shields.io/badge/05_ACTIVITY-0d1117?style=for-the-badge&labelColor=da3633)](#engineering-activity)

</div>

<a id="hello"></a>

## `$ whoami`

```yaml
name: Vishnu Sangadala
role: Software Engineer
focus: [Java Backends, C++ Systems, CUDA, Distributed Systems, AI Automation]
experience: 2+ years
education: MS in Data Science — Stony Brook University
currently_building: reliable systems where performance and intelligence meet
```

I design software across three layers: **services that scale**, **native code that moves fast**, and **automation that can reason about an interface before acting**. My work ranges from Spring Boot microservices and Kafka pipelines to custom CUDA kernels and voice-driven Windows automation.

<div align="center">

[![LinkedIn](https://img.shields.io/badge/LET'S_CONNECT-LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/vishnusangadala/)
[![Repositories](https://img.shields.io/badge/EXPLORE-36_REPOSITORIES-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/vishnusangadala?tab=repositories)
[![Profile Views](https://komarev.com/ghpvc/?username=vishnusangadala&style=for-the-badge&color=7c3aed&label=VISITORS)](https://github.com/vishnusangadala)

</div>

---

<a id="selected-work"></a>

## Selected work

<p align="center"><i>Click a card to open the repository. Expand a build note below for the engineering story.</i></p>

<table>
  <tr>
    <td width="50%">
      <a href="https://github.com/vishnusangadala/cuda-image-processing">
        <img src="https://github-readme-stats.vercel.app/api/pin/?username=vishnusangadala&repo=cuda-image-processing&theme=github_dark&hide_border=true&description_lines_count=3" width="100%" alt="CUDA Image Processing Accelerator" />
      </a>
    </td>
    <td width="50%">
      <a href="https://github.com/vishnusangadala/creditflow-ai">
        <img src="https://github-readme-stats.vercel.app/api/pin/?username=vishnusangadala&repo=creditflow-ai&theme=github_dark&hide_border=true&description_lines_count=3" width="100%" alt="CreditFlow AI" />
      </a>
    </td>
  </tr>
  <tr>
    <td width="50%">
      <a href="https://github.com/vishnusangadala/Distributed_Social_Networking">
        <img src="https://github-readme-stats.vercel.app/api/pin/?username=vishnusangadala&repo=Distributed_Social_Networking&theme=github_dark&hide_border=true&description_lines_count=3" width="100%" alt="Distributed Social Networking Platform" />
      </a>
    </td>
    <td width="50%">
      <a href="https://github.com/vishnusangadala/UI-automation">
        <img src="https://github-readme-stats.vercel.app/api/pin/?username=vishnusangadala&repo=UI-automation&theme=github_dark&hide_border=true&description_lines_count=3" width="100%" alt="LLM-powered UI Automation" />
      </a>
    </td>
  </tr>
</table>

<details>
<summary><b>⚡ Build note: CUDA Image Processing Accelerator</b> — what makes it more than a demo</summary>

### A benchmarkable CPU/GPU pipeline

The application implements grayscale conversion, Gaussian blur, and Sobel edge detection through matched **C++/OpenCV** and **custom CUDA** paths.

- Shared-memory halo tiles and constant-memory Gaussian coefficients
- CUDA-event timing split into transfer, kernel, and download phases
- CPU/GPU maximum-error validation, including non-block-aligned images
- Multi-resolution benchmark runner with CSV output
- CMake presets, development container, tests, and CPU-only CI

```text
image ─┬─> C++ / OpenCV reference ──────────────┐
       └─> upload ─> CUDA kernel ─> download ───┼─> verify + benchmark + report
```

[Open the CUDA project →](https://github.com/vishnusangadala/cuda-image-processing)

</details>

<details>
<summary><b>🏦 Build note: CreditFlow AI</b> — deterministic finance inside an agentic workflow</summary>

### Evidence in, verified decisions out

Five agents extract loan terms, calculate risk ratios, assess risk, draft a credit memo, and verify the result. Financial calculations stay in deterministic Python; questionable cases stop at `NEEDS_REVIEW` for a human decision.

```mermaid
flowchart LR
    D[Loan document] --> E[Extraction agent]
    E --> M[Deterministic metrics]
    M --> R[Risk + memo agents]
    R --> V{Verifier}
    V -->|pass| A[Audited result]
    V -->|flag| H[Human review]
```

`Java 21` · `Spring Boot` · `PostgreSQL` · `Python` · `FastAPI` · `LangGraph` · `React`

[Open CreditFlow AI →](https://github.com/vishnusangadala/creditflow-ai)

</details>

<details>
<summary><b>📊 Bonus build: LLM Inference Benchmark</b> — performance claims with evidence</summary>

A reproducible benchmark for vLLM and PyTorch/Transformers across batch sizes, prompt lengths, and generation lengths. It records TTFT, inter-token latency, throughput, GPU utilization, and peak GPU memory, then exports raw JSON/CSV and Prometheus metrics.

[Open the benchmark →](https://github.com/vishnusangadala/llm-inference-benchmark)

</details>

---

<a id="under-the-hood"></a>

## Under the hood

<details open>
<summary><h3>☕ Java backend engineering</h3></summary>

I build Java 17/21 services with **Spring Boot**, explicit API contracts, and ownership boundaries that stay understandable as a system grows.

| Design concern | How I approach it |
|---|---|
| Service boundaries | Independent services and data ownership instead of shared persistence |
| Communication | REST for direct requests; Kafka for asynchronous domain events |
| Data | PostgreSQL for relational content, Neo4j for graph relationships, Redis for low-latency access |
| Reliability | Validation, DTO boundaries, testable service layers, audit trails, and visible failure states |
| Delivery | Maven, Docker, Kubernetes, CI/CD, and reproducible local environments |

```mermaid
flowchart LR
    U[user-service] -->|follow event| K((Kafka))
    P[post-service] -->|post / like event| K
    K --> F[feed-service]
    U --> N[(Neo4j)]
    P --> G[(PostgreSQL)]
```

[Inspect the Java microservices project →](https://github.com/vishnusangadala/Distributed_Social_Networking)

</details>

<details>
<summary><h3>⚡ C++ and CUDA systems</h3></summary>

I use modern C++ and CUDA when latency, throughput, and memory behavior are part of the product—not implementation details.

- Native C++17 design with CMake and clear CPU/GPU abstractions
- Custom kernels, coalesced access, shared-memory tiling, and CUDA event timing
- Correctness comparisons before performance claims
- Warmups, repeated measurements, raw artifacts, and hardware-aware reporting

> My rule: **benchmark the complete path, publish the method, and never invent the speedup.**

[Inspect the CUDA implementation →](https://github.com/vishnusangadala/cuda-image-processing)

</details>

<details>
<summary><h3>🖥️ AI-powered UI automation</h3></summary>

My Windows desktop agent converts spoken requests into inspectable UI actions. Rather than guessing coordinates, it grounds each decision in the live accessibility tree.

```mermaid
flowchart LR
    V[Voice] --> W[Faster Whisper]
    W --> L[LLM planner]
    T[Live UI tree] --> L
    L --> J[Structured JSON action]
    J --> P[PyWinAuto]
    P --> T
```

The loop performs one action, reads the interface again, and continues only from the updated state. Hotkey recording, a tray interface, and spoken feedback make it usable as a desktop assistant.

`Python` · `LangChain` · `LangGraph` · `Faster Whisper` · `Windows UIA` · `PyWinAuto`

[Inspect the UI automation tool →](https://github.com/vishnusangadala/UI-automation)

</details>

---

<a id="toolbox"></a>

## Toolbox

<div align="center">

### Core

[![Core skills](https://skillicons.dev/icons?i=java,spring,cpp,python,postgres,redis,kafka,docker,kubernetes,aws&perline=10)](https://skillicons.dev)

### Performance, AI & product

[![Systems and AI skills](https://skillicons.dev/icons?i=pytorch,opencv,fastapi,react,ts,maven,cmake,linux,git,githubactions&perline=10)](https://skillicons.dev)

`CUDA` · `vLLM` · `LangGraph` · `Neo4j` · `Prometheus` · `REST APIs` · `Microservices` · `CI/CD`

</div>

<details>
<summary><b>My engineering operating system</b></summary>

```text
01  Make ownership explicit        04  Measure before optimizing
02  Keep deterministic logic testable
03  Verify probabilistic output    05  Leave an evidence trail
```

</details>

---

<a id="engineering-activity"></a>

## Engineering activity

<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github-readme-stats.vercel.app/api?username=vishnusangadala&show_icons=true&hide_border=true&theme=github_dark&rank_icon=github&include_all_commits=true">
  <source media="(prefers-color-scheme: light)" srcset="https://github-readme-stats.vercel.app/api?username=vishnusangadala&show_icons=true&hide_border=true&theme=default&rank_icon=github&include_all_commits=true">
  <img alt="Vishnu's GitHub statistics" src="https://github-readme-stats.vercel.app/api?username=vishnusangadala&show_icons=true&hide_border=true&theme=github_dark&rank_icon=github&include_all_commits=true" height="170" />
</picture>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://streak-stats.demolab.com?user=vishnusangadala&theme=github-dark-blue&hide_border=true">
  <source media="(prefers-color-scheme: light)" srcset="https://streak-stats.demolab.com?user=vishnusangadala&theme=default&hide_border=true">
  <img alt="Vishnu's contribution streak" src="https://streak-stats.demolab.com?user=vishnusangadala&theme=github-dark-blue&hide_border=true" height="170" />
</picture>

<br/>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=vishnusangadala&theme=github_dark">
  <source media="(prefers-color-scheme: light)" srcset="https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=vishnusangadala&theme=github">
  <img alt="Vishnu's GitHub contribution summary" src="https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=vishnusangadala&theme=github_dark" width="96%" />
</picture>

</div>

---

<div align="center">

### Have a backend, performance, or automation problem worth solving?

[![Start a conversation](https://img.shields.io/badge/START_A_CONVERSATION-Connect_on_LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/vishnusangadala/)
[![Browse all work](https://img.shields.io/badge/BROWSE_ALL_WORK-Open_repositories-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/vishnusangadala?tab=repositories)

<sub>Built with systems thinking, measurable evidence, and an unreasonable dislike of vague claims.</sub>

</div>
