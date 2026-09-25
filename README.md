<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&height=200&color=gradient&customColorList=0,2,4,6&text=Juan%20Luna&fontSize=64&fontColor=ffffff&animation=fadeIn&fontAlignY=38&desc=Building%20tamper-evident%20infrastructure%20for%20AI%20systems&descAlignY=58&descSize=20" width="100%" alt="Juan Luna" />

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=24&duration=2600&pause=1100&color=00F0FF&center=true&vCenter=true&width=760&lines=Cryptographic+evidence+for+AI+%C2%B7+not+trust%2C+proof;Merkle+Mountain+Ranges+%C2%B7+Ed25519+%C2%B7+ML-DSA-65+(FIPS+204);Applied+topology+%C2%B7+persistent+homology+%C2%B7+category+theory;Open+source+%C2%B7+AGPLv3+%C2%B7+every+claim+ships+with+a+receipt" alt="Typing SVG" />

<p>
  <a href="https://github.com/JuanLunaIA?tab=followers">
    <img src="https://img.shields.io/github/followers/JuanLunaIA?label=Followers&style=for-the-badge&color=00F0FF&logo=github&logoColor=0d1117&labelColor=0d1117" alt="Followers" />
  </a>
  <a href="https://github.com/JuanLunaIA/aegis-latent-core">
    <img src="https://img.shields.io/github/stars/JuanLunaIA/aegis-latent-core?label=Aegis%20Stars&style=for-the-badge&color=A55CFF&logo=github&logoColor=0d1117&labelColor=0d1117" alt="Aegis Stars" />
  </a>
  <a href="https://github.com/JuanLunaIA/aegis-latent-core/forks">
    <img src="https://img.shields.io/github/forks/JuanLunaIA/aegis-latent-core?label=Forks&style=for-the-badge&color=00F0FF&logo=github&logoColor=0d1117&labelColor=0d1117" alt="Aegis Forks" />
  </a>
  <a href="mailto:juan.c.luna04@gmail.com">
    <img src="https://img.shields.io/badge/Email-juan.c.luna04%40gmail.com-0d1117?style=for-the-badge&logo=gmail&logoColor=A55CFF&labelColor=0d1117" alt="Email" />
  </a>
</p>

</div>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/JuanLunaIA/JuanLunaIA/output/github-contribution-grid-snake-dark.svg" />
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/JuanLunaIA/JuanLunaIA/output/github-contribution-grid-snake.svg" />
  <img alt="A snake eating my real contribution graph, one square at a time" src="https://raw.githubusercontent.com/JuanLunaIA/JuanLunaIA/output/github-contribution-grid-snake.svg" width="100%" />
</picture>

<sub align="center">↑ generated once a day from my actual contribution calendar — <a href=".github/workflows/snake.yml">workflow</a>, not a drawing.</sub>

<br /><br />

```yaml
identity:
  name:      "Juan Luna"
  handle:    "@JuanLunaIA"
  role:      "Independent developer — AI security, cryptographic evidence, applied topology"
  license:   ["AGPLv3", "Commercial", "MIT"]     # varies per project, see below
  status:    "🟢 open to full-time roles, contract work, and technical collaboration"
```

Everything below links to a real, public repository with its own CI badge, test suite, and — where relevant — a
benchmark you can re-run yourself. Nothing here is a slide; it's a table of contents to code that already runs.

---

## What I build

I design and ship systems where **the interesting part is the proof, not the API call**: infrastructure that has
to keep working — and keep being *checkable* — when the person reading the evidence doesn't trust the person who
produced it. That habit shows up in three places: a production-grade AI governance gateway, a topological
anomaly detector held to a 147-test theorem-verification suite, and a program compiler whose one headline number
is gated by CI on every commit.

I write Python and Rust for anything that has to be correct under adversarial conditions, and TypeScript/React
for the interfaces people actually use to see that correctness. I'd rather publish a real benchmark with its
measurement methodology than a marketing number — every project below does exactly that.

<br />

## 🛡️ Flagship — Aegis Latent Core

<table>
<tr>
<td width="60%" valign="top">

**AI governance and cryptographic evidence gateway.** Aegis sits in front of any OpenAI-compatible LLM
provider and commits a **signed, hash-linked record of every governed call — before the response is observable
by the caller** — then issues a portable proof a third party can verify **without trusting the gateway, the
vendor, or the operator who discloses the record.**

- **Append-only evidence.** Every record is a leaf in a Merkle Mountain Range; a portable `O(log n)` inclusion
  proof lets an outsider verify a disclosed record against a root they obtained independently.
- **Real cryptography, not a demo.** HMAC by default, **Ed25519 (RFC 8032)** or **ML-DSA-65 (FIPS 204,
  post-quantum)** where configured, with an HSM signing path in the enterprise build.
- **Offline, zero-trust verification.** A 313-line pure-Python verifier and a TypeScript twin with identical
  semantics — no network call, no dependency on Aegis itself being honest.
