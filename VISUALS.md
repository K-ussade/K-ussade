# Public Account Visuals

## Purpose

These Mermaid diagrams make the K-ussade public account architecture visible without creating placeholder products, fake models, fake datasets, live deployment claims, or unreviewed Hugging Face releases.

## Account Surface Map

```mermaid
flowchart LR
  subgraph person["Person And Public Account Surface"]
    alexandra["Alexandra Caussade<br/>person, legal name, founder identity"]:::authority
    profile["K-ussade<br/>public technical brand/account surface"]:::public
  end

  subgraph foundation["218 Network Foundation"]
    network["218.network<br/>Foundation public surface"]:::foundation
    civicDocs["civic AI docs<br/>public-trust technical systems"]:::foundation
  end

  subgraph company["YOSO-YAi LLC"]
    yoso["yoso-yai.com<br/>company surface"]:::company
    yosor["yosor.app<br/>YOSOR product surface"]:::product
  end

  subgraph release["Release Readiness Surfaces"]
    github["GitHub public repos<br/>published or scaffolded proof surfaces"]:::public
    hf["Hugging Face<br/>planned until reviewed release exists"]:::release
  end

  alexandra --> profile
  alexandra --> network
  alexandra --> yoso
  profile --> github
  github --> civicDocs
  github -. cards, indexes, and safety notes .-> hf
  network -. independent from .-> yoso
  yosor --> yoso

  classDef company fill:#e8f1ff,stroke:#2457a6,color:#0f2345;
  classDef product fill:#e6f7f1,stroke:#1f7a55,color:#0f3d2d;
  classDef foundation fill:#fff3d7,stroke:#9a6b00,color:#463100;
  classDef public fill:#edf7ed,stroke:#3a7d3a,color:#1f3d1f;
  classDef release fill:#f4edff,stroke:#6941c6,color:#2f1b63;
  classDef authority fill:#eaf7ff,stroke:#027a9d,stroke-width:2px,color:#083344;
```

## Recommended Pin Map

```mermaid
flowchart TB
  profile["K-ussade profile<br/>public technical surface"]:::authority

  subgraph pins["Recommended Six Pins"]
    graphKit["foundation-graph-kit<br/>Mermaid graph standards"]:::public
    roadmap["foundation-public-roadmap<br/>status and release-readiness ledger"]:::public
    safety["civic-ai-safety-notes<br/>safety, limits, claim review"]:::foundation
    modelCards["foundation-model-cards<br/>future model-card readiness"]:::release
    datasetCards["foundation-dataset-cards<br/>future dataset-card readiness"]:::release
    aiOps["autonomous-ai-ops-kit<br/>supervised AI ops governance"]:::workflow
  end

  subgraph secondary["Secondary Proof Surfaces"]
    research["research-agent-workflows<br/>research workflow discipline"]:::workflow
    trading["trading-agent-governance<br/>governance only, no advice"]:::risk
    portfolio["foundation-portfolio-proof<br/>future review-required proof index"]:::public
    templates["foundation-doc-templates<br/>documentation templates"]:::public
  end

  subgraph plannedHf["Planned Hugging Face Artifacts"]
    models["models<br/>planned until reviewed release"]:::release
    datasets["datasets<br/>planned until reviewed release"]:::release
    spaces["Spaces<br/>planned until reviewed release"]:::release
  end

  profile --> graphKit
  profile --> roadmap
  profile --> safety
  profile --> modelCards
  profile --> datasetCards
  profile --> aiOps
  profile -. visible but not first-six pins .-> research
  profile -. visible but not first-six pins .-> trading
  profile -. visible but not first-six pins .-> portfolio
  profile -. visible but not first-six pins .-> templates
  modelCards -. readiness docs only .-> models
  datasetCards -. readiness docs only .-> datasets
  roadmap -. status only .-> spaces

  classDef public fill:#edf7ed,stroke:#3a7d3a,color:#1f3d1f;
  classDef foundation fill:#fff3d7,stroke:#9a6b00,color:#463100;
  classDef release fill:#f4edff,stroke:#6941c6,color:#2f1b63;
  classDef workflow fill:#eaf7ff,stroke:#027a9d,color:#083344;
  classDef risk fill:#fff1f2,stroke:#be123c,stroke-width:2px,color:#5f0715;
  classDef authority fill:#eaf7ff,stroke:#027a9d,stroke-width:2px,color:#083344;
```

## Public Trust Boundary

