ScholarPath

Decentralized scholarship and grant management platform built on the Stellar network using Soroban smart contracts.

ScholarPath enables transparent, milestone-based funding so donors can track impact and students can receive grants without intermediaries.

💡 Problem

Traditional scholarship systems often suffer from:

High administrative overhead reducing funds delivered

Limited transparency for donors and beneficiaries

Slow cross-border payments and verification delays

Lack of tamper-proof records for fund distribution

🚀 Solution

ScholarPath solves these challenges by leveraging blockchain technology and smart contracts:

Milestone-Based Escrow – Funds are released only when academic milestones are verified

Direct Payments – Grants can pay tuition or transfer directly to student wallets

Transparent Ledger – Every transaction is recorded immutably

Low Transaction Costs – Built on the efficient infrastructure of the Stellar network

Secure Identity – Wallet authentication via SEP-10

The protocol operates on the blockchain powered by the blockchain organization Stellar Development Foundation.

🛠 Tech Stack
Frontend

Next.js (App Router)

Tailwind CSS

Soroban Client SDK

TypeScript

Backend

Node.js / Express (or NestJS)

PostgreSQL

JWT Authentication

Event Logging & API Services

Smart Contracts

Rust

Soroban SDK

Stellar network

📂 Repository Structure
.
├── contracts/                 # Soroban smart contracts
│   ├── scholarship_vault/      # Escrow and milestone logic
│   └── governance/              # Voting and approval logic
│
├── frontend/                    # Next.js application
│   ├── components/              # Reusable UI components
│   ├── lib/                      # Blockchain integration
│   └── app/                      # Routes and pages
│
├── backend/                     # API and services
│   ├── src/
│   ├── controllers/
│   ├── services/
│   └── routes/
│
└── scripts/                     # Deployment and automation
🚦 Getting Started
1. Clone the Repository
git clone https://github.com/your-org/scholarpath.git
cd scholarpath
2. Install Dependencies

Frontend:

cd frontend
npm install

Backend:

cd backend
npm install
3. Run Development Servers

Frontend:

npm run dev

Backend:

npm run dev
📝 Environment Variables

Frontend (.env.local):

NEXT_PUBLIC_SOROBAN_RPC_URL=https://soroban-testnet.stellar.org
NEXT_PUBLIC_NETWORK=testnet

Backend (.env):

DATABASE_URL=postgres://...
JWT_SECRET=...
STELLAR_RPC_URL=https://soroban-testnet.stellar.org
🔐 Wallet Authentication

ScholarPath uses SEP-10 for secure wallet authentication, enabling:

Message signing

Wallet ownership verification

Personalized dashboards

📜 Smart Contract Commands

Build:

stellar contract build

Test:

cargo test

Deploy:

stellar contract deploy \
  --wasm target/wasm32-unknown-unknown/release/contract.wasm

🤝Contributing

Contributions are welcome!

Fork the repository

Create a feature branch

Submit a pull request

Please follow project coding standards and include tests where applicable.

📄 License

MIT
