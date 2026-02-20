# Quantum Ledger Pro 🚀

**Standalone AI-Powered Cryptocurrency Trading Platform with Real ML Models, Live Trading, and Full Customization**

> Production-ready trading bot that runs on Windows & Linux with LSTM, GBM, Ensemble, and Transformer AI models

## ✨ Features

### 🤖 Advanced AI Models
- **LSTM** - Long Short-Term Memory neural networks for time-series prediction
- **GBM** - XGBoost gradient boosting machines for feature-based prediction  
- **Ensemble** - Weighted combination of multiple models
- **Transformer** - Attention-based models via Hugging Face
- **Live Model Training** - Continuous learning with new market data
- **Custom Model Support** - Add your own models

### 📊 Real Trading Capabilities
- **10+ Exchanges**: Binance, Bybit, OKX, Coinbase, Kraken, KuCoin, FTX, Huobi, Gateio, Upbit
- **All Crypto Pairs** - 100+ trading pairs (BTC, ETH, SOL, DOGE, XRP, etc.)
- **Trading Modes** - Spot, Futures, Margin, Lending
- **Order Types** - Market, Limit, Stop-Loss, Take-Profit
- **Risk Management** - Position sizing, drawdown limits, daily loss limits
- **Paper Trading** - Test strategies risk-free

### 🎯 Advanced Features
- Real-time price tracking with WebSocket streams
- AI signal generation with confidence scores
- Auto-execution based on AI predictions
- Portfolio tracking & P&L calculations
- Advanced charting with TradingView integration
- Historical backtesting engine
- Multi-strategy management
- API key management with encryption
- Alerts & notifications
- Performance analytics & metrics

### 🛠️ Development Ready
- Full TypeScript/React frontend
- Express.js REST API backend
- Python ML training pipeline
- SQLite/PostgreSQL database
- Docker containerization
- GitHub Actions CI/CD
- Comprehensive testing

## 📋 System Requirements

### Windows
- Windows 10/11 (64-bit)
- Node.js 18+
- Python 3.10+
- 8GB RAM (16GB recommended)
- 5GB disk space

### Linux (Ubuntu 20.04+, Debian, Fedora)
- Node.js 18+
- Python 3.10+
- 8GB RAM (16GB recommended)
- 5GB disk space

## 🚀 Quick Start

### Option 1: Automated Setup (Recommended)

**Windows:**
```batch
git clone https://github.com/jai-fire/nue.git
cd nue
scripts\\setup-windows.bat
scripts\\start-dev.bat
```

**Linux/macOS:**
```bash
git clone https://github.com/jai-fire/nue.git
cd nue
chmod +x scripts/setup-linux.sh
./scripts/setup-linux.sh
./scripts/start-dev.sh
```

### Option 2: Manual Setup

**1. Clone Repository**
```bash
git clone https://github.com/jai-fire/nue.git
cd nue
```

**2. Install Dependencies**
```bash
# Frontend
cd frontend
npm install

# Backend
cd ../backend
npm install

# AI Models
cd ../ai-models
pip install -r requirements.txt
```

**3. Configure Environment**
```bash
cp .env.example .env
# Edit .env with your API keys
```

**4. Start Services**
```bash
# Terminal 1: Backend API
cd backend
npm run dev

# Terminal 2: Python AI Server
cd ai-models
python -m uvicorn main:app --reload

# Terminal 3: Frontend
cd frontend
npm run dev
```

## 📂 Project Structure

```
nue/
├── frontend/                # React + TypeScript UI
│   ├── src/
│   │   ├── components/     # Reusable React components
│   │   ├── pages/          # Page components
│   │   ├── hooks/          # Custom React hooks  
│   │   ├── api/            # API client functions
│   │   ├── types/          # TypeScript types
│   │   └── App.tsx
│   ├── package.json
│   └── vite.config.ts
│
├── backend/                 # Express.js REST API
│   ├── src/
│   │   ├── routes/         # API endpoints
│   │   ├── controllers/    # Request handlers
│   │   ├── services/       # Business logic
│   │   ├── models/         # Database models
│   │   ├── middleware/     # Auth, validation
│   │   └── server.ts
│   └── package.json
│
├── ai-models/              # Python ML Training
│   ├── models/
│   │   ├── lstm_model.py
│   │   ├── gbm_model.py
│   │   ├── ensemble.py
│   │   └── transformer.py
│   ├── training/
│   │   ├── trainer.py
│   │   └── data_handler.py
│   ├── inference/
│   │   └── predictor.py
│   └── requirements.txt
│
├── database/
│   ├── migrations/         # DB migrations
│   └── schema.sql
│
├── docker/                 # Docker configs
│   ├── docker-compose.yml
│   └── Dockerfile
│
├── scripts/                # Setup & utility scripts
│   ├── setup-windows.bat
│   ├── setup-linux.sh
│   ├── start-dev.bat/sh
│   └── build-prod.sh
│
├── docs/                   # Documentation
│   ├── API.md
│   ├── AI_MODELS.md
│   ├── SETUP.md
│   └── TRADING.md
│
└── README.md
```

