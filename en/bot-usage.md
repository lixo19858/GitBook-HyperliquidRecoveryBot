# Bot Usage Guide

This document provides detailed instructions on all functions and usage methods of Hyperliquid Recovery Bot.

## 🤖 Bot Commands

### Basic Commands

| Command | Function | Description |
|---------|----------|-------------|
| `/start` | Start Bot | Display main menu and function introduction |
| `/detect` | Address Detection | Enter address detection function directly |
| `/recovery` | Asset Recovery | Enter asset recovery function directly |

### Command Usage Examples

```
User: /start
Bot: 🤖 Welcome to Hyperliquid Recovery Bot!
     [Display main menu and function buttons]

User: /detect
Bot: 🔍 Please enter the Hyperliquid address to detect:
     [Wait for user to input address]

User: /recovery
Bot: 🛠️ Asset Recovery Function
     [Display recovery options and instructions]
```

## 🔍 Address Detection Function Details

### Function Features
- **4 Asset Types**: Automatically identify Spot, Perpetual, Vault, and Staked assets
- **Real-time Data**: Get latest asset balance and price information
- **Lock Status**: See which assets are locked and when they unlock
- **Value Calculation**: Calculate total asset value (USD)

### Usage Process

#### 1. Start Detection
```
Click: 🔍 Address Detection
Or enter: /detect
```

#### 2. Input Address
```
Bot prompt: 🔍 Please enter the Hyperliquid address to detect:

Valid address formats:
✅ 0x1234567890123456789012345678901234567890
✅ 0xabcdefABCDEF1234567890123456789012345678

Invalid address formats:
❌ 1234567890123456789012345678901234567890 (missing 0x prefix)
❌ 0x12345 (insufficient length)
❌ 0xGHIJKL... (contains invalid characters)
```

#### 3. Detection Process
```
🔍 Detecting address assets...
⏳ Connecting to Hyperliquid API...
📊 Analyzing asset data...
🔒 Assessing risk level...
💰 Calculating asset value...
```

#### 4. Result Display
```
✅ Detection Complete

📍 Address: 0x1234...7890
💰 Total Value: $1,234.56

📊 Assets Found:
[SPOT] USDC: 500.00 ($500.00)
[SPOT] ETH: 0.5 ($734.56)
[PERP] BTC-PERP: 0.001 BTC ($45.00)
[VAULT] USDC: 100.00 ($100.00) 🔒 Locked (3 days)
[STAKED] HYPE: 50.00 ($89.00)

💡 Asset Types:
• [SPOT] = Spot account assets
• [PERP] = Perpetual contract positions
• [VAULT] = Vault deposits (may be locked)
• [STAKED] = Staked HYPE tokens (requires waiting period)

🛠️ Recoverable: Yes
💡 Next Step: Click "Start Recovery" to begin
```

### Asset Type Description

| Type | Description | Special Notes |
|------|-------------|---------------|
| SPOT | Tokens in spot account | Auto-converted to USDC |
| PERP | Perpetual positions | Auto-closed |
| VAULT | Vault deposits | Withdrawn if unlocked |
| STAKED | Staked HYPE | Requires 1 day + 7 days waiting |
| 🟡 Medium Risk | Address has minor risk flags | Operate cautiously |
| 🔴 High Risk | Address flagged as high risk | Recommend asset recovery |

## 🛠️ Asset Recovery Function Details

### Function Features
- **Automated Process**: Fully automated asset recovery process
- **Smart Liquidation**: Automatically convert all assets to USDC for unified withdrawal
- **Safe Withdrawal**: Safely transfer USDC from perp account to Arbitrum
- **Transparent Fees**: Clearly display all fees and costs

### Recovery Process Details

#### 1. Start Recovery
```
Click: 🛠️ Asset Recovery
Or enter: /recovery
```

#### 2. Recovery Center Interface
```
Bot: 🔄 Asset Recovery Center

Intelligent asset recovery system providing secure and reliable asset retrieval services.

✨ Features:
• Automatic asset detection and analysis
• Secure recovery process execution
• Support for all Hyperliquid asset types

💡 How it works:
1. Enter the address to recover assets from
2. System analyzes available assets
3. Provide private key or mnemonic phrase for secure recovery
4. Automated recovery execution

Click the button below to start asset recovery

[🚀 Auto Recovery] [⬅️ Back]
```

#### 3. Address Input
After clicking "Auto Recovery":
```
Bot: 💬 Please enter the Hyperliquid address for recovery analysis:

You: 0x1234567890abcdef1234567890abcdef12345678
```

#### 4. Asset Analysis
```
🔍 Analyzing assets...

📊 Recovery Analysis Progress
Address: 0x1234...5678

🌐 Connecting to Hyperliquid network ✅
📊 Detecting asset balances ✅
🧠 Analyzing recovery options ✅
📋 Generating recovery plan ✅
```

#### 5. Private Key Verification
```
Bot: 🔐 Please enter the private key for this address:

⚠️ Security Tips:
• Private key is only used for asset recovery operations
• Will be automatically cleaned after operation completion
• Please ensure input in secure environment

Private key format (without 0x prefix):
1234567890abcdef1234567890abcdef1234567890abcdef1234567890abcdef
```

#### 6. Recovery Plan Confirmation
```
📋 Asset Recovery Plan

🎯 Recovery Target: Safely transfer all assets
💰 Total Asset Value: $1,234.56
🏦 Service Fee: $6.17 (0.5%)
💸 Withdrawal Fees: $2.00 (Hyperliquid)
💵 You Will Receive: $1,226.39

📝 7-Step Process:
1. Convert Spot Assets
2. Transfer to Perpetual
3. Close Positions
4. Withdraw Vaults
5. Process Staking
6. Collect Fee
7. Final Withdrawal

Confirm execution of recovery operation?
[Confirm Recovery] [Cancel Operation]
```

#### 7. Execute Recovery
```
🚀 Starting 7-step recovery process...

Step 1/7: Convert Spot Assets
🔄 Converting spot ETH to USDC...
✅ ETH → USDC: 0.5 ETH → 734.56 USDC
🔄 Converting spot BTC to USDC...
✅ BTC → USDC: 0.001 BTC → 45.00 USDC
✅ Spot conversion complete: 1,279.56 USDC

Step 2/7: Transfer to Perpetual
🔄 Transferring USDC from spot to perp account...
✅ Transfer complete: 1,279.56 USDC

Step 3/7: Close Positions
🔄 Closing BTC-PERP position...
✅ Position closed

Step 4/5: Withdraw from perp account
🔄 Withdrawing all USDC from perp account to Arbitrum...
✅ Withdrawal complete

Step 5/5: Collect service fee
🔄 Collecting service fee...
✅ Service fee collection complete

🎉 Recovery complete!
```

#### 7. Recovery Results
```
✅ Asset Recovery Complete

📊 Execution Summary:
• Total Steps: 7
• Completed Steps: 7
• Recovered Amount: 1226.39 USDC
• Actual Fees: 8.17 USDC
- Service Fee: 6.17 USDC
- Withdrawal Fees: 2.00 USDC

Thank you for using Hyperliquid Recovery Bot!
```




