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


import pathlib, textwrap

root = "/mnt/data/veintree-cypherpunk-hackathon"
roadmap_path = pathlib.Path(f"{root}/docs/ROADMAP.md")

content = textwrap.dedent("""\
# 🗺️ Veintree Roadmap – Priorisation des fonctionnalités

## FR – Priorisation (MoSCoW)

| Priorité | Fonctionnalité | Détail | Cible |
|----------|----------------|--------|-------|
| **Must have** (indispensable) | Programme Solana minimal (Rust/Anchor) | Instructions `register_proof` & `verify_proof` avec hash on-chain | Hackathon |
| | SDK TS & Rust | Générer hash, appeler `register_proof` & `verify_proof` | Hackathon |
| | App Next.js (démo bilingue) | UI simple : enregistrer une preuve & vérifier son état | Hackathon |
| | Simulation biométrique | Mock de scan de veines → hash unique | Hackathon |
| | Sécurité minimale | Hashing fort (SHA3/Blake2) + signature Ed25519 native | Hackathon |
| **Should have** (important) | Gestion multi-utilisateurs | PDAs par user, mapping comptes → preuves | Hackathon |
| | Script devnet | Deploy/test auto (airdrop, init) | Hackathon |
| | CI/CD | Build/test/lint auto + déploiement App (Vercel/Cloudflare) | Hackathon |
| **Could have** (optionnel) | Liveness check basique | Challenge/response simulé (timestamp/random) | Hackathon |
| | QR code partage | Vérification cross-device | Post-hackathon |
| | Intégration wallet | Connect wallet (Phantom/Solana CLI) | Post-hackathon |
| **Won’t have (pour l’instant)** | FPGA dongle | Intégration hardware réelle | Post-hackathon |
| | ZK Proofs | zk-SNARK / ZKML pour preuve de biométrie | Post-hackathon |
| | Cas d’usage régulés | EUDI Wallet, santé, clinique | Post-hackathon |

---

## EN – Prioritization (MoSCoW)

| Priority | Feature | Detail | Target |
|----------|---------|--------|--------|
| **Must have** | Minimal Solana program (Rust/Anchor) | `register_proof` & `verify_proof` instructions with on-chain hash | Hackathon |
| | TS & Rust SDK | Hash generation, call `register_proof` & `verify_proof` | Hackathon |
| | Next.js App (bilingual demo) | Simple UI: register a proof & verify status | Hackathon |
| | Biometric simulation | Mock vein scan → unique hash | Hackathon |
| | Basic security | Strong hashing (SHA3/Blake2) + native Ed25519 signatures | Hackathon |
| **Should have** | Multi-user support | PDAs per user, mapping accounts → proofs | Hackathon |
| | Devnet script | Auto deploy/test (airdrop, init) | Hackathon |
| | CI/CD | Auto build/test/lint + App deployment (Vercel/Cloudflare) | Hackathon |
| **Could have** | Basic liveness check | Simulated challenge/response (timestamp/random) | Hackathon |
| | QR code sharing | Cross-device verification | Post-hackathon |
| | Wallet integration | Connect wallet (Phantom/Solana CLI) | Post-hackathon |
| **Won’t have (yet)** | FPGA dongle | Real hardware integration | Post-hackathon |
| | ZK Proofs | zk-SNARK / ZKML for biometric proof | Post-hackathon |
| | Regulated use cases | EUDI Wallet, healthcare, clinical | Post-hackathon |

---

## 🎯 Hackathon MVP Summary
- On-chain program (Rust/Anchor) → write/verify proof  
- SDK → hashing + program calls  
- Next.js bilingual App (FR/EN)  
- Mock biometric → generate hash from “vein scan”  
- Devnet deploy + CI/CD ready  

""")

roadmap_path.write_text(content, encoding="utf-8")
roadmap_path
