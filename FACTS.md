# FACTS.md — single source of truth

Every number on `index.html`, `resume.pdf` and `resume-web.pdf` must trace to a line
here. Every line here must trace to an artifact — a repo file, a release manifest, a
live site, a photographed document — not to memory, not to a prior conversation, and
not to a resume claim, which is exactly what's under audit.

Format: `key: value  # source`. `UNVERIFIED` means no artifact was found; it is a
question for Vibhor, not a placeholder to fill from context.

Last verified: 2026-08-27, against live repos and sites at that date.

---

## Identity

    name: Vibhor Pandey
    location: Dehradun, IN (also Ghaziabad)                    # self-attested
    education: B.Tech CSE (AI/ML), UPES, class of 2029          # self-attested; resolves an
                                                                 # internal contradiction in
                                                                 # index.html v1, which said
                                                                 # "second year" AND "class of
                                                                 # 2028" simultaneously — both
                                                                 # can't be true in Aug 2026 for
                                                                 # a 4-year degree starting 2025
    year_of_study: second year                                  # self-attested
    cfa_level_1: candidate                                      # self-attested. No public
                                                                 # CFA Institute candidate
                                                                 # lookup exists — this is not
                                                                 # independently verifiable by
                                                                 # me. Flagging, not blocking.
    email: vibhorpandey09@gmail.com                             # user-provided, in use on live site
    github: github.com/vibhorxpandey                            # live, 20 public repos as of this date
    linkedin: linkedin.com/in/vibhorpandeyx                     # user-provided
    x: x.com/vibhorxpandey                                      # user-provided

## Aurelius IDE

    aurelius.repo: github.com/vibhorxpandey/Aurelius-IDE
    aurelius.description: "A language server that treats research papers like source
      code. Write LaTeX, and it checks your document live — inline diagnostics for
      undefined citations, references that don't exist in any scholarly index,
      retracted works, mismatched authors, and uncited empirical claims."   # repo description field, GitHub API
    aurelius.tests: 207                                          # release-manifest.json @ main, "tests": 207
    aurelius.version: 0.4.0                                      # release-manifest.json @ main
    aurelius.invariants: 8                                       # ARCHITECTURE.md §9, eight numbered items
    aurelius.diagnostics: 11                                     # release-manifest.json, diagnosticCodes[]: AUR001–AUR011
    aurelius.indexes: OpenAlex, Crossref, arXiv, Semantic Scholar # release-manifest.json, indexes[]
    aurelius.pypi_published: false                                # pypi.org/pypi/aurelius-ide/json -> 404, re-verified 2026-08-27
    aurelius.pypi_name_collision: true                            # pypi.org/project/aurelius belongs to
                                                                   # "Aurelius Technologies" <eng@aurelius.com>,
                                                                   # github.com/Aurelius-OS/aurelius, v0.0.1,
                                                                   # uploaded 2026-02-18 — a different company.
                                                                   # `pip install aurelius` installs THEIR package.
    aurelius.license: MIT                                         # GitHub API license field
    aurelius.compiler: real pdflatex / Tectonic subprocess         # verified visually, Fig. 2 (compiled-paper
                                                                    # screenshot): console shows raw LaTeX
                                                                    # toolchain transcript, not a summary
    aurelius.demo_paper_title: "Hybrid Retrieval for Indian Equity Filings"  # verified visually, Fig. 1/2,
                                                                              # this is the bundled DEMO
                                                                              # workspace, not a real paper
    aurelius.pilot.flagged_pct: 23                               # user-stated, "the data exists" — NOT sourced
                                                                  # to a public artifact. Re-confirm before this
                                                                  # ships to the resume (asked in Phase 1).
    aurelius.pilot.trials: 60                                    # same as above — user-stated, unverified externally

