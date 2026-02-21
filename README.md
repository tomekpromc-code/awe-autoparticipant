# awe-autoparticipant

Automated script to participate in the [AgentBeat](https://www.agentbeat.fun/) Chinese New Year red packet campaign — 1,000 USDC split among eligible agents.

## What it does

Fully automated 9-step flow:

1. Auto-generates a unique agent profile (name, description, category)
2. Generates a dedicated reward wallet (shows private key to save)
3. Creates an agent EVM wallet
4. Registers on [Moltbook](https://www.moltbook.com/) (AI agent social network)
5. Walks you through claiming your Moltbook account (email + tweet verification) — **script blocks until verified**
6. Waits for you to fund the wallet with ~$0.01 ETH on Base
7. Mints an ERC-8004 identity NFT on Base mainnet
8. Submits to AgentBeat API and saves your voucher
9. Posts the voucher claim comment on the Moltbook campaign post

**Total user input:** save private key, claim Moltbook account (email + tweet), send ~$0.01 ETH. Everything else is automatic.

## Requirements

- Node.js >= 18
- npm

## Setup

```bash
npm install
```

## Usage

```bash
# Fresh run (new user)
node agentbeat-submit.mjs

# Start completely fresh (wipes previous progress)
node agentbeat-submit.mjs --fresh
```

Progress is saved to `~/.config/agentbeat/credentials.json`. Re-run to resume if interrupted.

## Campaign details

- **Timeline:** Feb 18 – Mar 4, 2026
- **Reward pool:** 1,000 USDC split evenly among eligible agents
- **Required:** ERC-8004 identity NFT on Base mainnet + voucher claim comment on Moltbook
- **Campaign post:** https://www.moltbook.com/post/72986c76-4d1c-4398-8070-842eb1881ea2

## Check claim status

```bash
curl https://api.agentbeat.fun/api/v1/submissions/check/YOUR_VOUCHER
```
