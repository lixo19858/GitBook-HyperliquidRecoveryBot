# Hyperliquid Recovery Bot User Guide

![Hyperliquid Recovery Bot](https://img.shields.io/badge/Hyperliquid-Recovery%20Bot-blue)
![Version](https://img.shields.io/badge/version-2.6.0-green)
![License](https://img.shields.io/badge/license-MIT-blue)
![Last Updated](https://img.shields.io/badge/last%20updated-2025--10-brightgreen)

## 🤖 What is Hyperliquid Recovery Bot?

Hyperliquid Recovery Bot is a professional Telegram bot designed for Hyperliquid users to help you safely recover digital assets from addresses flagged as high-risk.

Encountering address risk flagging on Hyperliquid platform and unable to operate assets normally?

## ⚠️ Flagged Address Warning

If your address is flagged by Hyperliquid's third-party screening tool, the system will display the following warning:

**English**: Your address has been flagged as high risk by a third-party screening tool. This frontend interface does not support connection to the Hyperliquid blockchain by high risk addresses. If you think this is an error, you can open a support ticket.

**中文**: 您的地址已被第三方筛选工具标记为高风险。此前端界面不支持高风险地址连接到Hyperliquid区块链。如果您认为这是一个错误，您可以开启一个支持票据。

**한국어**: 귀하의 주소가 제3자 검증 도구에 의해 고위험으로 표시되었습니다. 이 프론트엔드 인터페이스는 고위험 주소의 하이퍼리퀴드 블록체인 연결을 지원하지 않습니다. 오류라고 생각되는 경우, 지원 티켓을 열 수 있습니다.

**Français**: Votre adresse a été signalée comme à haut risque par un outil de filtrage tiers. Cette interface frontend ne prend pas en charge la connexion à la blockchain Hyperliquid par des adresses à haut risque. Si vous pensez qu'il s'agit d'une erreur, vous pouvez ouvrir un ticket de support.

When your Hyperliquid address is flagged as high-risk and you cannot operate through the official frontend interface, this bot can help you:
- Detect all assets in the address
- Safely recover and transfer assets
- Avoid asset loss

## ✨ Main Features

### 🔍 Smart Address Detection
- **4 Asset Types**: Detect Spot, Perpetual, Vault, and Staked assets
- **Real-time Data**: Display latest balances and USD values
- **Lock Status**: See which assets are locked and when they unlock
- **Instant Results**: Get complete asset overview in seconds

### 🛠️ 7-Step Automated Recovery
- **Fully Automated**: Just provide private key, bot does everything
- **All Asset Types**: Handles spot, perpetual, vault, and staked assets
- **Smart Processing**: Converts everything to USDC and withdraws
- **Progress Tracking**: See real-time progress for each step

### 💰 Clear Pricing
- **Service Fee**: 0.5% (minimum 1 USDC)
- **Withdrawal Fees**: 2 USDC (Hyperliquid platform)
- **No Hidden Costs**: All fees shown upfront
- **Example**: Recover $1,000 → You get $993

### 🌐 User-friendly
- **Bilingual**: Complete English and Chinese support
- **Simple Steps**: Easy-to-follow process
- **Safe & Secure**: Private key never saved

## 🚀 Get Started

### Step 1: Access the Bot
Click the link to access directly: **[https://t.me/HyperliquidRecoveryBot](https://t.me/HyperliquidRecoveryBot)**

### Step 2: Start Using
1. Send `/start` command
2. Select "Address Detection" to view your assets
3. If recovery is needed, select "Asset Recovery" function

### Step 3: Safe Operation
- Operate in a secure environment
- Read each step's instructions carefully
- Confirm all information before proceeding

## 💰 Fee Structure

- **Address Detection**: Completely FREE
- **Service Fee**: 0.5% of total value (minimum 1 USDC)
- **Hyperliquid Withdrawal Fees**:
  - Service fee withdrawal: 1 USDC (to pay platform fee for service fee withdrawal)
  - Final withdrawal: 1 USDC (to withdraw your assets to target address)
  - Subtotal: 2 USDC
- **Total Cost Calculation**: Service Fee + 2 USDC
- **Fee Examples**:
  - Recover $1,000 → Service Fee $5 + Withdrawal Fees $2 = Total $7 → You Get $993
  - Recover $100 → Service Fee $1 + Withdrawal Fees $2 = Total $3 → You Get $97

## 🔒 Security Guarantee

- **Private Key Safety**: Never saved, automatically deleted after use
- **Transparent Operations**: Every transaction has a verifiable hash
- **Official Network**: All operations on official Hyperliquid blockchain
- **You Stay in Control**: Verify everything on blockchain explorer


## 📞 Get Help

If you encounter any issues while using:

1. **View Guide**: Read the detailed user guide in this documentation
2. **FAQ**: Check the [FAQ page](faq.md) for answers
3. **Contact Support**: Use the feedback function within the bot to contact us

## ⚠️ Important Notice

### Use Case
- This bot is only for helping recover assets from high-risk flagged addresses
- Please ensure you understand the related risks and operate carefully

### Private Key Security
- Private keys are temporarily encrypted and stored in memory (not written to disk)
- Automatically deleted after recovery completion (maximum 30 minutes retention)
- It is recommended to operate in a secure network environment

### Asset Destination
- **All assets are finally withdrawn to Arbitrum network**
- Please ensure your target address supports Arbitrum network
- You can use the same address as the source address to receive assets

### Minimum Recovery Amount
- Total asset value must be **> $5.00** to recover
- Below this amount cannot cover transaction fee costs

### Locked Asset Limitations
- **Vault assets during lock-up period**: Cannot be withdrawn, need to wait for unlock and run recovery again
- **Staked assets**: Require multi-stage recovery (see details below)

### Staked Asset Recovery Process (Important)

⚠️ **Staked assets require 3 separate recovery runs** (Hyperliquid protocol limitation):

**First Run**:
- Execute undelegate operation (remove delegation)
- Assets enter **1-day lock-up period**

**Second Run (after 1 day)**:
- Execute withdraw operation (withdraw to perpetual account)
- Assets enter **7-day lock-up period**

**Third Run (after 7 days)**:
- Assets fully unlocked and can be withdrawn normally

💡 **Recommendation**: If you have staked assets, please record the timeline and run recovery 3 times as scheduled

---

**Ready to start?** Click [Quick Start Guide](quick-start.md) for detailed usage steps!
