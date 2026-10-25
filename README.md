# Hashtrion — Agentic Commerce on XRPL

**Policy-Controlled AI Payments & Blockchain Settlement**

*XRPL AI & Fintech Hackathon 2026 | Agentic Finance*

## 1. Overview

Hashtrion is building payment and settlement infrastructure that enables AI agents to make payments within spending limits defined by wallet owners.

Built on the XRP Ledger, Hashtrion provides a payment rail that integrates with existing AI platforms and commerce systems
enabling secure payment authorization, transaction signing, and direct settlement to merchant wallets.

## 2. How It Works

1. **Wallet Setup** — Users create an Agent Account and locally authorize an XRPL RegularKey signing authority.
2. **Spending Policy** — Wallet owners define permitted assets, transaction limits, and expiration.
3. **AI Shopping** — An AI agent discovers products and prepares a merchant checkout using UCP. The user reviews and confirms the purchase.
4. **Payment Authorization** — Hashtrion validates the payment credential, Agent Account, platform connection, Spending Policy, and payment details.
5. **Transaction Signing** — Transaction API prepares the XRPL payment, while Signing API signs using the agent's key in KMS.
6. **Blockchain Settlement** — Transaction API verifies and submits the signed transaction. XRP or RLUSD is transferred directly to the merchant wallet on XRPL.
7. **Order Confirmation** — The merchant confirms the payment and completes the order. The wallet displays the blockchain transaction history.

## 3. System Architecture

The solution consists of an iOS wallet, an AI shopping application, a UCP-enabled demonstration merchant, and Hashtrion's payment infrastructure.

**Core Payment Infrastructure**

Wallet-X → Platform API → Transaction API  ↔ Signing API

Transaction API → XRPL

**Commerce Integration**

AI Shopping Agent → UCP Merchant Checkout → Hashtrion Payment Rail → Merchant Order Confirmation

## 4. Source Repositories

| Repository | Responsibility |
|---|---|
| [wallet-x](https://github.com/gralok3961/wallet-x) | Agent Account and Spending Policy management |
| [ac-platformapi](https://github.com/gralok3961/ac-platformapi) | Agent authorization, credentials, policy enforcement and payment processing |
| [ac-tranapi](https://github.com/gralok3961/ac-tranapi) | XRPL payment execution, transaction validation and finality |
| [ac-signingapi](https://github.com/gralok3961/ac-signingapi) | Secure transaction signing and key management |
| [hashtrion-agent-ai](https://github.com/gralok3961/hashtrion-agent-ai) | AI shopping and checkout demonstration |
| [hashtrion-merchant-api](https://github.com/gralok3961/hashtrion-merchant-api) | UCP merchant checkout and order management |
| [hashtrion-merchant-ui](https://github.com/gralok3961/hashtrion-merchant-ui) | Bluefern merchant storefront and discovery |


Hashtrion also publishes its [UCP Payment Handler metadata](https://pay.hashtrion.com/ucp/payment-handlers/com.hashtrion.pay/schema.json), 
which is not included in the submitted source repositories.

## 5. Demo & Documentation

- **Demo Video:** [Watch the demo](https://hashtrionassets.blob.core.windows.net/public-media/hackathon_demo_web.mp4)
- **Architecture Diagrams:**
  - [1A — Agent Account Creation & KMS Provisioning](https://hashtrionassets.blob.core.windows.net/public-media/1A%20-%20Agent%20Account%20Creation%20%26%20KMS%20Provisioning.png)
  - [1B — XRPL RegularKey Activation & Spending Policy](https://hashtrionassets.blob.core.windows.net/public-media/1B%20-%20XRPL%20RegularKey%20Activation%20%26%20Spending%20Policy.png)
  - [2 — UCP Discovery & Checkout](https://hashtrionassets.blob.core.windows.net/public-media/2%20-%20UCP%20Discovery%20%26%20Checkout%20.png)
  - [3 — Hashtrion Payment Execution & XRPL Settlement](https://hashtrionassets.blob.core.windows.net/public-media/3%20-%20Hashtrion%20Payment%20Execution%20%26%20XRPL%20Settlement%20.png)

The demonstration focuses on policy-controlled AI purchasing, XRPL payment execution, and merchant settlement confirmation.

## 6. Development History and Hackathon Scope

### Before the Hackathon

After completing the Make Waves program, we developed the Agentic Payment flow during the three weeks leading up to the hackathon, across three core services:

- **Platform API** — Payment authorization and spending policy enforcement
- **Transaction API** — XRPL transaction execution and finality tracking
- **Signing API** — KMS-based transaction signing

The Wallet, AI Shopping Agent, and Bluefern Merchant were also developed before the event and support the end-to-end demonstration.

### Built During the Hackathon — October 24–25, 2026

During the hackathon, we added **Agent payment authority revocation**, enabling users to revoke previously granted Agent payment authority through the Wallet.

## 7. Technology

- **Blockchain:** XRP Ledger — XRP and RLUSD
- **Backend:** .NET, Node.js, TypeScript
- **Frontend:** Next.js, SwiftUI
- **Infrastructure:** Microsoft Azure, Azure SQL, Azure Key Vault
- **Commerce Integration:** Universal Commerce Protocol (UCP)
- **Signing:** Azure Key Vault–backed ECDSA signing (secp256k1), with on-chain signing authority delegated via XRPL RegularKey.

---

**Hashtrion — Building payment and settlement rails for the agentic economy.**