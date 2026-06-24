<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=26&duration=3000&pause=1000&color=00FF66&center=true&vCenter=true&width=1000&lines=SYSTEM+STATE%3A+ACTIVE+%7C+USER%3A+JuanLunaIA;ROLE%3A+Principal+Systems+Engineer+%26+Applied+Cryptographer;FOCUS%3A+Post-Quantum+AI+Governance+%26+Kernel+Hardening;MISSION%3A+Zero-Trust+Infrastructure+for+the+AI+Era" alt="JuanLunaIA System Terminal" />

<p align="center">
  <a href="https://github.com/JuanLunaIA">
    <img src="https://img.shields.io/github/followers/JuanLunaIA?label=Network%20Nodes&style=for-the-badge&color=00FF66&logo=github&logoColor=0d1117" alt="Followers" />
  </a>
  <a href="https://github.com/JuanLunaIA/aegis-latent-core">
    <img src="https://img.shields.io/github/stars/JuanLunaIA/aegis-latent-core?label=Aegis%20Stars&style=for-the-badge&color=00E5FF&logo=github&logoColor=0d1117" alt="Aegis Stars" />
  </a>
  <a href="mailto:juan.c.luna04@gmail.com">
    <img src="https://img.shields.io/badge/Secure_Uplink-juan.c.luna04@gmail.com-000000?style=for-the-badge&logo=protonmail&logoColor=00FF66" alt="Email" />
  </a>
</p>

<br>

> *"I build the cryptographic infrastructure that transforms AI inference into mathematically admissible proof."*

</div>

---

### 📡 SYSTEM TELEMETRY & OPERATOR IDENTITY

```yaml
Operator_ID:      "Juan Luna"
Handle:           "@JuanLunaIA"
Base_of_Ops:      "Argentina (UTC-3)"
Academic_Matrix:  "Artificial Intelligence"
Core_Disciplines: ["Low-Level Systems Engineering", "Applied Cryptography", "Linux Kernel Hardening"]
Current_Status:   "Scaling Aegis Latent Core for Enterprise B2B/B2G Deployment"
```

---

### 🏛️ EXECUTIVE SUMMARY: THE ENGINEERING MANIFESTO

I am a **Systems Engineer and Applied Cryptographer** operating at the intersection of low-level software hardening, deterministic persistence, and post-quantum security protocols. 

As the AI market matures into the strict regulatory environment of 2026, the industry faces a critical deficit: the inability to mathematically prove what an LLM received and generated. I do not build superficial API wrappers. I engineer the rigid, zero-trust intermediate infrastructure that enterprise and government systems require to operate securely under hostile conditions and strict compliance audits.

My design philosophy is absolute: **Eliminate the assumption of trust in high-level software layers, replacing it with verifiable mathematical guarantees and hardware-level isolation.**

---

### 🛡️ FLAGSHIP ARCHITECTURE: AEGIS LATENT CORE

