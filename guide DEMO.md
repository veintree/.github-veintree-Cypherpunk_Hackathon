# Create DEMO guide and a devnet seeding script
import os, pathlib, textwrap, json, zipfile

root = "/mnt/data/veintree-cypherpunk-hackathon"

def write(path, content):
    p = pathlib.Path(path); p.parent.mkdir(parents=True, exist_ok=True); p.write_text(content.strip()+"\n", encoding="utf-8")

# 1) DEMO.md (bilingual step-by-step)
demo_md = textwrap.dedent("""\
# 🎬 Veintree — Demo Guide (FR/EN)

## FR — Démo pas-à-pas (devnet)

# 1) **Préparer le wallet**  
```bash
./scripts/anchor-keys.sh
solana config set --url https://api.devnet.solana.com
solana airdrop 2

# 2)**Déployer le programme**
./scripts/anchor-deploy-devnet.sh
# Si l'ID change, mettez-le dans: sdk/ts/src/veintree-sdk.ts (PROGRAM_ID)

# 3)**Installer et builder le SDK**
cd sdk/ts && npm ci && npm run build

# 4) Lancer l'app
cd ../../app && npm ci && npm run dev
# Ouvrez http://localhost:3000
# Connectez Phantom (réseau: devnet)
# - Register Proof: écrit un hash SHA3-256 dans le PDA utilisateur
# - Verify Proof: vérifie le hash on-chain
# - Register + Index: ajoute la preuve dans l'index utilisateur
# - List Proofs: liste les hashes de l'index
# - Server Verify: vérifie une signature côté serveur (API Next.js)

#5) (Optionnel) Peupler des données de démo
# Revenir à la racine du repo
cd ..
node scripts/seed-devnet.mjs "user-demo-1" "user-demo-2" "user-demo-3"
