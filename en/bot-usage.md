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
- **Smart Recognition**: Automatically identify spot and perpetual contract assets
- **Real-time Data**: Get latest asset balance and price information
- **Risk Assessment**: Assess address risk level
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
🔍 Risk Level: High Risk
💰 Total Value: $1,234.56
📊 Asset Count: 3 types of assets

📋 Detailed Asset Information:
┌─────────────────────────────────┐
│ Spot Assets (Spot Account)      │
├─────────────────────────────────┤
│ USDC: 500.00 ($500.00)         │
│ ETH: 0.5 ($734.56)             │
│ BTC: 0.001 ($45.00)            │
└─────────────────────────────────┘

┌─────────────────────────────────┐
│ Perpetual Contracts (Perp)     │
├─────────────────────────────────┤
│ No perpetual contract assets    │
└─────────────────────────────────┘

🛠️ Recoverable: Yes
💡 Suggestion: This address contains recoverable assets, recommend using recovery function
```

### Risk Level Description

| Level | Description | Recommendation |
|-------|-------------|----------------|
| 🟢 Low Risk | Address not flagged | Normal use |
| 🟡 Medium Risk | Address has minor risk flags | Operate cautiously |
| 🔴 High Risk | Address flagged as high risk | Recommend asset recovery |

## 🛠️ Asset Recovery Function Details

### Function Features
- **Automated Process**: Fully automated asset recovery process
- **Smart Conversion**: Automatically convert perpetual contract assets to spot assets
- **Safe Withdrawal**: Safely transfer assets to specified address
- **Transparent Fees**: Clearly display all fees and costs

### Recovery Process Details

#### 1. Start Recovery
```
Click: 🛠️ Asset Recovery
Or enter: /recovery
```

#### 2. Address Input
```
Bot: 🛠️ Asset Recovery Function

Please select operation method:
[Enter New Address] [Use Detected Address]

If choosing to enter new address:
🔍 Please enter the Hyperliquid address that needs asset recovery:
```

#### 3. Private Key Verification
```
Bot: 🔐 Please enter the private key for this address:

⚠️ Security Tips:
• Private key is only used for asset recovery operations
• Will be automatically cleaned after operation completion
• Please ensure input in secure environment

Private key format (without 0x prefix):
1234567890abcdef1234567890abcdef1234567890abcdef1234567890abcdef
```

#### 4. Asset Analysis
```
🔍 Analyzing assets...
📊 Detected the following assets:

Spot Assets:
• USDC: 500.00 ($500.00)
• ETH: 0.5 ($734.56)

Perpetual Contract Assets:
• None

💰 Total Value: $1,234.56
🔄 Assets needing conversion: None
```

#### 5. Recovery Plan Confirmation
```
📋 Asset Recovery Plan

🎯 Recovery Target: Safely transfer all assets
💰 Total Asset Value: $1,234.56
🏦 Service Fee: $6.17 (0.5%)
💵 Actual Receipt: $1,228.39

📝 Execution Steps:
1. ✅ Asset analysis complete
2. 🔄 Convert perpetual contract assets (if any)
3. 🔄 Withdraw spot assets
4. 🔄 Collect service fee
5. 🔄 Clean temporary data

⏱️ Estimated Time: 2-5 minutes

Confirm execution of recovery operation?
[Confirm Recovery] [Cancel Operation]
```

#### 6. Execute Recovery
```
🚀 Starting recovery execution...

Step 1/4: Prepare recovery environment
✅ Verify private key and address
✅ Check network connection
✅ Initialize recovery parameters

Step 2/4: Convert assets (if needed)
🔄 Converting perpetual contract assets...
✅ Conversion complete

Step 3/4: Withdraw assets
🔄 Withdrawing USDC...
✅ USDC withdrawal complete
🔄 Withdrawing ETH...
✅ ETH withdrawal complete

Step 4/4: Collect service fee
🔄 Collecting service fee...
✅ Service fee collection complete

🎉 Recovery complete!
```

#### 7. Recovery Results
```
✅ Asset recovery successful!

📊 Recovery Summary:
┌─────────────────────────────────┐
│ Recovery Details                │
├─────────────────────────────────┤
│ Source Address: 0x1234...7890   │
│ Target Address: 0x5678...1234   │
│ Recovery Time: 2024-01-15 14:30:25 │
└─────────────────────────────────┘

💰 Asset Details:
• USDC: 493.83 (service fee deducted)
• ETH: 0.5

🧾 Fee Details:
• Service Fee: $6.17 (0.5%)
• Network Fee: Included

🔗 Transaction Records:
• Transaction Hash: 0xabcd...ef12
• Block Confirmation: Confirmed

Thank you for using Hyperliquid Recovery Bot!
```




