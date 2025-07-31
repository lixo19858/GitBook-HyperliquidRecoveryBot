# Address Detection Function

Address detection is one of the core functions of Hyperliquid Recovery Bot, helping users quickly understand the asset situation in Hyperliquid addresses.

## 🎯 Function Overview

### Main Features
- **Smart Asset Recognition**: Automatically identify spot and perpetual contract assets
- **Real-time Data Retrieval**: Use Hyperliquid official API to get latest data
- **Risk Level Assessment**: Evaluate the security risk level of addresses
- **Value Calculation**: Real-time calculation of asset USD value
- **Recoverability Judgment**: Determine if assets can be recovered through the bot

### Supported Asset Types
- **Spot Assets**: USDC, ETH, BTC and other mainstream tokens
- **Perpetual Contracts (Perp)**: Perpetual contract positions and margin
- **Staked Assets**: Assets staked in various protocols (partial support)

## 🚀 Usage Methods

### Method 1: Through Main Menu
1. Send `/start` command to open main menu
2. Click **🔍 Address Detection** button
3. Enter the Hyperliquid address to detect

### Method 2: Direct Command
1. Send `/detect` command
2. Directly enter the address to detect

### Method 3: Quick Detection
If you have previously detected addresses, you can:
1. Select **🔍 Address Detection** in the main menu
2. Choose **Use Historical Address**
3. Select from the list of previously detected addresses

## 📝 Address Format Requirements

### Valid Address Formats
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
The bot automatically validates address format:
- **Length Check**: Must be 42 characters (including 0x prefix)
- **Prefix Check**: Must start with 0x or 0X
- **Character Check**: Can only contain 0-9 and a-f (or A-F) characters
- **Checksum Validation**: Verify address checksum (if applicable)

## 🔍 Detection Process Details

### 1. Address Validation Phase
```
🔍 Validating address format...
✅ Address format valid
✅ Length check passed
✅ Character validation passed
```

### 2. Data Retrieval Phase
```
📡 Connecting to Hyperliquid API...
🔄 Getting account information...
📊 Querying spot assets...
📈 Querying perpetual contracts...
💰 Getting price data...
```

### 3. Data Processing Phase
```
🧮 Calculating asset value...
🔒 Evaluating risk level...
📋 Generating detection report...
✅ Detection completed
```

## 📊 Detection Result Interpretation

### Basic Information
```
📍 Address: 0x1234...7890
🔍 Risk Level: High Risk
💰 Total Value: $1,234.56
📊 Asset Types: 3 types
🛠️ Recoverable: Yes
⏰ Detection Time: 2024-01-15 14:30:25
```

### Spot Asset Details
```
┌─────────────────────────────────┐
│ Spot Assets (Spot Account)      │
├─────────────────────────────────┤
│ USDC: 500.00 ($500.00)         │
│ ETH: 0.5 ($734.56)             │
│ BTC: 0.001 ($45.00)            │
│ DOGE: 1000 (Price Unknown)     │
└─────────────────────────────────┘

💡 Description:
• Shows token symbol and quantity
• USD value in parentheses
• "Price Unknown" indicates temporarily unavailable price information
```

### Perpetual Contract Details
```
┌─────────────────────────────────┐
│ Perpetual Contracts (Perp Account) │
├─────────────────────────────────┤
│ USDC Margin: 200.00 ($200.00)  │
│ ETH-USD Position: 0.1 ETH       │
│ BTC-USD Position: 0.005 BTC     │
│ Unrealized PnL: +$15.50        │
└─────────────────────────────────┘

💡 Description:
• Shows margin balance
• Shows positions for each contract
• Shows unrealized profit and loss
```

### Risk Level Description

#### 🟢 Low Risk
- **Description**: Address not flagged by any risk database
- **Characteristics**: Normal trading activity, no abnormal behavior
- **Recommendation**: Can use Hyperliquid frontend normally
- **Recovery Need**: Usually no need to use recovery function

