# Quick Start

![Version](https://img.shields.io/badge/version-2.6.0-green)
![Last Updated](https://img.shields.io/badge/last%20updated-2025--01-brightgreen)

Welcome to Hyperliquid Recovery Bot! This guide will help you get started quickly, from first use to completing asset recovery.

## 🚀 Step 1: Access the Bot

### 1. Open Telegram
Make sure you have installed and logged into the Telegram app.

### 2. Access the Bot
There are two ways to access the bot:

**Method 1: Direct Link**
Click the following link to access directly:
[https://t.me/HyperliquidRecoveryBot](https://t.me/HyperliquidRecoveryBot)

**Method 2: Search for Bot**
Enter in Telegram search box: `@HyperliquidRecoveryBot`

### 3. Start the Bot
Click the **"Start"** button or send `/start` command to start the bot.

## 📱 Main Interface Introduction

After starting, you will see a clean main menu interface:

```
🤖 Hyperliquid Recovery Bot

Welcome to Hyperliquid Asset Recovery Bot!

🔍 Address Detection - Smart detection of all asset types in Hyperliquid addresses
🛠️ Asset Recovery - One-click recovery: automatic conversion, transfer, withdrawal

Available commands:
/start - Show main menu
/detect - Enter address detection directly
/recovery - Enter asset recovery directly
```

### Main Function Buttons

1. **🔍 Address Detection**
   - Quickly query all assets in Hyperliquid addresses
   - Display asset types, quantities and values
   - Identify recoverable assets

2. **🛠️ Asset Recovery**
   - One-click recovery solution
   - Automatic conversion, transfer, withdrawal process
   - Transparent fee structure

## 🔍 Address Detection Function

### Usage Steps

1. **Enter Detection Function**
   - Click the **🔍 Address Detection** button in the main menu
   - Or send `/detect` command

2. **Input Address**
   - The bot will prompt you to enter the Hyperliquid address to detect
   - Enter the complete address (42 characters, starting with 0x)
   - Example: `0x1234567890123456789012345678901234567890`

3. **Wait for Detection**
   - The bot will display detection progress
   - Usually takes a few seconds to a few minutes

4. **View Results**
   - After detection is complete, detailed asset information will be displayed
   - Including asset types, quantities, values, etc.

### Detection Result Example

```
✅ Detection Complete

📍 Address: 0x1234...7890
🔍 Risk Level: High Risk
💰 Total Value: $1,234.56

📊 Asset Details:
💰 Assets Found:

[SPOT] USDC: 500.00 ($500.00)
[SPOT] ETH: 0.5 ($734.56)
[PERP] USDC: 0.00 ($0.00)

💡 Notes:
• [SPOT] = Spot account assets
• [PERP] = Perpetual contract account assets
• All assets will be converted to USDC and withdrawn from perp account

🛠️ Recoverable Assets: Yes
💡 Suggestion: This address contains recoverable assets, recommend using asset recovery function
```

## 🛠️ Asset Recovery Function

### Usage Steps

1. **Enter Recovery Function**
   - Click the **🛠️ Asset Recovery** button in the main menu
   - Or send `/recovery` command

2. **Input Address**
   - Enter the Hyperliquid address that needs asset recovery
   - The system will automatically detect the asset situation of this address

3. **Provide Private Key**
   - Enter the private key corresponding to this address (without 0x prefix)
   - ⚠️ Private key is only used for recovery operations and will be automatically cleaned after completion

4. **Confirm Recovery Plan**
   - The system will analyze assets and formulate a recovery plan
   - Display recovery steps, estimated fees and other information
   - Start executing recovery after confirmation

5. **Wait for Completion**
   - The system will automatically execute recovery steps
   - Display progress and status in real time
   - Show recovery results after completion

### Recovery Process Example

```
🛠️ Asset Recovery Plan

📍 Source Address: 0x1234...7890
💰 Total Asset Value: $1,234.56

📋 7-Step Recovery Process:
1. Convert Spot Assets
2. Transfer to Perpetual
3. Close Positions
4. Withdraw Vaults
5. Process Staking
6. Collect Fee
7. Final Withdrawal

⚠️ Please confirm to start recovery

[Confirm Recovery] [Cancel Operation]
```

## 💰 Fee Description

### How Much Does It Cost?

**Service Fee**
- 0.5% of total asset value
- Minimum: 1 USDC

**Withdrawal Fees** (Hyperliquid Platform)
- 2 USDC total (2 withdrawals × 1 USDC each)

### Quick Examples

| Your Assets | Service Fee | Withdrawal Fees | You Receive |
|-------------|-------------|-----------------|-------------|
| $100 | $1 | $2 | **$97** |
| $1,000 | $5 | $2 | **$993** |
| $10,000 | $50 | $2 | **$9,948** |

## 🌐 Language Settings

The bot supports:
- 🇺🇸 **English**: Full English interface
- 🇨🇳 **中文**: Complete Chinese interface
- 🔄 **Auto-detect**: Automatically detects your language preference

## ⚠️ Important Notes

### Security Precautions
1. **Private Key Security**:
   - Only provide private key during recovery
   - Private key will be automatically cleaned after operation completion
   - Do not leak private key elsewhere

2. **Address Verification**:
   - Ensure the entered address format is correct
   - Confirm the address indeed belongs to you

3. **Network Security**:
   - Use secure network environment
   - Avoid operating on public networks

### Operation Suggestions
1. **Small Amount Testing**: Recommend testing with small amounts for first use
2. **Backup Important Information**: Record important transaction information
3. **Contact Promptly**: Contact technical support promptly when encountering problems

## 🆘 Get Help

If you encounter any problems during use:

1. **View FAQ**: [FAQ Page](faq.md)
2. **Contact Technical Support**: Through the feedback function within the bot

## 🎯 Next Steps

- Learn more features: [Bot Usage Guide](bot-usage.md)
- View FAQ: [FAQ](faq.md)
