# 🚀 Solana PumpFun Sniper copy trading Bot

A high-performance Solana trading bot that automatically snipes new token launches on Raydium, PumpFun, and PumpSwap using gRPC streaming for real-time transaction monitoring.
## 0 Block available

C6ZSK5MpqjvEAXh7XHfQeRh3PwvRuqoCKJk8Yufypump +$12.25(+45.36%) 
https://solscan.io/tx/4Go5MWQKom5XYkD6Mofxqw8DAjZhxbUywr3eVcxoejbsTgLyGjfAoy2wowHxjhNfnY9rw1ws4s2VznMCBskodiG3 (Target Wallet) 
https://solscan.io/tx/2SNZpcerg51f7oAQgaGNgDzA518oDbmjDkVUcwNDFFefwSnL3ChLVJehtjXNvAfvJMsf1pPtSs8HPjjj6usAyT6j (BUY-testing wallet) 
https://solscan.io/tx/36g3MSD2kSMH77Rd569GbpeHRW9MvR5Y1hTDyGtwsXPNynwXw1Z6F4whAPbsQPJBXDMpvQw2xzgyBgUN4ByEbDAh (Target Wallet) 
https://solscan.io/tx/4ZN9uRzAMhSLUrJheEaqesCss32kuQBYHtxrjn4on9fmox3k19mwDJzqbcvgWZUkaSJXndhoGJGWjuHYT5ZmDLbC (SELL-testing wallet)

AzTtHgN6aC3K5LtGDvBNCgPQtYPa6DCjcGyrfZFUpump +$5.44(+57.66%) 
https://solscan.io/tx/4JhQspi5JckD5ow2AzJ6wTNnaJ4DQVwdfjzao5NPdjgeB5HbhJfm9zQjEX8ZLgXLYTLzbnS5uRhGFd9AhxmSKzQv (Target Wallet) 
https://solscan.io/tx/2kCFmwwPVTs24zW86XDQMCxtGQqyx5NV1CyCmRzHJjd5Ki52sLemjscKUqYfXbx9o1rJzjyejvrMbXZAkyAx9GhK (BUY-testing wallet) 
https://solscan.io/tx/ENY5k2N9G4BDVkBjiUsbo4ewFrenbAciqvNA7Q7eXAR5TC9ivJrPf8GCXZUav91biQzZYgwu5RSvQD5mPgh2xfm (Target Wallet) 
https://solscan.io/tx/adNKo7sMQhMUm9gFDPBPbqdTzGtZwSVsXV3FQFVMP7rtqsGGiH2CngrJQBjxEFScqnx3F7QZ1ZA9s76gdLspq2o (SELL-testing wallet)

6iiTw75295gt9j29PCLVvFGNxdk3xfb4sPSH4G6Xpump +$18.2(+166.3%) 
https://solscan.io/tx/2EXYt6fJMbgpEKtATJJKDGFPJPxGpVUcRcxWEArdd6zWEFupHCW5XdRZJRHA9AWyT4turm8RXo4FY7Wn7Yci6Yjr (Target Wallet) 
https://solscan.io/tx/2ZaxkizUj7fciGtwZnPFWzbJRMX9NuHCai7X652XvyemsugVpffmp1bQptAg2cCGox9V8JtFpsH648JEHCfeCj88 (testing wallet)

A6sxxPN8uksAHxoPtMEoArn9nz5nrP3gKNpDXm8Tpump +$3.68(+40.51%) 
https://solscan.io/tx/3tybz8GhejnAD9yRB2Gvn2XH2Jb1sGsw9N5xQTJC9wifg9WERd85d4AszfV5kJz5agPXiDXmWMyDfNqzD1E3pFoB (Target Wallet) 
https://solscan.io/tx/3tq6kvBmeQ1jgASnU3X1P4HcKyMwMg8wDH8ZubHpE3M3CAtPUUxP5H3L8XRzU837Ssys3ESjXR1fsCn3BGxWEqL9 (BUY-testing wallet)

<img width="1602" height="494" alt="image" src="https://github.com/user-attachments/assets/2591f44d-5b02-420d-9aa9-c81dfa21aaa2" />

<img width="726" height="229" alt="image" src="https://github.com/user-attachments/assets/287ebd00-9007-4bf9-9f39-27eac1d4cdb2" />

