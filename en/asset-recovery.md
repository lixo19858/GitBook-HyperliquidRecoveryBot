# Asset Recovery Function

Asset recovery is the core function of Hyperliquid Recovery Bot, helping users safely recover digital assets from addresses flagged as high-risk.

## 🎯 Function Overview

### Recovery Principle
When a Hyperliquid address is flagged as high-risk, users cannot operate through the official frontend interface. This bot helps users recover assets by directly calling Hyperliquid API, bypassing frontend restrictions.

### Recovery Process
1. **Asset Analysis**: Detect all assets in the address
2. **Smart Conversion**: Convert perpetual contract assets to spot assets
3. **Safe Withdrawal**: Withdraw assets to safe address
4. **Fee Collection**: Collect service fees proportionally

### Supported Recovery Types
- **Spot Asset Recovery**: Direct withdrawal of spot assets
- **Perpetual Contract Recovery**: Convert to spot first then withdraw
- **Mixed Asset Recovery**: Handle both spot and perpetual contract assets simultaneously

## 🚀 Usage Methods

### Starting Recovery Function
```
Method 1: Click 🛠️ Asset Recovery in main menu
Method 2: Send /recovery command
Method 3: Click [Start Recovery] on detection result page
```

### Complete Recovery Process

#### Step 1: Select Recovery Method
```
🛠️ Asset Recovery Function

Please select operation method:
[Enter New Address] [Use Detected Address] [Select from Wallet]

💡 Suggestion: If you just completed address detection, you can directly use the detected address
```

#### Step 2: Address Confirmation
```
📍 Confirm Recovery Address

Address: 0x1234567890123456789012345678901234567890
Risk Level: High Risk
Total Asset Value: $1,234.56

Confirm using this address for recovery?
[Confirm] [Re-enter] [Cancel]
```

#### Step 3: Private Key Input
```
🔐 Private Key Verification

Please enter the private key corresponding to this address (without 0x prefix):

⚠️ Security Tips:
• Private key is only used for asset recovery operations
• Will be immediately cleaned after operation completion
• Please ensure input in secure environment
• Do not screenshot or copy private key elsewhere

Private key format example:
1234567890abcdef1234567890abcdef1234567890abcdef1234567890abcdef

[Enter Private Key] [Cancel Operation]
```

#### Step 4: Private Key Verification
```
🔍 Verifying private key...

✅ Private key format verification passed
✅ Private key matches address confirmed
✅ Account access permission verification passed

Continuing with asset analysis...
```

#### Step 5: Asset Analysis
```
📊 Analyzing assets...

🔍 Detected the following assets:

Spot Assets:
• USDC: 500.00 ($500.00)
• ETH: 0.5 ($734.56)
• BTC: 0.001 ($45.00)

Perpetual Contracts (Perp):
• USDC Margin: 200.00 ($200.00)
• ETH-USD Position: 0.1 ETH (needs closing)
• Unrealized PnL: +$15.50

💰 Total Asset Value: $1,495.06
🔄 Assets needing conversion: $215.50 (Perpetual contracts)
```

#### Step 6: Recovery Plan Confirmation
```
📋 Asset Recovery Plan

🎯 Recovery Strategy: Fully Automated Recovery
💰 Total Asset Value: $1,495.06
🏦 Service Fee (0.5%): $7.48
💵 Expected Receipt: $1,487.58

📝 Execution Steps:
1. ✅ Asset analysis complete
2. 🔄 Close perpetual contract positions
3. 🔄 Transfer perpetual contract margin to spot
4. 🔄 Withdraw all spot assets
5. 🔄 Collect service fee
6. 🔄 Clean temporary data

⏱️ Estimated execution time: 3-8 minutes
🎯 Target address: Will automatically generate safe address

⚠️ Important Notes:
• Operation cannot be cancelled once started
• Please ensure stable network connection
• Recommended to operate in good network environment

Confirm execution of recovery operation?
[Confirm Recovery] [Modify Plan] [Cancel Operation]
```

