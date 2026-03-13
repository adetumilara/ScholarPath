# ScholarPath

## Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Architecture](#-architecture)
- [Tech Stack](#-tech-stack)
- [Getting Started](#-getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Development](#development)
- [Project Structure](#-project-structure)
- [Smart Contracts](#-smart-contracts)
- [Frontend Application](#-frontend-application)
- [Testing](#-testing)
- [Deployment](#-deployment)
- [Configuration](#-configuration)
- [API Reference](#-api-reference)
- [Contributing](#-contributing)
- [Roadmap](#-roadmap)
- [FAQ](#-faq)
- [License](#-license)
- [Support](#-support)

---

## 💡 Overview

Decentralized scholarship and grant management platform built on the Stellar network using Soroban smart contracts.

ScholarPath enables transparent, milestone-based funding so donors can track impact and students can receive grants without intermediaries.

### Problem

Traditional scholarship systems often suffer from:

- High administrative overhead reducing funds delivered
- Limited transparency for donors and beneficiaries
- Slow cross-border payments and verification delays
- Lack of tamper-proof records for fund distribution

### Solution

ScholarPath solves these challenges by leveraging blockchain technology and smart contracts:

- **Milestone-Based Escrow** – Funds are released only when academic milestones are verified
- **Direct Payments** – Grants can pay tuition or transfer directly to student wallets
- **Transparent Ledger** – Every transaction is recorded immutably
- **Low Transaction Costs** – Built on the efficient infrastructure of the Stellar network
- **Secure Identity** – Wallet authentication via SEP-10

The protocol operates on the blockchain powered by the blockchain organization Stellar Development Foundation.

---

## ✨ Features

### For Students

- **Wallet Connection** - Connect Stellar wallets via SEP-10 for secure authentication
- **Scholarship Discovery** - Browse and apply for available scholarships
- **Profile Management** - Create and manage academic profile with verification
- **Milestone Submission** - Submit proof of academic milestones for verification
- **Fund Tracking** - View received funds and transaction history
- **Direct Payments** - Receive funds directly to personal Stellar wallet

### For Donors

- **Create Scholarships** - Establish scholarships with custom criteria and amounts
- **Milestone Tracking** - Monitor student progress through verified milestones
- **Transparent Transactions** - View all fund movements on the blockchain
- **Impact Analytics** - Track total impact and students supported
- **Fund Management** - Add/withdraw funds from scholarship vaults

### For Administrators

- **Verification System** - Approve or reject milestone submissions
- **Governance Controls** - Manage platform settings and parameters
- **Analytics Dashboard** - View platform-wide statistics and reports
- **User Management** - Manage user roles and permissions

### Platform Features

- **Milestone-Based Escrow** - Funds locked until milestones are verified
- **Direct Wallet Payments** - No intermediaries, peer-to-peer transfers
- **Immutable Records** - All transactions recorded on Stellar blockchain
- **Low Transaction Costs** - Minimal fees compared to traditional systems
- **Cross-Border Support** - Global accessibility without banking barriers
- **Real-time Notifications** - Webhook alerts for important events

---

## 🏗 Architecture

### System Overview

ScholarPath follows a decentralized architecture built on the Stellar blockchain with Soroban smart contracts. The system consists of three main layers:

```
┌─────────────────────────────────────────────────────────────┐
│                      Frontend Layer                          │
│                   (Next.js Application)                     │
└─────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────┐
│                       API Layer                              │
│                   (Node.js Backend)                         │
│    ┌─────────────┐  ┌─────────────┐  ┌─────────────┐      │
│    │  REST API   │  │  Webhooks   │  │   Auth      │      │
│    └─────────────┘  └─────────────┘  └─────────────┘      │
└─────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────┐
│                   Blockchain Layer                           │
│               (Stellar + Soroban)                           │
│    ┌──────────────────┐  ┌──────────────────┐              │
│    │  Scholarship     │  │    Governance    │              │
│    │  Vault Contract  │  │     Contract     │              │
│    └──────────────────┘  └──────────────────┘              │
└─────────────────────────────────────────────────────────────┘
```

### Core Components

#### 1. Smart Contracts (Soroban/Rust)

**Scholarship Vault Contract**

- Manages escrow funds for scholarships
- Handles milestone-based fund releases
- Tracks fund balances and distributions

**Governance Contract**

- Manages voting and approval workflows
- Handles multi-signature requirements
- Records governance decisions on-chain

#### 2. Backend Services (Node.js)

- **API Server** - RESTful endpoints for frontend communication
- **Event Processor** - Monitors blockchain events and updates database
- **Authentication Service** - SEP-10 wallet authentication
- **Notification Service** - Email/push notifications for events

#### 3. Frontend Application (Next.js)

- **Wallet Connection** - SEP-10 authentication integration
- **Dashboard** - Role-based views (student, donor, admin)
- **Transaction Interface** - Blockchain interaction tools
- **Analytics** - Fund tracking and reporting

### Data Flow

1. **User Authentication**
   - User connects wallet → SEP-10 challenge → Signature verification → JWT issued

2. **Creating a Scholarship**
   - Donor creates scholarship → Backend validates → Smart contract deployed → Funds deposited to vault

3. **Milestone Verification**
   - Student submits proof → Verifier approves → Smart contract releases funds → Event emitted

4. **Fund Distribution**
   - Vault contract transfers → Student wallet receives → Transaction recorded on-chain → Backend syncs event

### Security Considerations

- **Wallet Authentication** - SEP-10 ensures wallet ownership without exposing keys
- **Multi-signature** - Large transactions require multiple approvals
- **On-chain Verification** - All milestone completions verified by authorized parties
- **Immutability** - All transactions recorded permanently on Stellar ledger

### Network Configuration

| Network | Soroban RPC                         | Horizon                             | Network Passphrase                             |
| ------- | ----------------------------------- | ----------------------------------- | ---------------------------------------------- |
| Testnet | https://soroban-testnet.stellar.org | https://horizon-testnet.stellar.org | Test SDF Network ; September 2015              |
| Mainnet | https://soroban-mainnet.stellar.org | https://horizon.stellar.org         | Public Global Stellar Network ; September 2014 |

---

## 🛠 Tech Stack

### Frontend

- Next.js (App Router)
- Tailwind CSS
- Soroban Client SDK
- TypeScript

### Backend

- Node.js / Express (or NestJS)
- PostgreSQL
- JWT Authentication
- Event Logging & API Services

### Smart Contracts

- Rust
- Soroban SDK
- Stellar network

---

## 🚦 Getting Started

### Prerequisites

- Node.js 18+
- Rust and Cargo
- Stellar CLI
- PostgreSQL (for backend)
- npm or yarn

### Installation

1. Clone the Repository

```bash
git clone https://github.com/your-org/scholarpath.git
cd scholarpath
```

2. Install Dependencies

**Frontend:**

```bash
cd frontend
npm install
```

**Backend:**

```bash
cd backend
npm install
```

### Development

**Frontend:**

```bash
npm run dev
```

**Backend:**

```bash
npm run dev
```

---

## 📂 Project Structure

```
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
```

---

## 📜 Smart Contracts

### Build

```bash
stellar contract build
```

### Test

```bash
cargo test
```

### Deploy

```bash
stellar contract deploy \
  --wasm target/wasm32-unknown-unknown/release/contract.wasm
```

---

## 💻 Frontend Application

The ScholarPath frontend is built with Next.js using the App Router architecture.

### Key Components

- **Wallet Integration** - Connect Stellar wallets via SEP-10 authentication
- **Scholarship Dashboard** - View and manage scholarship applications
- **Milestone Tracker** - Track and verify academic milestones
- **Transaction History** - View all fund movements on the blockchain
- **Profile Management** - Manage student/donor profiles

### Running the Frontend

```bash
cd frontend
npm run dev
```

The frontend will be available at `http://localhost:3000`

### Building for Production

```bash
npm run build
npm start
```

---

## 🧪 Testing

### Smart Contract Testing

Run Rust tests for Soroban smart contracts:

```bash
cd contracts
cargo test
```

### Frontend Testing

Run unit and integration tests:

```bash
cd frontend
npm test
```

### Test Networks

- **Stellar Testnet** - `https://soroban-testnet.stellar.org`
- **Stellar Futurenet** - For latest Soroban features

---

## 🚀 Deployment

### Smart Contract Deployment

1. Build the contract:

```bash
stellar contract build
```

2. Deploy to testnet:

```bash
stellar contract deploy \
  --wasm target/wasm32-unknown-unknown/release/contract.wasm \
  --network testnet
```

3. Deploy to mainnet:

```bash
stellar contract deploy \
  --wasm target/wasm32-unknown-unknown/release/contract.wasm \
  --network mainnet
```

### Frontend Deployment

#### Vercel (Recommended)

```bash
vercel --prod
```

#### Docker

```bash
docker build -t scholarpath-frontend .
docker run -p 3000:3000 scholarpath-frontend
```

### Backend Deployment

#### Docker

```bash
cd backend
docker build -t scholarpath-backend .
docker run -p 4000:4000 scholarpath-backend
```

#### Manual Deployment

```bash
npm run build
pm2 start dist/index.js
```

---

## ⚙️ Configuration

### Environment Variables

**Frontend (.env.local):**

```
NEXT_PUBLIC_SOROBAN_RPC_URL=https://soroban-testnet.stellar.org
NEXT_PUBLIC_NETWORK=testnet
```

**Backend (.env):**

```
DATABASE_URL=postgres://...
JWT_SECRET=...
STELLAR_RPC_URL=https://soroban-testnet.stellar.org
```

---

## 🔐 Wallet Authentication

ScholarPath uses SEP-10 for secure wallet authentication, enabling:

- Message signing
- Wallet ownership verification
- Personalized dashboards

---

## 📚 API Reference

### Authentication

#### SEP-10 Web Authentication

```http
POST /api/auth/login
```

Authenticate using Stellar wallet signature.

**Request Body:**

```json
{
  "address": "G...",
  "signature": "base64...",
  "message": "challenge message"
}
```

**Response:**

```json
{
  "token": "jwt-token",
  "expires_in": 3600
}
```

---

### Scholarships

#### List Scholarships

```http
GET /api/scholarships
```

**Query Parameters:**

- `status` - Filter by status (active, completed, paused)
- `limit` - Number of results (default: 20)
- `offset` - Pagination offset

**Response:**

```json
{
  "scholarships": [
    {
      "id": "sch_123",
      "title": "Computer Science Grant",
      "amount": "1000",
      "currency": "XLM",
      "milestones": [...],
      "status": "active"
    }
  ]
}
```

#### Create Scholarship

```http
POST /api/scholarships
```

**Headers:**

```
Authorization: Bearer <jwt-token>
```

**Request Body:**

```json
{
  "title": "Computer Science Grant",
  "description": "For CS students",
  "amount": "1000",
  "currency": "XLM",
  "milestones": [
    {
      "name": "Enrollment",
      "amount": "250",
      "verification": "document"
    }
  ]
}
```

---

### Milestones

#### Verify Milestone

```http
POST /api/milestones/{id}/verify
```

**Headers:**

```
Authorization: Bearer <jwt-token>
```

**Request Body:**

```json
{
  "verification_doc": "base64...",
  "notes": "Semester enrollment confirmed"
}
```

---

### Transactions

#### Get Transaction History

```http
GET /api/transactions
```

**Query Parameters:**

- `address` - Filter by wallet address
- `type` - Filter by type (deposit, withdrawal, release)
- `limit` - Number of results

**Response:**

```json
{
  "transactions": [
    {
      "id": "tx_123",
      "type": "release",
      "amount": "250",
      "currency": "XLM",
      "from": "vault_address",
      "to": "student_address",
      "timestamp": "2024-01-15T10:30:00Z",
      "milestone_id": "ms_456"
    }
  ]
}
```

---

### Webhooks

#### Transaction Events

Subscribe to webhook events for real-time updates:

```http
POST /api/webhooks
```

**Event Types:**

- `scholarship.created`
- `milestone.completed`
- `funds.released`
- `funds.deposited`

---

## 🤝 Contributing

Contributions are welcome!

1. Fork the repository
2. Create a feature branch
3. Submit a pull request

Please follow project coding standards and include tests where applicable.

---

## 🗺️ Roadmap

### Phase 1 - Foundation (Q1 2024)

- [x] Project setup and architecture design
- [x] Core smart contract development (Scholarship Vault)
- [x] Basic wallet integration (SEP-10)
- [x] Frontend skeleton with Next.js

### Phase 2 - Core Features (Q2 2024)

- [ ] Milestone-based escrow implementation
- [ ] Student registration and profile management
- [ ] Donor dashboard
- [ ] Basic transaction history

### Phase 3 - Enhanced Features (Q3 2024)

- [ ] Governance module (voting and approvals)
- [ ] Multi-signature support
- [ ] Advanced reporting and analytics
- [ ] Mobile-responsive design

### Phase 4 - Launch (Q4 2024)

- [ ] Mainnet deployment
- [ ] Third-party audit
- [ ] Community governance transition
- [ ] Partner integration (universities, NGOs)

---

## ❓ FAQ

### General

**What is ScholarPath?**

ScholarPath is a decentralized platform for scholarship and grant management built on the Stellar blockchain. It enables transparent, milestone-based funding where donors can track their impact and students can receive grants directly without intermediaries.

**Why use blockchain for scholarships?**

Blockchain provides transparency, immutability, and reduced administrative costs. Every transaction is recorded on-chain, making it easy to verify fund flow from donors to recipients.

**What network does ScholarPath use?**

ScholarPath uses the Stellar network with Soroban smart contracts. It supports both testnet (for development) and mainnet (for production).

### For Students

**How do I receive funds?**

1. Connect your Stellar wallet via SEP-10 authentication
2. Create your student profile
3. Apply for scholarships
4. Once approved, funds are released as you complete milestones

**What wallets are supported?**

Any Stellar-compatible wallet that supports SEP-10 authentication, such as:

- Albedo
- Freighter
- Rabble
- StellarTerm

### For Donors

**How do I know my funds are being used correctly?**

All transactions are recorded on the Stellar blockchain. You can track fund releases through the milestone verification system, where funds are only released when predetermined academic milestones are verified.

**Can I specify how my funds are used?**

Yes, donors can specify funding requirements and preferred institutions when creating scholarships.

### Technical

**What are the transaction fees?**

Stellar network fees are extremely low (typically < 0.01 XLM per transaction), making it practical for micro-payments and milestone-based releases.

**Is my data private?**

Wallet addresses are pseudonymous. Personal information is stored off-chain with the user's control. On-chain data is limited to transaction records.

---

## 📄 License

MIT