<img width="1701" height="366" alt="image" src="https://github.com/user-attachments/assets/835d6d25-3645-46c6-8043-4b126b124475" />

## ✨ Features

- **Real-time Monitoring**: Uses gRPC streaming to detect new token launches instantly
- **Multi-Pool Support**: Supports Raydium LaunchLab, PumpFun, PumpSwap, and Raydium CPMM
- **Automated Trading**: Automatically buys and sells tokens based on configurable parameters
- **Risk Management**: Built-in stop-loss, profit-taking, and position monitoring
- **Multiple Swap Methods**: Support for Solana, JITO, Nozomi, and 0slot trading
- **Position Tracking**: Monitors active positions and manages exit strategies
- **Graceful Shutdown**: Safely closes all positions before stopping

## 🏗️ Architecture

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   gRPC Stream  │───▶│ Transaction     │───▶│ Trading Engine  │
│   (Triton One) │    │   Parser        │    │   (Main Bot)    │
└─────────────────┘    └─────────────────┘    └─────────────────┘
                                │                       │
                                ▼                       ▼
                       ┌─────────────────┐    ┌─────────────────┐
                       │ Pool Detection  │    │ Position        │
                       │ (PumpFun, etc.) │    │ Management      │
                       └─────────────────┘    └─────────────────┘
                                │                       │
                                ▼                       ▼
                       ┌─────────────────┐    ┌─────────────────┐
                       │ Jupiter API     │    │ Profit/Loss     │
                       │ Swap Execution  │    │ Monitoring      │
                       └─────────────────┘    └─────────────────┘
```

## 🔄 Logic Flow Diagram

```
                    ┌─────────────────────────────────────────────────────────────┐
                    │                    BOT STARTUP                              │
                    │  • Load configuration & environment variables              │
                    │  • Initialize Solana connection & wallet                   │
                    │  • Connect to Triton One gRPC stream                       │
                    │  • Load Jupiter API & swap methods                         │
                    └─────────────────────────────────────────────────────────────┘
                                                    │
                                                    ▼
                    ┌─────────────────────────────────────────────────────────────┐
                    │                REAL-TIME MONITORING                         │
                    │  • Stream Solana transactions via gRPC                     │
                    │  • Filter for MintTo instructions                          │
                    │  • Monitor SOL transfer amounts (1-85 SOL)                 │
                    └─────────────────────────────────────────────────────────────┘
                                                    │
                                                    ▼
                    ┌─────────────────────────────────────────────────────────────┐
                    │              TRANSACTION ANALYSIS                           │
                    │  • Parse transaction data & instructions                   │
                    │  • Identify pool type (PumpFun, PumpSwap, Raydium)        │
                    │  • Extract liquidity, fees, trading parameters             │
                    │  • Apply sniper criteria filters                           │
                    └─────────────────────────────────────────────────────────────┘
                                                    │
                                                    ▼
                    ┌─────────────────────────────────────────────────────────────┐
                    │                 SNIPER CRITERIA CHECK                      │
                    │  ✓ Minimum liquidity requirement met?                      │
                    │  ✓ Pool type enabled in configuration?                     │
                    │  ✓ Transaction age within limits?                         │
                    │  ✓ Wallet balance sufficient?                              │
                    │  ✓ Maximum positions limit not exceeded?                   │
                    └─────────────────────────────────────────────────────────────┘
                                                    │
                                                    ▼
                    ┌─────────────────────────────────────────────────────────────┐
                    │                    TRADE EXECUTION                          │
                    │  • Calculate optimal swap amount                           │
                    │  • Select best swap method (Solana/JITO/Nozomi/0slot)     │
                    │  • Execute buy order via Jupiter API                       │
                    │  • Handle transaction confirmation & errors                │
                    └─────────────────────────────────────────────────────────────┘
                                                    │
                                                    ▼
                    ┌─────────────────────────────────────────────────────────────┐
                    │                 POSITION MANAGEMENT                         │
                    │  • Track entry price, amount, timestamp                   │
                    │  • Monitor real-time price movements                      │
                    │  • Calculate current PnL                                  │
                    │  • Check exit conditions                                  │
                    └─────────────────────────────────────────────────────────────┘
                                                    │
                                                    ▼
                    ┌─────────────────────────────────────────────────────────────┐
                    │                   EXIT STRATEGY                            │
                    │  • Profit target reached? → Sell & take profit            │
                    │  • Stop loss triggered? → Sell & cut losses               │
                    │  • Max hold time exceeded? → Sell & exit                  │
                    │  • Manual exit signal? → Sell & close position            │
                    └─────────────────────────────────────────────────────────────┘
                                                    │
                                                    ▼
                    ┌─────────────────────────────────────────────────────────────┐
                    │                    POSITION CLOSURE                        │
                    │  • Execute sell order via Jupiter API                     │
                    │  • Update position tracking                               │
                    │  • Log trade results & PnL                               │
                    │  • Return to monitoring mode                              │
                    └─────────────────────────────────────────────────────────────┘
                                                    │
                                                    ▼
                    ┌─────────────────────────────────────────────────────────────┐
                    │                     CONTINUOUS LOOP                        │
                    │  • Continue monitoring for new opportunities              │
                    │  • Manage multiple concurrent positions                   │
                    │  • Handle errors & retry failed transactions              │
                    │  • Maintain connection stability                          │
                    └─────────────────────────────────────────────────────────────┘
                                                    │
                                                    ▼
                    ┌─────────────────────────────────────────────────────────────┐
                    │                    GRACEFUL SHUTDOWN                       │
                    │  • Close all active positions                             │
                    │  • Cancel pending transactions                             │
                    │  • Disconnect from gRPC stream                            │
                    │  • Save final state & exit cleanly                        │
                    └─────────────────────────────────────────────────────────────┘