**[Aegis Cognitive Governance Gateway](https://github.com/JuanLunaIA/aegis-latent-core)** is my magnum opus. It is an OpenAI-compatible governance proxy that introduces a cryptographically signed, tamper-evident forensic ledger over corporate AI inference flows—without adding observable latency to the client.

#### The Cryptographic Data Flow (Two-Path Execution)

```text
                                  [Inbound Client Request]
                                             │
                                             ▼
                             ┌───────────────────────────────┐
                             │    SYNCHRONOUS HOT PATH       │
                             │  WAF / Auth / RateLimiter     │
                             └───────────────┬───────────────┘
                                             │
                                             ▼
                             ┌───────────────────────────────┐
                             │   RUST-ACCELERATED FORWARDER  │
                             └──────┬─────────────────┬──────┘
                                    │                 │
                             (Sync Return)     (Async Trigger)
                                    │                 │
                                    ▼                 ▼
                              [Client OK]      ┌─────────────────────────────┐
                              (~2.4 µs p50)    │   ASYNCHRONOUS BACKGROUND   │
                                               │  H[i] = SHA256(prev || MMR) │
                                               └──────────────┬──────────────┘
                                                              │
                                                              ▼
                                                    [0o600 WAL Persistence]
```

#### Architectural Highlights
*   **Rust FFI Acceleration (PyO3):** Native Merkle Mountain Range (MMR) accumulators and **FIPS 204 (ML-DSA-65)** post-quantum signatures that explicitly release the Python GIL for true hardware-level concurrency.
*   **Zero Forensic Latency:** Asynchronous dispatch routing via `asyncio.create_task` executed *after* the transport response, yielding a scheduling overhead of just **2.43 µs p50**.
*   **Kernel-Level Hardening:** System call restrictions via compiled **seccomp-BPF** filters, AppArmor confinement, and POSIX real-time scheduler prioritization (`SCHED_FIFO`).

---

### ⚙️ TECHNICAL ARSENAL & DOMAIN EXPERTISE

<table align="center" style="width: 100%; border-collapse: collapse; background-color: #0d1117;">
  <tr>
    <th align="left" style="width: 30%; color: #00FF66; padding: 10px; border-bottom: 1px solid #30363d;">Operational Layer</th>
    <th align="left" style="color: #00E5FF; padding: 10px; border-bottom: 1px solid #30363d;">Technologies, Standards & Integrations</th>
  </tr>
  <tr>
    <td style="padding: 10px; border-bottom: 1px solid #30363d;"><strong>Low-Level Systems</strong></td>
    <td style="padding: 10px; border-bottom: 1px solid #30363d;">
      <img src="https://img.shields.io/badge/Rust-000000?style=flat-square&logo=rust&logoColor=white" alt="Rust" />
      <img src="https://img.shields.io/badge/C-00599C?style=flat-square&logo=c&logoColor=white" alt="C" />
      <img src="https://img.shields.io/badge/Python_3.12+-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python" />
      <img src="https://img.shields.io/badge/Linux_Kernel-FCC624?style=flat-square&logo=linux&logoColor=black" alt="Linux" />
      <img src="https://img.shields.io/badge/POSIX_Sched-000000?style=flat-square&logo=linux" alt="POSIX" />
    </td>
  </tr>
  <tr>
    <td style="padding: 10px; border-bottom: 1px solid #30363d;"><strong>Confinement & Security</strong></td>
    <td style="padding: 10px; border-bottom: 1px solid #30363d;">
      <img src="https://img.shields.io/badge/Seccomp_BPF-000000?style=flat-square&logo=linux&logoColor=green" alt="Seccomp" />
      <img src="https://img.shields.io/badge/AppArmor-7FBA00?style=flat-square&logo=linux" alt="AppArmor" />
      <img src="https://img.shields.io/badge/SELinux-000000?style=flat-square&logo=linux&logoColor=red" alt="SELinux" />
      <img src="https://img.shields.io/badge/Zero_Trust-2496ED?style=flat-square&logo=cloudflare" alt="Zero Trust" />
    </td>
  </tr>
  <tr>
    <td style="padding: 10px; border-bottom: 1px solid #30363d;"><strong>Applied Cryptography</strong></td>
    <td style="padding: 10px; border-bottom: 1px solid #30363d;">
      <img src="https://img.shields.io/badge/ML--DSA_65_(FIPS_204)-00FF66?style=flat-square&logo=security" alt="ML-DSA" />
      <img src="https://img.shields.io/badge/ML--KEM_1024_(FIPS_203)-000000?style=flat-square" alt="ML-KEM" />
      <img src="https://img.shields.io/badge/PKCS%2311_HSM-FF6F00?style=flat-square&logo=fortinet" alt="HSM" />
      <img src="https://img.shields.io/badge/Merkle_Mountain_Ranges-00E5FF?style=flat-square" alt="MMR" />
    </td>
  </tr>
  <tr>
    <td style="padding: 10px;"><strong>Distributed Infrastructure</strong></td>
    <td style="padding: 10px;">
      <img src="https://img.shields.io/badge/Tokio_Async-000000?style=flat-square&logo=rust" alt="Tokio" />
      <img src="https://img.shields.io/badge/mTLS_/_CAC--PIV-00E5FF?style=flat-square" alt="mTLS" />
      <img src="https://img.shields.io/badge/Docker_&_K8s-326CE5?style=flat-square&logo=kubernetes&logoColor=white" alt="K8s" />
      <img src="https://img.shields.io/badge/HashiCorp_Vault-000000?style=flat-square&logo=hashicorp&logoColor=white" alt="Vault" />
    </td>
  </tr>
</table>

---

### 📊 DEVELOPMENT TELEMETRY & CODE METRICS

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=JuanLunaIA&show_icons=true&theme=tokyonight&bg_color=0D1117&title_color=00FF66&icon_color=00E5FF&text_color=C9D1D9&border_color=30363D&hide_border=false" alt="Juan's GitHub Stats" width="48%" />
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=JuanLunaIA&layout=compact&theme=tokyonight&bg_color=0D1117&title_color=00FF66&icon_color=00E5FF&text_color=C9D1D9&border_color=30363D&hide_border=false" alt="Top Languages Card" width="48%" />
</p>

<p align="center">
  <img src="https://github-readme-streak-stats.herokuapp.com/?user=JuanLunaIA&theme=tokyonight&background=0D1117&ring=00FF66&fire=00E5FF&currStreakLabel=00FF66&sideNums=C9D1D9&sideLabels=C9D1D9&border=30363D&hide_border=false" alt="GitHub Contribution Streak" width="97%" />
</p>

---

### 🔐 SECURE INGRESS: B2B & CAREER ROUTING

I am actively opening channels for high-leverage opportunities. If you are looking to audit inference systems, establish B2B licensing for Aegis Latent Core, or recruit top-percentile engineering talent for low-level systems and cryptography:

*   **Primary Identity:** Juan Luna
*   **Secure Endpoint:** `juan.c.luna04@gmail.com`
*   **Commercial Licensing:** [Aegis Enterprise Reference](https://github.com/JuanLunaIA/aegis-latent-core/blob/main/COMMERCIAL.md)
*   **LinkedIn:** [Connect for B2B/GTM Operations](https://www.linkedin.com/in/juanluna04/)
