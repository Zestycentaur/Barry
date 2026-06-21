# Barry — Autonomous Trading Bot

> An autonomous algorithmic trading system that monitors crypto and equity markets 24/7, evaluates technical confluence in real-time, and manages the full trade lifecycle automatically.

**Status:** Live — running in paper mode on a $100K simulated account  
**Built with:** Python · Alpaca API · AI-assisted development

---

## What It Does

Barry watches crypto and stock markets around the clock. When market conditions align across multiple technical factors, it enters a trade, manages the position automatically (partial exits, stop adjustments, breakeven moves), and exits based on predefined rules — no manual intervention required.

**Key capabilities:**
- Real-time market scanning across crypto and equity assets
- Multi-factor confluence evaluation before any entry
- Automated risk management (position sizing, stop losses, max drawdown limits)
- Tiered exit system with partial profit-taking
- Market regime detection (bull/bear mode switching)
- Full trade lifecycle logging and performance tracking
- Automatic safety halts if drawdown exceeds thresholds

---

## Architecture

```
┌─────────────────────────────────────────────────────────┐
│                        BARRY                            │
├─────────────────────────────────────────────────────────┤
│                                                         │
│  MARKET SCANNER                                         │
│  ──────────────                                         │
│  15-min cycle → fetch OHLCV + indicators               │
│       ↓                                                 │
│  Confluence engine → score signals across factors       │
│       ↓                                                 │
│  Regime filter → bull/bear mode check                   │
│       ↓                                                 │
│  Risk gate → position size, daily loss limit            │
│                                                         │
│  TRADE MANAGER                                          │
│  ─────────────                                          │
│  Entry → partial exits at targets → stop management     │
│       ↓                                                 │
│  Breakeven moves → final exit → P&L logging             │
│                                                         │
│  SAFETY SYSTEMS                                         │
│  ───────────────                                        │
│  Max drawdown halt · Win rate monitor · Auto-revert     │
│  Daily loss limit · Regime-based position scaling       │
│                                                         │
│  Assets: BTC · ETH · SOL · AVAX · LINK · BNB           │
│          + 13 US equities (NVDA, AMD, MSFT, and more)  │
└─────────────────────────────────────────────────────────┘
```

---

## Performance (Paper Trading)

| Metric | Value |
|--------|-------|
| Account size | $100,000 (simulated) |
| Win rate | 66.7% |
| Max drawdown | 4.6% |
| Mode | Paper trading (Alpaca) |
| Target | 200 trades → live deployment |

---

## Backtesting Framework

Barry includes an institutional-grade backtesting pipeline to validate strategies before deployment:

- **CPCV** (Combinatorial Purged Cross-Validation) — prevents overfitting
- **Walk-Forward Validation** — tests on unseen data
- **Monte Carlo Simulation** — 10,000+ scenario stress tests
- **PSR/DSR** (Probabilistic/Deflated Sharpe Ratio) — statistical reality checks
- **Edge scoring system** — strategies must score 80/100 to deploy
- Full friction model (commissions, spread, slippage)

---

## Tech Stack

- **Language:** Python
- **Broker API:** Alpaca (paper + live)
- **Data:** Real-time OHLCV via Alpaca WebSocket
- **Indicators:** Custom confluence engine (RSI, EMA, VWAP, ATR, Bollinger Bands)
- **Logging:** JSON memory file + rolling log
- **Development:** AI-assisted development (OpenClaw + Claude)

---

## Disclaimer

This project is for educational and research purposes. Past paper trading performance does not guarantee future live results. Not financial advice.
