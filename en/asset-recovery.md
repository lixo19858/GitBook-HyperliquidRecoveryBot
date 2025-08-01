# Asset Recovery Function

Asset recovery is the core function of Hyperliquid Recovery Bot, helping users safely recover digital assets from Hyperliquid addresses.

## 🎯 Function Overview

### Recovery Principle
The bot helps users recover assets by directly calling Hyperliquid API to perform asset conversions, transfers, and withdrawals. This is particularly useful when users need to move assets from addresses that may have restricted access to the official frontend.

### Recovery Process
1. **Asset Detection**: Analyze all assets across spot, perp, vault, and staked accounts
2. **Smart Conversion**: Convert non-USDC assets to USDC for easier withdrawal
3. **Account Transfers**: Move assets between spot and perp accounts as needed
4. **Withdrawal Execution**: Withdraw USDC to Arbitrum network
5. **Fee Collection**: Collect service fees based on total recovery value

### Supported Asset Types
- **Spot Assets**: Direct conversion and withdrawal of spot account assets
- **Perpetual Contract Assets**: Close positions and transfer margin to spot
- **Vault Assets**: Withdrawal from Hyperliquid vaults (if supported)
- **Staked Assets**: Unstaking and recovery (if supported)

## 🚀 Usage Methods

### Starting Recovery Function
```
Method 1: Click 🛠️ Asset Recovery in main menu
Method 2: Send /recovery command
Method 3: Click [Start Recovery] on detection result page
Method 4: From wallet details page for imported wallets
```

### Complete Recovery Process

#### Step 1: Address Input
```
🛠️ Asset Recovery Function

Please enter the address you want to recover assets from:

💡 Tips:
• Use address from recent detection results
• Select from imported wallet list
• Enter new Hyperliquid address

[Enter Address] [Use Recent] [Select Wallet]
```

#### Step 2: Asset Analysis
```
📊 Analyzing assets...

🔍 Detected assets:
• Spot Account: 3 assets ($750.00)
• Perp Account: 2 assets ($485.06)
• Total Value: $1,235.06

📋 Recovery Plan:
1. Convert non-USDC spot assets to USDC
2. Transfer all spot USDC to perp account
3. Convert non-USDC perp assets to USDC
4. Withdraw all USDC to Arbitrum

💰 Service Fee: $6.18 (0.5%)
💵 Net Recovery: $1,228.88

[Continue] [Cancel]
```

#### Step 3: Private Key Input
```
🔐 Private Key Verification

Please enter the private key for this address:

⚠️ Security Notice:
• Private key is only used for recovery operations
• Automatically cleared from memory after completion
• Ensure you're in a secure environment
• Never share or screenshot your private key

Format: 64-character hexadecimal (with or without 0x prefix)
Example: 1234567890abcdef1234567890abcdef1234567890abcdef1234567890abcdef

[Enter Private Key] [Cancel]
```

#### Step 4: Private Key Verification
```
🔍 Verifying private key...

✅ Private key format valid
✅ Address match confirmed
✅ Account access verified

Proceeding with recovery execution...
```

#### Step 5: Recovery Execution
```
🚀 Executing recovery plan...

Step 1/4: Converting spot assets
🔄 Converting ETH to USDC...
✅ ETH conversion complete: 0.5 ETH → 734.56 USDC
🔄 Converting BTC to USDC...
✅ BTC conversion complete: 0.001 BTC → 45.00 USDC

Step 2/4: Transferring to perp account
🔄 Transferring 1,279.56 USDC from spot to perp...
✅ Transfer complete

Step 3/4: Converting perp assets
🔄 Closing ETH-USD position...
✅ Position closed: +0.1 ETH realized
🔄 Converting additional ETH to USDC...
✅ Conversion complete: 0.1 ETH → 147.12 USDC

Step 4/4: Final withdrawal
🔄 Withdrawing 1,420.50 USDC to Arbitrum...
💰 Service fee deducted: 7.10 USDC
✅ Withdrawal complete: 1,413.40 USDC

🎉 Recovery completed successfully!
```

