<div align="center">

# Matias Zapf

**Software Engineer · Cyberdefense**

[![zapf.dev](https://img.shields.io/badge/zapf.dev-303446?style=for-the-badge&logo=astro&logoColor=8caaee)](https://zapf.dev/)
[![Atlas](https://img.shields.io/badge/atlas-303446?style=for-the-badge&logoColor=ef9f76)](https://zapf.dev/atlas/)
[![Blog](https://img.shields.io/badge/blog-303446?style=for-the-badge&logoColor=8caaee)](https://zapf.dev/blog/)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-303446?style=for-the-badge&logo=linkedin&logoColor=8caaee)](https://www.linkedin.com/in/zapf/)
[![Email](https://img.shields.io/badge/matias@zapf.dev-303446?style=for-the-badge&logo=gmail&logoColor=8caaee)](mailto:matias@zapf.dev)

</div>

---

## Profile

Security-minded software engineer building reliable systems. Drawn to detecting fraud, vulnerabilities, and threats; now focused on **[cyberdefense](https://undef.edu.ar/fadena/carreras-de-grado/licciberdefensa/)**.

## Projects

I own the architecture, specs, threat models and verification gates; I orchestrate the AI agents that implement them, then review and audit the code against the plan.

- **[ensamble](https://github.com/MatiasZapf/ensamble)** — the multi-agent SDLC framework I build my software with. Specialized agent roles take each project from validation, architecture and threat modeling to test-driven implementation and independent QA, handing off through version-controlled artifacts. Hooks and scripts enforce its gates on agent file edits: code stays blocked until the plan is approved; specs, acceptance tests and checks are frozen during the build; and known-format secrets are rejected. Before approval, independent models challenge the plan and threat model in read-only mode. At the end of the build, "done" is computed by re-running the project's real checks instead of trusting the agent's report.
- **[monitor](https://github.com/MatiasZapf/monitor)** — a private multi-service system in Go, built with ensamble and in production 24/7 on a host with no internet-facing ports. A scraper limited to allowlisted, read-only API calls over pinned egress detects changes; messaging bots deliver them and answer commands. Single-purpose static binaries, each service in its own systemd sandbox, exchange data through a crash-atomic file spool rather than the network, with a reader that treats every file as hostile. A transactional outbox and an idempotent ledger give crash-recoverable, at-least-once delivery. Releases are signed offline with a FIDO2 key and verified in standard-library-only Go before an atomic switch. CI enforces the hexagonal layering, per-binary dependency limits and the systemd sandbox baseline.
- **[apuntes.md](https://apuntes.md)** — a private multi-agent pipeline that rebuilds my Cyberdefense coursework into audited study material grounded in evidence-based pedagogy ([Ausubel](https://en.wikipedia.org/wiki/David_Ausubel) · [Sweller](https://en.wikipedia.org/wiki/John_Sweller) · [Mayer](https://en.wikipedia.org/wiki/Richard_E._Mayer) · [Bloom](https://en.wikipedia.org/wiki/Bloom%27s_taxonomy) · [Matuschak](https://notes.andymatuschak.org/Evergreen_notes)). An orchestrator runs specialized agents through dependency-ordered stages, with auditor–enricher loops and deterministic gates: a write-time hook rejects any claim that the source is wrong unless it quotes the source verbatim, and a validator re-runs code examples, which must reproduce their recorded output. I run it every week: I verify what it produces, study from it and keep improving the pipeline. Its companion Rust tool, also built with ensamble, pairs a multi-threaded terminal UI built on message passing with watchdog-supervised process pipelines and size-capped, fail-closed input parsing.
- **Technical writing** — I write long-form posts on my **[blog](https://zapf.dev/blog/)** and maintain a **[technical atlas](https://zapf.dev/atlas/)**: a knowledge graph of security concepts as atomic, interlinked nodes, navigable as a D3 force-directed graph.

## Experience

### Programming Instructor — [Silicon Misiones](https://siliconmisiones.gob.ar/)
*March 2023 – May 2025* · Remote · Cohorts of ~50 students with prior programming experience

Designed and delivered a 24-class hands-on curriculum across three progressive modules, taught live through interactive Google Colab notebooks where theory and exercises lived inline — authored with explicit pedagogical scaffolding (advance organizers, worked examples, retrieval prompts, error taxonomies).

- **Python foundations:** types and control flow, pattern matching, OOP and design patterns, error handling, modules, and file I/O — applied to ETL exercises on real-world datasets.
- **Intermediate / advanced Python:** generators and lazy evaluation, comprehensions, closures and decorators (timer, debug, memoize), regex-driven validation and extraction, ETL pipelines built around `@dataclass` and `match/case`.
- **Data Science & AI:** NumPy vectorization, REST API integration with caching, Pandas data wrangling, data visualization with Seaborn/matplotlib, SQL and SQLAlchemy (Core/ORM), applied transfer learning via Hugging Face pipelines, and a closing module on exploratory data analysis (EDA).

## Education

- **[B.S. in Cyberdefense](https://undef.edu.ar/fadena/carreras-de-grado/licciberdefensa/)** — [UNDEF](https://undef.edu.ar/) · *2026 – 2029, in progress*
- **Online courses:** [CS50](https://www.edx.org/cs50) (Harvard), [The Missing Semester](https://missing.csail.mit.edu/) (MIT), [Python Programming MOOC](https://programming-22.mooc.fi/) (Helsinki)

## Technical Skills

| Category | Technologies |
|---|---|
| Languages &amp; systems | Go (Golang), Rust, Python, TypeScript, SQL, Bash, Linux (systemd, process groups &amp; signals, file locking, crash-atomic &amp; TOCTOU-safe file I/O), concurrent terminal UIs (ratatui) |
| AI &amp; agent systems | multi-agent orchestration, agentic SDLC (spec-driven, human-gated AI coding &amp; QA agents), AI coding agent guardrails (credential-path deny lists, secret-scan hooks, read-only sandboxed reviewers), LLM output validation, cross-model adversarial review, LLM application development, agentic pipelines, RAG, MCP server development, prompt &amp; context engineering, NLP (Transformers) |
| Application security (AppSec) | threat modeling (STRIDE, failure-mode analysis), security design review, secure SDLC (SSDLC), input validation &amp; defenses against path traversal, XSS and SSRF, web hardening (CSP, security headers), hardened TLS clients (rustls, Go net/http), secrets management (systemd-creds, OS keyring, leak tests), privacy engineering (PII &amp; log redaction), cybersecurity frameworks (fundamentals: MITRE ATT&amp;CK, NIST CSF, ISO 27001) |
| DevSecOps &amp; supply chain | CI/CD security gates on GitHub Actions (SHA-pinned actions, least-privilege tokens), SCA (govulncheck, cargo-deny, pnpm audit) with reachability-based vulnerability triage, static analysis &amp; custom SAST rules (staticcheck, clippy, ShellCheck, banned APIs), secret scanning (CI and agent-edit hooks), policy-as-code CI checks (dependency allowlists, systemd sandbox baseline), software supply chain security (FIDO2/SSHSIG artifact signing, pinned toolchains &amp; dependencies, Dependabot), Linux hardening &amp; least privilege (systemd sandboxing, nftables, egress filtering, automated patching), zero-trust access (Tailscale SSH) |
| Engineering practices | test-driven development (TDD), mutation testing (agent-run QA audits), hexagonal architecture (ports &amp; adapters), architecture fitness functions (Go import-graph rules), deterministic tests (injected clock &amp; randomness), golden-file testing, negative security tests (known-bad fixtures the verifiers must reject), configuration as code, CI-tested (systemd units, cloud-init, CI workflows, runbooks), accessibility testing (WCAG 2.2, axe) |
| Backend &amp; web | Go (event-driven services, transactional outbox, idempotent at-least-once delivery, cgo-free SQLite with additive migrations), Python (Django, FastAPI, async, Pydantic), PostgreSQL (multi-tenant RLS, SQLAlchemy), Next.js, REST APIs |
| Data analytics | exploratory data analysis (EDA), data wrangling &amp; ETL (Pandas, NumPy), analytical SQL, data visualization (Matplotlib, Seaborn, Power BI), applied ML (Hugging Face pipelines, scikit-learn), Jupyter &amp; Colab notebooks |
| Spoken languages | Spanish (native), English (B2), Portuguese (basic) |

---

<div align="center">

[![Download CV (PDF)](https://img.shields.io/badge/Download_CV-PDF-303446?style=for-the-badge&logo=adobeacrobatreader&logoColor=ef9f76)](https://zapf.dev/Matias_Zapf_Resume.pdf)

</div>
