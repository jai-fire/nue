# Quantum Ledger Pro - Installation & Setup Guide

## Complete Setup Instructions for Windows & Linux

### Prerequisites
- Node.js 18+ (https://nodejs.org)
- Python 3.10+ (https://python.org)
- Git (https://git-scm.com)
- npm or yarn package manager

## Quick Start (5 minutes)

### 1. Clone Repository
```bash
git clone https://github.com/jai-fire/nue.git
cd nue
```

### 2. Install All Dependencies
```bash
# Frontend
cd frontend
npm install
cd ..

# Backend (if exists)
cd backend
npm install
cd ..

# AI Models
cd ai-models
pip install -r requirements.txt
cd ..
```

### 3. Configure Environment
```bash
cp .env.example .env
# Edit .env with your API keys
```

### 4. Start Development Servers

**Terminal 1 - Frontend:**
```bash
cd frontend
npm run dev
# Runs on http://localhost:5173
```

**Terminal 2 - Backend (optional):**
```bash
cd backend
npm run dev
# Runs on http://localhost:3000
```

**Terminal 3 - AI Models (optional):**
```bash
cd ai-models
python -m uvicorn main:app --reload
# Runs on http://localhost:8001
```

## Complete Setup Instructions

### Windows Setup

**Option 1: Using Batch Script (Recommended)**
```batch
REM Run the setup script
scripts\setup-windows.bat

REM Start development
scripts\start-dev.bat
```

**Option 2: Manual Setup**

1. Open Command Prompt or PowerShell
2. Clone repository:
```batch
git clone https://github.com/jai-fire/nue.git
cd nue
```

3. Install Node.js and Python dependencies:
```batch
cd frontend && npm install && cd ..
if exist backend (cd backend && npm install && cd ..)
if exist ai-models (cd ai-models && pip install -r requirements.txt && cd ..)
```

4. Create .env file in root:
```batch
copy .env.example .env
REM Edit .env with your settings
```

5. Start services (use multiple terminals):
```batch
REM Terminal 1
cd frontend && npm run dev

REM Terminal 2 (optional)
cd backend && npm run dev

REM Terminal 3 (optional)
cd ai-models && python -m uvicorn main:app --reload
```

### Linux/macOS Setup

**Option 1: Using Shell Script (Recommended)**
```bash
chmod +x scripts/setup-linux.sh
./scripts/setup-linux.sh
./scripts/start-dev.sh
```

**Option 2: Manual Setup**

1. Clone repository:
```bash
git clone https://github.com/jai-fire/nue.git
cd nue
```

2. Install dependencies:
```bash
# Frontend
cd frontend
npm install
cd ..

# Backend (if exists)
if [ -d "backend" ]; then
  cd backend
  npm install
  cd ..
fi

# AI Models (if exists)
if [ -d "ai-models" ]; then
  cd ai-models
  pip install -r requirements.txt
  cd ..
fi
```

3. Create environment file:
```bash
cp .env.example .env
# Edit .env with your configuration
```

4. Start development servers (use tmux or multiple terminals):
```bash
# Terminal 1
cd frontend && npm run dev

# Terminal 2 (optional)
cd backend && npm run dev

# Terminal 3 (optional)
cd ai-models && python -m uvicorn main:app --reload
```

## Configuration Files

### Create .env file (root directory)
Copy `.env.example` to `.env` and configure:

```env
# Server Configuration
NODE_ENV=development
PORT=3000
API_PORT=8000
FRONTEND_URL=http://localhost:5173

# Database
DATABASE_URL=sqlite:///./trading.db
# For PostgreSQL: postgresql://user:password@localhost:5432/trading

# Exchange APIs - Binance
BINANCE_API_KEY=your_key_here
BINANCE_API_SECRET=your_secret_here
BINANCE_TESTNET=true

# Exchange APIs - Bybit
BYBIT_API_KEY=your_key_here
BYBIT_API_SECRET=your_secret_here
BYBIT_TESTNET=true

# AI Services
OPENAI_API_KEY=sk-...
GROQ_API_KEY=your_key_here
ANTHROPIC_API_KEY=your_key_here

# JWT
JWT_SECRET=your_secret_key_here
JWT_EXPIRATION=24h

# Logging
LOG_LEVEL=debug
LOG_FORMAT=json
```

## Troubleshooting

### Common Issues

**Node modules not found**
```bash
rm -rf node_modules package-lock.json
npm install
```

**Python dependencies error**
```bash
pip install --upgrade pip
pip install -r requirements.txt
```

**Port already in use**
```bash
# Change ports in .env or code
# Frontend: Change port in vite.config.js
# Backend: Change PORT in .env
# Python: Add --port 8002 to uvicorn command
```

**Build errors**
```bash
cd frontend
npm run build  # Test production build
```

## Production Deployment

### Build Frontend
```bash
cd frontend
npm run build
# Output in frontend/dist
```

### Build Backend
```bash
cd backend
npm run build
```

### Docker Deployment
```bash
docker-compose build
docker-compose up -d
```

## Next Steps

1. **Configure Trading API Keys** - Add your exchange API keys to `.env`
2. **Train AI Models** - Run training on historical data
3. **Backtest Strategies** - Test strategies on past data
4. **Start Paper Trading** - Test with simulated trades
5. **Go Live** - Switch to real trading (use testnet first!)

## Support & Documentation

- [Main README](README.md) - Project overview and features
- [API Documentation](docs/API.md) - REST API endpoints
- [AI Models Guide](docs/AI_MODELS.md) - ML model details
- [Trading Guide](docs/TRADING.md) - How to trade
- [GitHub Issues](https://github.com/jai-fire/nue/issues) - Report bugs

## License

MIT License - See LICENSE file
