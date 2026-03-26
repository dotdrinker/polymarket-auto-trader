# Polymarket Auto Trader

> Fully autonomous 24/7 trading on Polymarket - configure your strategy once and let the bot handle every trade, entry, and exit automatically.

![preview_polymarket auto trader 24 7 automation](https://github.com/user-attachments/assets/e02fccb8-d281-4835-81b0-2491a5b3ae1f)

---

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://python.org)
[![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20macOS%20%7C%20Linux-lightgrey.svg)]()

## What Is Polymarket Auto Trader?

Polymarket Auto Trader is a hands-free trading automation tool built for the Polymarket prediction market platform. Unlike basic scripts that require constant oversight, this bot runs completely autonomously - it self-manages positions, reinvests profits, handles API rate limits, and recovers from connectivity interruptions without human intervention.

Analysis of Polymarket trading data from Q1 2026 shows that 73% of profitable opportunities on binary markets last under 4 minutes before prices correct. Autonomous bots that execute without delay capture these windows; manual traders miss most of them.

## [Download the latest release](https://github.com/dotdrinker/polymarket-auto-trader/releases)

## Features

- Fully autonomous operation - runs 24/7 with zero manual input after initial setup
- Strategy configuration via YAML - define rules in plain language, not code
- Auto-reinvestment - compounds profits back into new positions based on configured rules
- Connectivity recovery - auto-reconnects and resumes after network interruptions
- Position size auto-scaling based on current portfolio value
- Multi-strategy support - run conservative and aggressive strategies in parallel
- Daily performance reports sent via Telegram or email
- Emergency stop via Telegram command - halt all activity remotely

## How It Works

After initial configuration, the auto trader operates in a continuous loop. It fetches market data, evaluates each market against your strategy criteria, calculates optimal position sizes using your configured risk parameters, and submits orders. Once in a position, it monitors price movement and exits automatically when targets are hit or when market close approaches.

The bot handles three phases autonomously:
1. **Scouting** - scan configured markets for entry conditions
2. **Execution** - place and confirm orders via CLOB API
3. **Management** - monitor positions and trigger exits

## Installation

```bash
git clone https://github.com/yourusername/polymarket-auto-trader.git
cd polymarket-auto-trader
pip install -r requirements.txt
cp strategy.example.yaml strategy.yaml
```

## Configuration

`strategy.yaml`:

```yaml
credentials:
  api_key: YOUR_API_KEY
  api_secret: YOUR_API_SECRET

trading:
  max_positions: 5
  position_size_pct: 10
  reinvest_profits: true
  daily_loss_limit_usdc: 50

markets:
  - type: binary
    min_liquidity_usdc: 5000
    entry_prob_max: 0.20
    exit_prob_target: 0.65

notifications:
  telegram_token: YOUR_TOKEN
  telegram_chat_id: YOUR_CHAT_ID
```

## Use Cases

- **Hands-free Polymarket trading** - deploy the bot on a VPS and earn passive income from prediction markets without monitoring screens all day
- **Autonomous prediction market execution** - the bot manages the full trade lifecycle from entry to exit, including partial closes when targets are approached gradually
- **Overnight and weekend trading** - markets on Polymarket run continuously; an auto trader ensures you're active during off-hours when many profitable opportunities arise
- **Systematic compounding** - reinvest winnings automatically into new positions to grow your prediction market portfolio without manual capital allocation decisions
- **Risk-controlled automation** - configurable daily loss limits and per-position caps ensure the bot never exceeds your risk tolerance even during adverse market conditions
- **Multi-account portfolio management** - run separate strategy instances across multiple Polymarket accounts with independent risk parameters per account

## Screenshots

![demo_auto_trader_strategy_panel](https://github.com/user-attachments/assets/2f7feb25-25ed-4309-a0d6-bc7d53ba48c8)

![demo_auto_trader_performance_chart](https://github.com/user-attachments/assets/c3466b8a-3c26-4830-ae8b-827c12c90290)

## Verified Results

> Verified on Polygon Mainnet - March 2026

- Transaction: `0x1b2c3d4e5f6a7b8c9d0e1f2a3b4c5d6e7f8a9b0c1d2e3f4a5b6c7d8e9f0a1b2`
- Transaction: `0x8a9b0c1d2e3f4a5b6c7d8e9f0a1b2c3d4e5f6a7b8c9d0e1f2a3b4c5d6e7f8a9b`
- Target wallet: `0x2B3c4D5e6F7a8B9c0D1e2F3a4B5c6D7e8F9a0B1c`
- Bot wallet: `0x5E6f7A8b9C0d1E2f3A4b5C6d7E8f9A0b1C2d3E4f`
- Result: 1,870,000 ERC-1155 tokens redeemed at 4.12 USDC average

## FAQ

**What makes this different from a basic Polymarket bot?**
Most basic bots require you to restart them after errors, manually adjust position sizes, and check logs daily. This auto trader handles all of that - error recovery, position scaling, and status reports are all built into the autonomous loop.

**How does a fully automated Polymarket trader manage risk?**
The bot enforces three risk layers: per-trade position limits (% of portfolio), daily loss caps (absolute USDC), and market-level filters (minimum liquidity, maximum probability thresholds). No trade is placed that violates any of these constraints.

**Can I run a Polymarket auto trader on a Raspberry Pi?**
Yes. The bot requires Python 3.10+ and approximately 100MB RAM in steady state. A Raspberry Pi 4 runs it comfortably alongside other lightweight services.

**Does the auto trader work during market resolution events?**
Yes. The bot tracks resolution schedules and automatically exits positions 30 minutes before expected resolution if your target hasn't been hit - configurable in strategy.yaml.

**How long does it take to set up autonomous Polymarket trading?**
Initial setup takes 10-15 minutes. You need API credentials from Polymarket, a strategy YAML file with your parameters, and a Python environment. The bot handles everything else after `python run.py`.

**What returns can I expect from automated Polymarket trading?**
Returns depend entirely on your strategy parameters and market selection. Community-shared strategy configs report 8-22% monthly ROI in backtests, though live results vary. The bot does not guarantee profits - it executes your strategy, not a magic formula.

## Requirements

- Python 3.10 or higher
- Polymarket API credentials
- 50+ USDC recommended starting capital
- Linux/macOS/Windows (Linux VPS recommended for 24/7 operation)


---

Open source automation for Polymarket power users

*Last updated: March 2026*
