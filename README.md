# QuarTrendSDK

**QuarTrendSDK** is a Software Development Kit (SDK) designed for the professional and modular development of algorithmic trading strategies.  
Built for scalability, performance, and flexibility, it is meant to integrate into advanced quantitative trading environments, providing a robust infrastructure to manage events, data, orders, and AI-based strategies in real time.

---

## 🚀 Overview

QuarTrendSDK is the core of the QuarTrend system: it allows developers to build, test, and deploy automated strategies, reactive to market events or based on predictive models.

> ✔️ Asynchronous  
> ✔️ Extensible  
> ✔️ Integrates with IBKR, alternative data, and custom plugins  
> ✔️ Production-ready

---

## 🔧 Installation

> ⚠️ Requires Python 3.9+ and an active IB Gateway

---

## 🧠 Quickstart

```python
from quartrend import Strategy, Context

class MyStrategy(Strategy):
    def on_start(self, ctx: Context):
        print("📈 Strategy started")

    async def on_bar(self, ctx: Context, bar):
        if bar.close > bar.open:
            await ctx.buy(qty=100)

    async def on_order_fill(self, ctx: Context, fill):
        print(f"Order filled: {fill}")
```

---

## 🧩 Architecture

```text
 ┌────────────────────┐
 │    User Strategy   │ ◄──── Write your logic here
 └────────┬───────────┘
          │
 ┌────────▼───────────┐
 │ Async Event Engine │ ◄──── Event dispatcher
 └────────┬───────────┘
          │
 ┌────────▼────────┐   ┌───────────────┐
 │   Data Feeds    │ + │   Broker API  │ ◄──── IBKR, simulations
 └─────────────────┘   └───────────────┘
```

---

## 📚 Documentation

Refer to the [Wiki](https://github.com/QuarTrend/QuarTrend-SDK/wiki) (in progress) for:

- Integration with QuarTrend Terminal
- Writing AI-based strategies
- Building custom plugins
- Handling alternative events (macro, insider, hedge funds, etc.)

---

## 🧪 Testing

```bash
pytest tests/
```

Test structure:
- `tests/unit` — unit tests for core components  
- `tests/integration` — integration tests with IBKR or external feeds  
- `examples/` — demo strategies

---

## 📄 License

Distributed under a proprietary license.  
© QuarTrend. All rights reserved.

---

## 📬 Contact

- Website: [quartrend.com](https://quartrend.com) *(coming soon)*  
- Instagram: [@quartrend](https://instagram.com/quartrend)  
- X: [@quartrend](https://x.com/quartrend)  