#### Step 7: Execute Recovery
```
🚀 Starting recovery operation execution...

Step 1/5: Prepare recovery environment
✅ Initialize recovery parameters
✅ Verify network connection
✅ Check account status

Step 2/5: Handle perpetual contracts
🔄 Closing ETH-USD position...
✅ ETH-USD position closing complete
🔄 Transferring margin to spot account...
✅ Margin transfer complete

Step 3/5: Withdraw spot assets
🔄 Withdrawing USDC (715.50)...
✅ USDC withdrawal complete (TxHash: 0xabc...123)
🔄 Withdrawing ETH (0.6)...
✅ ETH withdrawal complete (TxHash: 0xdef...456)
🔄 Withdrawing BTC (0.001)...
✅ BTC withdrawal complete (TxHash: 0x789...abc)

Step 4/5: Collect service fee
🔄 Collecting service fee...
✅ Service fee collection complete ($7.48)

Step 5/5: Cleanup and confirmation
✅ Clean temporary data
✅ Verify all transactions
✅ Generate recovery report

🎉 Recovery operation complete!
```

#### Step 8: Recovery Results
```
✅ Asset recovery successful!

📊 Recovery Summary:
┌─────────────────────────────────┐
│ Recovery Details                │
├─────────────────────────────────┤
│ Source Address: 0x1234...7890   │
│ Target Address: 0x5678...1234   │
│ Recovery Time: 2024-01-15 14:35:42 │
│ Execution Duration: 4 min 23 sec │
└─────────────────────────────────┘

💰 Recovered Asset Details:
• USDC: 708.02 (original 715.50 - service fee 7.48)
• ETH: 0.6 (original 0.5 + position closing profit 0.1)
• BTC: 0.001

🧾 Fee Details:
• Total Asset Value: $1,495.06
• Service Fee Rate: 0.5%
• Service Fee Amount: $7.48
• Network Transaction Fees: Included in service fee

🔗 Transaction Records:
• USDC Withdrawal: 0xabc...123 ✅ Confirmed
• ETH Withdrawal: 0xdef...456 ✅ Confirmed
• BTC Withdrawal: 0x789...abc ✅ Confirmed

📱 Follow-up Operations:
[View Target Address] [Download Recovery Report] [Return to Main Menu]

Thank you for using Hyperliquid Recovery Bot!
Your assets have been safely transferred to the new address.
```

## 💰 Fee Structure Details

### Service Fee Calculation
- **Base Rate**: 0.5% (calculated based on total recovery asset value)
- **Minimum Fee**: 1 USDC
- **Maximum Fee**: 100,000,000 USDC

### Fee Calculation Examples
```
Example 1: Recovery amount $100
Service fee = max($100 × 0.5%, $1) = $1.00

Example 2: Recovery amount $1,000
Service fee = $1,000 × 0.5% = $5.00

Example 3: Recovery amount $10,000
Service fee = $10,000 × 0.5% = $50.00

Example 4: Recovery amount $1,000,000
Service fee = $1,000,000 × 0.5% = $5,000.00
```

### Fee Includes
- **Recovery Service Fee**: Asset recovery operation fee
- **Network Transaction Fees**: Blockchain transaction fees
- **Technical Service Fee**: Technical support and maintenance fee
- **Risk Guarantee Fee**: Operation risk guarantee fee

### Fee Collection Method
- **Automatic Deduction**: Automatically deducted from recovered assets
- **Priority**: USDC > ETH > BTC > Other tokens
- **Transparent Billing**: All fees clearly displayed before operation
- **No Hidden Fees**: No additional fees charged

## 🔒 Security Guarantee

### Private Key Security
```
🔐 Private Key Security Measures:

1. Encrypted Storage:
   • Use AES-256 encryption algorithm
   • Randomly generate encryption keys
   • Temporary storage in memory

2. Access Control:
   • Only used during recovery process
   • Strict permission control
   • Operation log recording

3. Automatic Cleanup:
   • Immediate cleanup after operation completion
   • Memory data overwriting
   • No persistent storage
```

### Operation Security
```
🛡️ Operation Security Mechanisms:

1. Multi-layer Verification:
   • Address format verification
   • Private key matching verification
   • Asset status verification

2. Risk Control:
   • Operation amount limits
   • Frequency limit control
   • Abnormal behavior detection

3. Rollback Mechanism:
   • Automatic rollback on operation failure
   • Partial success status handling
   • Error recovery mechanism
```

