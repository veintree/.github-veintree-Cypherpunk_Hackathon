# Démo guidée
cat docs/DEMO.md

# Peupler des preuves de démo
node scripts/seed-devnet.mjs "user-demo-1" "user-demo-2" "user-demo-3"

# Lancer l'app et vérifier
cd app && npm ci && npm run dev
# http://localhost:3000  → Connect Phantom (devnet) → List Proofs
