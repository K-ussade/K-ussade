# Public Account Visuals

## Purpose

These Mermaid diagrams make the public account architecture visible without creating placeholder products, fake models, or unreviewed datasets. GitHub renders these diagrams directly in Markdown.

## Account Surface Map

```mermaid
flowchart LR
  subgraph identity["Public Technical Identity"]
    alexandra["Alexandra Caussade<br/>Founder: 218 Network Foundation<br/>Co-Founder: YOSO-YAi LLC"]:::authority
    profile["GitHub profile<br/>K-ussade"]:::public
  end

  subgraph foundationDomain["Foundation Public Surface"]
    network["218.network"]:::foundation
  end

  subgraph boundaryRefs["Boundary References Only"]
    yoso["yoso-yai.com<br/>company surface"]:::company
    yosor["yosor.app<br/>YOSOR product surface"]:::product
  end

  subgraph github["GitHub Public Repository Architecture"]
    publicFace["Foundation public face repos<br/>218-network-web planned<br/>foundation-governance scaffolded<br/>foundation-programs-public planned<br/>foundation-transparency-reports scaffolded"]:::foundation
    aiCompanions["AI companion repos<br/>foundation-model-cards scaffolded<br/>foundation-dataset-cards scaffolded<br/>foundation-spaces planned<br/>civic-ai-safety-notes scaffolded"]:::release
    standards["Templates and standards<br/>foundation-doc-templates<br/>foundation-graph-kit<br/>foundation-public-roadmap"]:::public
    programDocs["Future technical public docs<br/>neurona-public-docs<br/>cleanup-data-public<br/>schools-public-docs"]:::foundation
  end

  subgraph hf["Hugging Face Release Surface"]
    models["Planned models<br/>civic QA, NEURONA, cleanup,<br/>Spanish civic, school resources"]:::release
    datasets["Planned datasets<br/>cleanup, municipio, Foundation docs,<br/>NEURONA samples, school resources"]:::release
    spaces["Planned Spaces<br/>status, cleanup, map,<br/>docs assistant, school resources"]:::release
  end

  alexandra --> profile
  profile --> publicFace
  profile --> aiCompanions
  profile --> standards
  profile --> programDocs
  publicFace --> network
  aiCompanions -. cards and notes .-> models
  aiCompanions -. cards and notes .-> datasets
  aiCompanions -. companion code .-> spaces
  standards --> publicFace
  standards --> aiCompanions
  programDocs -. release context .-> models
  programDocs -. release context .-> datasets
  programDocs -. demo context .-> spaces
  alexandra -. boundary reference .-> yoso
  alexandra -. boundary reference .-> yosor
  yoso -. distinct from Foundation .-> network
  yosor -. product of YOSO-YAi .-> yoso

  classDef company fill:#e8f1ff,stroke:#2457a6,color:#0f2345;
  classDef product fill:#e6f7f1,stroke:#1f7a55,color:#0f3d2d;
  classDef foundation fill:#fff3d7,stroke:#9a6b00,color:#463100;
  classDef public fill:#edf7ed,stroke:#3a7d3a,color:#1f3d1f;
  classDef release fill:#f4edff,stroke:#6941c6,color:#2f1b63;
  classDef authority fill:#eaf7ff,stroke:#027a9d,stroke-width:2px,color:#083344;
```

## Public Trust Boundary

```mermaid
flowchart LR
  subgraph allowed["Allowed Public Material"]
    publicDocs["Public Foundation docs"]:::public
    governanceDocs["Public governance docs"]:::public
    reports["Public transparency reports"]:::public
    programs["Public program descriptions"]:::public
    civicRef["Public civic reference material"]:::public
    synthetic["Synthetic examples<br/>clearly labeled"]:::public
    sanitized["Sanitized public samples<br/>approved only"]:::risk
    approvedCode["Open-source code<br/>approved for public release"]:::public
    cards["Model and dataset cards<br/>with limitations"]:::release
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
  end

  subgraph gate["Review Gate"]
    boundary["Boundary review"]:::authority
    safety["Safety and limitations review"]:::risk
    governance["Foundation governance review"]:::authority
  end

  subgraph surfaces["Public Surfaces"]
    github["GitHub public repos"]:::release
    hf["Hugging Face releases"]:::release
    web["218.network"]:::foundation
  end

  publicDocs --> boundary
  governanceDocs --> boundary
  reports --> boundary
  programs --> boundary
  civicRef --> boundary
  synthetic --> boundary
  sanitized --> safety
  approvedCode --> boundary
  cards --> safety
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

  classDef foundation fill:#fff3d7,stroke:#9a6b00,color:#463100;
  classDef public fill:#edf7ed,stroke:#3a7d3a,color:#1f3d1f;
  classDef private fill:#f0f2f5,stroke:#5d6673,color:#20242a;
  classDef sealed fill:#fdecec,stroke:#b42318,stroke-width:2px,color:#5f1711;
  classDef release fill:#f4edff,stroke:#6941c6,color:#2f1b63;
  classDef authority fill:#eaf7ff,stroke:#027a9d,stroke-width:2px,color:#083344;
  classDef risk fill:#fff1f2,stroke:#be123c,stroke-width:2px,color:#5f0715;
```

## Release Flow Index

| Flow | Source Of Truth |
| --- | --- |
| Model release flow | `repo-blueprint/account-surfaces/graphs/model-release-flow.md` |
| Dataset release flow | `repo-blueprint/account-surfaces/graphs/dataset-release-flow.md` |
| Space demo flow | `repo-blueprint/account-surfaces/graphs/space-demo-flow.md` |
| GitHub to Hugging Face link map | `repo-blueprint/account-surfaces/graphs/github-to-huggingface-link-map.md` |

The public visuals intentionally show planned architecture and review gates. They do not claim that future models, datasets, Spaces, or Foundation program repositories already exist.
