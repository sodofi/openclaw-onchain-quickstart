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