#### Step 6: Recovery Results
```
✅ Asset Recovery Successful!

📊 Recovery Summary:
┌─────────────────────────────────┐
│ Recovery Details                │
├─────────────────────────────────┤
│ Source Address: 0x1234...7890   │
│ Target Network: Arbitrum        │
│ Recovery Time: 2024-01-15 14:35 │
│ Duration: 4 min 23 sec          │
└─────────────────────────────────┘

💰 Asset Breakdown:
• Original Total: $1,495.06
• Service Fee: $7.48 (0.5%)
• Network Fees: Included
• Final Amount: $1,487.58

🔗 Transaction Hash:
0xabc123...def456 ✅ Confirmed

[View on Explorer] [Return to Menu]
```

## 💰 Fee Structure Details

### Service Fee Calculation
The service fee is calculated as a percentage of the total recovery value:

- **Rate**: 0.5% of total asset value
- **Minimum Fee**: $1.00 USDC
- **Maximum Fee**: $100,000,000 USDC (effectively no maximum)
- **Currency**: Fees collected in USDC only

### Fee Calculation Examples
```
Example 1: Recovery value $100
Service fee = max($100 × 0.5%, $1.00) = $1.00

Example 2: Recovery value $1,000
Service fee = $1,000 × 0.5% = $5.00

Example 3: Recovery value $10,000
Service fee = $10,000 × 0.5% = $50.00

Example 4: Recovery value $100,000
Service fee = $100,000 × 0.5% = $500.00
```

### What's Included in the Fee
- **Asset Conversion**: Converting non-USDC assets to USDC
- **Account Transfers**: Moving assets between spot and perp accounts
- **Withdrawal Processing**: Executing withdrawal to Arbitrum network
- **Network Fees**: All blockchain transaction costs included
- **Technical Support**: Bot operation and maintenance costs

### Fee Collection Process
1. **Calculation**: Fee calculated based on total detected asset value
2. **Deduction**: Automatically deducted during final withdrawal step
3. **Transparency**: Fee amount clearly shown before execution
4. **Single Payment**: One-time fee, no additional charges

### Fee Configuration
The fee structure is configurable via environment variables:
- `SERVICE_FEE_ENABLED`: Enable/disable fee collection
- `SERVICE_FEE_PERCENTAGE`: Fee percentage (default 0.5%)
- `SERVICE_FEE_MIN_FEE`: Minimum fee amount (default $1.00)
- `SERVICE_FEE_MAX_FEE`: Maximum fee amount (default $100M)
- `SERVICE_FEE_RECIPIENT`: Address receiving fees

## 🔒 Security Implementation

### Private Key Handling
The bot implements strict security measures for private key management:

```
🔐 Private Key Security:

1. Memory-Only Storage:
   • Private keys never written to disk
   • Stored only in memory during operation
   • Automatically cleared after completion

2. Encryption in Transit:
   • All API communications use HTTPS
   • Private keys encrypted when passed between functions
   • No logging of sensitive data

3. Minimal Exposure:
   • Private key used only for signing transactions
   • No unnecessary operations performed
   • Immediate cleanup after each step
```

### Operation Security
```
🛡️ Security Mechanisms:

1. Input Validation:
   • Address format verification using viem library
   • Private key format validation
   • Asset balance verification before operations

2. Transaction Safety:
   • Each operation confirmed before proceeding
   • Automatic retry on network failures
   • Rollback capability for failed operations

3. API Security:
   • Official Hyperliquid SDK used exclusively
   • Rate limiting respected
   • Error handling for all API calls
```

### Recovery Process Security
```
💎 Process Security:

1. Step-by-Step Execution:
   • Each recovery step executed independently
   • Progress tracked and logged
   • Failure isolation prevents cascade errors

2. Asset Protection:
   • Withdrawals only to Arbitrum network
   • Transaction hashes provided for verification
   • Complete audit trail maintained

3. Error Recovery:
   • Graceful handling of partial failures
   • Detailed error reporting
   • Manual intervention support when needed
```

## ⚠️ Important Notes

