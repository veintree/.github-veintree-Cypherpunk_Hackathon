# .github-veintree-Cypherpunk_Hackathon
Repository for the Solana Cypherpunk Hackathon.  
We are preparing the repository from our private source that we opensource.
Stay tuned !
.veintree-cypherpunk-hackathon/
├─ README.md
├─ LICENSE
├─ docs/
│  ├─ ARCHITECTURE.md
│  ├─ STYLE_GUIDE.md
│  └─ ROADMAP.md

├─ programs/                # Solana on-chain (Rust/Anchor)
│  └─ veintree_contract/
│     ├─ Cargo.toml
│     ├─ Anchor.toml
│     ├─ programs/veintree_contract/src/lib.rs
│     └─ tests/

├─ sdk/
│  ├─ rust/
│  │  └─ Cargo.toml
│  └─ ts/
│     ├─ package.json
│     └─ src/index.ts

├─ app/                     # Client (ex: Next.js/TS) 
│  ├─ package.json
│  └─ src/

├─ scripts/
│  ├─ devnet-init.sh
│  └─ lint-all.sh

├─ .github/
│  ├─ ISSUE_TEMPLATE/
│  │  ├─ bug_report.md
│  │  ├─ feature_request.md
│  │  └─ config.yml
│  ├─ PULL_REQUEST_TEMPLATE.md
│  ├─ workflows/
│  │  ├─ ci.yml
│  │  └─ markdown-link-check.yml
│  ├─ CONTRIBUTING.md
│  ├─ CODE_OF_CONDUCT.md
│  └─ SECURITY.md

└─ .editorconfig