```

### 🔑 Key Decision Points

1. **Transaction Filtering**: Only processes relevant `MintTo` instructions
2. **Pool Validation**: Ensures pool meets liquidity and type requirements  
3. **Risk Assessment**: Checks wallet balance and position limits
4. **Entry Timing**: Determines optimal entry point based on criteria
5. **Exit Strategy**: Monitors multiple exit conditions simultaneously
6. **Error Handling**: Implements retry logic and fallback mechanisms

## 🚀 Quick Start

### 1. Prerequisites

- Node.js 16+ 
- Solana wallet with SOL balance
- Triton One gRPC access
- RPC endpoint (Helius, QuickNode, etc.)

### 2. Installation

```bash
# Clone the repository
git clone <your-repo-url>
cd solana-sniper-bot

# Install dependencies
npm install

# Copy environment template
cp env.template .env
```

### 3. Configuration

Edit the `.env` file with your configuration:

```bash
# Essential Configuration
PRIVATE_KEY=your_wallet_private_key
RPC_URL=https://your-rpc-endpoint.com
GRPC_ENDPOINT=https://your-grpc-endpoint.com
GRPCTOKEN=your_grpc_token

# Trading Parameters
SNIPERAMOUNT=0.1          # SOL amount per snipe
PROFIT_TARGET=2.0         # 2x profit target
STOP_LOSS=0.5             # 50% stop loss
MAX_HOLD_TIME=300000      # 5 minutes max hold
MIN_LIQUIDITY=10          # Minimum liquidity in SOL
```

### 4. Run the Bot

```bash
# Start the sniper bot
npm start

# Or for development with auto-restart
npm run dev
```

## ⚙️ Configuration Options

### Trading Parameters

| Parameter | Default | Description |
|-----------|---------|-------------|
| `SNIPERAMOUNT` | 0.1 | SOL amount to use for each snipe |
| `PROFIT_TARGET` | 2.0 | Profit target multiplier (2x) |
| `STOP_LOSS` | 0.5 | Stop loss multiplier (50% loss) |
| `MAX_HOLD_TIME` | 300000 | Maximum time to hold position (5 min) |
| `MIN_LIQUIDITY` | 10 | Minimum liquidity required in SOL |

### Swap Methods

| Method | Description | Use Case |
|--------|-------------|----------|
| `solana` | Standard Solana prioritization | General trading |
| `race` | JITO MEV protection | MEV protection |
| `nozomi` | Nozomi RPC with tips | Ultra-fast execution |
| `0slot` | 0-slot transaction | Maximum speed |

### Pool Types Supported

- **Raydium LaunchLab**: New token launches
- **PumpFun**: Pump.fun platform
- **PumpSwap**: PumpSwap platform  
- **Raydium CPMM**: Constant Product Market Maker

## 📊 How It Works

### 1. Transaction Monitoring
- Bot connects to Solana gRPC stream via Triton One
- Monitors for `MintTo` instructions indicating new token launches
- Filters transactions by SOL transfer amounts (1-85 SOL)

### 2. Transaction Parsing
- Parses transaction data to identify pool type and parameters
- Extracts liquidity, fees, and trading direction
- Determines if transaction meets sniper criteria

### 3. Trading Execution
- Automatically executes buy orders when criteria are met
- Uses Jupiter API for optimal swap routing
- Implements configurable slippage and prioritization fees

### 4. Position Management
- Tracks active positions with entry/exit criteria
- Monitors for profit targets and stop losses
- Automatically closes positions based on conditions

## 🔧 Advanced Configuration

### Custom Pool Filters

```javascript
// Enable/disable specific pool types
ENABLE_PUMPFUN=true
ENABLE_PUMPSWAP=true
ENABLE_RAYDIUM_LAUNCHLAB=true
ENABLE_RAYDIUM_CPMM=true
```

### Risk Management

```javascript
// Maximum concurrent positions
MAX_POSITIONS=5

