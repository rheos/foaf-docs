# Growoperative Project Plan: Centralized to Decentralized Transition

## Phase 1: Centralized MVP (Live Now)
- Backend: Ruby on Rails with MySQL
- Frontend: React PWA or mobile-native app
- Features:
  - User auth via email/password
  - Offer/request system for produce and services
  - Mutual credit ledger stored in MySQL
  - Contact-based visibility of listings
  - Manual payment handling (cash, PayPal, barter)
- Status: MVP completed and under iteration

## Phase 2: Blockchain Readiness Layer
- Add internal token simulation for FOAF credit in MySQL
- Build mock wallet structure (token balances stored in SQL)
- Develop blockchain gateway service:
  - Mirrors transactions to testnet (Polygon/Gnosis)
  - Uses web3.js or ethers.js
- Begin logging all transactions in a replayable format for future chain import

## Phase 3: Identity Binding & Snapshot
- Prompt users to bind accounts to Web3 wallets (MetaMask, WalletConnect)
- Generate signed migration claims for:
  - Credit balances
  - Outstanding obligations (who owes whom)
  - Credit trust graph (friend connections)
- Store mappings: app user ID → wallet address

## Phase 4: Smart Contract Deployment
- Deploy FOAF ERC-20 token (25M indivisible supply)
- Deploy smart contracts:
  - Mutual credit ledger contract
  - Credit claim & onboarding contract (to verify migration claims)
  - Contact-based trust/limit contract
  - Transaction fee logic (3% to treasury)
- Accept user-submitted migration claims on-chain

## Phase 5: dApp Interface & On-Chain Launch
- Add Web3 frontend:
  - Wallet connection
  - On-chain offer/request listing
  - Transaction signing
  - Smart contract credit ledger interaction
- Maintain dual-mode operation during transition:
  - Centralized and decentralized backends coexist
  - Incentivize migration with FOAF rewards or bonuses

## Phase 6: Full Decentralization
- Migrate listing metadata to IPFS or Ceramic
- Host frontend on IPFS or Arweave
- Replace OAuth with decentralized ID (ENS, Lens Protocol)
- Freeze centralized backend
- Launch DAO for treasury and platform governance

## Optional Enhancements
- Privacy-preserving trust networks (zk-proofs for contact links)
- Native mobile app with Web3 wallet support
- DAO grant programs for local food producers and tech maintenance