### Pre-Operation Requirements
1. **Stable Network**: Ensure reliable internet connection throughout the process
2. **Secure Environment**: Use the bot in a secure, private environment
3. **Private Key Access**: Have the correct private key ready for the source address
4. **Sufficient Time**: Allow 5-15 minutes for complete recovery process

### During Operation
1. **Stay Connected**: Keep Telegram app open and connected
2. **No Interference**: Avoid other operations on the same address
3. **Monitor Progress**: Watch for any error messages or requests for input
4. **Be Patient**: Some steps may take several minutes to complete

### Post-Operation Verification
1. **Check Transaction**: Verify the withdrawal transaction on Arbitrum explorer
2. **Confirm Receipt**: Check that funds arrived at the destination address
3. **Save Records**: Keep transaction hash for your records
4. **Clear Data**: Private key is automatically cleared from bot memory

## 🔧 Technical Implementation

### Recovery Algorithm
The bot follows a standardized recovery process:

```
📋 Recovery Steps:

1. Asset Detection:
   • Query all account types (spot, perp, vault, staked)
   • Calculate total USD value
   • Identify conversion requirements

2. Asset Conversion:
   • Convert non-USDC spot assets to USDC
   • Close perp positions and convert to USDC
   • Handle vault/staked assets if applicable

3. Account Consolidation:
   • Transfer all spot USDC to perp account
   • Ensure all assets are in USDC in perp account

4. Final Withdrawal:
   • Calculate service fee
   • Execute withdrawal to Arbitrum
   • Provide transaction confirmation
```

### Supported Networks
- **Source**: Hyperliquid (mainnet or testnet)
- **Destination**: Arbitrum One (for mainnet) or Arbitrum Sepolia (for testnet)
- **Asset**: USDC only (all assets converted to USDC before withdrawal)

### Error Handling
- **Network Issues**: Automatic retry with exponential backoff
- **API Failures**: Graceful degradation and error reporting
- **Partial Failures**: Detailed status reporting for manual intervention
- **Transaction Failures**: Retry mechanism with user notification

## 🆘 Troubleshooting

### Common Issues and Solutions

#### Q: Private Key Verification Failed
```
❌ Possible Causes:
1. Invalid private key format
2. Private key doesn't match the address
3. Incorrect key length (not 64 hex characters)

✅ Solutions:
1. Ensure private key is 64 hexadecimal characters
2. Remove 0x prefix if present
3. Verify the private key corresponds to the correct address
4. Try importing the key into a wallet to verify it works
```

#### Q: Asset Conversion Failed
```
❌ Possible Causes:
1. Insufficient liquidity for the asset
2. Market volatility causing slippage
3. Hyperliquid API temporary issues

✅ Solutions:
1. Retry the operation after a few minutes
2. Check if the asset is actively traded
3. Contact support if the issue persists
```

#### Q: Withdrawal Transaction Failed
```
❌ Possible Causes:
1. Network congestion on Arbitrum
2. Insufficient balance for network fees
3. Temporary API connectivity issues

✅ Solutions:
1. Wait for network conditions to improve
2. Ensure sufficient USDC balance for fees
3. Retry the withdrawal operation
4. Check transaction status on Arbitrum explorer
```

#### Q: Recovery Process Stuck
```
❌ Possible Causes:
1. Network connectivity issues
2. Hyperliquid API rate limiting
3. Large transaction requiring more time

✅ Solutions:
1. Check your internet connection
2. Wait for the current step to complete (up to 5 minutes)
3. Do not close Telegram during the process
4. Contact support if stuck for more than 10 minutes
```

### Getting Help
If you encounter issues not covered above:

1. **Use Bot Feedback**: Send feedback through the bot's built-in feedback system
2. **Provide Details**: Include the address, error message, and time of the issue
3. **Transaction Hash**: If available, provide any transaction hashes
4. **Screenshots**: Screenshots of error messages can be helpful

### Recovery Limitations
- **Minimum Recovery**: $0.01 total value required
- **Supported Assets**: Only assets with available market prices
- **Network Dependency**: Requires both Hyperliquid and Arbitrum networks to be operational
- **API Availability**: Dependent on Hyperliquid API uptime