#### 🟡 Medium Risk
- **Description**: Address has minor risk flags
- **Characteristics**: May have some suspicious trading activity
- **Recommendation**: Operate cautiously, monitor account status
- **Recovery Need**: May need recovery function

#### 🔴 High Risk
- **Description**: Address flagged as high risk
- **Characteristics**: Cannot access Hyperliquid frontend interface
- **Recommendation**: Use recovery function immediately to transfer assets
- **Recovery Need**: Strongly recommend using recovery function

## 💡 Detection Result Analysis

### Recoverability Judgment
The bot determines if assets are recoverable based on the following factors:

1. **Asset Type**:
   - ✅ Spot assets: Usually recoverable
   - ✅ Perpetual contract margin: Recoverable
   - ⚠️ Active positions: Need to close positions first

2. **Asset Quantity**:
   - ✅ Quantity > 0: Recoverable
   - ❌ Quantity = 0: No need for recovery

3. **Network Status**:
   - ✅ Network normal: Recoverable
   - ❌ Network abnormal: Temporarily unable to recover

### Value Calculation Description
- **Real-time Price**: Use Hyperliquid API to get real-time prices
- **Price Source**: Mainly from Hyperliquid internal prices
- **Update Frequency**: Get latest prices for each detection
- **Missing Prices**: Some new tokens may temporarily have no price information

## 🔄 Re-detection

### When Re-detection is Needed
- **Asset Changes**: When address assets change
- **Price Updates**: When latest price information is needed
- **Risk Status**: Check if risk status has changed
- **Regular Monitoring**: Regularly monitor address status

### Re-detection Methods
1. **Quick Re-check**: Click **🔄 Re-detect** on detection result page
2. **Complete Re-check**: Re-enter address for complete detection
3. **Batch Re-check**: Batch re-detection for multiple addresses

## 📈 History Records

### Detection History
The bot saves your detection history:
```
📚 Detection History

Recent Detections:
1. 0x1234...7890 - 2024-01-15 14:30 (High Risk)
2. 0x5678...1234 - 2024-01-14 10:15 (Low Risk)
3. 0x9abc...def0 - 2024-01-13 16:45 (Medium Risk)

[View Details] [Re-detect] [Delete Record]
```

### Historical Data Usage
- **Quick Re-check**: Quickly re-detect previously checked addresses
- **Trend Analysis**: Observe changes in address risk levels
- **Asset Monitoring**: Monitor changes in asset quantities
- **Recovery Decision**: Help decide whether recovery is needed

## ⚠️ Important Notes

### Detection Limitations
- **Frequency Limit**: Maximum 10 addresses per user per minute
- **Concurrency Limit**: Only 1 detection task can run simultaneously
- **API Limit**: Subject to Hyperliquid API rate limits

### Data Accuracy
- **Real-time**: Data may have 1-2 minutes delay
- **Price Volatility**: Price information may change due to market volatility
- **Network Conditions**: Network issues may affect data accuracy

### Privacy Protection
- **Address Privacy**: Detected address information is temporarily stored
- **Data Cleanup**: Regularly clean expired detection data
- **Anonymization**: No association with user identity information

## 🆘 Frequently Asked Questions

### Q: What to do if detection fails?
A: Please check:
1. Whether the address format is correct
2. Whether the network connection is normal
3. Whether detection frequency limit is exceeded
4. Try again later or contact technical support

### Q: Why do some assets have no price?
A: Possible reasons:
1. Newly listed tokens have no price data yet
2. Low liquidity tokens
3. Price API temporarily unavailable
4. Token has been delisted or stopped trading

### Q: How is the risk level determined?
A: Based on multiple factors:
1. Third-party risk databases
2. Trading behavior analysis
3. Address activity patterns
4. Community reports

### Q: Can detection results be exported?
A: Currently supports:
1. Copy detection result text
2. Generate detection report screenshots
3. Export function is under development