## Aurelius (MCP server) — a real, separate, currently-active sibling to Aurelius IDE

    aurelius_mcp.repo: github.com/vibhorxpandey/Aurelius            # NOT the same repo as Aurelius-IDE
    aurelius_mcp.description: "A fact-checked research MCP server — screen a topic,
      draft it, and verify every citation and claim against live web sources. Works
      in Claude, Gemini CLI, Cursor, and any MCP app."               # repo description, GitHub API
    aurelius_mcp.pushed_at: 2026-08-10                                # GitHub API, actively maintained
    aurelius_mcp.pypi_name: aurelius-mcp
    aurelius_mcp.pypi_published: true                                 # pypi.org/pypi/aurelius-mcp/json -> 200
    aurelius_mcp.pypi_author: "Vibhor Pandey <vibhorpandey09@gmail.com>"  # matches, genuinely his package —
                                                                            # unlike aurelius-ide, no collision
    aurelius_mcp.pypi_releases: 8                                     # v0.1.0 through v0.6.1, latest
                                                                       # 2026-07-25
    aurelius_mcp.pypi_latest_version: 0.6.1
    aurelius_mcp.relationship_to_aurelius_ide: "Sibling, not predecessor. The MCP
      server's own README explicitly describes Aurelius-IDE as '[the] language server
      that runs these same retraction-aware checks inline in your editor.' Both are
      live, both maintained. The IDE is not a rewrite that replaced the MCP server."
    aurelius_mcp.retraction_aware: true                               # README + live worked example: verified
                                                                       # against the retracted Wakefield
                                                                       # MMR-autism paper via OpenAlex
    aurelius_mcp.verify_stat: true                                    # `verify_stat(claim, …)` tool,
                                                                       # verifies a statistic against
                                                                       # World Bank data — README tool table
    aurelius_mcp.dependencies: "mcp>=1.2.0, httpx>=0.27"              # pyproject.toml, verbatim.
      # NO crewai. NO langgraph. NO autogen. Nothing else. The multi-agent
      # orchestration is custom-built on top of these two, not built on CrewAI.
    aurelius_mcp.agent_architecture: "20 named agent files across four groups —
      execution (4), hypothesis (4), publication (6), verification (3), plus a
      standalone memory_agent — orchestrated via `autonomous_research_graph`, a
      multi-stage agent DAG (literature mining -> hypothesis swarm -> feasibility
      screening -> ... -> proof-of-rigor), audit-trailed and checkpointed."  # repo
      # file tree + README line 249-254. This is REAL and is actually more
      # substantial than the resume's claim — but it is ~20 agents in 4 GROUPS,
      # not "four agents." No agent anywhere is named "Editor" or described as
      # "confidence-gated." Closest real agents: citation_verifier_agent.py,
      # adversarial_reviewer_agent.py, methodology_auditor_agent.py — none of
      # these three is called "Editor" in any file, README, or ARCHITECTURE.md.
    aurelius_mcp.pilot_23pct_60trials: UNVERIFIED
    aurelius_mcp.pilot_note: "Checked both Aurelius repos' README.md and
      ARCHITECTURE.md for '23%', '60-trial', 'pilot', 'confidence-gated' — zero
      matches anywhere. This is the same 23%/60-trial figure already flagged
      elsewhere in this file as user-stated, not artifact-sourced. Still true here."

## SMRITI / Hello Doctor

    smriti.repo: github.com/vibhorxpandey/Smriti-AI
    smriti.description: "Consent-gated clinical memory agent. Verified patient history
      from fragmented hospital records, every claim cited, consent enforced before
      retrieval scores anything."                                # repo description, GitHub API
    smriti.recall_at_1: 0.946                                    # README.md eval table, n=37
    smriti.mrr: 0.968                                             # README.md eval table, n=37
    smriti.ndcg_at_10: 0.961                                     # README.md eval table, n=37 — NOT currently
                                                                  # used anywhere on the site or old resume
    smriti.conflict_recall: 1.000                                # README.md eval table, n=5
    smriti.abstention_on_absent_evidence: 1.000                  # README.md eval table, n=1
    smriti.consent_leakage: 0                                    # README.md eval table: 0 out of 0 target,
                                                                  # "10 probes / 10 attack classes"
    smriti.adversarial_suite_note: "README also separately states an 18-probe
      adversarial suite green on every commit (line 391), distinct from the 10-probe/
      10-attack-class table entry. Both are real per the README; cite the 10-probe
      figure since it's the one paired with the 0 leakage result in the eval table."
    smriti.event: HiDevs x AI House, national finale             # user-stated in original portfolio interview,
                                                                  # not independently re-verified this pass —
                                                                  # low risk, external hackathon naming