```mermaid
flowchart LR
  subgraph allowed["Allowed Public Material"]
    publicDocs["Public Foundation docs"]:::public
    governanceDocs["Public governance docs"]:::public
    roadmapDocs["Roadmap and status ledgers"]:::public
    civicRef["Public civic reference material"]:::public
    synthetic["Synthetic examples<br/>clearly labeled"]:::public
    approvedCode["Open-source code<br/>approved for public release"]:::public
    cards["Model and dataset cards<br/>with limitations"]:::release
    diagrams["Mermaid diagrams<br/>no private topology"]:::public
  end

  subgraph forbidden["Forbidden Public Material"]
    donor["Donor private data"]:::sealed
    student["Student data"]:::sealed
    school["School private data"]:::sealed
    volunteer["Volunteer private data"]:::sealed
    ops["Private Foundation operations"]:::private
    companyIP["Sealed YOSO-YAi LLC IP"]:::sealed
    customer["Customer data"]:::sealed
    weights["Unreleased model weights"]:::sealed
    corpora["Private training corpora"]:::sealed
    secrets["Secrets, tokens, API keys"]:::sealed
    infra["Precise sensitive infrastructure locations"]:::sealed
    neurona["Security-sensitive NEURONA operational details"]:::sealed
    trading["Trading strategies, signals,<br/>returns, balances, account data,<br/>performance claims"]:::sealed
    autonomous["Live autonomous agents,<br/>runnable orchestration,<br/>private prompts or outputs"]:::sealed
  end

  subgraph gates["Review Gates"]
    boundary["Boundary review"]:::authority
    safety["Safety and limitations review"]:::risk
    governance["Human governance review"]:::authority
  end

  subgraph surfaces["Public Surfaces"]
    github["GitHub public repos"]:::public
    hf["Hugging Face releases"]:::release
    web["218.network"]:::foundation
  end

  publicDocs --> boundary
  governanceDocs --> boundary
  roadmapDocs --> boundary
  civicRef --> boundary
  synthetic --> boundary
  approvedCode --> boundary
  cards --> safety
  diagrams --> boundary
  boundary --> governance
  safety --> governance
  governance --> github
  governance --> hf
  governance --> web

  donor -. blocked .-> boundary
  student -. blocked .-> boundary
  school -. blocked .-> boundary
  volunteer -. blocked .-> boundary
  ops -. blocked .-> boundary
  companyIP -. blocked .-> boundary
  customer -. blocked .-> boundary
  weights -. blocked .-> boundary
  corpora -. blocked .-> boundary
  secrets -. blocked .-> boundary
  infra -. blocked .-> boundary
  neurona -. blocked .-> boundary
  trading -. blocked .-> boundary
  autonomous -. blocked .-> boundary

  classDef foundation fill:#fff3d7,stroke:#9a6b00,color:#463100;
  classDef public fill:#edf7ed,stroke:#3a7d3a,color:#1f3d1f;
  classDef private fill:#f0f2f5,stroke:#5d6673,color:#20242a;
  classDef sealed fill:#fdecec,stroke:#b42318,stroke-width:2px,color:#5f1711;
  classDef release fill:#f4edff,stroke:#6941c6,color:#2f1b63;
  classDef authority fill:#eaf7ff,stroke:#027a9d,stroke-width:2px,color:#083344;
  classDef risk fill:#fff1f2,stroke:#be123c,stroke-width:2px,color:#5f0715;
```

## Interpretation Notes

- Alexandra Caussade is the person and founder identity; K-ussade is the public technical account surface.
- The six recommended pins show public documentation infrastructure, status discipline, civic AI safety, Hugging Face release readiness, data governance, and supervised AI operations governance.
- Research-agent and trading-agent governance repos remain visible proof surfaces but are secondary to reduce first-view claim risk.
- Planned Hugging Face models, datasets, and Spaces remain planned until reviewed public artifacts exist.

## Boundary Notes

- The 218 Network Foundation is not YOSO-YAi LLC marketing, CSR framing, or product proof.
- Public GitHub repositories are proof surfaces for documentation and governance discipline, not evidence of live deployments or active services.
- Trading-agent governance documentation is not financial advice, not investment advice, not a trading bot, not a trading system, and not a performance claim.
- Private Foundation operations, sealed YOSO-YAi LLC IP, customer data, donor data, student data, volunteer data, private training corpora, secrets, and security-sensitive NEURONA details stay outside public visuals.

## Follow-Up Actions

- Keep GitHub profile pins aligned with `PINNED_REPOS.md`.
- Add Hugging Face links only after public artifacts, cards, release notes, safety notes, companion links, and review status exist.
- Re-audit the first-view pins before any portfolio, Upwork, press, or partner-facing reuse.