## 🔧 Configuration

### Exchange API Keys

Edit `.env` to add exchange credentials:

```env
# Binance
BINANCE_API_KEY=your_key
BINANCE_API_SECRET=your_secret
BINANCE_TESTNET=true

# Bybit
BYBIT_API_KEY=your_key
BYBIT_API_SECRET=your_secret
BYBIT_TESTNET=true

# Other exchanges...
```

### AI Model Configuration

```yaml
# config/models.yaml
models:
  lstm:
    enabled: true
    lookback: 60
    layers: 3
    units: 128
  
  gbm:
    enabled: true
    estimators: 200
    max_depth: 7
  
  ensemble:
    enabled: true
    weights:
      lstm: 0.5
      gbm: 0.5
```

## 📊 Trading

### Configure Strategy

1. Navigate to **Strategies** page
2. Click **Create Strategy**
3. Set parameters:
   - Trading pair (BTC/USDT, ETH/USDT, etc.)
   - Timeframe (1m, 5m, 15m, 1h, 4h, 1d)
   - AI Model (LSTM, GBM, Ensemble)
   - Risk per trade (2%)
   - Stop loss / Take profit
   - Confidence threshold

### Run Analysis

1. Click **Run AI Analysis**
2. System analyzes price, volume, technicals
3. AI generates signal (STRONG_BUY, BUY, NEUTRAL, SELL, STRONG_SELL)
4. If confidence > threshold, auto-execute trade

### Monitor Positions

- Live price updates every 1.5 seconds
- P&L calculated in real-time
- Manual close or let take-profit/stop-loss trigger

## 🧠 AI Models

### LSTM (Long Short-Term Memory)
```python
# 60-day lookback window
# 3 hidden layers, 128 units each
# Captures temporal patterns in price action
```

### GBM (Gradient Boosting)
```python
# Technical indicators as features:
# RSI, MACD, Bollinger Bands, Volume
# 200 decision trees, max depth 7
```

### Ensemble
```python
# Weighted combination: 50% LSTM + 50% GBM
# More robust predictions
# Lower overfitting risk
```

### Model Training

Train models on new data:

```python
python ai-models/training/trainer.py \
  --symbol BTC/USDT \
  --days 360 \
  --models lstm gbm ensemble
```

## 📈 Backtesting

Test strategies on historical data:

```bash
curl -X POST http://localhost:3000/api/backtest \
  -H "Content-Type: application/json" \
  -d '{
    "strategy_id": "btc-lstm-1h",
    "start_date": "2024-01-01",
    "end_date": "2024-12-31"
  }'
```

Response:
```json
{
  "total_return": 45.3,
  "sharpe_ratio": 1.87,
  "max_drawdown": 12.5,
  "win_rate": 62,
  "trades": 124
}
```

## 🔌 API Documentation

### Strategies
```bash
# Create
POST /api/strategies

# List
GET /api/strategies

# Get
GET /api/strategies/:id

# Update
PUT /api/strategies/:id

# Delete
DELETE /api/strategies/:id
```

### Trades
```bash
# Create
POST /api/trades

# List
GET /api/trades

# Close
POST /api/trades/:id/close

# History
GET /api/trades/history?symbol=BTC/USDT&status=closed
```

### AI Signals
```bash
# Generate signal
POST /api/signals/analyze

# History
GET /api/signals/history/:strategy_id
```

### Portfolio
```bash
# Get metrics
GET /api/portfolio/metrics

# Get allocation
GET /api/portfolio/allocation
```

## 🐳 Docker

### Build & Run

```bash
docker-compose build
docker-compose up -d
```

### Access
- Frontend: http://localhost:3000
- Backend API: http://localhost:8000
- Database: localhost:5432

## 🧪 Testing

```bash
# Frontend
cd frontend && npm test

# Backend  
cd backend && npm test

# AI Models
cd ai-models && pytest
```

## 📚 Documentation

- [Setup Guide](docs/SETUP.md)
- [API Reference](docs/API.md)
- [AI Models Guide](docs/AI_MODELS.md)
- [Trading Guide](docs/TRADING.md)
- [Architecture](docs/ARCHITECTURE.md)

## ⚠️ Disclaimer

**This software is for educational purposes only.** Cryptocurrency trading involves substantial risk of loss. Never risk money you cannot afford to lose. Always:

- Use testnet/paper trading first
- Start with small amounts
- Implement proper risk management
- Monitor trades actively
- Never leave API keys with unlimited permissions

## 🤝 Contributing

Contributions welcome! Please:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit changes (`git commit -am 'Add amazing feature'`)
4. Push to branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

MIT License - see LICENSE file for details

## 👨‍💻 Author

Built with ❤️ by [jai-fire](https://github.com/jai-fire)

## 📞 Support

- **Issues**: [GitHub Issues](https://github.com/jai-fire/nue/issues)
- **Discussions**: [GitHub Discussions](https://github.com/jai-fire/nue/discussions)
- **Email**: support@example.com

---

**Star ⭐ if this project helps you!**
