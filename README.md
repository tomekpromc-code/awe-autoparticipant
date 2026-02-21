# awe-autoparticipant

Automated script to participate in the [AgentBeat](https://www.agentbeat.fun/) Chinese New Year red packet campaign — **1,000 USDC** split among eligible agents (deadline: Mar 4, 2026).

## Quickstart

### 1. Install Node.js

Download from https://nodejs.org (version 18 or higher)

### 2. Clone and install

```bash
git clone https://github.com/0xpinger/awe-autoparticipant.git
cd awe-autoparticipant
npm install
```

### 3. Run

```bash
node agentbeat-submit.mjs
```

That's it. The script guides you through everything interactively.

---

## What you'll need to do manually

The script handles everything automatically except these 3 things:

**1. Save your private keys** — the script generates 2 wallets and shows the private keys. You must save them before continuing.

**2. Claim your Moltbook account** (~2 min)
- Open a link in your browser
- Enter email + any username
- Confirm your email
- Post one tweet with a verification code

**3. Send ~$0.01 ETH on Base** to the generated wallet address
- Any exchange or wallet that supports Base network works (Coinbase, MetaMask, etc.)

---

## What the script does automatically

1. Generates a unique random agent name and profile
2. Creates a reward wallet (USDC will be sent here after the campaign)
3. Creates an agent wallet (used for gas)
4. Registers your agent on [Moltbook](https://www.moltbook.com/)
5. Waits for you to verify your Moltbook account
6. Waits for you to fund the wallet
7. Mints an ERC-8004 identity NFT on Base mainnet (~$0.01 gas)
8. Submits your agent to AgentBeat
9. Posts the claim comment on the campaign post

---

## Resuming after interruption

If the script stops for any reason, just re-run it — it picks up where it left off:

```bash
node agentbeat-submit.mjs
```

To start completely fresh:

```bash
node agentbeat-submit.mjs --fresh
```

---

## Check your reward status after Mar 4

```bash
curl https://api.agentbeat.fun/api/v1/submissions/check/YOUR_VOUCHER
```

Your voucher is saved in `~/.config/agentbeat/credentials.json`.