## EchoMind

    echomind.repo: github.com/vibhorxpandey/Echomind
    echomind.description: "Institutional-memory AI agent for college clubs... Google
      Agent Labs Hackathon 2026, Problem Statement 2."           # README.md, line 4
    echomind.stack: Google ADK + Gemini, Qdrant hybrid retrieval, cross-encoder rerank  # README.md
    echomind.stack_note: "CORRECTED 2026-08-27: index.html never actually said
      'pgvector' for EchoMind — that was my own error in an earlier pass, stated to
      Vibhor and written into this file before being re-checked. The EchoMind row
      simply didn't name a vector store at all. Fixed by adding 'Qdrant' (matching
      the repo) to both the 03 Evidence row and the DOCS corpus entry, committed and
      pushed. No pgvector reference to EchoMind ever existed to correct."
    echomind.team: Vibhor Pandey (Founder, Agent & Retrieval), Bhavya Dubey (Frontend),
      Yuvraj Arora (Backend), Rohit Singh Rajawat (Data & Evaluation)  # README.md Team & roles table
    echomind.award: "Best use case of Lyzr", Google Agent Labs Hackathon 2026, as VeilTeam
      # SOURCED TO: a photograph of the physical/printed award card (not a repo
      # artifact). Card lists Vibhor Pandey, Rohit Singh Rajawat, Bhavya Dubey —
      # THREE names, not the four founders listed in the Echomind repo README.
      # The README itself does not mention "award" or "winner" anywhere. The claim
      # is very likely true (a printed award card is strong evidence) but it does
      # not meet this file's own bar of "sourced to an artifact" in the repo sense.
    echomind.award_credit: "Vibhor Pandey, Bhavya Dubey, Yuvraj Arora, Rohit Singh
      Rajawat — all four, per Vibhor's explicit decision 2026-08-27. The photographed
      card names only three; the repo README names four. Credit follows the repo,
      not the card."
    echomind.award_announcement_link: UNVERIFIED
    echomind.award_announcement_note: "Vibhor's decision message left this blank —
      either a link exists and needs to be supplied, or the claim ships without a
      link and is described without the word 'award' per his own fallback option.
      Ask before Phase 2."

## redrob-ranker

    redrob.repo: github.com/vibhorxpandey/redrob-ranker
    redrob.tests: "76/76 passing"                                 # README.md, three separate mentions incl.
                                                                   # exact test command `python -m pytest -q`
    redrob.note: "No LLM is called at [some threshold] — hybrid, not model-dependent."  # README.md

## LendLens (IDBI Bank hackathon)

    lendlens.repo: github.com/vibhorxpandey/IDBI
    lendlens.live_prototype: https://lendlens-idbi-track02.vercel.app/  # README.md, confirmed live in
                                                                          # Vercel project list, "Ready"
    lendlens.description: "Consent-first pre-approved offer engine"     # README.md
    lendlens.stack: XGBoost (default-risk engine), T-learner uplift model,
      Fairlearn 80%-rule fairness gate, hybrid SHAP + heuristic reason codes  # README.md,
                                                                               # "Fairlearn" confirmed verbatim
    lendlens.eval_population: 5,001 synthetic customers            # README.md
    lendlens.uplift_qini: 0.087                                    # README.md eval table
    lendlens.uplift_top_decile: "+26.0%"                           # README.md eval table
    lendlens.note: "Qini 0.087 and +26.0% top-decile uplift are real, sourced, and
      currently used NOWHERE — not on index.html (which just says 'SHAP + fairlearn'
      as a tag with no number), not on the old resume. Strongest unused LendLens fact
      found this pass."
    lendlens.eval_population_label_rule: "Always say 'synthetic customers,' never
      just 'customers.' Vibhor's explicit instruction 2026-08-27 — the 5,001-record
      eval set is synthetic and every mention of it must say so, every time."

## QLLM survey

    qllm.status: UNVERIFIED
    qllm.note: "No public artifact found. Checked: GitHub repo search under
      vibhorxpandey (0 results), arXiv API search (no match — the arXiv hits that DO
      exist for 'QLLM' are a well-known, unrelated ICLR 2024 paper by different
      authors), general web search. This may be published somewhere not indexed by
      these searches (a student journal, a preprint server, a conference proceedings
      page, or simply not yet public) — absence of a hit is not evidence it's false,
      only that I can't source it. ASK: a link, a DOI, a PDF, or a repo."

## FinNLP benchmark

    finnlp.status: in progress                                    # self-attested; a project that's
                                                                    # explicitly not-yet-complete has no
                                                                    # artifact to check by definition
    finnlp.target: FinNLP @ EMNLP / ACL                            # self-attested
    finnlp.scope: cross-table numerical QA over Indian annual reports — KPIT, Syngene, CAMS  # self-attested