- **Fail-closed.** No signer or a ledger that fails to replay means *no service* — never silent, unevidenced
  traffic.
- **Signed supply chain.** Releases are Sigstore-signed (`gitsign verify-tag`), container images pass
  `cosign verify` with build-provenance attestations, and published artifacts re-hash to their own
  `SHA256SUMS`.

<sub>Regulatory framing (EU AI Act Art. 12, HIPAA, SEC 17a-4, MiFID II) is treated as **technical input, not
compliance** — no certification exists or is claimed. That candor is enforced in CI, not just written down.</sub>

</td>
<td width="40%" valign="top">

```
caller ──► Aegis gateway ──► upstream LLM
             │ auth · WAF
             │ rate limits
             │ (pass) forward
             │ ◄── response ──
             │ redact → hash
             │ → sign → WAL
             │ fsync → MMR leaf
caller ◄── response
     + X-Aegis-Evidence-Status
     + X-Aegis-MMR-* proof
```

**Measured** (2026-09-24, one shared 4-vCPU
container, reproducible via
`scripts/run_benchmarks_5.0.1.py`):

| Metric | Result |
|---|---:|
| Commit p99 | **1.22 ms** |
| Commit p50 | 0.62 ms |
| Throughput @10 threads | **1,727/s** |
| +RSS @ 1,000 SSE streams | **20.1 MB** |
| Test coverage | **91.30 %** |

</td>
</tr>
</table>

<p>
  <a href="https://github.com/JuanLunaIA/aegis-latent-core"><img src="https://img.shields.io/badge/Repository-public-00F0FF?style=flat-square&logo=github&logoColor=0d1117&labelColor=0d1117" alt="Repository" /></a>
  <a href="https://github.com/JuanLunaIA/aegis-latent-core/actions/workflows/ci.yml"><img src="https://github.com/JuanLunaIA/aegis-latent-core/actions/workflows/ci.yml/badge.svg" alt="CI" /></a>
  <a href="https://github.com/JuanLunaIA/aegis-latent-core/actions/workflows/security.yml"><img src="https://github.com/JuanLunaIA/aegis-latent-core/actions/workflows/security.yml/badge.svg" alt="Security" /></a>
  <a href="https://github.com/JuanLunaIA/aegis-latent-core/blob/main/LICENSE"><img src="https://img.shields.io/badge/license-AGPLv3%20or%20Commercial-A55CFF?style=flat-square&labelColor=0d1117" alt="License" /></a>
  <a href="https://aegis-latent-core.vercel.app"><img src="https://img.shields.io/badge/Live_site-aegis--latent--core.vercel.app-00F0FF?style=flat-square&logo=vercel&logoColor=0d1117&labelColor=0d1117" alt="Live site" /></a>
</p>

<br />

## 🔬 Research-grade side projects

Both of these exist because I wanted to know if a theoretical result actually held up under test — so I built
the harness that would prove me wrong if it didn't.

<table>
<tr>
<td width="50%" valign="top">

### [topo-net-anomaly](https://github.com/JuanLunaIA/network-telemetry-topology)

Topological anomaly detection for network telemetry: Takens delay-coordinate embedding → Vietoris–Rips
persistent homology → Betti-number (β₀/β₁) preservation check across PCA/UMAP reduction → robust-z / LOF /
Wasserstein ensemble detection.

The test suite doesn't just check the code — it checks the **math**: β₀=1, β₁=1 on a noisy circle; β₀=1, β₁=2,
β₂=1 on a torus; β₀=1, β₁=0, β₂=1 on a sphere. It also reports the one place theory predicts *failure*
(PCA destroys loops) and confirms that failure empirically, instead of hiding it.

- **147 / 147 tests passing** — unit, integration, property-based (Hypothesis), and theorem-verification
- **100 % coverage**, `perf_counter_ns` timing at 59 ns median resolution
- β₀ preservation under PCA: **100 %** · β₁ preservation: **0 %** (theory-confirmed, not a bug)

<img src="https://img.shields.io/badge/tests-147%20passed-00F0FF?style=flat-square&labelColor=0d1117" alt="tests" />
<img src="https://img.shields.io/badge/coverage-100%25-A55CFF?style=flat-square&labelColor=0d1117" alt="coverage" />
<img src="https://img.shields.io/badge/TDA-giotto--tda-00F0FF?style=flat-square&labelColor=0d1117" alt="TDA" />

</td>
<td width="50%" valign="top">

### [discopy-workflow](https://github.com/JuanLunaIA/discopy-workflow)

A JSON workflow DAG, run through two backends: a naive re-walking runner (what most off-the-shelf DAG
engines do), and a compiler that turns the workflow into a **DisCoPy Markov-category diagram**, then freezes
it into a single Python closure — no per-node dicts, no JSON walks at execution time.