### Asset Security
```
💎 Asset Security Guarantee:

1. Target Address:
   • Automatically generate safe address
   • User can specify target address
   • Address validity verification

2. Transaction Confirmation:
   • Wait for block confirmation
   • Transaction status monitoring
   • Failure retry mechanism

3. Asset Tracking:
   • Complete operation records
   • Transaction hash records
   • Asset flow tracking
```

## ⚠️ Important Notes

### Pre-Operation Preparation
1. **Network Environment**: Ensure stable network connection
2. **Device Security**: Operate on secure devices
3. **Private Key Preparation**: Ensure private key is correct and available
4. **Time Arrangement**: Reserve sufficient operation time

### During Operation
1. **Don't Close**: Don't close Telegram during operation
2. **Maintain Connection**: Keep network connection stable
3. **Don't Interfere**: Don't perform other blockchain operations
4. **Be Patient**: Some steps may take longer time

### Post-Operation Confirmation
1. **Check Results**: Carefully check recovery results
2. **Verify Transactions**: Verify transactions in blockchain explorer
3. **Save Records**: Save important transaction records
4. **Security Cleanup**: Clean related sensitive information

## 🔧 Advanced Options

### Custom Target Address
```
🎯 Target Address Settings

Current Setting: Auto-generate safe address

Options:
[Use Auto-generated Address] [Specify Target Address] [Select from Wallet]

If choosing to specify target address:
Please enter target address: 0x...

⚠️ Note: Please ensure target address is safe and controlled by you
```

### Batch Recovery
```
📦 Batch Recovery Settings

Current Asset Value: $10,000
Recommended Batch Quantity: 2 batches

Batch Plan:
Batch 1: $5,000 (USDC + ETH)
Batch 2: $5,000 (BTC + Others)

Advantages:
• Reduce single operation risk
• Improve operation success rate
• Facilitate asset management

[Use Batch Recovery] [One-time Recovery]
```

### Recovery Plan Customization
```
⚙️ Recovery Plan Customization

Standard Plan: Fully Automated Recovery (Recommended)
Custom Plan: Manually select recovery steps

Custom Options:
☑️ Close perpetual contract positions
☑️ Transfer margin to spot
☑️ Withdraw spot assets
☑️ Collect service fee

Advanced Options:
□ Retain partial assets
□ Specify withdrawal order
□ Set slippage protection

[Use Standard Plan] [Custom Plan]
```

## 📊 Recovery Statistics

### Personal Recovery Records
```
📈 My Recovery Records

Total Recovery Count: 3 times
Total Recovery Amount: $15,678.90
Total Service Fees: $78.39
Average Recovery Time: 4 min 32 sec

Recent Recoveries:
1. 2024-01-15 - $1,495.06 ✅ Success
2. 2024-01-10 - $8,234.50 ✅ Success
3. 2024-01-05 - $5,949.34 ✅ Success

[View Details] [Download Report]
```

### System Recovery Statistics
```
🌐 System Statistics

Today's Recovery:
• Recovery Count: 156 times
• Recovery Amount: $2,345,678.90
• Success Rate: 99.2%

Historical Statistics:
• Total Recovery Count: 12,345 times
• Total Recovery Amount: $123,456,789.01
• Average Recovery Amount: $10,003.45
```

## 🆘 Troubleshooting

### Common Issues and Solutions

#### Q: Private Key Verification Failed
```
❌ Possible Causes:
1. Incorrect private key format (contains 0x prefix)
2. Private key doesn't match address
3. Incorrect private key length

✅ Solutions:
1. Check private key format (64-bit hexadecimal)
2. Confirm private key corresponds to correct address
3. Re-enter private key
```

#### Q: Recovery Operation Failed
```
❌ Possible Causes:
1. Unstable network connection
2. Hyperliquid API temporarily unavailable
3. Abnormal account status

✅ Solutions:
1. Check network connection
2. Retry operation later
3. Contact technical support
```

#### Q: Partial Asset Recovery Failed
```
❌ Possible Causes:
1. Some assets are currently in use
2. Network congestion causing transaction failure
3. Insufficient asset balance to pay fees

✅ Solutions:
1. Check asset status
2. Wait for network recovery and retry
3. Ensure sufficient balance to pay fees
```

### Emergency Contact
If you encounter serious problems, please contact technical support immediately:
- **Bot Feedback**: Use the bot's feedback function
- **Emergency Situation**: Describe problems and operation steps in detail
- **Provide Information**: Address, time, error information, etc.
