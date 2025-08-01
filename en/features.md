# Features

Hyperliquid Recovery Bot provides a complete asset detection and recovery solution, specifically designed to solve Hyperliquid high-risk address issues.

## 🔍 Address Detection Function

### Smart Asset Recognition
- **Comprehensive Detection**: Automatically identify spot and perpetual contract (Perp) assets
- **Real-time Data**: Use Hyperliquid official API to get latest asset information
- **Precise Calculation**: Real-time calculation of asset USD value and holding quantities
- **Status Monitoring**: Monitor asset status changes and availability

### Risk Assessment System
- **Smart Rating**: Automatically assess address risk levels
  - 🟢 **Low Risk**: Normal address, can be used normally
  - 🟡 **Medium Risk**: Minor risk flags, recommend cautious operation
  - 🔴 **High Risk**: Restricted address, recommend immediate asset recovery
- **Third-party Verification**: Integrate multiple risk databases for cross-validation
- **Real-time Updates**: Risk status updated in real-time to ensure information accuracy

### Detection Result Display
```
✅ Detection Complete

📍 Address: 0x1234...7890
🔍 Risk Level: High Risk
💰 Total Value: $1,234.56
📊 Asset Types: 3 types

📋 Asset Details:
┌─────────────────────────────────┐
│ Spot Assets (Spot)              │
├─────────────────────────────────┤
│ USDC: 500.00 ($500.00)         │
│ ETH: 0.5 ($734.56)             │
└─────────────────────────────────┘

🛠️ Recoverable: Yes
💡 Suggestion: Immediately use asset recovery function
```

## 🛠️ Asset Recovery Function

### Automated Recovery Process
- **One-click Operation**: Users only need to provide private key, system automatically completes all recovery steps
- **Smart Path**: Automatically select optimal asset conversion and withdrawal paths
- **Progress Tracking**: Real-time display of recovery progress, letting users understand each step's status
- **Error Handling**: Smart error handling and retry mechanisms to ensure operation success

### Asset Conversion Processing
- **Spot Liquidation**: Automatically convert non-USDC assets in spot account to USDC
- **Perp Liquidation**: Intelligently handle perpetual contract positions, close positions and convert to USDC
- **Account Consolidation**: Transfer spot USDC to perp account for unified withdrawal
- **Precision Control**: Precisely handle decimal places and minimum trading units
- **Slippage Protection**: Automatically set reasonable slippage to protect user interests

### Secure Withdrawal Mechanism
- **Multiple Verification**: Address verification, private key verification, asset verification
- **Batch Processing**: Large assets support batch withdrawal to reduce risk
- **Target Address**: Support custom target address or use system-generated safe address
- **Transaction Confirmation**: Wait for block confirmation to ensure transaction success

## 💰 Transparent Fee Structure

### Fee Calculation
- **Base Rate**: 0.5% (calculated based on total recovered asset value)
- **Minimum Fee**: 1 USDC
- **Calculation Formula**: `Service Fee = max(Recovery Amount × 0.5%, 1 USDC)`

### Fee Includes
- **Recovery Service**: Complete asset recovery operations
- **Network Fees**: All blockchain transaction fees
- **Risk Guarantee**: Operation risk guarantee and insurance

### Charging Method
- **Automatic Deduction**: Automatically deducted from recovered assets
- **Priority**: USDC > ETH > BTC > Other tokens
- **Transparent Display**: All fees clearly displayed before operation
- **No Hidden Fees**: No additional or hidden fees charged

## 🌐 Multilingual Support

### Supported Languages
- **Chinese (zh)**: Complete Simplified Chinese interface
- **English (en)**: Complete English interface
- **Dynamic Switching**: Users can switch interface language at any time

### Localization Features
- **Cultural Adaptation**: Optimize user experience for different cultural backgrounds
- **Number Format**: Format numbers and currency according to language habits
- **Time Display**: Localized time and date formats

## 🔒 Security Features

### Private Key Protection
- **Encrypted Storage**: Use AES-256 encryption algorithm
- **Temporary Storage**: Only temporarily stored during recovery process
- **Automatic Cleanup**: Immediately clean all sensitive data after operation completion
- **Memory Protection**: Prevent memory dumps from leaking private key information

### Operation Security
- **Multiple Verification**: Address, private key, asset status multiple verification
- **Operation Logs**: Record detailed logs of all critical operations
- **Anomaly Detection**: Automatically detect abnormal operations and suspicious behavior
- **Emergency Stop**: Provide emergency stop mechanism

### Risk Control
- **Amount Limits**: Set reasonable single operation amount limits
- **Frequency Control**: Prevent malicious or abnormally frequent operations
- **IP Monitoring**: Monitor abnormal IP access and operations
- **Behavior Analysis**: Analyze user behavior patterns to identify risks




These features ensure that Hyperliquid Recovery Bot can provide users with secure and efficient asset recovery services.