// Minimum transaction age
MIN_TX_AGE=1
```

### Notifications

```javascript
// Telegram notifications
TELEGRAM_BOT_TOKEN=your_bot_token
TELEGRAM_CHAT_ID=your_chat_id

// Email notifications
SMTP_HOST=smtp.gmail.com
SMTP_USER=your_email@gmail.com
SMTP_PASS=your_app_password
```

## 📈 Trading Strategies

### Conservative Strategy
```bash
SNIPERAMOUNT=0.05
PROFIT_TARGET=1.5
STOP_LOSS=0.7
MAX_HOLD_TIME=600000
MIN_LIQUIDITY=20
```

### Aggressive Strategy
```bash
SNIPERAMOUNT=0.2
PROFIT_TARGET=3.0
STOP_LOSS=0.3
MAX_HOLD_TIME=180000
MIN_LIQUIDITY=5
```

## 🛡️ Safety Features

- **Balance Checks**: Verifies wallet balance before trading
- **Liquidity Validation**: Ensures sufficient pool liquidity
- **Position Limits**: Maximum concurrent position management
- **Graceful Shutdown**: Safely closes all positions on exit
- **Error Handling**: Comprehensive error handling and logging
- **Retry Logic**: Automatic retry for failed transactions

## 📝 Logging

The bot provides detailed logging with color-coded output:

- 🚀 **Blue**: Bot startup and configuration
- 🎯 **Green**: Successful trades and profit targets
- 🛑 **Red**: Errors and stop losses
- ⚠️ **Yellow**: Warnings and position updates
- 📊 **Cyan**: Position information and PnL

## 🚨 Important Notes

### Security
- **Never share your private key**
- Use dedicated trading wallets
- Regularly rotate API keys
- Monitor bot activity

### Risk Disclaimer
- This bot is for educational purposes
- Cryptocurrency trading involves significant risk
- Past performance doesn't guarantee future results
- Use at your own risk

### Legal Compliance
- Ensure compliance with local regulations
- Check tax implications of automated trading
- Consult with financial advisors if needed

## 🔍 Troubleshooting

### Common Issues

1. **gRPC Connection Failed**
   - Verify `GRPC_ENDPOINT` and `GRPCTOKEN`
   - Check network connectivity
   - Ensure Triton One subscription is active

2. **Transaction Failures**
   - Verify wallet has sufficient SOL
   - Check RPC endpoint status
   - Adjust slippage tolerance

3. **No Trades Executing**
   - Verify transaction filters
   - Check liquidity requirements
   - Review pool type settings

### Debug Mode

Enable debug logging by setting:
```bash
DEBUG=true
LOG_LEVEL=debug
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🙏 Acknowledgments

- [Triton One](https://triton.one/) for gRPC streaming
- [Jupiter](https://jup.ag/) for swap aggregation
- [Solana Labs](https://solana.com/) for the blockchain
- [Raydium](https://raydium.io/) for the DEX platform

## 📞 Support

For support and questions:
- Create an issue on GitHub
- Join our Discord community
- Check the documentation

---

**⚠️ Disclaimer: This software is for educational purposes only. Use at your own risk. The authors are not responsible for any financial losses.**