## IMGNet

    imgnet.status: in progress, no published result                # self-attested
    imgnet.method: "face verification replacing cosine similarity with localized
      spatial sign-agreement patterns"                             # self-attested
    imgnet.note: "No benchmark, no number. Per Phase 1 of the resume prompt: either
      Vibhor supplies a metric + benchmark now, or this stays a no-number line under
      Building/Projects, not Evidence."

## Veil Research

    veilresearch.site: https://veilresearch.com                    # DNS resolves, 216.198.79.1, live 200
    veilresearch.early_access_users: "2,400+"                      # scraped verbatim from the live homepage
                                                                    # HTML, 2026-08-27
    veilresearch.modes: research, biology, flywheel, write, mathematics   # user-stated in original
                                                                            # portfolio interview
    veilresearch.byok: true                                        # user-stated, not independently
                                                                    # re-checked this pass
    veilresearch.fitt: UNVERIFIED
    veilresearch.fitt_note: "index.html claims 'FITT incubation' for Veil Research.
      Checked veilresearch.com homepage and /about page (both 200, both fetched and
      searched) — no mention of FITT or 'incubat' anywhere in either page's HTML.
      /team and /press return 404. This may be true and simply not published on the
      site (incubation status often isn't marketing copy) — but I cannot source it
      from the product artifact itself. ASK: an acceptance email, a FITT program
      page, or a press mention to cite."

## Veil Finance

    veilfinance.domain: veilfinance.ink
    veilfinance.dns_status: does not resolve                       # re-verified 2026-08-27,
                                                                    # getaddrinfo failed, same as prior check
    veilfinance.note: "Unlinked on index.html per Vibhor's prior instruction. Same
      applies to the resume — do not print a URL that 404s."

## AI Founders Lab

    foundlab.program: "AI Founders Lab", Runway Incubator UPES, supported by MeitY Startup Hub
      # confirmed real via public web search: upes.ac.in/research/start-ups and
      # related coverage (ciol.com, cxotoday.com)
    foundlab.duration: "8 to 10 week blended incubation"           # public UPES Runway program pages
    foundlab.selected: true                                        # self-attested
    foundlab.grant_DISCREPANCY: "index.html states 'Pre-seed track up to ₹5,00,000.'
      Public UPES Runway pages describe the general program grant as a 'Runway
      Ignition Grant of ₹1 lakh, with potential for additional equity-based funding' —
      i.e. ₹1,00,000, not ₹5,00,000. These may be describing different things: AI
      Founders Lab could be a specific higher-ceiling pre-seed track distinct from
      the general Ignition Grant everyone else in Runway gets. I am not overwriting
      ₹5,00,000 with ₹1,00,000 on a guess — ASK Vibhor which figure is right, and
      ideally get the acceptance email or program page that states AI Founders Lab's
      specific number."

## Corpus / retriever

    corpus.doc_count: 19                                           # index.html, DOCS.length, live-verified
                                                                    # via Playwright on the deployed site,
                                                                    # matches the load-sequence counter

---

## Open questions this file surfaces — needs Vibhor, not inference

1. Aurelius pilot (23% / 60 trials) — re-confirm the data exists; it has no artifact behind it, only your word.
2. EchoMind's Lyzr award — the photographed card lists 3 names, the repo README lists 4 team members. Is there a results page or email to cite instead of / alongside the photo?
3. QLLM survey — completely unfound. Link, DOI, PDF, or repo?
4. Veil Research's FITT incubation — not on the live site anywhere I can find. Source?
5. AI Founders Lab's ₹5,00,000 figure — public program pages say ₹1 lakh general grant. Same track, different track, or has it changed?
6. IMGNet — a metric + benchmark, or it ships without a number.
7. CFA L1 candidacy — no public verification exists by nature; flagging only so it's explicitly self-attested rather than silently assumed.

Two things found and fixed as a side effect, not blocking:
- EchoMind's vector store is Qdrant per its own README, not pgvector as index.html currently states.
- `github.com/vibhorxpandey/veil` has an unresolved git merge-conflict marker committed into `README.md` on `main` (boilerplate Next.js scaffold either side of the conflict). Not resume-relevant, flagging because it's a live repo under your name.
