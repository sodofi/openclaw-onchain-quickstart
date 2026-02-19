# openclaw-onchain-quickstart
Quickstart tutorial of building an agent using Openclaw that can do onchain actions.

# Resources
- [List of tools and resources](https://github.com/sodofi/awesome-onchain-agents)
- [EthSkills](https://ethskills.com/)

# Overview

How it all fits together

```
         ┌──────────────┐         ┌──────────────┐
         │  Ethskills   │         │ MCP Servers  │
         │  How to build│         │ Live on-chain│
         │  on Ethereum │         │ data & tools │
         └──────┬───────┘         └──────┬───────┘
                └────────────┬────────────┘
                             │ injected into
                             ▼
                   ┌──────────────────┐
                   │   BRAIN (LLM)    │
                   │  Claude · GPT-4  │
                   │  Reasons·Decides │
                   └────────┬─────────┘
                            │ drives
                            ▼
                   ┌──────────────────┐
                   │      BODY        │
                   │    OpenClaw      │
                   │    ElizaOS       │
                   │     Virtuals     │
                   └───┬─────┬────┬───┘
                       │     │    │
           ┌───────────┘     │    └────────────┐
           ▼                 ▼                 ▼
  ┌─────────────┐   ┌─────────────┐   ┌─────────────┐
  │  COMMUNICATE│   │   TRANSACT  │   │   IDENTITY  │
  │             │   │             │   │             │
  │  Telegram   │   │  AgentKit   │   │     ENS     │
  │  Twitter    │   │  Agentic    │   │  ERC-8004   │
  │  Farcaster  │   │  Wallets    │   │  ERC-7710   │
  │  Discord    │   │  x402       │   │    SIWA     │
  └─────────────┘   └──────┬──────┘   └─────────────┘
                            │
                  ══════════╧══════════
                       ETHEREUM
                   Base · Mainnet · L2s
                  ═════════════════════
```

# Setup

### Installing Openclaw

1. Use a VPS like [hostinger](https://www.hostinger.com/support/how-to-install-openclaw-on-hostinger-vps/)
2. Once you install, navigate to Docker Manager > Projects > Terminal
3. Paste the following into the terminal:

   ```
   curl -fsSL https://openclaw.ai/install.sh | bash
   
   ```
   then paste
   ```
   openclaw onboard --install-daemon
   ```
   
5. Add your API keys (Claude recommended)


### Setting up Telegram bot

1. Message @BotFather on telegram
2. Type `/newbot`
3. Paste the bot token into the Openclaw terminal
4. Message your bot to test if it works (Note: You might need to add the pairing code to openclaw using `openclaw pairing approve telegram CODE_HERE`)


### Setting up personality

1. create a soul file (I got inspo from [here](https://github.com/aaronjmars/soul.md/blob/main/SOUL.template.md))

## Creating A Wallet

There are many different ways you can connect your agent to a wallet. Here are a list of following options that I tested and the prompts I used.

### Coinbase Agentic Wallet

A custodial wallet controlled by Coinbase Agentic Wallet, you don't manage the private keys directly—they are handled by the service and the authenticated session here.

Great if you want strong gurantees your agent wont accidentally expose its seed phrase.

```
I want you to integrate coinbase agentic wallet using these docs https://docs.cdp.coinbase.com/agentic-wallet/welcome.

Figure out how to install and configure the ‎`agentic-wallet-skills` and the ‎`awal` CLI on this machine, and then give me a status update.

Ask me for any required Coinbase auth (email OTP, etc.).

Ask me for confirmation before doing onchain things
```

[Docs](https://docs.cdp.coinbase.com/agentic-wallet/welcome.)
