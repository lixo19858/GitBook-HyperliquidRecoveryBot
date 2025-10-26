# Address Detection Function

![Version](https://img.shields.io/badge/version-2.6.0-green)
![Last Updated](https://img.shields.io/badge/last%20updated-2025--01-brightgreen)

Address detection is one of the core functions of Hyperliquid Recovery Bot, helping users quickly understand the asset situation in Hyperliquid addresses.

## 🎯 Function Overview

### Main Features
- **Real-time Asset Detection**: Use Hyperliquid official API to get latest asset data
- **Multi-Account Support**: Detect assets across Spot, Perp, Vault, and Staked accounts
- **USD Value Calculation**: Real-time calculation of asset USD value using market prices
- **Risk Level Assessment**: Simple risk assessment based on total asset value
- **Recovery Assessment**: Determine if assets meet minimum recovery thresholds

### Supported Asset Types
- **Spot Assets**: USDC, ETH, BTC and other tokens in spot account
- **Perpetual Contracts (Perp)**: Margin balances and positions in perp account
- **Vault Assets**: Assets deposited in Hyperliquid vaults
- **Staked Assets**: Assets staked in various protocols

## 🚀 Usage Methods

### Method 1: Through Main Menu
1. Send `/start` command to open main menu
2. Click **🔍 Address Detection** button
3. Enter the Hyperliquid address to detect

### Method 2: Direct Command
1. Send `/detect` command
2. Directly enter the address to detect

## 📝 Address Format Requirements

### Valid Address Formats
Hyperliquid uses Ethereum-compatible addresses:
```
✅ Standard format: 0x1234567890123456789012345678901234567890
✅ Mixed case: 0xAbCdEf1234567890123456789012345678901234
✅ All uppercase: 0X1234567890ABCDEF1234567890ABCDEF12345678
✅ All lowercase: 0x1234567890abcdef1234567890abcdef12345678
```

### Invalid Address Formats
```
❌ Missing prefix: 1234567890123456789012345678901234567890
❌ Insufficient length: 0x12345
❌ Excessive length: 0x1234567890123456789012345678901234567890123
❌ Invalid characters: 0x123456789012345678901234567890123456789G
❌ Space characters: 0x1234 5678 9012 3456 7890 1234 5678 9012 3456 7890
```

### Address Validation
The bot automatically validates address format using viem library:
- **Length Check**: Must be exactly 42 characters (including 0x prefix)
- **Prefix Check**: Must start with 0x or 0X
- **Character Check**: Can only contain 0-9 and a-f (or A-F) characters
- **Checksum Validation**: Validates Ethereum address checksum

## 🔍 Detection Process Details

### 1. Address Validation Phase
```
🔍 Validating address format...
✅ Address format valid (using viem library)
✅ Length check passed (42 characters)
✅ Checksum validation passed
```

### 2. Data Retrieval Phase
```
📡 Connecting to Hyperliquid API...
🔄 Getting market prices for USD valuation...
📊 Querying spot account state...
📈 Querying perpetual contracts state...
🏦 Querying vault assets...
🔒 Querying staked assets...
```

### 3. Data Processing Phase
```
🧮 Calculating USD values using market prices...
📊 Processing asset balances across all accounts...
🔒 Evaluating risk level based on total value...
📋 Generating detection report...
✅ Detection completed
```

## 📊 Detection Result Interpretation

### Basic Information
```
📍 Address: 0x1234...7890
🔍 Risk Level: Medium Risk
💰 Total Value: $1,234.56
📊 Asset Count: 5 assets
🛠️ Recoverable: Yes (above $5.00 threshold)
⏰ Detection Time: 2024-01-15 14:30:25
```

### Asset Display Format
Assets are displayed with the following information:
- **Token Symbol**: The asset's symbol (e.g., USDC, ETH)
- **Account Type**: [SPOT], [PERP], [VAULT], or [STAKED]
- **Balance**: Precise token amount
- **USD Value**: Current market value (if price available)

### Example Asset Display
```
💰 Assets Found:

[SPOT] USDC: 500.00 ($500.00)
[SPOT] ETH: 0.5 ($734.56)
[PERP] USDC: 200.00 ($200.00)
[VAULT] BTC: 0.001 ($45.00)
[STAKED] DOGE: 1000 (Price Unknown)

💡 Notes:
• [SPOT] = Spot account assets
• [PERP] = Perpetual contract account assets
• [VAULT] = Vault deposited assets
• [STAKED] = Staked assets
• "Price Unknown" = Market price temporarily unavailable
```

### Risk Level Description

Risk level is assessed based on multiple factors:

#### 🟢 Low Risk (Score < 25)
- **Characteristics**: Simple asset structure
- **Description**: Basic asset portfolio with straightforward recovery
- **Recommendation**: Standard recovery procedures apply

#### 🟡 Medium Risk (Score 25-49)
- **Characteristics**: Moderate complexity portfolio
- **Description**: May include multiple asset types or perpetual positions
- **Recommendation**: Review recovery plan carefully before execution

#### 🔴 High Risk (Score ≥ 50)
- **Characteristics**: Complex asset portfolio
- **Description**: High-value assets, multiple types, staking waiting periods, etc.
- **Recommendation**: Requires extra caution and priority handling

**Scoring Factors**:
- Total asset value (> $100,000: +30 points; > $10,000: +15 points)
- Asset type diversity (≥ 3 types: +20 points)
- Staking waiting periods (has waiting assets: +25 points)
- Open perpetual positions (has open positions: +15 points)

## 💡 Detection Result Analysis

### Recoverability Assessment
The bot determines if assets are recoverable based on:

1. **Minimum Value Threshold**:
   - ✅ Total value ≥ $5.00: Considered recoverable
   - ❌ Total value < $5.00: Below minimum threshold

2. **Asset Types Supported**:
   - ✅ Spot assets: Recoverable (converted to USDC, transferred to perp account, then withdrawn)
   - ✅ Perp margin: Recoverable (positions closed, margin withdrawn from perp account)
   - ✅ Vault assets: Recoverable (may require withdrawal from vault)
   - ✅ Staked assets: Recoverable (may require unstaking)

3. **Technical Feasibility**:
   - ✅ Valid address format: Required for all operations
   - ✅ API accessibility: Hyperliquid API must be responsive
   - ✅ Network status: Blockchain network must be operational

### USD Value Calculation
- **Price Source**: Hyperliquid API market data (`getAllMids()`)
- **Update Frequency**: Real-time prices fetched for each detection
- **Calculation Method**: `token_balance × current_market_price`
- **Missing Prices**: Displayed as "Price Unknown" when market data unavailable
- **Precision**: Values displayed with appropriate decimal places

## 🔄 Re-detection and Updates

### When Re-detection is Needed
- **Asset Changes**: After trading or transferring assets
- **Price Updates**: When current market prices are needed
- **Recovery Planning**: Before starting asset recovery operations
- **Portfolio Monitoring**: Regular monitoring of asset values

### Re-detection Methods
1. **From Detection Results**: Click **🔄 Re-detect** button
2. **New Detection**: Enter the same address again for fresh detection



## ⚠️ Important Notes

### Technical Limitations
- **API Dependency**: Requires Hyperliquid API to be operational
- **Network Requirements**: Stable internet connection needed
- **Rate Limits**: Subject to Hyperliquid API rate limiting
- **Testnet Support**: Configurable for testnet or mainnet

### Data Accuracy
- **Real-time Prices**: Market prices updated with each detection
- **Balance Precision**: Uses full precision from Hyperliquid API
- **Network Delays**: Minor delays possible due to blockchain confirmation times
- **Price Availability**: Some new or low-volume tokens may lack price data

### Security Considerations
- **Read-only Operations**: Detection only reads data, never modifies accounts
- **No Private Keys**: Address detection doesn't require private keys
- **API Security**: Uses official Hyperliquid API endpoints
- **Data Privacy**: No sensitive data stored permanently

## 🆘 Frequently Asked Questions

### Q: What to do if detection fails?
A: Check the following:
1. **Address Format**: Ensure it's a valid Ethereum-format address (42 characters, starts with 0x)
2. **Network Connection**: Verify stable internet connection
3. **API Status**: Hyperliquid API may be temporarily unavailable
4. **Retry**: Wait a moment and try again, or contact support if issue persists

### Q: Why do some assets show "Price Unknown"?
A: Possible reasons:
1. **New Tokens**: Recently listed tokens may not have price data yet
2. **Low Liquidity**: Tokens with very low trading volume
3. **API Issues**: Hyperliquid price API temporarily unavailable
4. **Delisted Tokens**: Tokens no longer actively traded

### Q: How is the risk level calculated?
A: Risk level is based on a scoring system considering multiple factors:
1. **Total Asset Value**: > $100,000 (+30 points), > $10,000 (+15 points)
2. **Asset Type Diversity**: ≥ 3 types (+20 points)
3. **Staking Waiting Periods**: Has waiting assets (+25 points)
4. **Open Perpetual Positions**: Has open positions (+15 points)
5. **Scoring Criteria**:
   - Low Risk: < 25 points
   - Medium Risk: 25-49 points
   - High Risk: ≥ 50 points

### Q: What does "recoverable" mean?
A: An address is considered recoverable if:
1. **Minimum Value**: Total asset value ≥ $5.00
2. **Supported Assets**: Contains spot, perp, vault, or staked assets (all withdrawn via perp account)
3. **Technical Access**: Address is accessible via Hyperliquid API

### Q: Can I detect the same address multiple times?
A: Yes, you can re-detect addresses to:
1. **Get Updated Balances**: After trading or transfers
2. **Refresh Prices**: Get current market values
3. **Monitor Changes**: Track portfolio changes over time
4. **Pre-Recovery Check**: Verify assets before recovery operations
