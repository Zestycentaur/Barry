# 🤖 Barry — Autonomous Trading Bot

![Status](https://img.shields.io/badge/status-paper%20trading-yellow)
![Win Rate](https://img.shields.io/badge/win%20rate-66.7%25-brightgreen)
![Drawdown](https://img.shields.io/badge/max%20drawdown-4.6%25-blue)
![Assets](https://img.shields.io/badge/assets-crypto%20%2B%20equities-purple)
![Built With](https://img.shields.io/badge/built%20with-Python%20%C2%B7%20Alpaca%20%C2%B7%20AI--assisted-orange)

> An autonomous algorithmic trading system that monitors crypto and equity markets 24/7, evaluates real-time technical confluence, and manages the full trade lifecycle — entries, exits, risk, and safety — automatically.

**Currently:** Live paper trading on a $100K simulated Alpaca account · Target: 200 validated trades → live deployment

---

## 📊 Live Performance

| Metric | Value |
|--------|-------|
| 💰 Account Size | $100,000 (simulated) |
| ✅ Win Rate | 66.7% |
| 📉 Max Drawdown | 4.6% |
| 🔄 Scan Cycle | Every 15 minutes |
| 📈 Assets Monitored | 6 crypto + 13 equities |
| 🎯 Go-Live Target | 200 paper trades |

---

## ⚙️ How It Works

Barry runs a continuous loop every 15 minutes:

```
Market Data (OHLCV)
        ↓
Confluence Engine
(RSI · EMA · VWAP · ATR · Bollinger Bands)
        ↓
Regime Filter (Bull / Bear mode)
        ↓
Risk Gate (position size · daily loss limit)
        ↓
Trade Entry → Automated Management → Exit
        ↓
P&L Logging + Safety Monitoring
```

When multiple technical factors align above a threshold score, Barry enters a position. It then manages the trade autonomously — moving stops to breakeven, taking partial profits at targets, and exiting fully when the trade completes or a safety condition triggers.

---

## 🛡️ Safety Systems

Barry is built around capital protection first:

- **Max drawdown halt** — trading stops automatically if losses exceed threshold
- **Win rate monitor** — auto-reverts settings if performance degrades
- **Daily loss limit** — hard cap on losses per day
- **Regime detection** — scales down position size in bear markets
- **Single position rule** — one crypto trade at a time
- **No data, no trade** — refuses to trade without confirmed live market feed

---

## 📈 Assets Covered

**Crypto:** BTC · ETH · SOL · AVAX · LINK · BNB

**Equities:** NVDA · AMD · MSFT · PLTR · AVGO · XOM · UNH · SMCI · AMZN · GOOGL · SOFI · IWM · SOXL

---

## 🔬 Backtesting Framework

Strategies must pass an institutional-grade pipeline before deploying to Barry:

| Method | Purpose |
|--------|---------|
| CPCV (Combinatorial Purged Cross-Validation) | Prevents overfitting |
| Walk-Forward Validation | Tests on unseen data only |
| Monte Carlo Simulation (10,000+ scenarios) | Stress testing |
| PSR / DSR (Probabilistic / Deflated Sharpe) | Statistical reality checks |
| Edge Scoring (0–100) | Must score ≥80 to deploy |
| Full Friction Model | Commissions + spread + slippage |

---

## 🧰 Tech Stack

| Layer | Technology |
|-------|-----------|
| Language | Python |
| Broker / Paper Trading | Alpaca Markets API |
| Market Data | Alpaca WebSocket (real-time OHLCV) |
| Indicators | Custom confluence engine |
| State Management | JSON memory + rolling log |
| Development | AI-assisted (OpenClaw + Claude Sonnet) |

---

## 🗺️ Roadmap

- [x] Core confluence engine
- [x] Automated trade lifecycle management
- [x] Institutional backtesting framework
- [x] Market regime detection
- [x] Safety systems & auto-revert
- [ ] 200 paper trades (currently: 6)
- [ ] Live deployment on Bybit
- [ ] Full position sizing at 30 live trades

---

## ⚠️ Disclaimer

This project is for educational and research purposes only. Paper trading results do not guarantee live performance. Nothing here is financial advice.