The project's headline claim (**≥ 15 % less peak memory**) is asserted by the test suite and **enforced by
CI on every commit** — the benchmark job fails the build if a regression drops below target.

- **>99 % peak-memory reduction** measured via `tracemalloc` (target ≥ 15 %, CI-gated)
- CI matrix across Python 3.10–3.13, plus macOS/Windows smoke tests
- CLI + typed public API, ready for PyPI packaging

<img src="https://img.shields.io/badge/CI--gated_benchmark-≥15%25_target-00F0FF?style=flat-square&labelColor=0d1117" alt="benchmark" />
<img src="https://img.shields.io/badge/measured-%3E99%25_reduction-A55CFF?style=flat-square&labelColor=0d1117" alt="measured" />
<img src="https://img.shields.io/badge/license-MIT-00F0FF?style=flat-square&labelColor=0d1117" alt="MIT" />

</td>
</tr>
</table>

<br />

## ⚙️ Stack

<p>
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python" />
  <img src="https://img.shields.io/badge/Rust-000000?style=for-the-badge&logo=rust&logoColor=white" alt="Rust" />
  <img src="https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white" alt="TypeScript" />
  <img src="https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB" alt="React" />
  <img src="https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white" alt="FastAPI" />
  <img src="https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=node.js&logoColor=white" alt="Node.js" />
</p>
<p>
  <img src="https://img.shields.io/badge/Cryptography-Ed25519_%7C_ML--DSA--65-A55CFF?style=for-the-badge&logoColor=white" alt="Cryptography" />
  <img src="https://img.shields.io/badge/Merkle_Trees-00F0FF?style=for-the-badge&logoColor=white" alt="Merkle Trees" />
  <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" alt="Docker" />
  <img src="https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white" alt="GitHub Actions" />
  <img src="https://img.shields.io/badge/pytest-0A9EDC?style=for-the-badge&logo=pytest&logoColor=white" alt="pytest" />
  <img src="https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white" alt="Git" />
</p>

<br />

## 📊 GitHub, in numbers that update themselves

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=JuanLunaIA&show_icons=true&theme=tokyonight&bg_color=0D1117&title_color=00F0FF&icon_color=A55CFF&text_color=C9D1D9&border_color=30363D&hide_border=false" alt="GitHub Stats" width="49%" />
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=JuanLunaIA&layout=compact&theme=tokyonight&bg_color=0D1117&title_color=00F0FF&icon_color=A55CFF&text_color=C9D1D9&border_color=30363D&hide_border=false&langs_count=8" alt="Top Languages" width="42%" />
</p>
<p align="center">
  <img src="https://github-readme-streak-stats.herokuapp.com/?user=JuanLunaIA&theme=tokyonight&background=0D1117&ring=00F0FF&fire=A55CFF&currStreakLabel=00F0FF&sideNums=C9D1D9&sideLabels=C9D1D9&border=30363D&hide_border=false" alt="Streak Stats" width="97%" />
</p>
<p align="center">
  <img src="https://github-profile-trophy.vercel.app/?username=JuanLunaIA&theme=algolia&no-frame=true&no-bg=true&column=7&margin-w=8&margin-h=8" alt="Trophies" width="97%" />
</p>

<sub>All four widgets query the GitHub API live — they reflect whatever is true right now, not a snapshot I typed in.</sub>

<br />

## 🧭 Right now

```text
🔭 Currently building   Aegis Latent Core v5.x — enterprise hardening & SDK surface
🔬 Currently exploring  persistent homology for streaming telemetry, categorical compilers
💬 Ask me about         cryptographic audit trails, fail-closed system design, Merkle proofs
🟢 Open to              full-time roles · contract work · technical due-diligence reviews
📫 Reach me at          juan.c.luna04@gmail.com
```

<br />

<div align="center">

[![Email](https://img.shields.io/badge/Email-juan.c.luna04%40gmail.com-0d1117?style=for-the-badge&logo=gmail&logoColor=A55CFF&labelColor=0d1117)](mailto:juan.c.luna04@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Juan_Luna-0d1117?style=for-the-badge&logo=linkedin&logoColor=00F0FF&labelColor=0d1117)](https://www.linkedin.com/in/juanluna04/)
[![Aegis Latent Core](https://img.shields.io/badge/Flagship-Aegis_Latent_Core-0d1117?style=for-the-badge&logoColor=A55CFF&labelColor=0d1117)](https://github.com/JuanLunaIA/aegis-latent-core)

<sub>© 2026 Juan Luna · sole copyright holder & maintainer of Aegis Latent Core (see <a href="https://github.com/JuanLunaIA/aegis-latent-core/blob/main/AUTHORS">AUTHORS</a>)</sub>

<img src="https://capsule-render.vercel.app/api?type=waving&height=100&color=gradient&customColorList=6,4,2,0&section=footer&animation=fadeIn" width="100%" alt="" />

</div>
